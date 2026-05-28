# Day 4 - Build Websites with Claude, Gemini, OpenAI, and LLM Leaderboards

This notebook compares multiple commercial LLM APIs and uses them to generate a complete static landing page. It configures OpenAI, Google Gemini, and Anthropic Claude clients, tests their responses on sample prompts, then asks each model to generate HTML for a startup landing page.

## What This Project Covers

- Loading `OPENAI_API_KEY`, `GEMINI_API_KEY`, and `ANTHROPIC_API_KEY` from `.env`
- Configuring OpenAI, Gemini, and Claude Python clients
- Testing model behavior on reasoning and creative prompts
- Building a shared landing-page generation prompt
- Generating HTML with OpenAI `gpt-4o`
- Generating HTML with Gemini `gemini-2.5-flash`
- Generating HTML with Claude models
- Saving generated HTML files locally
- Opening the generated static HTML page in a browser

## Project Structure

```text
Day4 Build Websites with Claude, Gemini, OpenAI & LLMs Leaderboads/
|-- Build-websites-LLMs-leaderboards.ipynb
|-- gemini_landing_page.html
|-- requirements.txt
`-- README.md
```

The notebook may also create additional generated files when the corresponding API calls succeed:

```text
openai_landing_page.html
claude_landing_page.html
```

These files are generated outputs and may not exist until you run the notebook cells.

## Requirements

- Python 3.12 or newer
- Jupyter Notebook, JupyterLab, or the VS Code notebook interface
- API keys for the providers you want to test:
  - OpenAI
  - Google Gemini
  - Anthropic Claude

You can run only the Gemini sections if you only have a Gemini key.

## Installation

From the repository root, activate the virtual environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

Install the required packages:

```powershell
pip install -r "Day4 Build Websites with Claude, Gemini, OpenAI & LLMs Leaderboads/requirements.txt"
```

With `uv`:

```powershell
uv pip install --python .\.venv\Scripts\python.exe -r "Day4 Build Websites with Claude, Gemini, OpenAI & LLMs Leaderboads/requirements.txt"
```

## Environment Variables

Create or update the repository-level `.env` file:

```env
OPENAI_API_KEY=your_openai_api_key_here
GEMINI_API_KEY=your_gemini_api_key_here
ANTHROPIC_API_KEY=your_anthropic_api_key_here
```

Do not commit `.env` to GitHub.

## How to Run

1. Open `Build-websites-LLMs-leaderboards.ipynb`.
2. Select the Python kernel that points to the repository `.venv`.
3. Run the setup cell that loads API keys and configures clients.
4. Run the prompt testing cells to compare model behavior.
5. Run the landing-page generation cells for the providers you want to test.
6. Open the generated `.html` files in a browser.

## Generated Website

The committed example output is:

[gemini_landing_page.html](./gemini_landing_page.html)

The notebook prompt asks the model to generate a static landing page for a fictional startup named `ConnectGenius`, an AI-powered CRM product.

## Live Demo

The generated landing page is also deployed here:

[Live Demo - Gemini Landing Page](https://curious-pudding-c7eae5.netlify.app/)

## Main Code Flow

```text
.env API keys
  -> configure OpenAI, Gemini, and Claude clients
  -> run comparison prompts
  -> define one shared HTML generation prompt
  -> call each provider
  -> strip Markdown code fences if needed
  -> save provider output as .html
  -> open generated static page
```

## Notes

- Provider APIs may fail if billing, quota, model access, or API keys are not configured correctly.
- The notebook includes error handling for failed provider calls and can continue with the providers that are available.
- Generated HTML is model output. Review it before publishing or reusing it in production.
- The folder name contains the typo `Leaderboads`; paths in this README match the current repository name exactly.
