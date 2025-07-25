Công cụ Chuyển đổi PDF sang DOCX Hàng Loạt (Colab + Google Drive)

Mục tiêu: Tự động hoá việc chuyển đổi nhiều tệp PDF trong một thư mục Google Drive sang định dạng DOCX, đồng thời hỗ trợ OCR cho các file scan bằng Tesseract hoặc Google Gemini AI.

1. Tính năng chính

Chức năng

Mô tả

Ba chế độ xử lý

none (không OCR), tesseract (OCR truyền thống), gemini (OCR AI)

Xử lý hàng loạt

Quét toàn bộ thư mục Drive, tự động bỏ qua file đã chuyển đổi

Giữ bố cục

Chế độ tesseract cố gắng giữ layout gốc; chế độ none giữ 100 % khi PDF chứa văn bản sẵn

Độ chính xác cao

Chế độ gemini tận dụng mô hình đa phương thức Gemini để đọc văn bản khó

Hoàn toàn trên đám mây

Chạy trên Google Colab, không cần cài phần mềm nặng ở máy local

2. Kiến trúc & Thư viện sử dụng

PyDrive2 – giao tiếp Google Drive (tải xuống / tải lên)

pdf2docx – chuyển PDF → DOCX

OCRmyPDF + Tesseract – OCR truyền thống, giữ bố cục

Google Gemini API – OCR AI đa phương thức

pdf2image, Pillow – chuyển trang PDF thành ảnh (cho Gemini)

python‑docx – tạo DOCX khi dùng Gemini

3. Cách chạy nhanh (TL;DR)

Mở notebook Colab pdf_to_docx_batch.ipynb.

Chạy cell "Cài đặt môi trường" (chỉ lần đầu hoặc khi Colab reset).

Nhập thông số:

Folder ID của thư mục PDF trên Drive.

Chọn OCR Engine (none, tesseract, gemini).

Nếu dùng tesseract: điền tesseract_language (vd vie+eng) và tesseract_mode (force_ocr | skip_text).

Nếu dùng gemini: điền Gemini API Key lấy từ Google AI Studio.

Nhấn ▶️ ở cell "Chạy Tiến trình Chuyển đổi". Cafe time ☕.

Kết thúc, DOCX mới sẽ xuất hiện ngay trong thư mục Drive gốc.

Mẹo: Nếu bạn chỉ muốn update file mới, công cụ tự động bỏ qua PDF đã có DOCX cùng tên.

4. Hướng dẫn chi tiết

4.1 Chuẩn bị thư mục Google Drive

Tạo (hoặc chọn) một thư mục chứa các file PDF cần xử lý.

Chuột phải → Get link → đặt quyền Editor cho “Anyone with the link”.

Sao chép Folder ID (chuỗi sau /folders/ trong URL).

4.2 Chọn OCR Engine

Engine

Khi nào dùng

Ưu

Nhược

none

PDF sẵn có text

Nhanh, giữ định dạng 100 %

Không chạy với PDF scan

tesseract

Scan, muốn giữ layout

Giữ bố cục, miễn phí

Lâu hơn, OCR phụ thuộc chất lượng scan

gemini

Scan khó, cần độ chính xác

AI đọc tốt, đa ngôn ngữ

Mất layout, cần API Key & Internet

4.3 Thông số Tesseract

tesseract_language: mã ngôn ngữ Tesseract (ví dụ vie, eng, vie+eng).

tesseract_mode:

force_ocr: OCR mọi trang (kể cả trang có text ẩn).

skip_text: Chỉ OCR trang chưa có text (nhanh hơn).

4.4 Thông số Gemini

Đăng nhập Google AI Studio ➜ API Keys ➜ Create API Key.

Dán key vào ô gemini_api_key_input (bao gồm cả ký tự "").

6. Góp ý & Phát triển thêm

PR & Issue luôn chào đón! Ý tưởng tương lai:

Giao diện Gradio / Streamlit ➜ người dùng phổ thông không đụng Colab.

Hậu xử lý DOCX Gemini bằng LLM để nhận dạng tiêu đề, bảng, bullet list.

Hỗ trợ xuất thêm Markdown / TXT / PDF A.

