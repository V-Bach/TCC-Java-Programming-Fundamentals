# **CHAPTER 4 CHEAT SHEET**

### **1. The concepts of methods, static methods, and static variables**
*   **Phương thức (Method):** Là tập hợp các câu lệnh thực hiện một nhiệm vụ cụ thể, hoạt động như một "hộp đen" (black box) để ẩn giấu độ phức tạp bên trong. Cú pháp: `modifiers return-type function-name(parameter-list) { statements; }`.
*   **Phương thức tĩnh (Static methods):** Khai báo với từ khóa `static`, thuộc về chính lớp đó chứ không thuộc về đối tượng. Có thể gọi trực tiếp thông qua tên lớp (VD: `ClassName.methodName()`) mà không cần khởi tạo đối tượng (new).
*   **Biến tĩnh (Static variables):** Cũng sử dụng từ khóa `static`, tồn tại độc lập với đối tượng và vùng nhớ của nó được chia sẻ dùng chung cho tất cả các thể hiện của lớp. 

### **2. Parameters and parameter types**
*   **Tham số hình thức (Formal parameters):** Các biến được định nghĩa trong phần khai báo của phương thức.
*   **Tham số thực tế (Actual parameters/Arguments):** Các giá trị thực tế được truyền vào khi bạn gọi phương thức.
*   **Tham số linh hoạt (Varargs):** Ký hiệu bằng `...` (VD: `int... j`), cho phép phương thức nhận số lượng tham số tùy ý. Khai báo này phải nằm ở cuối cùng và mỗi phương thức chỉ được có một varargs.
*   **Tham số mảng (Array Parameters):** Cho phép truyền toàn bộ một mảng (VD: `int[] list`) vào làm tham số.
*   **Tham số dòng lệnh (Command-line arguments):** Mảng chuỗi `String[] args` được truyền vào phương thức `main()` khi người dùng chạy chương trình từ dòng lệnh.

### **3. Method overloading**
*   **Nạp chồng phương thức:** Khả năng định nghĩa nhiều phương thức **cùng tên** nhưng **khác nhau về danh sách tham số đầu vào** (khác số lượng hoặc kiểu dữ liệu) trong cùng một lớp.
*   **Lưu ý:** Không thể nạp chồng phương thức nếu chúng chỉ khác nhau về kiểu trả về (return type).

### **4. Exceptions and exception handling**
*   **Ngoại lệ (Exception):** Các lỗi hoặc tình huống bất thường xảy ra khi chạy chương trình (runtime). Tất cả các đối tượng ngoại lệ đều kế thừa từ lớp `java.lang.Throwable`.
*   **Xử lý ngoại lệ (`try...catch...finally`):**
    *   `try`: Chứa khối lệnh có nguy cơ sinh ra lỗi.
    *   `catch`: Bắt và xử lý ngoại lệ tương ứng nếu có lỗi xảy ra trong khối `try` để tránh chương trình bị ngưng đột ngột.
    *   `finally`: Chứa các lệnh **luôn được thực thi** (như đóng kết nối mạng, dọn bộ nhớ) bất kể có lỗi xảy ra hay không.
*   **Ném ngoại lệ (`throw` và `throws`):**
    *   `throw`: Cố tình ném ra một đối tượng ngoại lệ cụ thể bên trong khối lệnh.
    *   `throws`: Khai báo trên header của phương thức để cảnh báo phương thức này có khả năng ném ra lỗi bắt buộc (checked exceptions), yêu cầu nơi gọi nó phải xử lý.

### **5. Create documentation using Javadocs**
*   **Khái niệm:** Công cụ tự động tạo tài liệu mô tả (document) theo chuẩn của Java.
*   **Cú pháp:** Đặt đoạn mô tả trong khối bình luận đặc biệt bắt đầu bằng `/**` và kết thúc bằng `*/` trước khai báo phương thức/lớp.
*   **Thẻ (Tags) phổ biến:** Dùng `@param` để mô tả tham số, `@return` để mô tả giá trị trả về, `@exception` cho các ngoại lệ.
*   **Lệnh:** Dùng lệnh `javadoc filename.java` trong command line để xuất tài liệu.
