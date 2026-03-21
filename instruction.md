# HƯỚNG DẪN XỬ LÝ DỮ LIỆU: BÀI TOÁN TÍNH THỜI GIAN VÀ NHIÊN LIỆU APU PHỤC VỤ BẢO DƯỠNG (WP)

## 1. Mục tiêu (Objective)
Hướng dẫn mô hình AI/Lập trình viên phân tích dữ liệu hoạt động của máy bay để bóc tách chính xác khoảng thời gian nguồn phụ (APU) được sử dụng riêng cho các gói công việc bảo dưỡng (WP). Từ đó, tính toán lượng nhiên liệu (Fuel) mà APU đã tiêu thụ cho công tác bảo dưỡng này.

## 2. Cấu trúc dữ liệu đầu vào (Input Data Structure)

Dữ liệu gồm 2 bảng chính của 1 máy bay trong 1 ngày:

### Bảng 1: APU (Hoạt động của nguồn phụ)
* `apu_start_time`: Thời điểm khởi động APU (Datetime).
* `apu_end_time`: Thời điểm tắt APU (Datetime) -> Được tính bằng `apu_start_time` + `Duration`.
* `Duration`: Khoảng thời gian APU hoạt động (Phút/Giờ).
* `Fuel`: Tổng lượng nhiên liệu tiêu hao trong toàn bộ `Duration` (Kg/Lít).

### Bảng 2: WP (Gói công việc bảo dưỡng)
* `wp_start_time`: Thời điểm bắt đầu gói công việc (Datetime).
* `wp_end_time`: Thời điểm kết thúc gói công việc (Datetime).

---

## 3. Thuật toán cốt lõi: Tính khoảng thời gian giao nhau (Overlap Duration)

Thay vì dùng nhiều vòng lặp IF/ELSE phức tạp, hệ thống cần áp dụng công thức toán học sau để tìm ra phần thời gian giao nhau giữa 1 chu kỳ chạy APU và 1 khoảng thời gian WP:

1. **Điểm bắt đầu giao nhau:** `Overlap_Start = MAX(apu_start_time, wp_start_time)`
2. **Điểm kết thúc giao nhau:** `Overlap_End = MIN(apu_end_time, wp_end_time)`
3. **Thời gian giao nhau thực tế:** `Overlap_Duration = MAX(0, Overlap_End - Overlap_Start)`
   *(Nếu kết quả <= 0, nghĩa là hai sự kiện không giao nhau, thời gian tính bằng 0).*

---

## 4. Phân tích 5 Trường hợp Logic (1 APU vs 1 WP)

Dưới đây là mô tả trực quan các trường hợp có thể xảy ra khi đối chiếu 1 chu kỳ APU với 1 gói WP.

### Trường hợp 1: Không giao nhau (No Overlap)
* **Logic:** `apu_end_time <= wp_start_time` HOẶC `apu_start_time >= wp_end_time`
* **Mô phỏng:**
  APU: [---]                hoặc                [---]
  WP :       [========]             [========]
* **Kết quả:** Overlap_Duration = 0.

### Trường hợp 2: APU bao trùm hoàn toàn WP (APU Encloses WP)
* **Logic:** `apu_start_time <= wp_start_time` VÀ `apu_end_time >= wp_end_time`
* **Mô phỏng:**
  APU: [------------------]
  WP :     [========]
* **Kết quả:** Overlap_Duration = `wp_end_time` - `wp_start_time`

### Trường hợp 3: APU nằm hoàn toàn trong WP (WP Encloses APU)
* **Logic:** `apu_start_time >= wp_start_time` VÀ `apu_end_time <= wp_end_time`
* **Mô phỏng:**
  APU:     [------]
  WP : [================]
* **Kết quả:** Overlap_Duration = `Duration` của APU.

### Trường hợp 4: Giao nhau ở phần đầu của WP (Left Overlap)
* **Logic:** `apu_start_time <= wp_start_time` VÀ (`apu_end_time` > `wp_start_time` VÀ `apu_end_time` <= `wp_end_time`)
* **Mô phỏng:**
  APU: [----------]
  WP :       [================]
* **Kết quả:** Overlap_Duration = `apu_end_time` - `wp_start_time`

### Trường hợp 5: Giao nhau ở phần cuối của WP (Right Overlap)
* **Logic:** (`apu_start_time` >= `wp_start_time` VÀ `apu_start_time` < `wp_end_time`) VÀ `apu_end_time >= wp_end_time`
* **Mô phỏng:**
  APU:             [----------]
  WP : [================]
* **Kết quả:** Overlap_Duration = `wp_end_time` - `apu_start_time`

---

## 5. Xử lý Trường hợp Thực tế: 1 WP vs Nhiều lần bật/tắt APU (1-to-N)

Trong thực tế bảo dưỡng (VD: A-check), một WP có thể kéo dài và APU được bật/tắt nhiều lần để phục vụ ngắt quãng.

* **Mô phỏng:**
  WP  : [=================================================]
  APU 1:     [----]
  APU 2:                 [------]
  APU 3:                                       [-------]

* **Quy trình xử lý cho AI/Code:**
  1. **Lọc (Filter/Join):** Với mỗi một WP, tìm TẤT CẢ các bản ghi APU thỏa mãn điều kiện có giao nhau: `apu_start_time < wp_end_time` VÀ `apu_end_time > wp_start_time`.
  2. **Tính toán vòng lặp:** Áp dụng thuật toán cốt lõi (Mục 3) để tính `Overlap_Duration(i)` cho TỪNG bản ghi APU `(i)` vừa tìm được.
  3. **Tổng hợp (Aggregation):** Cộng dồn (SUM) tất cả các `Overlap_Duration(i)` để ra tổng thời gian APU chạy cho WP đó.

---

## 6. Công thức Tính Nhiên Liệu Tiêu Hao (Fuel Calculation)

Giả định APU tiêu thụ nhiên liệu tuyến tính theo thời gian. Lượng nhiên liệu cho WP được tính theo tỷ lệ:

Fuel_WP(i) = (Overlap_Duration(i) / Duration(i)) * Fuel(i)

**Tổng Fuel cho 1 gói WP:**
Total_Fuel_WP = SUM( Fuel_WP(i) ) với mọi i thuộc WP đó.