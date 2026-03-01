# QLoRA Fine-Tuning with Unsloth (Qwen2.5-7B)

This project demonstrates parameter-efficient fine-tuning of
**Qwen2.5-7B-Instruct** using **QLoRA (4-bit quantization)** with
**Unsloth** on Google Colab (T4 GPU).

## ✅ What This Project Includes

-   Train / Validation / Test split
-   Training & validation loss tracking
-   Test perplexity before vs after fine-tuning
-   Qualitative generation comparison

------------------------------------------------------------------------

## 🧠 Model & Method

-   Base Model: Qwen2.5-7B-Instruct
-   4-bit quantization (bitsandbytes)
-   LoRA adapters (rank 8--16)
-   1 epoch fine-tuning
-   Weight decay for regularization

Frameworks used: - Unsloth - Hugging Face Transformers - TRL
(SFTTrainer)

------------------------------------------------------------------------

## 📊 Evaluation

Metrics: - Cross-Entropy Loss - Perplexity = exp(loss)

Example result:

  Model        Test Perplexity
  ------------ -----------------
  Base Model   91.7
  Fine-Tuned   74.4

Lower perplexity indicates improved alignment with the target
distribution.

------------------------------------------------------------------------

## 🧪 Before vs After Example

Prompt:

> Write a LinkedIn post about burnout in startups.\
> 5--8 lines. No emojis. End with a question.

After fine-tuning: - More consistent structure - Stronger stylistic
alignment - Clear reflective closing

------------------------------------------------------------------------

## 💻 Hardware

Tested on Google Colab T4 (15GB VRAM) using: - 4-bit quantization -
Gradient accumulation - Runtime restart for safe inference

------------------------------------------------------------------------

## 🎯 Key Takeaways

-   Practical QLoRA fine-tuning on consumer GPU
-   Proper evaluation workflow
-   Overfitting detection via loss curves
-   Quantitative + qualitative comparison
