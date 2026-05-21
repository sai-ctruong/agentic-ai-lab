# Day 1 - AI Chatbot với Gemini

Notebook này minh họa cách tạo một chatbot AI đơn giản bằng Gemini API trong Python.

## Nội dung

- Đọc API key từ file `.env`
- Cấu hình Gemini client
- Gửi prompt đến model `gemini-2.5-flash`
- In phản hồi từ AI trong Jupyter Notebook

## Cấu trúc thư mục

```text
Day1-AI-Chatbot/
├── chat-with-geminiAI.ipynb
├── requirements.txt
└── README.md
```

## Yêu cầu

- Python 3.12 hoặc mới hơn
- Jupyter Notebook / VS Code Notebook
- Gemini API key

## Cài đặt

Từ thư mục gốc project, kích hoạt virtual environment đang dùng:

```powershell
.\.venv\Scripts\Activate.ps1
```

Cài các thư viện cần thiết:

```powershell
pip install -r Day1-AI-Chatbot/requirements.txt
```

Nếu venv được tạo bằng `uv` và chưa có `pip`, có thể dùng:

```powershell
uv pip install --python .\.venv\Scripts\python.exe -r Day1-AI-Chatbot/requirements.txt
```

## Cấu hình môi trường

Tạo file `.env` ở thư mục gốc project:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

Không commit file `.env` lên GitHub vì file này chứa API key.

## Cách chạy

1. Mở file `chat-with-geminiAI.ipynb`.
2. Chọn kernel `LLM-agentic` hoặc kernel trỏ tới `.venv`.
3. Chạy lần lượt các cell từ trên xuống dưới.

## Ví dụ prompt

```python
my_message = "Write me three interesting facts about people."
```

## Lưu ý

Package `google-generativeai` hiện có cảnh báo deprecated từ Google. Notebook vẫn chạy được, nhưng các project mới nên cân nhắc chuyển sang SDK mới `google-genai`.
