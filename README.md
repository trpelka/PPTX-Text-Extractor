# PowerPoint Text Extractor

A Python utility for extracting text and table content from PowerPoint presentations and saving the results as a structured plain-text file.

The script is designed to run in Google Colab and provides a simple upload, extraction, and download workflow.

## Features

* Upload a PowerPoint presentation directly in Google Colab
* Extract text from text boxes, placeholders, and other text-containing shapes
* Extract content from PowerPoint tables
* Organize extracted content by slide number
* Save extracted content as a `.txt` file
* Preserve table rows using a simple pipe-delimited format
* Count the total number of extracted words
* Report the total number of slides processed
* Automatically download the resulting text file
* Save output using UTF-8 encoding

## How It Works

The script:

1. Installs the `python-pptx` package.
2. Prompts the user to upload a PowerPoint file.
3. Identifies the uploaded presentation.
4. Opens the presentation using `python-pptx`.
5. Processes each slide individually.
6. Extracts text from slide shapes.
7. Extracts content from tables.
8. Writes the extracted content to a text file.
9. Counts the extracted words.
10. Reports the number of slides and words processed.
11. Downloads the resulting text file.

## Example Output

The extracted content is organized by slide:

```text
============================================================
SLIDE 1
============================================================

Introduction

This presentation provides an overview of...

============================================================
SLIDE 2
============================================================

Market Overview

Company | Revenue | Growth
Company A | $10M | 12%
Company B | $8M | 9%

============================================================
SLIDE 3
============================================================

Conclusion

The results indicate that...
```

## Use Cases

The extracted text can be used for:

* Reviewing presentation content as plain text
* Searching presentation content
* Document analysis
* Preparing presentation content for further processing
* Text and NLP workflows
* Summarization
* Building searchable document collections
* Preparing presentation content for RAG or other downstream workflows

## Requirements

* Python 3.x
* `python-pptx`
* Google Colab

The script installs the required package automatically in Google Colab:

```python
!pip -q install python-pptx
```

For local Python environments, install the package separately:

```bash
pip install python-pptx
```

## Input

The script checks for uploaded files with the following extensions:

* `.pptx`
* `.ppt`

`python-pptx` is designed primarily for `.pptx` files. Older `.ppt` files may need to be converted to `.pptx` before processing.

## Output

The output file uses the original presentation filename followed by `_ALL_TEXT.txt`.

For example:

```text
presentation.pptx
```

produces:

```text
presentation_ALL_TEXT.txt
```

The script also reports the number of slides and extracted words:

```text
Done!
Slides: 12
Words extracted: 3,482
Output: presentation_ALL_TEXT.txt
```

## Text Extraction

The script extracts text from PowerPoint shapes that expose text content, including common text boxes, placeholders, titles, and body text.

## Table Extraction

Tables are processed separately and written as pipe-delimited rows:

```text
Product | Revenue | Growth
Product A | $12M | 15%
Product B | $8M | 11%
```

## Limitations

The current version extracts text and table content only. It does not extract:

* Text embedded in images
* OCR content
* Speaker notes
* Chart data as structured data
* Audio
* Video
* Animations
* Images
* Slide formatting or visual layout

## Possible Extensions

Future versions could include:

* Speaker-note extraction
* OCR for image-based text
* JSON or Markdown output
* CSV export for tables
* Batch processing of multiple presentations
* Command-line usage
* PowerPoint metadata extraction
* Improved structure preservation
* Document chunking
* Integration with search or retrieval workflows

## License

MIT License
