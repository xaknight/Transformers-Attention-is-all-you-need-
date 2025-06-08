---

# Transformers from Scratch — "Attention Is All You Need"

This repository contains a complete implementation of the Transformer architecture introduced in the paper ["Attention is All You Need"](https://arxiv.org/abs/1706.03762). Built using Python, PyTorch, and NumPy, the model is trained for an English-Hinglish translation task and achieves over 80% accuracy on a dataset of more than 180,000 labeled examples.

## Key Features

- Full Transformer architecture implemented from scratch using PyTorch.
- Trained on a real-world English-Hinglish translation dataset.
- Integrated **Grouped Multi-Query Attention (MQA)** and **Key-Value (KV) Caching**, inspired by the LLaMA architecture:
  - Reduced model size by 25%
  - Improved inference time by 20%
- Switched from character-level to **subword tokenization** using Hugging Face's tokenizer:
  - Increased translation accuracy from 70–75% to 80–85%

## Technology Stack

- **Language**: Python
- **Core Libraries**:
  - PyTorch – deep learning framework
  - NumPy – numerical computation
  - Hugging Face Tokenizers – fast and flexible tokenization

## Performance Summary

| Component                  | Baseline                | Optimized Version            | Improvement       |
|---------------------------|-------------------------|------------------------------|-------------------|
| Translation Accuracy      | 70–75% (char-level)     | 80–85% (subword tokenizer)   | +10%              |
| Model Size                | Standard Transformer    | With Grouped MQA & KV Cache  | -25%              |
| Inference Time            | Standard Transformer    | With KV Cache                | -20%              |
| Retrieval Search Time     | Naive Search            | FAISS Indexing               | -40%              |

## Project Structure

```
.
├── data.py             # data loading logics
├── models/             # Transformer model and attention modules
├── paper/              # Hugging Face tokenizer code and config
├── util/               # Training loop and logic
├── evaluate.py         # Evaluation and inference
├── conf.py             # Model and training configuration
└── README.md           # Project documentation
```

## Future Work

- Add support for advanced decoding techniques (beam search, top-k sampling)
- Experiment with alternative positional embeddings (e.g., RoPE, ALiBi)
- Provide pretrained model checkpoints and inference script
- Add interactive notebook/demo for quick testing

## License

This project is licensed under the MIT License.

## Contribution

Contributions are welcome. If you'd like to add improvements or report issues, feel free to open a pull request or raise an issue.

---
