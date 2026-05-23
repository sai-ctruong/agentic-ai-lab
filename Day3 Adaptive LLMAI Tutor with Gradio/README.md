# Day 3 - Adaptive LLM AI Tutor với Gradio

Notebook này minh họa cách xây dựng một AI Tutor tương tác bằng Gemini API và Gradio. Người dùng có thể nhập câu hỏi, nhận câu trả lời từ AI, xem phản hồi dạng streaming và điều chỉnh mức độ giải thích bằng slider.

## Nội dung

- Đọc API key từ file `.env`
- Cấu hình Gemini client với model `gemini-2.5-flash`
- Tạo hàm AI Tutor trả lời câu hỏi học tập
- Hiển thị kết quả trong Jupyter Notebook bằng Markdown
- Xây dựng giao diện Gradio cơ bản
- Xây dựng giao diện Gradio có streaming response
- Thêm slider để chọn mức độ giải thích từ đơn giản đến chuyên sâu

## Cấu trúc thư mục

```text
Day3 Adaptive LLMAI Tutor with Gradio/
├── LLMAI-Tutor-with-Gradio.ipynb
├── requirements.txt
└── README.md
```

## Yêu cầu

- Python 3.12 hoặc mới hơn
- Jupyter Notebook / VS Code Notebook
- Gemini API key
- Virtual environment `.venv` ở thư mục gốc project

## Cài đặt

Từ thư mục gốc project, kích hoạt virtual environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

Cài các thư viện cần thiết:

```powershell
uv pip install -r "Day3 Adaptive LLMAI Tutor with Gradio/requirements.txt"
```

Nếu môi trường đã có `pip`, có thể dùng:

```powershell
pip install -r "Day3 Adaptive LLMAI Tutor with Gradio/requirements.txt"
```

## Cấu hình môi trường

Tạo file `.env` ở thư mục gốc project:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

Không commit file `.env` lên GitHub vì file này chứa API key.

## Cách chạy

1. Mở file `LLMAI-Tutor-with-Gradio.ipynb`.
2. Chọn kernel trỏ tới `.venv` của project.
3. Chạy các cell cấu hình Gemini trước.
4. Chạy cell định nghĩa hàm tutor.
5. Chạy một trong các giao diện Gradio:
   - Simple AI Tutor
   - AI Tutor with Streaming
   - Advanced AI Tutor với slider chọn mức độ giải thích

Khi Gradio chạy thành công, notebook sẽ hiển thị link local dạng:

```text
http://127.0.0.1:7860
```

Mở link đó trên trình duyệt để dùng app.

## Public link với Gradio

Nếu muốn tạo link public tạm thời, đổi:

```python
ai_tutor_interface_slider.launch()
```

thành:

```python
ai_tutor_interface_slider.launch(share=True)
```

Khi dùng `share=True`, Gradio có thể tạo thư mục `.gradio/` để lưu file tạm như certificate. Thư mục này không cần commit lên GitHub.

## Mức độ giải thích

Notebook dùng slider từ 1 đến 5:

```text
1 - like I'm 5 years old
2 - like I'm 10 years old
3 - like a high school student
4 - like a college student
5 - like an expert in the field
```

Giá trị slider sẽ được đưa vào system prompt để Gemini điều chỉnh cách giải thích.

## Lưu ý

- Nếu thấy dòng `DEBUG: Using System Prompt: ...`, đó chỉ là log debug để kiểm tra prompt đang được dùng.
- Có thể xóa hoặc comment dòng `print(...)` debug nếu muốn output sạch hơn.
- Package `google-generativeai` có cảnh báo deprecated từ Google. Notebook hiện vẫn dùng được, nhưng project mới có thể cân nhắc SDK mới `google-genai`.
