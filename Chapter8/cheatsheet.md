# **CHAPTER 8 CHEAT SHEET: MULTI-THREAD PROGRAMMING**

### **1. Process vs. Thread (Tiến trình và Luồng)**
*   **Process (Tiến trình):** Là một chương trình đang thực thi, có không gian bộ nhớ (address space) riêng. Tạo process tốn nhiều tài nguyên hệ thống.
*   **Thread (Luồng):** Là đơn vị thực thi nhỏ nhất bên trong một process. Các thread của cùng một process **chia sẻ chung không gian bộ nhớ**, giúp giao tiếp trực tiếp và khởi tạo nhanh hơn process.

### **2. How to create threads (Cách tạo Luồng)**
*   **Cách 1 - Kế thừa lớp `Thread`:** Tạo lớp `extends Thread`, ghi đè (override) phương thức `run()`, tạo đối tượng và gọi hàm `start()` để luồng bắt đầu chạy.
*   **Cách 2 - Triển khai giao diện `Runnable`:** Tạo lớp `implements Runnable`, ghi đè `run()`. Sau đó tạo đối tượng `Thread` (truyền Runnable vào constructor) và gọi `start()`.
*   **Cách 3 - Anonymous Thread / Lambda:** Viết code ngắn gọn không cần tạo lớp riêng: `new Thread(() -> { lệnh; }).start();`.

### **3. Quản lý vòng đời và phương thức của Thread**
*   **Trạng thái:** Một luồng có thể ở các trạng thái như New (Mới), Runnable (Đang chạy/Sẵn sàng), Waiting/Blocked (Chờ đợi/Bị chặn), và Terminated (Kết thúc).
*   **Phương thức quan trọng:** 
    *   `join()`: Yêu cầu chương trình đợi cho đến khi thread này kết thúc.
    *   `isAlive()`: Kiểm tra xem thread còn đang chạy hay không.
    *   `wait()` / `notify()`: Tạm dừng thread để nhả tài nguyên / Đánh thức thread đang chờ.

### **4. Synchronization (Xử lý đồng bộ hóa)**
Đồng bộ hóa giải quyết vấn đề xung đột dữ liệu khi nhiều thread cùng thao tác lên một biến/tài nguyên:
*   **Từ khóa `synchronized`:** Đảm bảo tính độc quyền (mutual exclusion), chỉ cho phép một thread thực thi khối lệnh ở một thời điểm.
*   **Từ khóa `volatile`:** Đảm bảo thay đổi giá trị của biến được hiển thị ngay lập tức với các luồng khác (ngăn việc CPU đọc nhầm dữ liệu cũ từ bộ nhớ cache).
*   **Locks (`ReentrantLock`):** Sử dụng hàm `lock()` để khóa tài nguyên và `unlock()` để mở khóa (luôn đặt `unlock()` trong khối `finally` để đảm bảo chắc chắn mở khóa).
*   **Điều phối luồng (Conditions):** Dùng `Condition` sinh ra từ Lock để điều khiển luồng qua hàm `await()` (đợi) và `signalAll()` (đánh thức tất cả). Hoặc dùng trực tiếp `wait()` và `notifyAll()` bên trong hàm `synchronized`.

### **5. Sử dụng Fork-Join Framework**
*   **Nguyên lý:** Khung (framework) này giúp tăng tốc độ xử lý song song nhằm tối đa hóa hiệu suất CPU dựa trên nguyên tắc **"chia để trị" (divide-and-conquer)**.
*   **Cách dùng:** Kết hợp `ForkJoinPool` với các lớp như `RecursiveTask` (chia nhỏ mảng dữ liệu khổng lồ thành các mảng nhỏ để tính toán đồng thời).

### **6. Create and manage processes (Tạo và quản lý Tiến trình)**
*   Java cho phép bạn tạo một tiến trình hoàn toàn mới (khởi chạy một ứng dụng hoặc lệnh hệ điều hành) bằng cách sử dụng lớp **`Process`** và **`ProcessBuilder`** (VD: `new ProcessBuilder("/bin/ls", "-l").start();`).
