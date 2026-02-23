Dưới đây là **quy trình mẫu chuẩn hóa cho Phòng IT trong hãng hàng không / tổ chức bảo dưỡng**.  
Quy trình này dựa trên các best practice từ **IATA Technical Operations**, tài liệu về **quản lý tài liệu & workflow** trong hàng không, và chuẩn **EASA Part-145** liên quan đến hệ thống dữ liệu và quản lý kỹ thuật.

---

# 🛠 **QUY TRÌNH MẪU CHO PHÒNG IT (PHÒNG CÔNG NGHỆ THÔNG TIN)**

_(Áp dụng cho hãng hàng không hoặc tổ chức bảo dưỡng hàng không dân dụng)_

---

# **I. MỤC ĐÍCH**

Quy trình nhằm thiết lập hệ thống quản trị CNTT đảm bảo:

- Hỗ trợ vận hành kỹ thuật – bảo dưỡng theo chuẩn IATA và EASA.
- Đảm bảo an toàn dữ liệu, tuân thủ tiêu chuẩn hàng không và hỗ trợ hoạt động bảo dưỡng – khai thác.
- Tự động hóa và tối ưu hóa quy trình tài liệu & maintenance workflows theo best practice ngành. [[iata.org]](https://www.iata.org/en/programs/ops-infra/techops/), [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

---

# **II. PHẠM VI ÁP DỤNG**

Bao gồm tất cả các hệ thống:

- **Hệ thống bảo dưỡng (MRO/CMMS)**: AMOS, TRAX, Ramco hoặc tương đương.
- **Hệ thống tài liệu kỹ thuật (TechPub/DMS)**: Web Manuals, PDF management, OCR.
- **Hệ thống an toàn – chất lượng – báo cáo kỹ thuật**.
- **Hệ thống hạ tầng IT**: mạng, máy chủ, bảo mật, backup.
- **Hỗ trợ kỹ thuật người dùng (Helpdesk)**.

---

# **III. CƠ SỞ THAM CHIẾU**

- **IATA Technical Operations Guidelines**: tiêu chuẩn tối ưu kỹ thuật, dữ liệu, công nghệ. [[iata.org]](https://www.iata.org/en/programs/ops-infra/techops/)
- **Workflow Automation trong hàng không**: quản lý tài liệu, báo cáo bảo dưỡng, tự động tạo work order. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **EASA Part-145 – Maintenance Organisation Exposition**: yêu cầu về dữ liệu, kiểm soát tài liệu, bảo mật, system integrity. [[easa.europa.eu]](https://www.easa.europa.eu/en/acceptable-means-compliance-and-guidance-material-group/part-145-maintenance-organisation-approvals), [[assets.ctfassets.net]](https://assets.ctfassets.net/8k0h54kbe6bj/6OrZYCRRspEjN0KMV6ugHQ/c59255a047286c3e70134a67806a22f9/LHD-240_MOE_checklist.docx)
- **Airline Documentation Systems (Web Manuals, IronOCR)**: chuẩn hóa distribution–approval workflow. [[webmanuals.aero]](https://webmanuals.aero/), [[ironsoftware.com]](https://ironsoftware.com/customers/white-papers/transforming-airline-document-management/)

---

# **IV. SƠ ĐỒ QUY TRÌNH TỔNG THỂ (TÓM TẮT)**

1. **Tiếp nhận yêu cầu IT** →
2. **Phân loại & ưu tiên** →
3. **Xử lý sự cố / yêu cầu** →
4. **Thay đổi hệ thống (Change Management)** →
5. **Kiểm thử & xác nhận** →
6. **Triển khai** →
7. **Theo dõi – Báo cáo – Cập nhật tài liệu hệ thống**

---

# **V. QUY TRÌNH CHI TIẾT**

---

# **1. TIẾP NHẬN YÊU CẦU (IT SERVICE REQUEST / INCIDENT)**

### **1.1. Kênh tiếp nhận**

- Helpdesk ticket (ưu tiên)
- Email nội bộ
- Điện thoại trực IT (24/7 nếu hãng vận hành liên tục)
- API/Auto-alert từ hệ thống MRO: khi xuất hiện lỗi, bất thường thiết bị hoặc dữ liệu (theo mô tả workflow automation). [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

### **1.2. Phân loại**

- **Incident**: lỗi hệ thống, không truy cập được dữ liệu, lỗi phần mềm bảo dưỡng…
- **Service Request**: cấp quyền, cấp thiết bị, tạo tài khoản MRO/DMS…
- **Change Request**: nâng cấp phần mềm, thay đổi biểu mẫu, chỉnh data logic.

### **1.3. Mức độ ưu tiên (theo EASA Part-145 – yêu cầu duy trì dữ liệu & hệ thống hỗ trợ bảo dưỡng)**

- **P1**: Ảnh hưởng an toàn bay / bảo dưỡng (không truy cập AMM/TSM, Work Order).
- **P2**: Ảnh hưởng vận hành nhưng có giải pháp tạm.
- **P3**: Không ảnh hưởng vận hành (UX, tối ưu, yêu cầu nhỏ). [[easa.europa.eu]](https://www.easa.europa.eu/en/acceptable-means-compliance-and-guidance-material-group/part-145-maintenance-organisation-approvals)

---

# **2. XỬ LÝ SỰ CỐ / YÊU CẦU**

### **2.1. Quy trình chung**

1. IT tiếp nhận & đánh giá mức ưu tiên.
2. Kiểm tra log hệ thống MRO/DMS.
3. Thực hiện khắc phục / hướng dẫn tạm thời.
4. Nếu sự cố liên quan dữ liệu kỹ thuật → phối hợp với Maintenance/Engineering.
5. Nếu liên quan tài liệu kỹ thuật → kiểm tra qua hệ thống Web Manuals hoặc OCR-based DMS.
    - Web Manuals cho phép kiểm tra revision, compliance với FAA/EASA/IOSA. [[webmanuals.aero]](https://webmanuals.aero/)
    - IronOCR hỗ trợ tự động hóa nhập tài liệu bảo dưỡng. [[ironsoftware.com]](https://ironsoftware.com/customers/white-papers/transforming-airline-document-management/)

### **2.2. Thời gian phản hồi**

- P1: ≤ 15 phút
- P2: ≤ 1 giờ
- P3: ≤ 4 giờ

---

# **3. QUẢN LÝ THAY ĐỔI (CHANGE MANAGEMENT)**

Áp dụng theo chuẩn:

- **IATA Technical Operations** – tiêu chuẩn hóa dữ liệu & các thay đổi hệ thống kỹ thuật. [[iata.org]](https://www.iata.org/en/programs/ops-infra/techops/)
- **EASA Part-145 MOE** – yêu cầu ghi nhận và phê duyệt mọi thay đổi ảnh hưởng dữ liệu bảo dưỡng. [[assets.ctfassets.net]](https://assets.ctfassets.net/8k0h54kbe6bj/6OrZYCRRspEjN0KMV6ugHQ/c59255a047286c3e70134a67806a22f9/LHD-240_MOE_checklist.docx)

### **3.1. Bước thực hiện**

1. **Tiếp nhận Change Request**.
2. **Đánh giá tác động**:
    - Ảnh hưởng đến dữ liệu bảo dưỡng
    - Ảnh hưởng đến chứng nhận/airworthiness
    - Ảnh hưởng đến các phòng ban khác
3. **Trình phê duyệt** (theo MOE):
    - IT Manager
    - Engineering / CAMO
    - Quality Assurance (bắt buộc)
4. **Kế hoạch triển khai**: thời gian, rollback plan, người thực hiện.
5. **Kiểm thử** (UAT)
6. **Triển khai**
7. **Ghi nhật ký thay đổi + Cập nhật tài liệu hệ thống**

---

# **4. QUY TRÌNH QUẢN LÝ TÀI LIỆU KỸ THUẬT & DỮ LIỆU**

Theo tiêu chuẩn:

- Hệ thống quản lý tài liệu hàng không phải đảm bảo **tính toàn vẹn, theo dõi revision, alert compliance** (Web Manuals). [[webmanuals.aero]](https://webmanuals.aero/)
- Workflow nhập tài liệu bảo dưỡng được tự động hóa nhằm giảm lỗi thủ công (IronOCR). [[ironsoftware.com]](https://ironsoftware.com/customers/white-papers/transforming-airline-document-management/)

### **4.1. Kiểm soát phiên bản**

- Mọi AMM/IPC/SRM/SB/AD phải được cập nhật đúng revision.
- Hệ thống cần có chức năng **alert khi có thay đổi từ nhà sản xuất / IATA / FAA / EASA**.

### **4.2. Quy trình**

1. Engineering gửi yêu cầu cập nhật tài liệu.
2. IT xử lý định dạng (XML/PDF/S1000D nếu áp dụng).
3. Upload lên hệ thống DMS.
4. QA/Engineering kiểm tra và phê duyệt.
5. Publish đến người dùng cuối (Line Maintenance, MCC, Planning).

---

# **5. QUY TRÌNH QUẢN LÝ DỮ LIỆU BẢO DƯỠNG**

Theo EASA Part-145 yêu cầu hệ thống phải lưu trữ dữ liệu bảo dưỡng đúng chuẩn, truy xuất được, bảo mật. [[easa.europa.eu]](https://www.easa.europa.eu/en/acceptable-means-compliance-and-guidance-material-group/part-145-maintenance-organisation-approvals)

### **5.1. Backup**

- Backup 2 lớp: onsite + cloud/offsite
- Báo cáo log backup hàng ngày

### **5.2. Bảo mật**

- MFA cho các hệ thống MRO/DMS
- Chỉ cấp quyền “need to know" cho dữ liệu kỹ thuật (Part-145 yêu cầu phân quyền rõ ràng).

### **5.3. Data Integrity**

- Kiểm tra lịch sử thay đổi work order
- Đối chiếu dữ liệu bảo dưỡng từ người dùng với hệ thống

---

# **6. QUY TRÌNH QUẢN LÝ HẠ TẦNG IT**

### **6.1. Giám sát hệ thống 24/7**

- Hệ thống phải có cảnh báo tự động khi lỗi (lấy từ mô tả về workflow automation). [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

### **6.2. Bảo trì định kỳ**

- Update OS, DB, middleware
- Kiểm thử hiệu năng

### **6.3. Kiểm soát truy cập**

- Quản lý tài khoản theo chuẩn Aviation cybersecurity.
- Tích hợp với IATA Cybersecurity framework về bảo mật dữ liệu & hệ thống. [[iata.org]](https://www.iata.org/en/publications/manuals/)

---

# **7. HELP DESK & BÁO CÁO HIỆU SUẤT**

### **7.1. SLA**

- Tỷ lệ xử lý ticket đúng hạn ≥ 95%
- Không để tồn đọng P1 > 0

### **7.2. Báo cáo hàng tháng**

- Thống kê incident theo loại
- Phân tích lỗi hệ thống MRO (theo xu hướng)
- Báo cáo cho QA theo chuẩn EASA về theo dõi dữ liệu kỹ thuật

---

# **VI. BIỂU MẪU – TÀI LIỆU ĐÍNH KÈM**

1. Form tiếp nhận yêu cầu
2. Change request form
3. Change impact assessment
4. Checklist backup
5. Checklist kiểm thử hệ thống
6. SOP xử lý sự cố MRO/DMS
7. Quy trình cập nhật tài liệu kỹ thuật

---

# 🎯 **Bạn muốn mình làm tiếp bước nào?**

Mình có thể tiếp tục hỗ trợ:  
✅ Tạo **bản SOP hoàn chỉnh dạng Word/PDF**  
✅ Tạo **luồng quy trình dạng flowchart**  
✅ Viết **quy trình theo chuẩn EASA Part-145** riêng cho phòng IT-CAMO/MRO  
Bạn muốn chọn hướng nào?