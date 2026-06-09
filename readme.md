# PDF Annotation Remapper

A tool that automatically repositions PDF annotations when content shifts between document versions.

## How It Works

Each annotation points at a specific element (text or graphic) in the PDF. When a new version of the document arrives with shifted content, this tool:

1. Reads every annotation from the **annotated source PDF** and identifies the nearest text it points to (its "anchor")
2. Finds that same anchor text in the **new PDF**
3. Calculates how far it moved and shifts every annotation by that amount
4. Outputs a new PDF with all annotations correctly repositioned

---

## Option A: Use the Web App (recommended for teams)

### Deploy to Streamlit Cloud (free, one-time setup)

1. **Create a GitHub account** at [github.com](https://github.com) if you don't have one
2. **Create a new repository** and upload these three files:
 - `app.py`
 - `remap_annotations.py`
 - `requirements.txt`
3. **Go to** [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub
4. Click **New app** → select your repository → set **Main file path** to `app.py` → click **Deploy**
5. In ~2 minutes you'll get a public URL — share it with anyone on your team

### Using the app

1. Upload the **annotated PDF** (the current version with annotations)
2. Upload the **new PDF** (the updated version, no annotations yet)
3. Set the **page number** where the annotations live
4. Click **Remap Annotations**
5. Download the finished PDF

---

## Option B: Run Locally (command line)

### Setup (one-time)

```bash
pip install pymupdf