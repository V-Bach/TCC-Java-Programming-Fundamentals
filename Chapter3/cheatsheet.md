# **CHAPTER 3 CHEAT SHEET**

### **1. Control structure (Cấu trúc điều khiển)**
*   **Khái niệm:** Dùng để thay đổi luồng thực thi tuần tự từ trên xuống dưới của chương trình thông qua rẽ nhánh (if, switch) hoặc lặp lại (for, while).

### **2. Command block (Khối lệnh)**
*   **Định nghĩa:** Là một dãy các lệnh được đặt trong cặp dấu ngoặc nhọn `{ }`. 
*   **Phạm vi:** Các biến được khai báo bên trong một khối lệnh chỉ có phạm vi sử dụng **nội bộ bên trong khối đó** và sẽ bị hủy (thu hồi bộ nhớ) khi khối lệnh kết thúc.
*   **Lệnh rỗng:** Một khối có thể không chứa lệnh nào (khối rỗng) hoặc chỉ có dấu chấm phẩy `;` (lệnh rỗng chỉ thị máy tính không làm gì).

### **3. Conditional structures: if, switch (Cấu trúc rẽ nhánh)**
*   **Lệnh `if...else`:** Rẽ nhánh dựa trên một biểu thức logic (true/false).
    *   *Cú pháp:* `if (điều_kiện) { lệnh_1 } else { lệnh_2 }`.
    *   *Lưu ý:* Luôn nên dùng `{ }` để tránh lỗi logic khó tìm (đặc biệt khi có if lồng nhau).
*   **Lệnh `switch` truyền thống:** Kiểm tra giá trị của biểu thức (hỗ trợ `int`, `short`, `byte`, `char`, `String`, `enum` - **không dùng được `float`/`double`**) để nhảy trực tiếp đến `case` tương ứng.
    *   Bắt buộc phải có `break` ở mỗi `case` để ngăn máy tính chạy tiếp sang các `case` bên dưới.
*   **Lệnh `switch` mới (Từ Java 14):** 
    *   Sử dụng **toán tử mũi tên `->`** thay cho dấu hai chấm `:`.
    *   **Không cần `break`** (tự động thoát sau khi xử lý xong case).
    *   Hỗ trợ gộp nhiều giá trị trên cùng một dòng, cách nhau bằng dấu phẩy (VD: `case 2, 4, 8 ->`).
    *   Có thể dùng như một biểu thức trả về giá trị (thông qua từ khóa `yield`).

### **4. Enum data type (Kiểu dữ liệu liệt kê)**
*   **Khái niệm:** Là một kiểu dữ liệu đặc biệt cho phép khai báo một biến chỉ nhận các giá trị là tập hợp các hằng số đã định nghĩa trước.
*   **Ví dụ:** `enum Season {SPRING, SUMMER, FALL, WINTER}`.
*   **Ứng dụng:** Rất phù hợp để làm kiểu biểu thức trong lệnh `switch`.

### **5. Loop structures: for, while, do...while (Cấu trúc lặp)**
*   **`while` (Kiểm tra trước):** Lặp lại một khối lệnh **chừng nào** biểu thức điều kiện còn đúng. Nếu điều kiện sai ngay từ đầu, vòng lặp không chạy lần nào.
*   **`do...while` (Kiểm tra sau):** Thực thi khối lệnh trước, sau đó mới kiểm tra điều kiện. Do đó, thân vòng lặp **luôn được thực thi ít nhất một lần**.
*   **`for` (Lặp với bộ đếm):** Thường dùng khi đã biết trước số lần lặp. Cú pháp: `for(Khởi_tạo; Điều_kiện; Cập_nhật) { lệnh }`. Cả 3 thành phần này đều có thể bỏ trống (tạo vòng lặp vô hạn `for(;;)`).
*   **`break` và `continue`:**
    *   `break`: Lập tức **thoát khỏi vòng lặp** hiện tại.
    *   `continue`: **Bỏ qua** các lệnh còn lại của lần lặp hiện tại và quay lại kiểm tra điều kiện để bắt đầu lần lặp tiếp theo.
    *   Có thể kết hợp với **Label** (VD: `break bigloop;`) để nhảy trực tiếp ra khỏi cấu trúc vòng lặp lồng nhau nhiều tầng.

### **6. Working with arrays (Làm việc với mảng)**
*   **Định nghĩa:** Là một cấu trúc dữ liệu gồm tập hợp các phần tử **cùng kiểu**, được truy cập qua **chỉ số (index)** bắt đầu từ `0`.
*   **Khởi tạo:** Bắt buộc dùng từ khóa `new` với kích thước mảng (VD: `String[] arr = new String;`). Các phần tử tự động có giá trị mặc định (`0` cho số, `false` cho boolean, `null` cho chuỗi/đối tượng).
*   **Thuộc tính kích thước:** Lấy qua thuộc tính `.length` (VD: `arr.length`).
*   **Duyệt mảng:** Thường dùng vòng lặp `for` theo chỉ số, hoặc lặp **`foreach`** (VD: `for (double e : arr) { }`).
*   **Mảng đa chiều:** Mảng 2 chiều sắp xếp theo hàng và cột, được xử lý thông qua vòng lặp `for` lồng nhau (VD: `int[][] arr = new int;`).
*   **Lớp tiện ích `Arrays`:** Java có sẵn lớp `Arrays` cung cấp các tiện ích xử lý mảng nhanh chóng, ví dụ như hàm `Arrays.sort(a)` để sắp xếp mảng.