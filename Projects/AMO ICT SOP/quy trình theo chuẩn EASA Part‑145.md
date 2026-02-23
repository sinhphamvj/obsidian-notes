Dưới đây là **quy trình theo chuẩn EASA Part‑145** dành riêng cho **Khối IT‑CAMO/MRO (AMO Technology)**, cấu trúc **03 team** như sơ đồ bạn gửi: **Project Research & Development Team**, **System Operation Team**, **Monitoring & Support Team**. Nội dung bám sát yêu cầu trong **Part‑145.A.45/48/50/55/60/65/70** và cách tổ chức trong **MOE** theo **AMC & GM** và **MOE Checklist**. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation), [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/), [[seguridada…rea.gob.es]](https://www.seguridadaerea.gob.es/en/ambitos/aeronaves/aeronavegabilidad-continuada/organizaciones/aprobacion-de-organizaciones-parte-145)

> **Lưu ý:** Quy trình này để đưa vào **Chương phụ trợ CNTT** của **MOE** (Maintenance Organisation Exposition) hoặc tài liệu liên kết (IT‑QMS Manual) và sẽ được thẩm tra bởi QA theo Part‑145.A.65. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

---

## 1) Mục đích – Phạm vi – Tài liệu tham chiếu

**Mục đích:** Thiết lập và kiểm soát hoạt động CNTT hỗ trợ bảo dưỡng/engineering, đảm bảo **tính toàn vẹn dữ liệu, khả dụng hệ thống, kiểm soát tài liệu, truy vết & tuân thủ** theo EASA Part‑145 và tài liệu liên quan trong MOE. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation), [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

**Phạm vi:** Áp dụng cho toàn bộ hệ thống **MRO/CMMS**, **DMS/TechPub**, cơ sở dữ liệu bảo dưỡng, hạ tầng CNTT, giám sát, hỗ trợ người dùng và dự án cải tiến công nghệ trong phạm vi **AMO**. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

**Tài liệu tham chiếu bắt buộc đưa vào MOE/IT‑QMS:**

- **EASA AMC & GM to Part‑145** (Issue mới nhất) – căn cứ điều khoản A.45/48/50/55/60/65/70. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **CAA CAP 2375 – MOE Guidance** (cấu trúc & kiểm soát MOE; dùng làm mẫu định dạng phụ lục CNTT). [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **LHD‑240 MOE Checklist** (đối chiếu đầy đủ phần thủ tục, biểu mẫu & đối sánh điều khoản). [[seguridada…rea.gob.es]](https://www.seguridadaerea.gob.es/en/ambitos/aeronaves/aeronavegabilidad-continuada/organizaciones/aprobacion-de-organizaciones-parte-145)
- **IATA Technical Operations** (chuẩn hoá quy trình kỹ thuật & dữ liệu hỗ trợ vận hành, reliability). [[studylib.net]](https://studylib.net/doc/27739324/easa-part-145-training-guide)

---

## 2) Cơ cấu tổ chức – Vai trò – Năng lực

**Khối AMO Technology (IT‑CAMO/MRO)** gồm 3 team:

### 2.1. Project Research & Development (PRD) Team

- **Nhiệm vụ:** Nghiên cứu, phát triển và tích hợp giải pháp CNTT cho MRO/TechPub; chuẩn hóa dữ liệu (SB/AD/AMM/SRM/XML/S1000D), tự động hóa quy trình; đề xuất thay đổi quy trình/ứng dụng. [[studylib.net]](https://studylib.net/doc/27739324/easa-part-145-training-guide)
- **Tuân thủ:** Mọi thay đổi ảnh hưởng dữ liệu/maintenance phải theo **Change Management** trong MOE, có đánh giá rủi ro an toàn/airworthiness theo 145.A.65, lưu vết theo 145.A.55. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation), [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Năng lực yêu cầu:** Kiến thức Part‑145, dữ liệu kỹ thuật, quản trị DMS/MRO, kiểm thử UAT, quản trị yêu cầu (REQ), kỹ năng tài liệu hóa theo MOE. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

### 2.2. System Operation (SO) Team

- **Nhiệm vụ:** Vận hành hạ tầng, DB, ứng dụng MRO/DMS; cấu hình quyền; quản lý bản vá; backup/DR; đảm bảo **availability** và **data integrity**; phát hành phần mềm theo cửa sổ bảo trì. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **Tuân thủ:** Quản lý dữ liệu/records theo 145.A.55; kiểm soát maintenance data theo 145.A.45; báo cáo occurrence theo 145.A.60 nếu sự cố CNTT ảnh hưởng an toàn bay/maintenance release. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **Năng lực yêu cầu:** DB admin, hệ điều hành, bảo mật, CMDB, sao lưu 3‑2‑1; hiểu các mục A.45/48/50/55 của Part‑145. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

### 2.3. Monitoring & Support (MS) Team

- **Nhiệm vụ:** Giám sát 24/7 các hệ thống MRO/DMS; tiếp nhận & phân loại ticket; hỗ trợ tuyến 1–2; đo SLA/KPI; thống kê, RCA; phối hợp QA audit. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Tuân thủ:** Quy định báo cáo & lưu hồ sơ incident theo 145.A.55, tham chiếu 145.A.65 về quality system và cải tiến. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **Năng lực yêu cầu:** Service management, triage, tool giám sát, kiến thức nghiệp vụ bảo dưỡng cơ bản & kiểm soát tài liệu. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

> **Tất cả vị trí** phải được mô tả trong MOE/Phụ lục, có đào tạo định kỳ và đánh giá năng lực phù hợp điều khoản nhân sự/đào tạo của Part‑145 (tham chiếu trong MOE). [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

---

## 3) Quy trình cốt lõi theo Part‑145

### 3.1. Kiểm soát **Maintenance Data & Technical Publications** (áp dụng 145.A.45, 145.A.48, 145.A.50)

**Mục tiêu:** Đảm bảo **tài liệu/ dữ liệu** sử dụng để bảo dưỡng **đúng, cập nhật, kiểm soát phiên bản** và **sẵn có** trước khi thực hiện công việc. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

**Luồng công việc:**

1. **Tiếp nhận/cập nhật**: PRD nhận thông báo SB/AD/AMM/SRM từ OEM/Regulator → chuẩn hóa định dạng (PDF/XML/S1000D) và metadata. [[studylib.net]](https://studylib.net/doc/27739324/easa-part-145-training-guide)
2. **Kiểm soát tài liệu**: SO cấu hình DMS/TechPub, thiết lập **quyền truy cập**, **compliance links**, **revision control**, **audit trail** theo hướng dẫn MOE. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
3. **Rà soát & phê duyệt**: Engineering/CAMO kiểm tra tính đúng/sử dụng; QA kiểm tra tuân thủ; phát hành bản **Controlled Copy** cho Line/Base Maintenance. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
4. **Sẵn sàng khi bảo dưỡng**: MS xác nhận đội bảo dưỡng truy cập được tài liệu hợp lệ trước khi mở work card; nếu lỗi truy cập, kích hoạt xử lý P1. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
5. **Lưu hồ sơ**: Lưu vết phát hành, nhật ký truy cập, thay đổi phiên bản theo 145.A.55. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

**Chỉ báo:** % tài liệu đúng revision tại thời điểm phát hành WO; sự cố “wrong/no data at point of use”. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

---

### 3.2. **Quản lý Thay đổi CNTT** liên quan đến bảo dưỡng (áp dụng 145.A.65, 145.A.70)

**Mục tiêu:** Mọi thay đổi hệ thống/dữ liệu/quy trình có ảnh hưởng tới bảo dưỡng đều **được đánh giá rủi ro, phê duyệt, thử nghiệm, triển khai có kiểm soát**, hậu kiểm & ghi hồ sơ. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

**Luồng công việc & RACI:**

- **Khởi tạo CR:** Đề xuất từ PRD/SO/Engineering → **MS** ghi ticket/CR và phân loại (Standard/Normal/Emergency). **(R: Đơn vị đề xuất; A: IT Manager; C: QA/Engineering; I: CAMO/Users)**. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Đánh giá tác động:** PRD + SO + Engineering phân tích tác động tới **airworthiness, dữ liệu, con người, tuân thủ**; QA rà soát theo 145.A.65. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **Phê duyệt:** IT Manager + Engineering/CAMO + QA phê duyệt theo quy định trong MOE (đảm bảo phân quyền và độc lập QA). [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Kế hoạch & thử nghiệm:** SO lập plan (cửa sổ bảo trì, back‑out); PRD chuẩn bị bản build; **UAT** với Engineering/CAMO; lưu biên bản. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Triển khai & giám sát:** SO triển khai; MS giám sát thời gian thực; ghi nhận bất thường. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Hậu kiểm & cập nhật hồ sơ:** QA chủ trì review; cập nhật **CMDB**, tài liệu vận hành, work instruction trong MOE; đóng CR. [[seguridada…rea.gob.es]](https://www.seguridadaerea.gob.es/en/ambitos/aeronaves/aeronavegabilidad-continuada/organizaciones/aprobacion-de-organizaciones-parte-145)

**Hồ sơ bắt buộc:** CR form, Impact Assessment, UAT record, Release note, Back‑out plan, Post‑Implementation Review; lưu giữ theo 145.A.55. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

---

### 3.3. **Quản lý Dữ liệu & Hồ sơ Bảo dưỡng** (áp dụng 145.A.55)

**Mục tiêu:** Bảo đảm **tính toàn vẹn, truy xuất, bảo mật** và **thời hạn lưu** của hồ sơ bảo dưỡng/IT logs theo MOE. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

**Yêu cầu chính:**

- **Phân quyền** “need‑to‑know”, **MFA** cho MRO/DMS, nhật ký truy cập. SO chịu trách nhiệm cấu hình & định kỳ kiểm tra. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **Sao lưu 3‑2‑1**, test khôi phục định kỳ; quy định **RTO/RPO**. SO vận hành; MS giám sát việc chạy backup; QA kiểm tra khi audit. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Chuẩn đặt tên & metadata** để truy xuất nhanh; **hash/checksum** cho tệp quan trọng; kiểm soát **audit trail**. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Thời hạn lưu** theo Part‑145.A.55 và quy định nhà chức trách; mô tả trong MOE bảng retention. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

---

### 3.4. **Giám sát Hệ thống, Ứng phó Sự cố & Báo cáo Occurrence** (áp dụng 145.A.60/65)

**Mục tiêu:** Phát hiện sớm, giảm thiểu thời gian gián đoạn hệ thống **ảnh hưởng đến bảo dưỡng** và đáp ứng yêu cầu **occurrence reporting** khi có rủi ro an toàn. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

**Quy trình:**

1. **Giám sát chủ động:** MS vận hành công cụ APM/siem/log để cảnh báo lỗi truy cập AMM/Work Card/MRO, dung lượng DB, hiệu năng. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
2. **Phân loại/Prioritise:** P1 nếu tác động tới khả năng phát hành CRS/tiếp tục công việc bảo dưỡng; kích hoạt on‑call. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
3. **Xử lý sự cố:** SO khôi phục dịch vụ theo SOP; PRD hỗ trợ phân tích nguyên nhân nếu liên quan thay đổi/bản phát hành. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
4. **Occurrence:** Nếu sự cố IT có tiềm ẩn rủi ro safety/airworthiness (ví dụ tài liệu sai phiên bản đã được sử dụng), QA phối hợp khai báo **145.A.60** theo quy trình báo cáo của MOE. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
5. **RCA & CAPA:** MS tổng hợp, QA chủ trì phân tích gốc rễ, ban hành **CAPA**; cập nhật KPI chất lượng theo 145.A.65. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

---

### 3.5. **Bảo trì Hạ tầng, Bảo mật & Liên tục Kinh doanh** (áp dụng 145.A.65)

- **Hardening & Patch:** SO định kỳ vá lỗi OS/DB/ứng dụng; tuân lịch **maintenance window** trong MOE; ghi hồ sơ release. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Bảo mật:** Chính sách mật khẩu, MFA, phân quyền vai trò; quản lý lỗ hổng và kiểm thử xâm nhập phạm vi hệ thống bảo dưỡng; tích hợp vào hệ thống chất lượng theo 145.A.65. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **DR/BCP:** Kịch bản thảm họa (RTO/RPO), diễn tập; tài liệu hóa trong MOE; báo cáo kết quả cho QA. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

---

## 4) Giao diện liên phòng ban (Engineering/CAMO/QA/Line‑Base Maintenance)

- **Engineering/CAMO:** Cung cấp yêu cầu business, xác minh dữ liệu/ấn phẩm kỹ thuật, tham gia UAT & phê duyệt thay đổi tác động tới airworthiness (liên kết 145.A.65/70). [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **QA:** Độc lập kiểm soát tuân thủ; phê duyệt tài liệu IT‑MOE; thực hiện audit theo checklist MOE; quản lý occurrence & CAPA. [[seguridada…rea.gob.es]](https://www.seguridadaerea.gob.es/en/ambitos/aeronaves/aeronavegabilidad-continuada/organizaciones/aprobacion-de-organizaciones-parte-145), [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Line/Base Maintenance:** Tiếp nhận controlled copy tài liệu; phản hồi usability; tạo incident khi không truy cập được tài liệu/WO. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

---

## 5) Hồ sơ – Biểu mẫu – Lưu giữ (áp dụng 145.A.55/70)

**Hồ sơ tối thiểu phải quản lý trong DMS/MOE:**

- **IT‑IN‑01**: Incident Record & RCA/CAPA (occurrence liên quan IT nếu có). [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **IT‑CR‑01**: Change Request + Impact Assessment + Phê duyệt đa bên + UAT + Release Note + PIR. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **IT‑BK‑01**: Nhật ký backup/restore, kết quả diễn tập DR. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **IT‑DMS‑REQ**: Yêu cầu cập nhật ấn phẩm kỹ thuật, bảng đối sánh revision/compliance links, biên bản phát hành controlled copy. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

**Lưu giữ & truy xuất:** Thời hạn, nơi lưu, người chịu trách nhiệm được mô tả trong MOE; đảm bảo truy xuất nhanh và kiểm tra trong audit. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)

---

## 6) Đào tạo – Năng lực – Nhận thức (áp dụng 145.A.65)

- Đào tạo ban đầu & định kỳ về **Part‑145**, **quy trình MOE**, quản lý dữ liệu & tài liệu kỹ thuật, bảo mật, công cụ MRO/DMS. **QA** theo dõi kế hoạch & hồ sơ đào tạo. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- Đào tạo theo vai trò cho **PRD/SO/MS** (ví dụ: S1000D/XML cho PRD; DB/backup/DR cho SO; triage/SLA/occurrence cho MS). [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

---

## 7) Chỉ số KPI & Mục tiêu chất lượng (áp dụng 145.A.65)

- **Availability hệ thống MRO/DMS** ≥ 99,5% (trừ bảo trì kế hoạch). SO chịu trách nhiệm. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Tài liệu đúng revision tại điểm sử dụng**: 100%; mọi sai lệch là occurrence cần điều tra. PRD/SO/MS + QA. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **SLA xử lý P1** (mất truy cập tài liệu/WO, lỗi ảnh hưởng phát hành CRS): phản hồi ≤ 15 phút, khôi phục tạm ≤ 60 phút. MS theo dõi, QA giám sát. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **Tỷ lệ triển khai thay đổi đúng quy trình (no unapproved change)**: 100%. QA audit theo MOE checklist. [[seguridada…rea.gob.es]](https://www.seguridadaerea.gob.es/en/ambitos/aeronaves/aeronavegabilidad-continuada/organizaciones/aprobacion-de-organizaciones-parte-145)

---

## 8) Kiểm toán nội bộ – Cải tiến liên tục (áp dụng 145.A.65/70)

- **QA audit** định kỳ các quy trình 3 team theo **MOE checklist**, phỏng vấn và thử truy xuất hồ sơ/records; phát hành **findings** (Level 1/2) và theo dõi **CAPA**. [[seguridada…rea.gob.es]](https://www.seguridadaerea.gob.es/en/ambitos/aeronaves/aeronavegabilidad-continuada/organizaciones/aprobacion-de-organizaciones-parte-145)
- **Management Review** của AMO Technology: xem xét KPI, occurrence, hiệu quả CAPA, nguồn lực, nhu cầu thay đổi MOE/IT‑QMS. Kết quả review được lưu và phản hồi cho các team. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

---

## 9) Phân công trách nhiệm (tóm tắt RACI)

|Quy trình|PRD|SO|MS|Eng/CAMO|QA|IT Mgr|
|---|---|---|---|---|---|---|
|Quản lý tài liệu kỹ thuật (nhận–chuẩn hoá–phát hành)|R|C|C|A/C|C/A (tuân thủ)|I|
|Change Management (CR→UAT→Release→PIR)|R/C|R|C|C/A (nội dung)|A (tuân thủ)|A|
|Giám sát & Sự cố hệ thống|C|C|R|I|C|I|
|Backup/DR & Bảo mật|C|R|C|I|C/A (kiểm tra)|A|
|Báo cáo KPI & Management Review|C|C|R|I|C|A|

_(R: Responsible; A: Accountable; C: Consulted; I: Informed). Thể hiện trong phụ lục MOE/IT‑QMS._ [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

---

## 10) Biểu mẫu – Tài liệu hoá trong MOE

- **Phụ lục IT‑MOE‑01:** Cấu trúc tổ chức AMO Technology (sơ đồ 3 team) + mô tả vị trí/chức năng. [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Phụ lục IT‑MOE‑02:** Quy trình kiểm soát maintenance data & TechPub (flow + biểu mẫu IT‑DMS‑REQ). [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Phụ lục IT‑MOE‑03:** Change Management (CR form, Impact Assessment, UAT, Release note, PIR). [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)
- **Phụ lục IT‑MOE‑04:** Incident/Occurrence Handling (IT‑IN‑01, phân loại P1/P2/P3, báo cáo 145.A.60). [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation)
- **Phụ lục IT‑MOE‑05:** Backup/DR Plan & kết quả diễn tập; bảng retention hồ sơ theo 145.A.55. [[airwaysmag.com]](https://www.airwaysmag.com/legacy-posts/document-workflow-automation), [[aircraften…ineer.info]](https://www.aircraftengineer.info/easa-part-145/)

---

### Bạn muốn mình:

- **Xuất bản quy trình này thành file Word/PDF** (đưa vào định dạng MOE chuẩn, có mã biểu mẫu, RACI, flowchart)?
- Tùy biến theo **tên hệ thống bạn đang dùng (AMOS/TRAX/…**) và **SLA nội bộ**?

Mình có thể tạo ngay **bản Word** với các phụ lục nêu trên để bạn nộp QA/nhà chức trách khi cần.