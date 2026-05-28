# Day 2 - AI Calorie Tracker with Gemini Vision

This notebook builds a simple AI calorie tracker that analyzes a food image with Gemini Vision. It sends both an image and a prompt to Gemini, asks the model to identify the food, estimate nutrition information, and return a structured JSON-style result.

## What This Project Covers

- Loading `GEMINI_API_KEY` from `.env`
- Configuring Gemini with `google-generativeai`
- Opening and displaying a local food image with Pillow
- Sending image-plus-text prompts to `gemini-2.5-flash`
- Asking Gemini for a human-readable food description
- Asking Gemini for structured nutrition output in JSON format
- Parsing and displaying model output in a notebook-friendly way

## Project Structure

```text
Day2 Build an AI Calorie Tracker Usisng GeminiAI API (Vision)/
|-- calories-tracker.ipynb
|-- food_image.jpg
|-- requirements.txt
`-- README.md
```

## Requirements

- Python 3.12 or newer
- Jupyter Notebook, JupyterLab, or the VS Code notebook interface
- A Google Gemini API key
- A local image file named `food_image.jpg`

## Installation

From the repository root, activate the virtual environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install the required packages:

```powershell
pip install -r "Day2 Build an AI Calorie Tracker Usisng GeminiAI API (Vision)/requirements.txt"
```

With `uv`:

```powershell
uv pip install --python .\.venv\Scripts\python.exe -r "Day2 Build an AI Calorie Tracker Usisng GeminiAI API (Vision)/requirements.txt"
```

## Environment Variables

Create or update the repository-level `.env` file:

```env
GEMINI_API_KEY=your_gemini_api_key_here
```

Do not commit `.env` to GitHub.

## How to Run

1. Open `calories-tracker.ipynb`.
2. Select the Python kernel that points to the repository `.venv`.
3. Confirm that `food_image.jpg` is in the same folder as the notebook.
4. Run the cells from top to bottom.
5. Replace `food_image.jpg` with another food image if you want to test a different meal.

## Main Code Flow

```text
food_image.jpg
  -> PIL.Image.open(...)
  -> Gemini prompt with image input
  -> food identification and calorie estimate
  -> second prompt for structured nutrition JSON
  -> parse and display result in the notebook
```

## Output Format

The notebook asks Gemini for information such as:

- Food name
- Serving description
- Estimated calories
- Fat, protein, and other nutrition values
- Confidence level

Example structured shape:

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

## Important Limitations

- Nutrition values are estimates generated from an image, not verified measurements.
- Portion size, lighting, image angle, hidden ingredients, and sauces can significantly affect accuracy.
- This project is for learning and prototyping only. It should not be used as medical, dietary, or clinical advice.
- The notebook currently uses the legacy `google-generativeai` package to match the course code.
