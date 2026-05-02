# 🤖 Kehuishere - Multimodal Chatbot AI (Image-to-Text Analysis)

Hệ thống chatbot thông minh có khả năng nhận diện hình ảnh và trả lời câu hỏi dựa trên ngữ cảnh thị giác. Dự án ứng dụng kiến trúc **Multimodal RAG** kết hợp giữa Computer Vision và xử lý ngôn ngữ tự nhiên.

---

## 🏗 Kiến trúc hệ thống (Architecture)
Dự án được xây dựng dựa trên 4 giai đoạn chính theo sơ đồ thiết kế:
1.  **YOLO - Visual Detection**: Sử dụng YOLOv8 (đã train trên Colab) để phát hiện vật thể trong ảnh.
2.  **Visual Feature / Embedding**: Trích xuất đặc trưng hình ảnh của các đối tượng được phát hiện.
3.  **Text Embedding**: Chuyển đổi câu hỏi của người dùng thành vector không gian.
4.  **Fusion & Transformer**: Kết hợp dữ liệu ảnh và văn bản để sinh câu trả lời tự nhiên qua LLM (Gemini API).

---

## 🚀 Tính năng nổi bật
*   **Multimodal Input**: Hỗ trợ tải lên hình ảnh (.jpg, .png) kèm câu hỏi văn bản.
*   **Real-time Inference**: Nhận diện vật thể nhanh chóng ngay trên máy cá nhân sau khi train.
*   **Modern UI/UX**: Giao diện dạng Glassmorphism, hỗ trợ Dark Mode và xem trước ảnh (Preview).
*   **Lịch sử trò chuyện**: Lưu trữ phiên làm việc tạm thời tại LocalStorage.

---

## 🛠 Công nghệ sử dụng (Tech Stack)

### Backend
*   **Ngôn ngữ**: Python 3.9+
*   **Framework**: FastAPI
*   **AI Model**: 
    *   YOLOv8 (Object Detection) - Huấn luyện trên Google Colab.
    *   Gemini API (Generative AI) - Bộ não xử lý ngôn ngữ.
*   **Thư viện**: `ultralytics`, `pillow`, `python-multipart`, `uvicorn`.

### Frontend
*   **HTML5/CSS3**: Tailwind CSS (Styling).
*   **JavaScript (ES6)**: Xử lý logic chat và gọi API.

---

## 📦 Hướng dẫn cài đặt và Chạy Demo

### 1. Yêu cầu chuẩn bị
*   Tải file model `best.pt` từ Google Colab về.
*   Cài đặt Python trên máy cá nhân.

### 2. Cài đặt thư viện
Mở Terminal tại thư mục dự án và chạy lệnh:
```bash
pip install fastapi uvicorn ultralytics python-multipart pillow