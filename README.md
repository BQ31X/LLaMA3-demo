# LLaMA 3.1 Summarization Model – FlamingNeuron

This repository contains the example notebook and usage instructions for a fine-tuned LLaMA 3.1 model trained to generate concise summaries using Meta-style structured prompts.

🧠 **Model on Hugging Face:**  
[FlamingNeuron/llama381binstruct_summarize_short_merged](https://huggingface.co/FlamingNeuron/llama381binstruct_summarize_short_merged)

📓 **Example Notebook:**  
FlamingNeuron_ModelTest_20250418.ipynb  
(You can open this notebook directly in Google Colab to test the model.)

## About This Model

- **Base Model**: `NousResearch/Meta-Llama-3.1-8B-Instruct`
- **Adapter Training**: LoRA via `peft` + `trl`
- **Task**: Legal-style text summarization via structured dialogue format
- **Deployment**: Merged model uploaded to Hugging Face

## Training Procedure

This model was trained using Supervised Fine-Tuning (SFT) on a legal document summarization dataset. LoRA adapters were applied during training using the PEFT library, and the final model was produced by merging the adapters into the base model using PEFT’s `merge_and_unload()` method.

## Prompt Format

The model expects input in the following format:

```json
{
  "original_text": "The license allows personal use only. Redistribution requires explicit permission.",
  "reference_summary": ""
}
```

## How to Use

Open the notebook in Colab and run all cells. It will:

- Load the merged model from Hugging Face
- Format and send prompts
- Display the generated summary

> 📌 **Note:** For best performance, use a GPU-backed runtime (e.g., A100 via Colab Pro).

## Framework Versions

- TRL: 0.16.1
- Transformers: 4.51.3
- PyTorch: 2.6.0+cu124
- Datasets: 3.5.0
- Tokenizers: 0.21.1

## Citations

This model was fine-tuned using TRL.

## Legal Notice

This project builds on Meta’s LLaMA 3.1 architecture and is subject to the LLaMA 3.1 Community License. All use must comply with Meta’s acceptable use policy.

The model was fine-tuned using a `legal_summarization` dataset for research and educational purposes only.

This project is not intended for commercial use beyond the limitations described in the Meta license (e.g., more than 700M monthly active users).

## Credits & Tools

- Fine-tuned using Google Colab Pro, Hugging Face PEFT, and Weights & Biases
- Developed by [@BQ31X](https://github.com/BQ31X) (GitHub), and `FlamingNeuron` (Hugging Face)

---
