# Day 4 - Build Websites with Claude, Gemini, OpenAI & LLMs Leaderboards

Notebook nay minh hoa cach su dung cac LLM API nhu OpenAI, Google Gemini va Anthropic Claude de tao noi dung va build landing page bang HTML.

## Noi dung chinh

- Cau hinh API keys tu file `.env`
- Goi thu nghiem cac model OpenAI, Gemini va Claude
- So sanh ket qua sinh noi dung giua cac LLM
- Tao landing page HTML bang Gemini
- Luu ket qua thanh file web tinh co the mo truc tiep tren trinh duyet

## Demo website

Xem demo landing page tren GitHub Pages:

[Live Demo - Gemini Landing Page](https://sai-ctruong.github.io/agentic-ai-lab/Day4%20Build%20Websites%20with%20Claude%2C%20Gemini%2C%20OpenAI%20%26%20LLMs%20Leaderboads/gemini_landing_page.html)

Neu link chua hien thi, hay bat GitHub Pages trong repository:

1. Vao `Settings` cua repo tren GitHub
2. Chon `Pages`
3. Trong `Build and deployment`, chon source la `Deploy from a branch`
4. Chon branch `main` va folder `/root`
5. Bam `Save`, doi GitHub build xong roi mo lai link demo

## File web HTML

Mo landing page da tao tai day:

[gemini_landing_page.html](./gemini_landing_page.html)

Neu link khong mo truc tiep trong IDE, hay mo file sau trong trinh duyet:

```text
Day4 Build Websites with Claude, Gemini, OpenAI & LLMs Leaderboads/gemini_landing_page.html
```

## Cai dat

Tu thu muc goc project, cai cac thu vien can thiet:

```bash
pip install -r "Day4 Build Websites with Claude, Gemini, OpenAI & LLMs Leaderboads/requirements.txt"
```

Neu dung `uv` voi virtual environment `.venv`:

```bash
uv pip install --python .venv/Scripts/python.exe -r "Day4 Build Websites with Claude, Gemini, OpenAI & LLMs Leaderboads/requirements.txt"
```

## Cau hinh `.env`

Tao hoac cap nhat file `.env` o thu muc goc project:

```env
OPENAI_API_KEY=your_openai_api_key
GEMINI_API_KEY=your_gemini_api_key
ANTHROPIC_API_KEY=your_anthropic_api_key
```

Luu y: Neu OpenAI hoac Anthropic bao loi quota/credit, hay kiem tra billing cua tung nha cung cap. Notebook van co the chay phan Gemini neu `GEMINI_API_KEY` hop le.

## Chay notebook

Mo file notebook:

```text
Build-websites-LLMs-leaderboards.ipynb
```

Sau khi cai dat requirements va cau hinh `.env`, restart kernel roi chay lai cac cell tu dau.
