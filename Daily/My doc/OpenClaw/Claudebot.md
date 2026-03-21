Dựa trên các nguồn tin được cung cấp, **Clawdbot** (hay Cloudbot) là một trợ lý AI hoạt động như một "gateway" (cổng kết nối) tin nhắn, cho phép bạn triển khai một đại lý (agent) tự động hóa trực tiếp trên phần cứng của mình hoặc trên đám mây [1], [2].

Dưới đây là chi tiết về các chức năng và ứng dụng thực tế của Claudebot:

### 1. Các chức năng chính (Functions)

*   **Kết nối đa nền tảng nhắn tin:**
    Clawdbot hoạt động như một cổng kết nối trung gian, cho phép bạn tương tác với các mô hình AI thông qua các ứng dụng chat phổ biến như Discord, WhatsApp, Telegram, Slack và thậm chí là iMessage [3], [2].
*   **Tự động hóa tự chủ (Autonomous Automation):**
    Không chỉ là chatbot trả lời câu hỏi, Claudebot được thiết kế để trở thành một "đại lý" (agent) có khả năng thực thi các lệnh mà không cần sự can thiệp liên tục của con người. Nó có thể tự cài đặt các gói phần mềm, tương tác với mạng lưới và thực hiện các thay đổi trên máy tính [1], [4].
*   **Quản lý tệp tin và hệ thống cục bộ:**
    Clawdbot có quyền truy cập vào hệ thống tệp tin của bạn. Nó có thể tạo thư mục, đổi tên tệp tin hàng loạt và sắp xếp dữ liệu trên máy tính [5], [6].
*   **Tích hợp đa mô hình AI (Multi-model support):**
    Nó cho phép kết nối với nhiều nhà cung cấp mô hình AI khác nhau. Đặc biệt, thông qua các plugin như **Anti-gravity** hoặc **Gemini CLI**, người dùng có thể truy cập miễn phí các mô hình mạnh mẽ như **Claude Opus 4.5**, **Gemini 3 Pro**, và **Gemini Flash** [2], [7].
*   **Định tuyến thông minh (Multi-agent routing):**
    Hệ thống có khả năng tự động phân loại yêu cầu: chuyển các câu hỏi đơn giản cho các mô hình nhanh (như Gemini Flash) và các tác vụ lập trình phức tạp cho các mô hình mạnh hơn (như Claude Opus) để tối ưu hóa hiệu suất [8].
*   **Khả năng thị giác (Vision Capabilities):**
    Thông qua plugin **Quen Portal**, Claudebot có thể sử dụng các mô hình vision để phân tích hình ảnh hoặc ảnh chụp màn hình mà bạn gửi cho nó [9].

### 2. Ứng dụng thực tế (Practical Applications)

Dựa trên các ví dụ trong nguồn tin, Claudebot có thể được ứng dụng vào các việc sau:

*   **Quản lý cuộc sống cá nhân (Life Automation):**
    Nó có thể giúp dọn dẹp hộp thư đến (inbox), gửi email, quản lý lịch trình, và thậm chí tự động làm thủ tục check-in cho các chuyến bay thông qua tin nhắn chat [1].
*   **Lập trình và Quản lý máy tính:**
    *   **Sắp xếp dữ liệu:** Trong một ví dụ thực tế, Claudebot đã tự động đổi tên hàng loạt tệp hình ảnh (thumbnails) lộn xộn trên màn hình desktop thành các tên có số thứ tự và di chuyển chúng vào một thư mục mới chỉ trong vài giây [6].
    *   **Hỗ trợ Coding:** Nó đặc biệt hữu ích cho các phiên viết code nặng (heavy coding sessions) nhờ khả năng xoay vòng tài khoản để tránh giới hạn tốc độ (rate limits) [10].
*   **Nghiên cứu thị trường và Giao dịch (Trading):**
    Claudebot đã được sử dụng để thực hiện giao dịch trên các nền tảng cá cược (ví dụ: cược Super Bowl). Nó có khả năng tự động nghiên cứu tin tức trên X (Twitter), xác thực tín hiệu thị trường và tự đưa ra quyết định giao dịch để kiếm lợi nhuận mà không cần con người chỉ đạo từng bước [1], [4].
*   **Phân tích hình ảnh:**
    Bạn có thể gửi ảnh chụp màn hình hoặc hình ảnh bất kỳ để AI phân tích nội dung, hỗ trợ cho việc giải quyết vấn đề hoặc lấy thông tin từ hình ảnh [9].
*   **Hỗ trợ sáng tạo nội dung:**
    Có khả năng tương tác với các ứng dụng như Excel để xử lý dữ liệu hoặc CapCut để chỉnh sửa video [11].

