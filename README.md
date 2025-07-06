# 🧬 PowerPoint Presentation Generator

This Python script leverages the **LLaMA 3.2** model (via a local [Ollama](https://ollama.ai/) server) to generate a **PowerPoint presentation** (`.pptx`) based on a biology lecture transcript and a PowerPoint template. The output is a 20-slide presentation saved as `test.pptx` using the `python-pptx` library.

---

## 📁 Features

- **Input**: Processes a biology lecture transcript and a PowerPoint template (`TemplatePro.pptx`).
- **Output**: Generates a 20-slide PowerPoint presentation with a title slide and 19 content slides, each with a topic and five detailed bullet points.
- **Slide Format**: Uses LLaMA to create a structured array of arrays, where each inner array contains a slide’s topic and five bullet points.
- **Dependencies**: Requires Python, `python-pptx`, and a local Ollama server with LLaMA 3.2.

---

## 📦 Requirements

Before running the script, ensure the following are installed:

### 🧠 Model Infrastructure
- [Ollama](https://ollama.ai/) with the LLaMA 3.2 model:
  ```bash
  ollama pull llama3.2
  ollama run llama3.2
  ```

### 🐍 Python Libraries
Install required packages:
  ```bash
  pip install requests python-pptx
  ```

### 📄 PowerPoint Template
- Provide a PowerPoint template file named `TemplatePro.pptx` with at least 20 slides, including a title slide and content slides with title and body placeholders.

---

## 🚀 Usage

1. Start the Ollama server locally on `http://localhost:11434`.
2. Ensure the PowerPoint template (`TemplatePro.pptx`) is in the script’s directory.
3. Insert your biology lecture transcript into the `prompt` field in the script (replace `{Transcript.txt}`).
4. Run the script:
   ```bash
   python pptx_generator.py
   ```

The script will:
- Query LLaMA 3.2 to generate a Python array of arrays for the slide content.
- Load the PowerPoint template and populate the title slide and 19 content slides.
- Save the output as `test.pptx`.

---

## 📄 Output

- **`test.pptx`**: A 20-slide PowerPoint presentation with a title slide and 19 content slides, each containing a topic and five bullet points.

### 🧬 Example Slide Blueprint
```python
[
  ["Introduction to Biology"],
  ["Cell Structure", "Cells are the basic unit of life.", "Prokaryotic cells lack a nucleus.", "Eukaryotic cells contain membrane-bound organelles.", "The cell membrane regulates material exchange.", "Mitochondria are the powerhouse of the cell."],
  ["DNA Replication", "DNA replication occurs during the S phase.", "Helicase unwinds the DNA double helix.", "DNA polymerase adds nucleotides to the new strand.", "Replication is semi-conservative.", "Errors in replication can lead to mutations."]
]
```

---

## 🛠️ Notes

- Replace `{Transcript.txt}` in the script with a valid biology lecture transcript.
- The script uses a low temperature (0.1) for deterministic LLaMA output.
- The PowerPoint template must have at least 20 slides with title and body placeholders.
- The script streams LLaMA’s response to handle large outputs efficiently.
- Ensure the template file (`TemplatePro.pptx`) is correctly formatted to avoid placeholder errors.

---

## 🔧 Troubleshooting

- **Ollama Error**: Confirm the Ollama server is running and LLaMA 3.2 is installed.
- **Template Error**: Verify `TemplatePro.pptx` exists and has the required slide layout (title and body placeholders).
- **Array Parsing Error**: Check the LLaMA output for valid Python array syntax to avoid `ast.literal_eval` failures.
- **PowerPoint Output Issues**: Ensure `python-pptx` is installed and the template has enough slides.

---

## 📜 License

MIT License. See `LICENSE` file for details.

---

✅ This file is fully Markdown compliant for GitHub.  
Let me know if you need help with `.gitignore`, a license file, or further customization!
