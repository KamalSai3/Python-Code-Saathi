# AI Code Assistant

## Project Overview
This project is an AI Code Assistant built with Python. Its primary goal is to help users solve coding problems by generating and executing Python code. The assistant provides solutions in the form of Python code and takes coding problems as input, similar to those found on platforms like LeetCode.

## Features
- Accepts coding problems via text or image upload (with OCR extraction)
- Uses large language models (LLMs) to generate Python solutions
- Executes generated code in a secure, cloud-based sandbox
- Displays extracted problem, generated code, and execution output or errors

## How It Works
1. **Input Reception**: User submits a coding problem as text or image.
2. **Image Processing**: If an image is uploaded, Pillow and PyTesseract extract the problem statement using OCR.
3. **Prompt Creation**: The problem statement is used to create a prompt for the LLM.
4. **LLM Interaction**: The Groq LLM (e.g., Meta's Llama 3.37B Versatile) generates Python code for the problem.
5. **Code Extraction**: Python code is extracted from the LLM's markdown response.
6. **Code Execution**: The code is executed in an E2B sandbox, capturing output or errors.
7. **Error Analysis**: If errors occur, the LLM explains them. All results are displayed to the user.

## Key Technologies
- **Python**
- **Flask** (web framework)
- **Pillow (PIL)** (image processing)
- **PyTesseract** (OCR)
- **Groq API** (LLM)
- **E2B Sandbox** (secure code execution)
- **dotenv** (environment variable management)

## Installation & Setup
1. **Clone the repository**
2. **Install Python dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
3. **Install Tesseract OCR (Windows):**
   - Download from [Tesseract OCR GitHub](https://github.com/tesseract-ocr/tesseract)
   - Add the install path (e.g., `C:\Program Files\Tesseract-OCR`) to your system PATH
4. **Set up API keys:**
   - Sign up for Groq and E2B, obtain API keys
   - Create a `.env` file in the project root:
     ```env
     GROQ_API_KEY=your_groq_api_key
     E2B_API_KEY=your_e2b_api_key
     ```

## Usage
1. **Run the Flask app:**
   ```bash
   python app.py
   ```
2. **Open your browser:** Go to [http://127.0.0.1:5000/](http://127.0.0.1:5000/)
3. **Submit a problem:** Type or upload an image, then click "Generate and Execute"
4. **View results:** See the extracted text, generated code, and output or error messages

## Security
- **Never commit your `.env` file or API keys to version control.**
- The `.gitignore` file is set up to exclude `.env`.

## License
This project is for educational and research purposes.
