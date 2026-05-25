# **CHAPTER 2 CHEAT SHEET**

### **1. The concepts of constants and variables**
*   **Biến (Variables):** Là giá trị **có thể thay đổi** trong chương trình và được cấp phát một vùng nhớ trong bộ nhớ chính (RAM) để lưu trữ. Mỗi biến cần có một tên duy nhất (định danh), có kiểu dữ liệu cụ thể, và nhận dữ liệu thông qua **toán tử gán `=`**. Từ Java 10, có thể dùng từ khóa `var` để tự động nhận diện kiểu dữ liệu.
*   **Hằng số (Constants):** Là các biến không bao giờ thay đổi so với giá trị ban đầu, được khai báo bằng cách kết hợp từ khóa `static` và `final`.

### **2. Variable classification**
Java chia biến thành 3 loại chính:
*   **Biến cục bộ (Local Variables):** Được khai báo bên trong phương thức hoặc khối lệnh. Biến này sinh ra khi phương thức/khối lệnh được gọi và tự động hủy khi kết thúc. **Bắt buộc phải được khởi tạo** giá trị trước khi sử dụng vì chúng không có giá trị mặc định.
*   **Biến thuộc tính (Instance Variables):** Được khai báo trong class nhưng nằm ngoài phương thức. Chúng phụ thuộc vào đối tượng (tạo bằng từ khóa `new`), có giá trị mặc định (VD: `0`, `false`, `null`) và bị hủy khi đối tượng bị hủy.
*   **Biến tĩnh (Static Variables):** Được khai báo với từ khóa `static` bên trong class. Biến tĩnh **độc lập với mọi đối tượng**, thuộc về chính class đó, được tạo ra khi chương trình bắt đầu và hủy khi chương trình kết thúc.

### **3. Naming rules**
*   **Quy tắc bắt buộc:** Tên chỉ được phép sử dụng **chữ cái, chữ số, ký hiệu `$`, và dấu gạch dưới `_`**. Tên **không được bắt đầu bằng chữ số**, không được chứa khoảng trắng hay từ khóa của Java và có **phân biệt chữ hoa chữ thường**.
*   **Quy ước đặt tên (Conventions):**
    *   **Class/Interface:** Bắt đầu bằng chữ in hoa (PascalCase), thường là danh từ hoặc tính từ (VD: `Employee`, `IPrintable`).
    *   **Biến/Phương thức:** Bắt đầu bằng chữ in thường, viết hoa chữ cái đầu tiên của các từ tiếp theo (camelCase) (VD: `firstName`, `draw()`).
    *   **Hằng số:** Viết IN_HOA_TOÀN_BỘ, các từ phân cách bằng dấu gạch dưới `_` (VD: `MAX_PRIORITY`).
    *   **Package:** Dùng chữ in thường toàn bộ, các từ phân cách bằng dấu chấm `.` (VD: `java.util`).

### **4. Basic data types**
Java có 8 kiểu dữ liệu cơ bản (Primitive types) chỉ lưu trữ giá trị đơn lẻ:
*   **Số nguyên:** `byte` (8-bit), `short` (16-bit), `int` (32-bit), `long` (64-bit).
*   **Số thực:** `float` (32-bit), `double` (64-bit). Đối với `float`, phải thêm hậu tố `F` hoặc `f` ở cuối số.
*   **Luận lý:** `boolean` (1-bit, chỉ chứa giá trị `true` hoặc `false`).
*   **Ký tự:** `char` (16-bit, lưu trữ ký tự Unicode).
*   *Lưu ý:* Mỗi kiểu cơ bản đều có một **Wrapper Class** tương ứng (VD: `Integer` cho `int`, `Double` cho `double`) để biến dữ liệu cơ bản thành đối tượng và cung cấp thêm nhiều phương thức xử lý.

### **5. The concept of operators and types of operators**
*   **Khái niệm:** Toán tử được sử dụng để **thực hiện các phép tính** trên biến và giá trị.
*   **Phân loại toán tử:**
    *   **Toán tử số học (Arithmetic):** Cộng (`+`), trừ (`-`), nhân (`*`), chia (`/`), chia lấy dư (`%`), tăng 1 đơn vị (`++`), giảm 1 đơn vị (`--`).
    *   **Toán tử gán (Assignment):** Dùng để gán giá trị cho biến, bao gồm `=`, `+=`, `-=`, `*=`, `/=`, `%=`, v.v..
    *   **Toán tử so sánh (Comparison):** Kiểm tra tính tương quan giữa hai giá trị: `==`, `!=`, `>`, `<`, `>=`, `<=`.
    *   **Toán tử logic (Logical):** Xác định logic giữa các biến/giá trị: `&&` (Và), `||` (Hoặc), `!` (Phủ định).
    *   **Toán tử điều kiện (Ternary Operator):** Viết tắt của lệnh `if-else`, có cú pháp: `Điều_kiện ? Lệnh_1_khi_đúng : Lệnh_2_khi_sai`.
    *   **Toán tử Bitwise:** Làm việc trực tiếp với các bit của một số nguyên: `~`, `&`, `^`, `|`, `<<`, `>>`.