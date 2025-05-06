# English–Telugu Machine Translation with Prosody Features

This project investigates how incorporating **prosody features** from speech into neural machine translation (NMT) models can improve English-to-Telugu translation, particularly in disambiguating meaning and improving fluency.

---

## 📁 Notebooks Overview

### `data.ipynb`
- Loads and preprocesses the **FLEURS** dataset.
- Prepares parallel English–Telugu sentence pairs for translation.

### `MT.ipynb`
- Implements a **baseline GRU encoder-decoder** model.
- Trains on text-only sentence pairs from **LJ Speech**.

### `MT_attention.ipynb`
- Adds an **attention mechanism** to the baseline GRU encoder-decoder.
- Improves handling of longer sentences and better aligns source and target.

### `MFA.ipynb`
- Uses **Montreal Forced Aligner (MFA)** to align audio with text.
- Extracts vowel timestamps and other durations for **prosody feature generation**.

### `MT_prosody.ipynb`
- Loads 19-dimensional **prosody features** generated from aligned audio.
- **Concatenates** these features to token embeddings in the encoder.
- Retrains the encoder-decoder model and evaluates performance.
- Shows **subtle but meaningful improvements** in translation quality—especially in cases of punctuation, word sense disambiguation, and emphasis.

---

## 🚀 Workflow

1. Align audio using `MFA.ipynb` and extract prosody features.
2. Preprocess text with `data.ipynb`.
3. Train:
   - Baseline: `MT.ipynb`
   - Attention model: `MT_attention.ipynb`
   - Prosody-enhanced model: `MT_prosody.ipynb`
4. Evaluate using BLEU score and qualitative comparisons.

---

## 📈 Evaluation

- **Metric**: ROUGE score with smoothing

---

## 🛠️ Dependencies

```bash
pip install torch pandas sentencepiece nltk
