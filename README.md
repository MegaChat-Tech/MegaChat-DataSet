# MegaChat: A Synthetic Persian Q&A Dataset for High-Quality Sales Chatbot Evaluation

<p align="center">
  <img src="heading.jpg" alt="MegaChat Dataset" width="100%">
</p>

---

## 📋 About

**MegaChat** is the first large-scale, fully synthetic Persian dataset designed for evaluating intelligent sales assistants in Telegram-based e-commerce environments. Generated using a novel multi-agent LLM architecture, this dataset addresses the critical gap in Persian language resources for conversational AI and sales chatbot development.

### Key Features

- 🤖 **Fully Synthetic Generation**: Multi-agent LLM architecture with no manual annotation required
- 👥 **Persona-Based Questions**: Realistic user queries reflecting diverse customer profiles
- 📊 **Multi-Domain Coverage**: 48 Telegram channels spanning a wide range of categories
- ✅ **Ground Truth Answers**: High-quality responses evaluated by GPT-5.1 as judge

### Statistics

| Metric | Value |
|--------|-------|
| **Telegram Channels** | 48 |
| **Total Posts Collected** | ~88,000 |
| **Product Categories** | A wide range of categories, including fashion, electronics, home goods, beauty, and other diverse consumer sectors |
| **Generated Q&A Pairs** | 137 (5 Channels) |
| **Language** | Persian (Farsi) |
| **Generation Method** | Fully Synthetic (LLM-Agent) |

---

## 📚 Dataset Description

### Data Collection Pipeline

The MegaChat dataset was constructed through a three-stage pipeline:

#### 1. **Telegram Channel Data Collection**
- Collected 5,000 most recent posts from 48 active Telegram shopping channels
- Automatic filtering to remove deleted posts and non-textual content
- Diverse domains

#### 2. **Multi-Agent Question Generation**
A sophisticated three-agent architecture generates realistic Persian questions:

- **Generator Agent**: Creates persona-aligned questions with natural typing patterns
- **Validator Agent**: Verifies authenticity against source channel data
- **Refiner Agent**: Enhances conversational naturalness and filters low-confidence outputs

**Design Principles:**
- Persona-driven generation reflecting authentic user motivations
- Data-grounded outputs verified against actual channel content
- Conversational authenticity with informal language and natural errors

#### 3. **Answer Generation & Ground Truth Selection**

Two parallel answer generation approaches:

**Classic RAG System:**
- FAISS vector stores with OpenAI text-embedding-3-large
- Top-5 retrieval based on cosine similarity
- Three LLM variants: GPT-4.1, GPT-4o, GPT-4-turbo

**Agentic Architecture:**
- Query expansion
- Parallel retrieval with re-ranking
- User profile analysis for personalized responses
- LLM-SLM collaboration for efficiency

**Ground Truth Selection:**
- GPT-5.1 as judge evaluating all candidate answers
- Ranking based on: factual correctness, persona alignment, emotional sensitivity, tone preference, interaction style, content preferences

### Sample Channels

| Channel | Posts | Questions | Domain |
|---------|-------|--------|--------|
| @LBASs2 | 3,148 | 22 | Men's & Women's Clothing |
| @nemo_shopir | 2,295 | 29 | Anime & Manga Products |
| @bargiTak | 1,779 | 33 | Personal & Home Electronics |
| @mahmoodikhanegi | 1,375 | 31 | Home Appliances & Bridal Items |
| @lbasTak2 | 881 | 22 | Children's Clothing |

---

## 📥 Download

### Dataset Files

The MegaChat dataset is released in two parts:

#### 1. Telegram Channel Posts (Raw Data)
Contains the original posts collected from 48 Telegram shopping channels.

**[📦 Download Channel Posts Dataset](https://drive.google.com/file/d/122c0JrHj_02TxuA9Az6P8Q5wTxtoLb6r)**


#### 2. Question-Answer Pairs
Contains generated questions with ground truth answers and metadata.

**[📦 Download Q&A Dataset](https://drive.google.com/file/d/11ugxQgz_ln2WnXvGApiJahJm0Uw6DxFP)**




---

## 🚀 Usage



### Use Cases

1. **Sales Chatbot Training**: Train Persian conversational AI models for e-commerce
2. **RAG System Evaluation**: Benchmark retrieval-augmented generation systems
3. **Persona-Based Response Generation**: Develop user-adaptive dialogue systems
4. **Persian NLP Research**: Advance Persian language understanding in commercial contexts
5. **Multi-Agent System Testing**: Evaluate agentic architectures for dialogue generation


---

## 📄 Citation

If you use the MegaChat dataset in your research, please cite our paper:

```bibtex
@article{MegaChat-DataSet,
  title={MegaChat: A Synthetic Persian Q\&A Dataset for High-Quality Sales Chatbot Evaluation},
  author={Rahmani, Mahdi and Saffari, AmirHossein and Rahmani, Reyhane},
  journal={arXiv preprint arXiv:XXXX.XXXXX},
  year={2025},
  url={https://arxiv.org/abs/XXXX.XXXXX},
  organization={Eastern Smart Innovators, Agentic AI Research Department}
}
```

**Paper:** [arXiv:XXXX.XXXXX](https://arxiv.org/abs/XXXX.XXXXX) *(Link to be updated)*

**Paper:** [researchgate.net](https://www.researchgate.net/publication/398084913_MegaChat_A_Synthetic_Persian_QA_Dataset_for_High-Quality_Sales_Chatbot_Evaluation)



---

## 📧 Contact

For questions, collaborations, or commercial inquiries:

- **Author:** 
- **Email:** Info@MegaChat.ir, MegaChat.Tech@gmail.com, Mahdi@MegaChat.ir, MahdiRahmani1375@gmail.com
- **Organization:** Eastern Smart Innovators (نوآوران هوشمندگستر شرق)
- **Website:** [ESmartInnovators.ir], [MegaChat.ir]

---


## 📜 License

### Code
This repository is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

### Dataset
The MegaChat dataset is licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

[![CC BY 4.0][cc-by-shield]][cc-by]

This means you are free to:
- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material for any purpose, even commercially

Under the following terms:
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made

For full license terms, see: https://creativecommons.org/licenses/by/4.0/

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg





---


<p align="center">
  Made with ❤️ for the Persian NLP Community
</p>

<p align="center">
  <sub>© 2025 Eastern Smart Innovators. Released under CC BY 4.0 License.</sub>
</p>
