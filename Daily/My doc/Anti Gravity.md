[https://www.antigravityforpms.com/getting-started/introduction?fbclid=IwVERDUAPjlYRleHRuA2FlbQIxMABzcnRjBmFwcF9pZAwzNTA2ODU1MzE3MjgAAR5swF4NkVEXC8aZJPtIHeEj-Rlidq9Z5_mT8k5u9AyZTnvLLk42A9h-Ylr3_Q_aem_rALj-XqjTJJyoSWAEd2XRw]()
### 1. Tính năng đột phá: Agent Skills (Kỹ năng Tác vụ)
[https://github.com/sickn33/antigravity-awesome-skills?fbclid=IwdGRjcAPjlgVjbGNrA-OWAmV4dG4DYWVtAjExAHNydGMGYXBwX2lkDDM1MDY4NTUzMTcyOAABHibDBsmwnJiOnltBy0u9SdyntvAMq4w3PoG_TFTmUgv4P6f2zTzHs-_SmcLF_aem_9jIN281_pP5UVKp-KY8o7w]()
Đây là bản cập nhật quan trọng nhất gần đây, biến Antigravity từ một công cụ hỗ trợ code thành một nền tảng điều phối AI mạnh mẽ.
*   **Định nghĩa:** Skills là một tiêu chuẩn mở, cho phép đóng gói kiến thức, quy trình (workflow) và các phương pháp tốt nhất (best practices) thành các đơn vị có thể tái sử dụng (thường là thư mục chứa file `SKILL.md`) [1], [2], [3].
*   **Cơ chế:** Khi bạn ra lệnh, Agent sẽ tự động quét, phát hiện và "học" kỹ năng phù hợp để thực hiện nhiệm vụ mà không cần bạn nhắc lại hướng dẫn chi tiết [4], [3].
*   **Các Skill nổi bật:**
    *   **UI/UX Pro Max:** Một skill giúp AI tự động áp dụng các nguyên tắc thiết kế chuyên nghiệp, bảng màu, và bố cục hiện đại thay vì tạo ra giao diện "AI generic" nhàm chán [5], [6].
    *   **Nano Banana Skill:** Cho phép Agent gọi mô hình tạo ảnh Nano Banana để tự động sinh hình ảnh, logo, assets cho dự án web ngay trong IDE, thậm chí vượt qua giới hạn số lượng tạo ảnh mặc định của hệ thống [7], [8].
    *   **NotebookLM Skill:** Kết nối Antigravity với Google NotebookLM để AI có thể "đọc" và nghiên cứu tài liệu từ notebook của bạn, sau đó áp dụng kiến thức đó vào việc code [9], [10].

### 2. Bộ công cụ Antigravity Kit 2.0
Cộng đồng và Google đã phát triển **Antigravity Kit 2.0**, một gói mở rộng giúp tăng cường sức mạnh cho IDE này:
*   **Chuyên môn hóa Agent:** Thay vì dùng một AI chung chung, bộ kit này cung cấp 16 agent chuyên biệt (như Frontend Specialist, Backend Architect, SEO Specialist, Game Developer...) [11], [12].
*   **Workflows có sẵn:** Tích hợp các quy trình chuẩn như "Brainstorm" (lên ý tưởng), "Debug" (sửa lỗi), hay "Plan" (lập kế hoạch) giúp người dùng không cần nghĩ prompt phức tạp [13], [14].
*   **Cài đặt:** Có thể cài đặt dễ dàng qua terminal bằng lệnh `npx` để biến dự án thành một hệ thống đa agent [15].

### 3. Cập nhật về Mô hình và Hiệu suất
*   **Gemini 1.5 Flash:** Google đã tích hợp model này vào gói miễn phí. Nó có tốc độ lập kế hoạch và thực thi nhanh gấp đôi so với Gemini Pro, rất phù hợp cho các tác vụ code hàng ngày [16].
*   **Hỗ trợ đa mô hình (Multi-model):** Mặc dù mặc định là Gemini, Antigravity hỗ trợ kết nối với **Claude 3.5 Sonnet**, **Claude Opus**, hoặc **GPT-4o** thông qua các tiện ích mở rộng như *Open Code* hoặc plugin xác thực. Điều này cho phép dùng mô hình giỏi nhất cho từng tác vụ (ví dụ: dùng Claude để code frontend, Gemini để xử lý ngữ cảnh lớn) [17], [18], [19].
*   **Chính sách sử dụng:** Google đã áp dụng giới hạn sử dụng (usage caps) hàng tuần cho người dùng gói Pro để đảm bảo tính bền vững, trong khi người dùng gói Ultra vẫn được không giới hạn [20], [21].

### 4. Kiến trúc "Agent-First" và Quản lý Tác vụ
Antigravity đang định hình lại cách lập trình với tư duy "Agent-first" (Tác vụ trước, Code sau):
*   **Mission Control (Manager View):** Một giao diện quản lý cho phép bạn chạy song song nhiều Agent cùng lúc. Ví dụ: một agent đang viết code backend, một agent khác đang viết tài liệu, và một agent thứ ba đang chạy test trên trình duyệt [21], [22].
*   **Artifacts:** Để giải quyết vấn đề "tin tưởng" vào AI, Antigravity tạo ra các *Artifacts* (tạo tác) như bản kế hoạch, video quay màn hình thao tác của AI, hoặc ảnh chụp màn hình lỗi. Người dùng review các artifacts này thay vì phải đọc từng dòng log [23], [24].
*   **Tự sửa lỗi (Self-Healing/Auto-Fix):** Với các file cấu hình như `agents.md`, hệ thống có khả năng tự phát hiện lỗi khi chạy (runtime errors), tự đọc log, và tự sửa lại code cho đến khi chạy đúng (self-annealing) [25], [26].

### 5. Tích hợp MCP (Model Context Protocol)
Antigravity hỗ trợ mạnh mẽ giao thức MCP để kết nối với các công cụ bên ngoài mà không cần code logic kết nối phức tạp:
*   **Database:** Kết nối trực tiếp với **Supabase** để tạo bảng, quản lý user, auth ngay trong chat [27], [28].
*   **Deployment:** Sử dụng MCP của **Netlify** hoặc **Vercel** để deploy ứng dụng ra internet chỉ bằng một câu lệnh tự nhiên (ví dụ: "Deploy cái này lên mạng giúp tôi") [29], [30].
*   **Google Workspace:** Thao tác trực tiếp với Google Sheets, Gmail, Drive để lấy dữ liệu hoặc gửi báo cáo [31].

### Tóm lại: Xu hướng "Vibe Engineering"
Cộng đồng đang chuyển dịch từ khái niệm "Vibe Coding" (code theo cảm tính) sang **"Vibe Engineering"** (Kỹ thuật Vibe). Điều này có nghĩa là thay vì chỉ chat ngẫu nhiên với AI, các lập trình viên đang tập trung xây dựng các **Skill** và **Rules** (quy tắc) chất lượng cao để điều phối đội ngũ AI làm việc chính xác và nhất quán [32], [33]. Google Antigravity đang là công cụ trung tâm cho xu hướng này.