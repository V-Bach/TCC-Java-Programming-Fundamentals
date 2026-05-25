# **CHAPTER 9 CHEAT SHEET: LAMBDA & STREAM**

### **1. Functional Interface (Giao diện hàm)**
*   **Định nghĩa:** Là một interface chỉ chứa **duy nhất một phương thức trừu tượng** (Single Abstract Method - SAM). Nó có thể chứa nhiều phương thức `default` hoặc `static`.
*   **Annotation:** Thường dùng `@FunctionalInterface` để báo lỗi biên dịch nếu bạn lỡ khai báo nhiều hơn một phương thức trừu tượng.
*   **Các Interface có sẵn phổ biến (thuộc `java.util.function`):**
    *   `Function<T, R>`: Nhận tham số T, trả về kết quả R.
    *   `Predicate<T>`: Nhận tham số T, trả về `boolean` (true/false).
    *   `Consumer<T>`: Nhận tham số T nhưng không trả về kết quả (void).
    *   `Supplier<T>`: Không nhận tham số, nhưng trả về một kết quả T.
    *   `Operator`: Nhận và trả về các giá trị cùng một kiểu (VD: `UnaryOperator`).

### **2. Lambda Expressions (Biểu thức Lambda)**
*   **Mục đích:** Viết code ngắn gọn, rõ ràng hơn để thay thế cho việc khởi tạo lớp nặc danh (anonymous class).
*   **Cú pháp chuẩn:** `(danh_sách_tham_số) -> { thân_hàm }`.
*   **Rút gọn cú pháp:** 
    *   Nếu chỉ có 1 tham số, có thể bỏ dấu ngoặc đơn `()`.
    *   Nếu thân hàm chỉ có 1 lệnh duy nhất, có thể bỏ cặp ngoặc nhọn `{ }` và từ khóa `return`.

### **3. Method References (Tham chiếu phương thức)**
*   Là cách viết tắt cực kỳ ngắn gọn của Lambda khi bạn chỉ muốn gọi một phương thức đã tồn tại.
*   **Các loại cú pháp:**
    *   **Static method:** `TênLớp::tênPhươngThức` (VD: `Program::saySomething`).
    *   **Non-static (Instance) method:** `TênĐốiTượng::tênPhươngThức` (VD: `new Program()::printMsg`).
    *   **Constructor:** `TênLớp::new` (VD: `Message::new`).

### **4. Optional**
*   **Khái niệm:** Một lớp đại diện cho việc "có" hoặc "không có" giá trị, giải pháp sinh ra để tránh lỗi `NullPointerException` cực kỳ nguy hiểm.
*   **Khởi tạo:**
    *   `Optional.empty()`: Tạo Optional rỗng.
    *   `Optional.of(value)`: Bọc một giá trị (nếu giá trị null sẽ bị lỗi).
    *   `Optional.ofNullable(value)`: An toàn nhất, tạo Optional chứa giá trị, hoặc trả về rỗng nếu giá trị là null.
*   **Thao tác phổ biến:**
    *   `isPresent()` / `isEmpty()`: Kiểm tra xem có chứa giá trị hay không.
    *   `get()`: Lấy giá trị ra (sẽ báo lỗi nếu Optional đang rỗng).
    *   `orElse(default_value)`: Lấy giá trị ra, nếu rỗng thì trả về `default_value`.
    *   `ifPresent(Consumer)`: Nếu có giá trị thì thực hiện lệnh truyền vào, nếu không thì bỏ qua.

### **5. Stream API**
*   **Khái niệm:** Dùng để xử lý một tập hợp dữ liệu theo phong cách Functional. Stream không lưu trữ dữ liệu, không làm thay đổi nguồn dữ liệu gốc, và chỉ được duyệt 1 lần duy nhất.
*   **Khởi tạo:** Có thể tạo Stream từ Collection (`list.stream()`), mảng (`Arrays.stream()`), hoặc các giá trị (`Stream.of()`).
*   **Intermediate Operations (Thao tác trung gian):** Các thao tác này trả về một Stream mới (tính chất lười - lazy, chưa chạy ngay).
    *   `filter()`: Lọc phần tử theo điều kiện.
    *   `map()`: Biến đổi từng phần tử.
    *   `limit()`, `skip()`, `distinct()`, `sorted()`, `peek()`.
*   **Terminal Operations (Thao tác cuối):** Các thao tác kích hoạt quá trình tính toán và đóng Stream.
    *   `count()`, `max()`, `min()`: Đếm, tìm lớn nhất/nhỏ nhất.
    *   `forEach()`: Duyệt và thực thi lệnh trên từng phần tử.
    *   `collect()`: Gom kết quả về lại thành List/Set.
    *   `reduce()`: Gộp các giá trị thành một kết quả duy nhất.

### **6. Parallel Streams (Luồng song song)**
*   **Mục đích:** Tự động chia nhỏ công việc ra nhiều luồng (CPU cores) để xử lý song song mà không cần viết code quản lý Thread phức tạp.
*   **Cách dùng:** Gọi `.parallelStream()` từ Collection hoặc thêm `.parallel()` vào Stream hiện tại.
*   **Lưu ý:** Không phải lúc nào chạy song song cũng nhanh hơn luồng tuần tự. Việc duyệt `forEach` với Parallel Stream có thể làm xáo trộn thứ tự phần tử, hãy dùng `forEachOrdered` nếu thứ tự là quan trọng. 