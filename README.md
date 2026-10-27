<<<<<<< HEAD
# AI-Powered PDF to Word Converter

A beginner-friendly project for **Windows + VS Code**. Upload a PDF containing selectable text, ask **Gemini** to identify headings, and download an editable **.docx**. Basic local conversion works without an API key.

## How it works

PDF upload (Streamlit) → PyMuPDF text blocks → optional Gemini heading classification → python-docx → Word download.

**Important:** Gemini identifies only heading *IDs*. All wording comes from PyMuPDF, not from generated AI text. The output is an editable Word document, but complex layout, fonts and columns might not match the original PDF. Scanned PDFs are not supported.

## Setup: Windows PowerShell (inside VS Code)

1. Install Python 3.11 or newer (Python 3.13 is fine) and VS Code.
2. Open this folder in VS Code. Open **Terminal > New Terminal**.
3. Create a virtual environment:

   ```powershell
   py -3 -m venv .venv
   ```

4. Activate it:

   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```

   If PowerShell blocks activation, use `cmd` instead and run `.venv\Scripts\activate.bat`.

5. Install libraries:

   ```powershell
   python -m pip install -r requirements.txt
   ```

6. Obtain a Gemini key from <https://aistudio.google.com/api-keys>. Copy `.env.example` to `.env`, then replace the placeholder with your key (without quotation marks). Do not share or commit `.env`.

   ```powershell
   Copy-Item .env.example .env
   ```

7. Run:

   ```powershell
   python -m streamlit run app.py
   ```

8. Visit the localhost address shown (usually http://localhost:8501), upload a text PDF, click **Convert to Word**, and download the DOCX.

## No API key? 

Uncheck **Use Gemini AI to identify headings** to create a plain Word document with local PDF text extraction and no API requests.

## Files

- `app.py` - all the application code
- `requirements.txt` - Python libraries
- `.env.example` - API key template
- `.gitignore` - prevents committing secrets
- `sample_text.pdf` - a short example PDF for testing

## Troubleshooting

- **`py` not found**: Install Python from python.org and enable its PATH/launcher integration.
- **`No module named ...`**: Activate the virtual environment and reinstall requirements.
- **API key is missing**: Create `.env` with `GEMINI_API_KEY=...` next to `app.py`, restart Streamlit, or uncheck the Gemini option.
- **Gemini permission/quota error**: Verify model access and account limits in Google AI Studio; basic mode needs no API.
- **No selectable text found**: Use a PDF whose text can be highlighted/copied; this starter project does not perform OCR.
- **DOCX formatting differs**: This starter converter preserves text content, not pixel-perfect PDF layout.

## Privacy and usage

In AI mode, small text snippets from your uploaded document are sent to the Gemini API for heading identification. Do not upload confidential documents without authorization. The program handles PDF and DOCX in memory; it does not save uploaded documents to disk. API free tier availability and limits depend on your account and region.
=======
# Text_PDF_to_Word
This will convert the text pdf into a document.
>>>>>>> 9d8fe91e23be098a5575dcc9e368452ee908fbac
