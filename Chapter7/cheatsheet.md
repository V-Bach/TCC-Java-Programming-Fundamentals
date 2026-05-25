# **CHAPTER 7 CHEAT SHEET: INPUT/OUTPUT (I/O)**

### **1. Data stream (Luồng dữ liệu)**
*   **Khái niệm:** Hoạt động vào/ra trong Java dựa trên các luồng (stream). Luồng đầu vào (**Input stream**) dùng để ĐỌC và luồng đầu ra (**Output stream**) dùng để GHI dữ liệu.
*   **Phân loại dữ liệu:** Gồm dữ liệu nhị phân (binary - máy đọc được) và dữ liệu văn bản (text/character - con người đọc được).
*   **Package `java.io`:** Cung cấp các lớp để xử lý I/O. Bốn bước cơ bản khi làm việc: `import java.io.*` -> Mở luồng -> Đọc/Ghi -> Đóng luồng (`close()`).

### **2. Input/output with binary data (I/O với dữ liệu nhị phân)**
*   **`FileInputStream` / `FileOutputStream`:** Đọc/ghi dữ liệu theo từng byte. Rất hữu ích để xử lý dữ liệu thô như file ảnh hoặc video.
*   **`DataInputStream` / `DataOutputStream`:** Cung cấp các phương thức để đọc/ghi trực tiếp các kiểu dữ liệu nguyên thủy (VD: `readInt()`, `writeDouble()`).
*   **`BufferedInputStream` / `BufferedOutputStream`:** Cung cấp cơ chế bộ đệm (buffer) giúp tăng tốc độ truyền tải và xử lý dữ liệu lên rất nhiều lần.

### **3. Input/output with text data (I/O với dữ liệu văn bản)**
*   **`InputStreamReader` / `OutputStreamWriter`:** Chuyển đổi dữ liệu từ dạng nhị phân sang định dạng ký tự để dễ thao tác (hỗ trợ mã hóa như UTF-8).
*   **`FileReader` / `FileWriter`:** Các lớp tiện ích giúp truyền trực tiếp tên file để thao tác đọc/ghi file văn bản nhanh chóng.
*   **`BufferedReader` / `BufferedWriter`:** Tối ưu hóa hiệu suất đọc/ghi văn bản bằng bộ đệm. Đặc biệt, `BufferedReader` có hàm `readLine()` cho phép đọc toàn bộ một dòng dữ liệu.

### **4. Working with object data (Làm việc với dữ liệu đối tượng)**
*   **`ObjectInputStream` / `ObjectOutputStream`:** Dùng để đọc và ghi trực tiếp một đối tượng Java ra file.
*   **Giao diện `Serializable`:** Đây là điều kiện **bắt buộc**. Lớp của đối tượng phải `implements Serializable` thì đối tượng đó mới được phép ghi ra file.
*   **Từ khóa `transient`:** Đặt trước những thuộc tính mà bạn **không muốn** ghi ra file (Java sẽ tự động bỏ qua các biến này khi serialize).