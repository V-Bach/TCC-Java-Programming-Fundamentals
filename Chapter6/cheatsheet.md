# **\CHAPTER 6 CHEAT SHEET: GENERICS & COLLECTIONS**

### **1. Generic Programming (Lập trình Tổng quát)**
*   **Mục đích:** Giúp viết code linh hoạt cho nhiều kiểu dữ liệu khác nhau mà không cần ép kiểu (type casting), đồng thời kiểm tra lỗi kiểu dữ liệu ngay lúc biên dịch.
*   **Generic Class:** Khai báo bằng cú pháp `class ClassName<T>`. Các tham số quy ước thường dùng: `T` (Type), `E` (Element), `K` (Key), `V` (Value).
*   **Khởi tạo đối tượng:** Bắt buộc sử dụng **kiểu tham chiếu (Wrapper classes)** như `Integer`, `Double`, `String`... (không dùng kiểu nguyên thủy như `int`). VD: `GenericClass<Integer> obj = new GenericClass<>(10);`.
*   **Generic Method:** Đặt tham số kiểu trước kiểu trả về của phương thức. VD: `public static <E> E getMiddle(E[] a)`.
*   **Type Limits (Giới hạn kiểu):** 
    *   `<T extends A>`: Giới hạn `T` phải là lớp con của lớp `A`.
    *   `<T extends B & C>`: `T` phải implement cả giao diện `B` và `C`.

### **2. Collections Framework**
Cung cấp bộ khung cấu trúc dữ liệu có sẵn để lưu trữ và thao tác với nhóm đối tượng. 

#### **A. LIST (Danh sách)**
*   **Đặc điểm:** Lưu trữ có thứ tự, cho phép phần tử trùng lặp, truy cập bằng chỉ số (index).
*   **ArrayList:** Lưu trữ dưới dạng mảng động. Truy cập phần tử (`get`) cực nhanh với độ phức tạp O(1). Thêm/xóa ở giữa danh sách chậm O(n) do phải dịch chuyển các phần tử.
*   **LinkedList:** Dựa trên danh sách liên kết đôi. Truy cập index chậm O(n), nhưng thêm/xóa phần tử ở đầu/cuối cực nhanh O(1).

#### **B. SET (Tập hợp)**
*   **Đặc điểm:** Chỉ lưu trữ **các phần tử duy nhất (không trùng lặp)**, không truy cập được qua index.
*   **HashSet:** Dùng bảng băm. Thêm, xóa, tìm kiếm cực nhanh O(1), nhưng **không đảm bảo thứ tự** phần tử.
*   **TreeSet:** Dùng cấu trúc cây (implements `SortedSet`). Các phần tử luôn được **sắp xếp theo thứ tự**, thao tác chậm hơn HashSet.

#### **C. MAP (Bản đồ / Từ điển)**
*   **Đặc điểm:** Lưu dữ liệu theo cặp **Key-Value (Khóa - Giá trị)**. Các `Key` luôn là duy nhất, `Value` có thể trùng lặp.
*   **HashMap:** Hoạt động dựa trên bảng băm, lấy/gán dữ liệu cực nhanh O(1), không đảm bảo thứ tự của `Key`.
*   **TreeMap:** Các `Key` luôn được sắp xếp theo thứ tự tự nhiên (implements `SortedMap`), chậm hơn HashMap.
*   **Các thao tác chính:** `put()`, `get()`, `remove()`. Bạn có thể duyệt Map thông qua `keySet()`, `values()`, hoặc `entrySet()`.

#### **D. LỚP TIỆN ÍCH (Collections Utility Class)**
*   Lớp `java.util.Collections` chứa các phương thức static dùng chung cho Collection như: `sort()` (sắp xếp), `reverse()` (đảo ngược), `shuffle()` (trộn ngẫu nhiên), `min()`, `max()`, `frequency()` (đếm tần suất).
