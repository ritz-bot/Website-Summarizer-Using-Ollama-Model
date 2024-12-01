# Website-Summarizer-Using-Ollama-Model


This repository contains a Python project that uses the **Ollama model** to summarize website content. By providing a website URL, the script extracts the page's textual content, sends it to the Ollama model for summarization, and returns a concise summary in markdown format.

## Features

- Extracts content from any publicly accessible website using `BeautifulSoup`.
- Summarizes the content using the Ollama model via its API.
- Ignores non-textual elements like navigation, images, and scripts for cleaner results.
- Displays the summary in markdown format for easy readability.

## Requirements

Before running the script, ensure you have the following:

1. **Python 3.8+**
2. The following Python libraries:
   - `requests`
   - `beautifulsoup4`
   - `ollama`
   - `IPython` (for displaying markdown in notebooks)

3. **Ollama**:
   - Install and run the Ollama server:
     ```bash
     brew install ollama
     ollama serve
     ```
   - Pull the required model (e.g., `llama3.2`):
     ```bash
     ollama pull llama3.2
     ```

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/ritz-botwebsite-summarizer.git
   cd website-summarizer
   ```

2. Install the required Python libraries:
   ```bash
   pip install -r requirements.txt
   ```

3. Start the Ollama server:
   ```bash
   ollama serve
   ```

## Usage

1. Open the `Olamasummary.ipynb` notebook in Jupyter or any compatible editor.

2. Ensure the Ollama server is running and the required model is available.

3. Run the following function with a desired website URL:
   ```python
   summarize_website("https://example.com")
   ```

4. The script will:
   - Extract the website's title and main content.
   - Send the content to the Ollama model for summarization.
   - Display the summarized output in markdown format.

## Example

### Input:
```python
summarize_website("https://example.com")
```

### Output:
```markdown
### Summary of Example Website

This website discusses the latest trends in technology, focusing on AI advancements in 2024. Key topics include...
```

## Code Overview

### Main Components

- **`Website` class**:
  Extracts website content using `requests` and `BeautifulSoup`.

- **`messages_for` function**:
  Prepares the input prompts for the Ollama model.

- **`summarize_website` function**:
  Combines the content extraction and API call to generate a summary.

### Error Handling
The script includes basic error handling for:
- Invalid URLs
- Network issues
- Unexpected API responses

## Troubleshooting

- **Error: 'ChatResponse' object has no attribute 'content'**
  Ensure the Ollama server is running and the model is pulled correctly.

- **Error: Unable to fetch website content**
  Verify that the URL is correct and publicly accessible.

## Future Enhancements

- Add support for handling different languages.
- Enhance navigation filtering for more accurate content extraction.
- Deploy the project as a web application for broader accessibility.



Contributions are welcome! Feel free to open issues or submit pull requests.
