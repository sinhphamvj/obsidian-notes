Dưới đây là tóm tắt dễ hiểu về 7 mẹo viết truy vấn SQL sạch, nhanh và đáng tin cậy hơn từ video **"7 Simple Tricks to Instantly Make Your SQL Queries Better"** của kênh techTFQ:

**1. Định dạng và viết code SQL sạch (Clean code)**
*   Code được đọc nhiều lần hơn là viết, vì vậy hãy giúp chính bạn và đồng nghiệp dễ đọc hơn [1]. 
*   **Nguyên tắc:** Viết hoa các từ khóa (SELECT, FROM, JOIN...), viết thường các định danh (tên cột, tên bảng), và luôn thụt lề rõ ràng (mỗi cột hoặc điều kiện nằm trên một dòng riêng) [1, 2].

**2. Chỉ lấy những dữ liệu thực sự cần thiết**
*   Khi muốn xem trước dữ liệu để phân tích, hãy dùng lệnh `LIMIT` (ví dụ: LIMIT 100) thay vì tải hàng triệu dòng để tiết kiệm chi phí và thời gian [2, 3].
*   **Tránh dùng `SELECT *`:** Hãy liệt kê chính xác các cột bạn cần. Việc dùng `SELECT *` bắt cơ sở dữ liệu phải tốn tài nguyên (I/O) để đọc tất cả các cột [3]. Ngoài ra, nếu cấu trúc bảng thay đổi (ví dụ: thêm cột mới), dùng `SELECT *` có thể làm hỏng hệ thống của bạn [4]. Liệt kê tên cột cũng giúp code đóng vai trò như tài liệu để người khác dễ hiểu hơn [4].

**3. Chia nhỏ truy vấn phức tạp bằng CTE**
*   Thay vì lồng ghép quá nhiều các truy vấn con (nested subqueries) vào nhau khiến code rối rắm, hãy tách chúng ra bằng **CTE** (Common Table Expressions - mệnh đề `WITH`) [5, 6]. 
*   Cách này giúp bạn dễ dàng đọc hiểu, gỡ lỗi từng phần một và đôi khi còn cải thiện hiệu suất [5, 6].

**4. Ưu tiên sử dụng JOIN thay vì Subquery (truy vấn con) trong mệnh đề SELECT**
*   Khi cần lấy dữ liệu liên quan từ bảng khác, hãy dùng mệnh đề `JOIN` rõ ràng (explicit join) thay vì viết một truy vấn con nằm ngay trong phần `SELECT` [6, 7].
*   Dùng `JOIN` giúp người đọc ngay lập tức hiểu được hai bảng liên kết với nhau bằng cột nào, đồng thời giúp SQL tối ưu hóa hiệu suất tốt hơn [7, 8].

**5. Viết điều kiện thân thiện với Index (Chỉ mục)**
*   Nếu bạn có một cột đã được đánh Index (để tăng tốc độ tìm kiếm), **đừng bọc cột đó trong bất kỳ hàm nào** ở mệnh đề `WHERE` (ví dụ: `DATE(order_date)`) [8, 9].
*   Việc sử dụng hàm lên cột có Index sẽ làm hệ thống không nhận diện được Index nữa và buộc phải quét toàn bộ bảng (full table scan), làm câu lệnh cực kỳ chậm [8, 9]. Hãy dùng chính xác tên cột đó để so sánh.

**6. Không dùng DISTINCT để "che giấu" code lỗi**
*   `DISTINCT` chỉ nên dùng khi bạn thực sự cần lấy danh sách các giá trị duy nhất [9, 10].
*   Nhiều người viết lệnh `JOIN` bị sai dẫn đến kết quả trả về bị nhân bản (trùng lặp dữ liệu), sau đó lại thêm `DISTINCT` vào để lọc trùng [11, 12]. Đây là cách làm sai. Bạn cần phải tìm ra nguyên nhân và sửa lại điều kiện `JOIN` (hoặc cấu trúc truy vấn) thay vì lạm dụng `DISTINCT` [11, 12].

**7. Hiểu rõ sự khác biệt giữa `COUNT(*)` và `COUNT(tên_cột)`**
*   `COUNT(*)`: Sẽ đếm **toàn bộ** số dòng trong bảng, bất kể dòng đó có chứa giá trị `NULL` hay không [10].
*   `COUNT(tên_cột)`: Chỉ đếm những dòng mà cột đó **có giá trị (khác NULL)** [10].
*   Nếu bạn muốn đếm tổng số dòng mà lại dùng `COUNT(tên_cột)`, kết quả sẽ bị sai nếu tương lai cột đó xuất hiện các giá trị `NULL` [13]. Do đó, phải luôn cẩn thận lựa chọn tùy thuộc vào mục đích của bạn.