Applied Learning Assignment (Seq2Seq & Multilingual NLP)Applied Learning Assignment (Seq2Seq & Multilingual NLP)

# Applied-Learning-Assignment-Seq2Seq-Multilingual-NLP

#### Project Overview
This project addresses the challenge of leveraging state-of-the-art sequence-to-sequence models for natural language processing tasks, specifically text summarization and multilingual machine translation. The rapid growth of textual data and the increasing need for cross-lingual communication necessitate robust and efficient NLP solutions. This assignment explores the capabilities of Transformer-based models, T5 and mT5, which are highly effective for these tasks.

The **overall goal** of this assignment is twofold: first, to demonstrate the fine-tuning of a T5 model for an English-centric summarization task; and second, to fine-tune an mT5 model for multilingual translation, focusing on a low-resource language pair (English-Yoruba), thereby showcasing the models' adaptability and performance in diverse linguistic contexts.

### Part A — Research: T5 vs. mT5 vs. BART (summary + differences)

#### summary (one paragraph)

T5 is a text-to-text Transformer that frames every NLP problem as text-in → text-out and was pre-trained on a massive English web corpus (C4), achieving strong results across tasks such as summarization and QA. mT5 is a multilingual variant of T5 pre-trained on mC4 (Common Crawl-derived corpus spanning 101 languages) and is designed to work well across many languages and multilingual benchmarks. BART is a denoising autoencoder sequence-to-sequence model (bidirectional encoder + autoregressive decoder) pre-trained by corrupting text and learning to reconstruct originals — it performs very strongly on generation tasks like summarization and dialogue.

#### Key differences (table-like bullets)

**Model family & training objective**

T5: Text-to-text unified objective (span-corruption style pretraining tasks & large-scale supervised fine-tuning approach). Pretrained on the English C4 dataset.

mT5: Same text-to-text recipe adapted to multilingual data (mC4) covering 101 languages; aims to reduce design changes from T5 but scale multilingually. Good for cross-lingual or multilingual tasks.

BART: Denoising autoencoder for seq2seq — corrupt text then reconstruct. Great at abstractive generation and tasks requiring strong generative decoders.

**Best use cases**

T5: Summarization, translation (English-centric), multi-task text transformations (prompt prefix like summarize:).

mT5: Multilingual summarization/translation/generation across many languages; good zero-shot multilingual transfer.

BART: Abstractive summarization, dialogue generation, machine translation fine-tuning, and text generation tasks that benefit from strong decoder capacity.

**Tokenization & vocabulary**

T5/mT5 uses SentencePiece and has model-specific vocabularies (mT5’s vocab covers many languages). BART models typically use byte-level BPE (in Hugging Face pretrained checkpoints).

### Practical notes

If working only in English and focusing on summarization, T5 or BART is strong — BART often produces very competitive abstractive summaries; T5 is flexible with task prefixes.

For multilingual tasks or low-resource languages, prefer mT5 (or mBART) since they were trained on multilingual corpora and often transfer better.

### Part B — Applied Learning Assignment 1 (deliverables & code)

**Task 1: Research summary** (done above)
**Task 2: Key differences** (done above)
**Task 3: Prepare a dataset suitable for a summarization task using T5**
Dataset format (CSV / JSONL)

Creating a CSV (or JSONL) with two columns: text and summary. Example CSV rows:
