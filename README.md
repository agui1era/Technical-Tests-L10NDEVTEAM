# SelenaCAT Technical Test

This project implements a minimal CAT (Computer-Assisted Translation) workflow:
- **Parser CLI** to convert `.docx` files into structured JSON and back.
- **Web UI** (`index.html`) to edit translations in the JSON format.

The goal is to simulate a round-tripping translation process.

---

## 📦 Requirements

- Python 3.10+
- Virtual environment recommended
- Dependencies:
  - `python-docx`
  - `uvicorn` (if you want to run the API later)

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## ⚙️ Usage

### 1. Extract text from a DOCX to JSON

```bash
python parser.py extract sample.docx output.json
```

This will produce a `output.json` file with the structure:

```json
[
  {
    "id": "sample_1",
    "key": "seg_1",
    "source": "This is a sentence.",
    "target": ""
  }
]
```

---

### 2. Edit JSON with the Web UI

1. Open `index.html` in a browser.
2. Click **Upload JSON** and select the `output.json` file.
3. Edit the **Target** column (your translations).
4. Export the updated JSON.

---

### 3. Rebuild the DOCX from JSON

After editing:

```bash
python parser.py build translated.json translated.docx
```

This generates a new `.docx` with the translated content.

---

## 🧪 Example Workflow

1. Start with `sample.docx`.
2. Run `extract` → get `output.json`.
3. Edit `output.json` in the web UI → save `translated.json`.
4. Run `build` → get `translated.docx`.

---

## ✅ Deliverables

- `parser.py` → CLI parser for DOCX ⇆ JSON.
- `index.html` → Web editor for JSON files.
- `README.md` → Instructions.

This setup simulates the round-tripping translation process required by the technical test.
