Dựa trên nội dung video "The Complete Agentic RAG Build", dưới đây là quy trình chi tiết từng bước để xây dựng một ứng dụng Agentic RAG hoàn chỉnh bằng cách cộng tác với Claude Code.
[[https://youtu.be/xgPWCuqLoek?si=8OvnaYmWh57r1qOr]
Quy trình được chia thành giai đoạn chuẩn bị và 8 mô-đun phát triển chính.

### Giai đoạn 1: Chuẩn bị và Thiết lập Môi trường

1.  **Xác định Tech Stack:**
    *   **Frontend:** React, TypeScript, Tailwind CSS, ShadCN UI (giao diện), Vite (build tool) [1].
    *   **Backend:** Python với FastAPI, Dockling (xử lý tài liệu) [2].
    *   **Database & Auth:** Supabase (PostgreSQL, PGVector, Authentication) [3][4].
    *   **AI Models:** Kết hợp mô hình đám mây (OpenAI, OpenRouter) và mô hình cục bộ (Local LLMs chạy qua LM Studio/Ollama) [5][6].
    *   **Công cụ lập trình:** Claude Code (CLI tool), IDE (Cursor hoặc VS Code), LangSmith (để theo dõi/observability) [5][7].

2.  **Khởi tạo Dự án:**
    *   Tải mã nguồn khởi đầu từ GitHub repo được cung cấp [8][9].
    *   Cấu hình các file quy tắc cho AI: `claude.md` (chứa quy tắc tech stack, quy ước đặt tên), `progress.mmd` (theo dõi tiến độ dự án) [10][11].
    *   Cài đặt biến môi trường: Tạo file `.env`, thêm API keys (Supabase, OpenAI, LangSmith, Tavily...) [12][13][14].

3.  **Quy trình làm việc (AI Dev Loop):**
    *   Sử dụng lệnh `/plan` để Claude lên kế hoạch cho từng mô-đun dựa trên tài liệu yêu cầu sản phẩm (PRD) [15][16].
    *   Sử dụng lệnh `/build` để thực thi code từ kế hoạch đã duyệt [17].
    *   Quản lý ngữ cảnh (Context Management): Xóa session (`/clear`) khi bộ nhớ đệm vượt quá 50% để tránh lỗi và tiết kiệm chi phí, sau đó dùng lệnh `/onboard` để AI nắm lại tình hình dự án [18][19].
    *   Cam kết mã nguồn (Git commit) sau mỗi mô-đun hoàn thành [20].

---

### Giai đoạn 2: Thực hiện 8 Mô-đun (Modules)

#### Mô-đun 1: App Shell & Giao diện Chat cơ bản
*   **Mục tiêu:** Tạo khung ứng dụng, đăng nhập và giao diện chat cơ bản.
*   **Thực hiện:**
    *   Kết nối Supabase Auth để quản lý người dùng và bảo mật dữ liệu theo từng người (Row Level Security) [21].
    *   Tạo giao diện Chat UI (React).
    *   Tích hợp "Managed RAG" ban đầu sử dụng OpenAI Responses API để test nhanh tính năng chat với tài liệu [21][22].
    *   Thiết lập LangSmith để theo dõi các luồng gọi API (Traces) [7][23].

#### Mô-đun 2: Ingestion UI & Backend (Tự xây dựng RAG)
*   **Mục tiêu:** Chuyển từ "Managed RAG" sang hệ thống RAG tự quản lý (Bring Your Own Retrieval).
*   **Thực hiện:**
    *   Xây dựng giao diện upload tài liệu (Ingestion UI) [4].
    *   Tạo backend để xử lý file, chia nhỏ (chunking) và tạo vector embeddings.
    *   Lưu trữ vector vào Supabase sử dụng PGVector [4].
    *   Thêm tính năng chọn mô hình (Model Selector) cho phép người dùng đổi giữa OpenAI, OpenRouter hoặc Local Models [24][25].

#### Mô-đun 3: Record Manager (Quản lý bản ghi)
*   **Mục tiêu:** Ngăn chặn việc upload trùng lặp tài liệu.
*   **Thực hiện:**
    *   Tạo cơ chế "băm" (hashing) nội dung file.
    *   Hệ thống sẽ kiểm tra: nếu file đã tồn tại và không đổi -> bỏ qua; nếu đã sửa đổi -> chỉ cập nhật phần thay đổi [4][26].

#### Mô-đun 4: Trích xuất Metadata & Lọc
*   **Mục tiêu:** Tăng độ chính xác khi tìm kiếm bằng cách lọc theo thuộc tính.
*   **Thực hiện:**
    *   Sử dụng LLM để tự động trích xuất tiêu đề, tóm tắt, ngôn ngữ, chủ đề từ nội dung tài liệu khi upload [27].
    *   Cấu hình lược đồ metadata (metadata schema) trong cài đặt [28].
    *   Cập nhật luồng tìm kiếm để hỗ trợ lọc theo metadata (ví dụ: chỉ tìm trong tài liệu loại "Báo cáo") [29][30].

#### Mô-đun 5: Hỗ trợ Đa định dạng (Multi-format)
*   **Mục tiêu:** Xử lý nhiều loại file ngoài văn bản thuần.
*   **Thực hiện:**
    *   Tích hợp thư viện **Dockling** để xử lý PDF, DocX, PowerPoint [29].
    *   Sử dụng Vision Language Models (VLM) trong Dockling để đọc hiểu cả biểu đồ và hình ảnh trong tài liệu [31].
    *   Tối ưu hóa hiệu suất (batch processing) để tránh quá tải RAM khi xử lý nhiều file nặng [32][33].

#### Mô-đun 6: Tìm kiếm Lai & Tái xếp hạng (Hybrid Search & Reranking)
*   **Mục tiêu:** Cải thiện chất lượng kết quả tìm kiếm.
*   **Thực hiện:**
    *   Kết hợp tìm kiếm từ khóa (Keyword Search) và tìm kiếm ngữ nghĩa (Vector Search) -> Hybrid Search [29][34].
    *   Tích hợp bước Reranking (tái xếp hạng kết quả) sử dụng Cohere hoặc các mô hình local reranker để chọn ra các đoạn văn bản liên quan nhất trước khi gửi cho LLM [34][35].

#### Mô-đun 7: Công cụ bổ sung (Agentic Tools)
*   **Mục tiêu:** Biến RAG thường thành Agentic RAG (có khả năng dùng công cụ).
*   **Thực hiện:**
    *   **Web Search:** Tích hợp công cụ tìm kiếm Tavily để agent tra cứu thông tin online [29][36].
    *   **Text-to-SQL:** Cho phép agent truy vấn dữ liệu có cấu trúc (ví dụ: database bán hàng). Lưu ý bảo mật bằng cách tạo một user database chỉ có quyền đọc (read-only) để tránh agent tự ý xóa dữ liệu [29][37][38].

#### Mô-đun 8: Tác nhân phụ (Sub-agents)
*   **Mục tiêu:** Xử lý các tác vụ phức tạp (như đọc toàn bộ tài liệu dài) mà không làm loãng ngữ cảnh của agent chính.
*   **Thực hiện:**
    *   Tạo công cụ "Analyze Document".
    *   Khi người dùng yêu cầu tóm tắt/phân tích sâu một file, agent chính sẽ gọi một sub-agent.
    *   Sub-agent load toàn bộ nội dung file đó vào ngữ cảnh riêng của nó để xử lý và trả về kết quả cho agent chính [7][39].
    *   Cập nhật Frontend để hiển thị quá trình suy nghĩ (thinking process) và các bước gọi công cụ lồng nhau (nested tool calls) của sub-agent [40][41].

### Giai đoạn 3: Hoàn thiện và Kiểm thử
*   **Validation Suite:** Tạo bộ test tự động để đảm bảo các tính năng mới không làm hỏng tính năng cũ (Regression testing) [42].
*   **Sửa lỗi UI/UX:** Thêm Dark mode, sửa lỗi hiển thị các bước suy nghĩ (thinking tags) của AI [43][41].
*   **Git Release:** Đóng gói phiên bản, gắn tag (v0.1, v0.2...) và đẩy lên GitHub private repo [44][45].

Video kết thúc ở giai đoạn Alpha (phiên bản 0.8), với lưu ý rằng cần thêm các bước triển khai (deployment) và quản lý môi trường (dev/staging/prod) cho một hệ thống thực tế [46][47].