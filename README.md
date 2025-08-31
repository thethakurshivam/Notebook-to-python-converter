# Notebook to Python file Converter (Flask GUI)

A tiny Flask web app to convert a Jupyter Notebook (`.ipynb`) into **separate Python files** (one per code cell) and an optional **combined** Python file.

## Features
- Upload a `.ipynb` and download a ZIP of `.py` files.
- Clean HTML/CSS interface (no JS build tools required).
- Uses only Python stdlib (`json`) to parse notebooks.
- Filenames include the base notebook name and cell index.

## Project Structure
```
notebook-to-python-converter/
├─ app.py
├─ templates/
│  └─ index.html
├─ static/
│  └─ styles.css
├─ utils/
│  └─ convert.py
└─ requirements.txt
```

## Quick Start
1. **Create & activate a virtualenv (recommended)**
   ```bash
   python -m venv .venv
   # Windows: .venv\Scripts\activate
   # macOS/Linux:
   source .venv/bin/activate
   ```
2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the app**
   ```bash
   python app.py
   ```
4. Open your browser at `http://localhost:5000` and upload a `.ipynb` file.

## Notes
- Only code cells are exported. Markdown/raw cells are ignored.
- Output ZIP contains:
  - `your_notebook_cell_001.py`, `your_notebook_cell_002.py`, ...
  - `your_notebook_combined.py`
- If a notebook has **no code cells**, the app will show a friendly message.

## Security
- This demo keeps uploads local in the `uploads/` folder and created files in `outputs/`. Adjust as needed.
- Replace `app.secret_key` with a random secret in production.

## License
MIT
