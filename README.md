# Hero Adventure — Localization Translator

A single-file web tool for translating **Hero Adventure** (Wuxia/RPG mobile game) text files into **Indonesian**, using the Mimo AI API for translation.

It's built to work directly with the `.xlsx` mod files found in:
```
ModEditor/Assets/GameRes/xls/3
```

## What it does

- Upload one or multiple `.xlsx` files (or a whole folder) extracted from the game's ModEditor assets.
- Automatically scans every row/column and detects which text cells contain English game text that needs translating (skipping cells that are already in Indonesian, IDs, stat abbreviations like HP/MP/ATK/DEF, proper nouns, etc.).
- Sends the detected text in batches to the **Mimo API** for translation, using a system prompt tuned for game RPG/Wuxia terminology.
- Lets you preview "before → after" results in a table, with search and filtering.
- Exports the translated `.xlsx` files, ready to drop back into the mod folder.

## Requirements

- A **Mimo API key** — get one at [platform.xiaomimimo.com](https://platform.xiaomimimo.com). The model used (`mimo-v2.5`) is very cheap, so a couple of dollars is enough to translate tens of thousands of lines.
- Any modern browser. No installation, no build step — it's a single HTML file.

## How to use

1. Open `hero-adventure-translator.html` in your browser.
2. Paste in your Mimo API key.
3. Upload the `.xlsx` files from `ModEditor/Assets/GameRes/xls/3`.
4. Run the translation and review the results.
5. Export and replace the original files in your game mod folder.

## Want a different target language?

This tool is currently hardcoded for **English → Indonesian**, including the system prompt and the logic that detects "already translated" text.

If you want to localize into another language, the easiest way is to open the HTML file in an AI coding assistant (e.g. Claude, ChatGPT) and ask it to:
- change the translation system prompt to your target language, and
- update the "already translated" detection logic to match that language instead of Indonesian.

It's a single, fairly small file, so this kind of edit is quick for an AI to do.

## Disclaimer

This is a fan-made community tool, not affiliated with the developers of Hero Adventure. Use at your own risk and always keep backups of your original game files before overwriting them.
