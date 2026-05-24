# Day 2 - AI Calorie Tracker với Gemini Vision

Notebook này minh họa cách xây dựng một công cụ nhận diện món ăn và ước tính dinh dưỡng từ hình ảnh bằng Gemini Vision trong Python.

## Nội dung

- Đọc API key từ file `.env`
- Cấu hình Gemini client với model `gemini-2.5-flash`
- Mở và hiển thị ảnh món ăn bằng `Pillow`
- Gửi ảnh kèm prompt đến Gemini Vision
- Trả về mô tả món ăn, nguyên liệu, khoảng calories ước tính
- Tạo prompt yêu cầu kết quả dinh dưỡng dạng JSON có cấu trúc

## Cấu trúc thư mục

```text
Day2-AI-Calorie-Tracker/
├── calories-tracker.ipynb
├── food_image.jpg
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
uv pip install google-generativeai python-dotenv pillow ipython gradio
```

Nếu môi trường đã có `pip`, có thể dùng:

```powershell
pip install google-generativeai python-dotenv pillow ipython gradio
```

## Cấu hình môi trường

Tạo file `.env` ở thư mục gốc project:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

Không commit file `.env` lên GitHub vì file này chứa API key.

## Cách chạy

1. Mở file `calories-tracker.ipynb`.
2. Chọn kernel trỏ tới `.venv` của project.
3. Đảm bảo file `food_image.jpg` nằm cùng thư mục với notebook.
4. Chạy lần lượt các cell từ trên xuống dưới.

## Luồng xử lý

```text
food_image.jpg
    ↓
Pillow mở ảnh
    ↓
Gemini Vision phân tích hình ảnh
    ↓
Prompt 1: mô tả món ăn và calories
    ↓
Prompt 2: trả về thông tin dinh dưỡng dạng JSON
```

## Ví dụ output

Kết quả mô tả ngắn:

```text
Food: ...
Description: ...
Ingredients: ...
Estimated calories: ...
Nutrition: ...
```

Kết quả JSON dinh dưỡng:

```json
{
  "food_name": "Example food",
  "serving_description": "1 serving",
  "calories": 250.0,
  "fat_grams": 8.0,
  "protein_grams": 12.0,
  "confidence_level": "Medium"
}
```

## Lưu ý

- Kết quả calories và dinh dưỡng chỉ là ước tính từ hình ảnh, không thay thế thông tin dinh dưỡng chính xác.
- Chất lượng ảnh, góc chụp và khẩu phần thực tế có thể làm thay đổi độ chính xác.
- Package `google-generativeai` có thể có cảnh báo deprecated từ Google. Notebook hiện vẫn dùng được, nhưng project mới có thể cân nhắc SDK mới `google-genai`.
