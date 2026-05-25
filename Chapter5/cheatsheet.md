# **CHAPTER 5: OOP CHEAT SHEET**

### **1. Basic Concepts: Classes, Objects, and Attributes**
*   **Class (Lớp):** Là khuôn mẫu (template) để tạo ra các đối tượng. Nó định nghĩa các thuộc tính và hành vi chung.
*   **Object (Đối tượng):** Là một thực thể cụ thể được tạo ra từ Class, có trạng thái (thuộc tính) và hành vi (phương thức) riêng. Tạo đối tượng bằng từ khóa `new`.
*   **Attribute (Thuộc tính):** Biến mô tả đặc điểm của đối tượng.
*   **4 Tính chất cốt lõi của OOP:**
    1.  **Encapsulation (Đóng gói):** Gộp dữ liệu và phương thức vào một đơn vị, hạn chế quyền truy cập trực tiếp từ bên ngoài để bảo vệ dữ liệu.
    2.  **Inheritance (Kế thừa):** Đối tượng con sử dụng lại thuộc tính/hành vi của đối tượng cha.
    3.  **Polymorphism (Đa hình):** Khả năng một đối tượng thể hiện nhiều hình thái/hành vi khác nhau tùy thuộc vào ngữ cảnh.
    4.  **Abstraction (Trừu tượng):** Ẩn các chi tiết cài đặt phức tạp, chỉ hiển thị các tính năng cần thiết cho người dùng.

### **2. Constructor Methods (Phương thức khởi tạo)**
*   **Đặc điểm:** Tên bắt buộc **trùng với tên Class**, **không có kiểu trả về** (kể cả `void`), tự động chạy khi dùng từ khóa `new` để tạo đối tượng.
*   **Phân loại:**
    *   *Parameterless (Không tham số):* Java tự động tạo nếu bạn không định nghĩa constructor nào, dùng để gán giá trị mặc định (`null`, `0`, `false`).
    *   *Parameterized (Có tham số):* Dùng để truyền giá trị khởi tạo ngay khi tạo đối tượng.
*   **Từ khóa `this`:** Dùng để tham chiếu đến chính đối tượng hiện tại, rất hữu ích để phân biệt giữa thuộc tính của class và tham số truyền vào khi chúng trùng tên.

### **3. Access Modifiers, Getter and Setter Methods**
*   **Access Modifiers (Phạm vi truy cập):**
    *   `private`: Chỉ truy cập được nội bộ trong Class.
    *   `default`: Truy cập được trong cùng Package.
    *   `protected`: Trong cùng Package hoặc Class con ở ngoài Package.
    *   `public`: Truy cập tự do từ mọi nơi.
*   **Getter/Setter:** Vì tính đóng gói, thuộc tính nên để `private`. Lấy dữ liệu qua hàm `getThuocTinh()` và ghi/sửa dữ liệu qua hàm `setThuocTinh()`.

### **4. Object Comparison (So sánh đối tượng)**
*   **Toán tử `==`:** Chỉ so sánh **địa chỉ bộ nhớ** (reference) xem hai đối tượng có trỏ về cùng một vị trí hay không, không so sánh giá trị.
*   **Phương thức `.equals()`:** Cần được ghi đè (Override) từ lớp `Object` để so sánh **giá trị** thực tế của các thuộc tính bên trong hai đối tượng.

### **5. Arrays of Objects (Mảng đối tượng)**
*   Khác với mảng nguyên thủy (`int`, `double`), mảng đối tượng bắt buộc phải **khởi tạo mảng**, sau đó **khởi tạo từng phần tử** (bằng `new`) trước khi dùng.
*   *Cú pháp:* `Student[] arr = new Student; arr = new Student("A", 20);`.

### **6. Overview of Common Built-in Classes**
*   **`StringBuilder`:** Dùng để nối/sửa chuỗi liên tục mà không tạo ra đối tượng mới, giúp tối ưu hiệu suất bộ nhớ cực tốt so với cộng chuỗi `String` thông thường.
*   **`Date`:** Lấy ngày giờ hệ thống hiện tại (`java.util.Date`).
*   **`Math`:** Chứa các hàm toán học tĩnh (static), ví dụ `Math.random()` tạo số ngẫu nhiên kiểu double từ 0.0 đến sát 1.0.

### **7. Inheritance, Polymorphism, and Abstraction**
*   **Kế thừa (Inheritance):** Dùng từ khóa `extends`. Lớp con thừa hưởng các thành viên `public`, `protected` của lớp cha. Lớp `Object` là cha của mọi lớp trong Java. Từ khóa `super` dùng để gọi phương thức/thuộc tính của lớp cha.
*   **Trừu tượng (Abstraction):**
    *   *Abstract Class:* Dùng từ khóa `abstract`, **không thể khởi tạo** đối tượng (không dùng được `new`). Chứa các phương thức trừu tượng (không có thân hàm) bắt buộc lớp con phải ghi đè.
    *   *Interface:* Dùng từ khóa `implements`. Tất cả phương thức mặc định là `abstract`, biến mặc định là `public static final` (hằng số). Một lớp có thể `implements` nhiều Interface (đa kế thừa hành vi).
*   **Đa hình (Polymorphism):** Trình diễn rõ nhất qua việc **Ghi đè phương thức (Method Overriding)** bằng annotation `@Override`. Java sẽ quyết định gọi phương thức của lớp cha hay lớp con dựa trên **kiểu thực tế của đối tượng lúc chạy (runtime)**. Dùng từ khóa `instanceof` để kiểm tra kiểu gốc của đối tượng.