### **Lưu ý quan trọng về bảo mật**
Mặc dù rất mạnh mẽ, việc cấp quyền truy cập cục bộ cho Claudebot tiềm ẩn rủi ro bảo mật lớn ("handing the keys to your computer"). Vì nó là một agent tự chủ, nếu không được cấu hình trong môi trường an toàn (sandbox), nó có thể đọc tất cả các tệp, thực hiện sai lệnh hoặc vô tình gây hại cho máy tính của bạn [4], [12].

Dưới đây là tài liệu hướng dẫn chi tiết cách cài đặt và sử dụng **Clawdbot** (hay Cloudbot) được tổng hợp từ các nguồn tin cung cấp. Tài liệu này bao gồm các yêu cầu hệ thống, quy trình cài đặt, cách cấu hình mô hình AI (bao gồm tùy chọn miễn phí), kết nối ứng dụng nhắn tin và các lưu ý quan trọng về bảo mật.

### **Tài liệu Hướng dẫn Sử dụng Clawdbot**

**1. Giới thiệu chung**
Clawdbot là một trợ lý AI mã nguồn mở hoạt động như một "gateway" (cổng kết nối) trung gian. Nó kết nối các mô hình ngôn ngữ lớn (LLM) như Claude hoặc GPT với các ứng dụng nhắn tin (WhatsApp, Telegram, Discord) và có khả năng chạy trực tiếp trên phần cứng của bạn (local-first) để thực hiện các tác vụ tự động hóa [1-3].

---

### **2. Chuẩn bị trước khi cài đặt**

**Yêu cầu hệ thống:**
*   **Phần cứng:** Bạn có thể chạy trên máy tính cá nhân (Mac Mini, PC có RAM tối thiểu 2GB - khuyến nghị 4GB trở lên) hoặc thuê máy chủ ảo VPS (ví dụ: Hetzner VPS giá rẻ) để chạy 24/7 [4-7].
*   **Hệ điều hành:** macOS, Linux, hoặc Windows (bắt buộc phải dùng qua **WSL2** - Windows Subsystem for Linux) [8, 9].
*   **Phần mềm:** Cần cài đặt **Node.js** (phiên bản 22 hoặc 24 trở lên) [6, 10].

**Kiểm tra Node.js:**
Chạy lệnh `node --version`. Nếu chưa có hoặc phiên bản thấp, hãy cài đặt/cập nhật Node.js trước [6].

---

### **3. Quy trình Cài đặt (Installation)**

Bạn có hai cách chính để cài đặt Clawdbot:

**Cách 1: Cài đặt nhanh qua Script (Khuyến nghị cho macOS/Linux/WSL)**
Chạy lệnh sau trong terminal:
```bash
curl -fsSL https://clawd.bot/install.sh | bash
```
Lệnh này sẽ tự động tải và cài đặt các thành phần cần thiết [11, 12].

**Cách 2: Cài đặt thủ công qua NPM**
Chạy lệnh:
```bash
npm install -g clawdbot@latest
```
Hoặc nếu dùng pnpm: `pnpm add -g clawdbot@latest` [12, 13].

---

### **4. Thiết lập và Cấu hình (Onboarding)**

Sau khi cài đặt xong, bạn cần chạy trình hướng dẫn thiết lập để khởi tạo gateway và kết nối tài khoản.

**Bước 1: Khởi chạy trình hướng dẫn**
Chạy lệnh:
```bash
clawdbot onboard --install-daemon
```
*Cờ `--install-daemon` giúp Clawdbot chạy ngầm như một dịch vụ nền, tự khởi động lại khi máy tính bật [8, 14].*

**Bước 2: Cấu hình Gateway**
Trình hướng dẫn sẽ hỏi các thông tin sau:
1.  **Vị trí Workspace:** Nhấn Enter để chọn mặc định (thường là `~/clawd`) [15].
2.  **Chọn nhà cung cấp mô hình (Model Provider):**
    *   Nếu bạn muốn trả phí: Chọn **Anthropic** hoặc **OpenAI** và dán API Key của bạn vào [11, 16].
    *   **Mẹo dùng Miễn phí (Từ video hướng dẫn):** Bạn có thể bỏ qua bước nhập key trả phí và cấu hình plugin miễn phí sau (xem mục 5 bên dưới).
3.  **Chọn kênh nhắn tin (Messaging Channels):** Chọn Telegram, WhatsApp hoặc Discord tùy nhu cầu [17].

---

### **5. Cấu hình Mô hình AI Miễn phí (Tùy chọn nâng cao)**

