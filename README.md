# Summarization experimentation

on this page...
 - [Purpose](#purpose)
 - [Outcome](#outcome)
     - [Quality](#quality)
     - [Time](#time)
 - [Usage](#usage)
 - [Output](#output)

---


## Purpose

(This is very old early summarization-experimentation work.)

With upcoming Hall-Hoag work, wanted to explore summarization using a pretrained general large-language-model (LLM) for possible inclusion into processing-pipeline.

---


## Outcome

### Quality

__NOT SATISFIED.__ Most of my online research indicates that summarizers work by yielding representative excerpts. I got this code to do that; it now yields roughly a single representative sentence.

However, I didn't want 'excerpts' as summarization. The current code, for the Obama first inaugural speech, yields:
```
SUMMARIZATION-EXCERPT, ``I want to thank every American who participated in this election, whether you voted for the very first time or waited in line for a very long time.``
```

What I wanted was something more like: "Summary: The person describes thanking voters, and thanking opponents, and expresses hope for the future. It touches on themes of..." That's _why_ I tried this with an LLM. I'm pretty new at this, there are very likely combinations of models and settings I could use/tweak to do this.

Eventually! 🙂

### Time

This could _easily_ be something I'm not optimizing, but the summarization is _slow_. Running it on my Mac M1-Pro on either of the two test-files processes about 30-40 words-per-second.

---


## Usage

(assumes `uv` is installed: <https://docs.astral.sh/uv/getting-started/installation/>)

`$ cd /path/to/llm_summarizer_code/`

Then...

`$ uv run ./summarizer.py  # will auto-run summarizer on the two test-files (be patient!)`

...or...

`$ uv run ./summarizer.py  --input_path "/path/to/target_file.txt"`

---


## Output

```
HHoag OCRed summarization ------------------------
[05/Dec/2025 12:43:47] DEBUG [summarizer-load_input_text()::69] word_count, ``2462``
[05/Dec/2025 12:44:57] INFO [summarizer-manage_summarization()::29] SUMMARIZATION-EXCERPT, ``“1313” swarms with an executive elite, including NML, who sit on each others boards, commissions, committees and secretariats.``

Obama speech ----------------------------------------
[05/Dec/2025 12:45:01] DEBUG [summarizer-load_input_text()::69] word_count, ``2156``
[05/Dec/2025 12:45:50] INFO [summarizer-manage_summarization()::29] SUMMARIZATION-EXCERPT, ``I want to thank every American who participated in this election, whether you voted for the very first time or waited in line for a very long time.``
```

---

keywords: hall-hoag, hh, summarization

---
