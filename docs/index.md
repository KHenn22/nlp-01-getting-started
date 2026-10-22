# Web Mining and Applied NLP Project Report

Web Mining and Applied NLP | Project 01 | Example Report

## Overview

This project establishes a professional Python environment
for acquiring and analyzing text from web pages.

The objective is to demonstrate that a Python project can
retrieve web content, extract text, compute word frequencies,
and produce visualizations using a reproducible workflow.

## Tools and Methods

The project uses:

- Python for text acquisition and analysis.
- Requests for retrieving HTML from web pages.
- BeautifulSoup for parsing HTML and extracting text.
- Polars for computing word frequencies.
- Matplotlib for frequency visualizations.
- WordCloud for visual exploration of vocabulary.
- Logging for execution records.
- Ruff, ty, and pytest for code verification.
- Zensical and GitHub Pages for published documentation.

The example script retrieves a Wikipedia article,
extracts text, cleans words,
and calculates token frequencies.

The analysis produces a frequency bar chart
and a word cloud.

## Verification

A successful execution displays:

    Pipeline executed successfully!

The script records execution details in a project log.

These results demonstrate that the environment can
retrieve, process, and visualize web text.

Automated tests provide additional verification
of the project's expected behavior.

## Interpretation

Web text contains both useful information and noise
introduced by document structure and formatting.

Simple text cleaning and frequency analysis
provide an initial view of a document's vocabulary.

These techniques establish a foundation
for later work involving text preprocessing,
corpus exploration, and natural language processing.
S
## Custom Modifications
**What changed:** In `src/nlp/web_words.py`, the `url` now points to the Wikipedia article on [Air traffic control](https://en.wikipedia.org/wiki/Air_traffic_control) instead of Natural language processing.
**Why:** To test whether word frequency analysis captures the topic of a different article.
**Prediction:** If I change the page to Air traffic control, I expect aviation words like "aircraft," "traffic," "control," and "airspace" to replace "language" and "processing" at the top, because word frequencies reflect the article's topic. Filler words like "that," "with," and "from" should stay. "air" won't appear, because the filter drops words of 3 letters or fewer.
**Result:** The top words became control (117), traffic (96), airport (51), aircraft (50), aviation (46), and flight (42). "airspace" did not make the top 10, but "airport," "tower," and "civil" did. "from" (40) stayed in the top 10, and Wikipedia noise like "retrieved" (33) remained.
**Surprise:** "air" and "atc" still appear in the word cloud. The script checks each word's length before stripping punctuation, so "air," and "(ATC)" pass the filter and are then stripped. Plain "air" is dropped, so it is heavily undercounted.
**What I learned:** Changing the input changes the vocabulary, but the cleaning rules carry over, so filler words and Wikipedia markup show up on any page. Stripping punctuation before filtering and removing common filler words would improve the results.

## Documentation Index

- **Home** - this landing page
- [**Project Instructions**](project-instructions.md)
- [**Glossary**](glossary.md)

## Project Links

- [GitHub Repository](https://github.com/KHenn22/nlp-01-getting-started)
- [Example Script](https://github.com/KHenn22/nlp-01-getting-started/blob/main/src/nlp/web_words.py)
- [Example Notebook](https://github.com/KHenn22/nlp-01-getting-started/blob/main/notebooks/web_words.ipynb)

## Project Resources

- [Project Instructions](project-instructions.md)
- [Professional Python Guide](https://denisecase.github.io/pro-analytics-02/)
- [Professional Python Project Explainer](https://pup-pack.github.io/professional-python-project-explainer/)