Dựa trên nguồn tin từ video, bạn có thể sử dụng các mô hình mạnh mẽ như **Claude Opus 4.5** hoặc **Gemini 3 Pro** miễn phí thông qua các plugin đặc biệt [18].

**Sử dụng Google Anti-gravity (Miễn phí Claude Opus/Sonnet):**
1.  **Kích hoạt plugin:** Chạy lệnh `Claudebot plugins enable Google Anti-gravity O` [19].
2.  **Đăng nhập:** Chạy lệnh `Claudebot models O login provider Google Anti-gravity set default`.
3.  Làm theo hướng dẫn trên màn hình để xác thực OAuth (không cần copy client ID/secret thủ công) [19].

**Sử dụng Gemini CLI:**
1.  **Kích hoạt:** `Claudebot plugins enable Google Gemini CL IO`.
2.  **Đăng nhập:** `Claudebot models O login provider Google Gemini CL i set default` [19].

**Quản lý Mô hình:**
*   Xem danh sách mô hình đã có: `Claudebot models list` [20].
*   Đặt mô hình mặc định: `Claudebot model set [tên_provider]/[tên_model]` (Ví dụ: `Google anti-gravity/cloud opus45`) [20].

---

### **6. Kết nối Ứng dụng Nhắn tin**

Để chat với bot, bạn cần liên kết tài khoản nhắn tin của mình.

*   **WhatsApp:**
    1.  Chạy lệnh `Claudebot channels login` [21].
    2.  Terminal sẽ hiện một mã QR. Mở WhatsApp trên điện thoại -> *Linked Devices* -> *Link a Device* và quét mã QR này [22, 23].
*   **Telegram:**
    1.  Chat với **@BotFather** trên Telegram để tạo bot mới (`/newbot`) và lấy **API Token** [24, 25].
    2.  Nhập token này vào cấu hình của Clawdbot khi được hỏi hoặc dùng lệnh cấu hình [25].
*   **Discord:**
    Cần tạo Bot trong *Discord Developer Portal*, bật các quyền "Privileged Gateway Intents" (Message Content) và lấy Token dán vào cấu hình [26, 27].

---

### **7. Hướng dẫn Sử dụng (Usage)**

Sau khi cài đặt, Clawdbot sẽ chạy trên cổng nội bộ (thường là `http://127.0.0.1:18789`). Bạn có thể truy cập địa chỉ này trên trình duyệt để xem bảng điều khiển (Dashboard) [21, 28].

**Các tính năng chính:**
*   **Chat:** Nhắn tin trực tiếp qua WhatsApp/Telegram. Ví dụ: "Tóm tắt email hôm nay cho tôi" hoặc "Thêm sữa vào danh sách mua sắm" [29, 30].
*   **Kỹ năng (Skills):** Clawdbot sử dụng file `SKILL.md` để học quy trình mới. Ví dụ: Tạo file hướng dẫn bot cách triển khai code (deploy) hoặc định dạng văn bản theo chuẩn công ty [31, 32].
*   **Tự động hóa (Cron Jobs):** Bạn có thể ra lệnh: "Gửi báo cáo công việc vào 5 giờ chiều mỗi thứ Sáu". Bot sẽ tự tạo lịch trình (cron job) để thực hiện [33, 34].
*   **Pairing Mode (Bảo mật):** Khi một người lạ nhắn tin cho bot, Clawdbot sẽ gửi một mã ghép đôi (pairing code). Bạn (Admin) cần chạy lệnh `clawdbot pairing approve [kênh] [mã]` để cho phép họ chat [35, 36].

---

### **8. Cảnh báo Bảo mật Quan trọng**

Việc sử dụng Clawdbot đi kèm với rủi ro lớn vì nó là một agent tự chủ chạy trên máy của bạn:
1.  **Quyền truy cập hệ thống:** Clawdbot có thể đọc/ghi tệp và thực thi lệnh. Nếu bị cấu hình sai hoặc bị tấn công, nó giống như việc "trao chìa khóa máy tính" cho người lạ [37, 38].
2.  **Không đưa ra Internet công cộng:** Mặc định, gateway chạy trên `localhost`. **Tuyệt đối không** mở cổng (port forwarding) này ra internet mà không có biện pháp bảo vệ (như VPN hoặc xác thực nghiêm ngặt), vì hacker có thể quét thấy và chiếm quyền điều khiển [39, 40].
3.  **Dữ liệu nhạy cảm:** Bot lưu trữ lịch sử chat, API key và thông tin đăng nhập trên máy. Cần bảo vệ thư mục cài đặt cẩn thận [40].

*Lưu ý: Clawdbot là dự án mã nguồn mở đang phát triển nhanh, các lệnh và tính năng có thể thay đổi theo thời gian [41].*