# MegaChat Dataset

<p align="center">
  <img src="heading.jpg" alt="MegaChat Dataset" width="100%">
</p>

<p align="center">
  <strong>A Synthetic Persian Q&A Dataset for High-Quality Sales Chatbot Evaluation</strong>
</p>

<p align="center">
  <a href="#about">About</a> •
  <a href="#dataset-description">Dataset</a> •
  <a href="#download">Download</a> •
  <a href="#usage">Usage</a> •
  <a href="#citation">Citation</a> •
  <a href="#license">License</a>
</p>

---

## 📋 About

**MegaChat** is the first large-scale, fully synthetic Persian dataset designed for evaluating intelligent sales assistants in Telegram-based e-commerce environments. Generated using a novel multi-agent LLM architecture, this dataset addresses the critical gap in Persian language resources for conversational AI and sales chatbot development.

### Key Features

- 🇮🇷 **First Persian Sales Chatbot Dataset**: Specifically designed for Telegram-based Iranian SMEs
- 🤖 **Fully Synthetic Generation**: Multi-agent LLM architecture with no manual annotation required
- 👥 **Persona-Based Questions**: Realistic user queries reflecting diverse customer profiles
- 📊 **Multi-Domain Coverage**: 48 Telegram channels across fashion, electronics, home goods, and beauty
- ✅ **Ground Truth Answers**: High-quality responses evaluated by GPT-5 as judge
- 🔄 **Dual Architectures**: Comparison between Classic RAG and Agentic systems

### Statistics

| Metric | Value |
|--------|-------|
| **Telegram Channels** | 48 |
| **Total Posts Collected** | ~240,000 |
| **Product Categories** | Fashion, Electronics, Home Goods, Beauty, Children's Items |
| **Generated Q&A Pairs** | [To be updated] |
| **Language** | Persian (Farsi) |
| **Generation Method** | Fully Synthetic (LLM-Agent) |

---

## 📚 Dataset Description

### Data Collection Pipeline

The MegaChat dataset was constructed through a three-stage pipeline:

#### 1. **Telegram Channel Data Collection**
- Collected 5,000 most recent posts from 48 active Telegram shopping channels
- Automatic filtering to remove deleted posts and non-textual content
- Diverse domains: fashion, electronics, home appliances, anime merchandise, children's clothing

#### 2. **Multi-Agent Question Generation**
A sophisticated three-agent architecture generates realistic Persian questions:

- **Generator Agent**: Creates persona-aligned questions with natural typing patterns
- **Validator Agent**: Verifies authenticity against source channel data
- **Refiner Agent**: Enhances conversational naturalness and filters low-confidence outputs

**Design Principles:**
- Persona-driven generation reflecting authentic user motivations
- Data-grounded outputs verified against actual channel content
- Conversational authenticity with informal language and natural errors
- Confidence-based filtering (threshold: 50%)

#### 3. **Answer Generation & Ground Truth Selection**

Two parallel answer generation approaches:

**Classic RAG System:**
- FAISS vector stores with OpenAI text-embedding-3-large
- Top-5 retrieval based on cosine similarity
- Three LLM variants: GPT-4.1, GPT-4o, GPT-4-turbo

**Agentic Architecture:**
- Query expansion (5-8 diverse search queries)
- Parallel retrieval with re-ranking
- User profile analysis for personalized responses
- LLM-SLM collaboration for efficiency

**Ground Truth Selection:**
- GPT-5 as judge evaluating all candidate answers
- Ranking based on: factual correctness, persona alignment, emotional sensitivity, tone preference, interaction style, content preferences

### Sample Channels

| Channel | Posts | Domain |
|---------|-------|--------|
| @LBASs2 | 3,148 | Men's & Women's Clothing |
| @nemo_shopir | 2,295 | Anime & Manga Products |
| @bargiTak | 1,779 | Personal & Home Electronics |
| @mahmoodikhanegi | 1,375 | Home Appliances & Bridal Items |
| @lbasTak2 | 881 | Children's Clothing |

---

## 📥 Download

### Dataset Files

The MegaChat dataset is released in two parts:

#### 1. Telegram Channel Posts (Raw Data)
Contains the original posts collected from 48 Telegram shopping channels.

**[📦 Download Channel Posts Dataset](LINK_TO_BE_ADDED)**

**File Format:** JSON  
**Size:** [To be updated]  
**Contents:** 
- Channel metadata
- Post text content
- Timestamps
- Channel categories

#### 2. Question-Answer Pairs
Contains generated questions with ground truth answers and metadata.

**[📦 Download Q&A Dataset](LINK_TO_BE_ADDED)**

**File Format:** JSON  
**Size:** [To be updated]  
**Contents:**
- User questions (persona-based)
- Ground truth answers
- User persona profiles
- Source channel information
- Confidence scores
- Answer generation metadata

### Data Format

```json
{
  "question_id": "unique_identifier",
  "question": "سلام، این مانتو به رنگ مشکی موجوده؟",
  "channel_id": "@LBASs2",
  "user_persona": {
    "demographics": {...},
    "preferences": {...},
    "purchase_behavior": {...}
  },
  "ground_truth_answer": "سلام! بله عزیزم، این مانتو در رنگ مشکی موجود هست...",
  "candidate_answers": [...],
  "generation_metadata": {...}
}
```

---

## 🚀 Usage

### Loading the Dataset

```python
import json

# Load channel posts
with open('megachat_channels.json', 'r', encoding='utf-8') as f:
    channels_data = json.load(f)

# Load Q&A pairs
with open('megachat_qa.json', 'r', encoding='utf-8') as f:
    qa_data = json.load(f)

print(f"Total channels: {len(channels_data)}")
print(f"Total Q&A pairs: {len(qa_data)}")
```

### Use Cases

1. **Sales Chatbot Training**: Train Persian conversational AI models for e-commerce
2. **RAG System Evaluation**: Benchmark retrieval-augmented generation systems
3. **Persona-Based Response Generation**: Develop user-adaptive dialogue systems
4. **Persian NLP Research**: Advance Persian language understanding in commercial contexts
5. **Multi-Agent System Testing**: Evaluate agentic architectures for dialogue generation

### Baseline Models

We provide baseline results comparing Classic RAG and Agentic architectures. See our paper for detailed evaluation metrics.

---

## 📄 Citation

If you use the MegaChat dataset in your research, please cite our paper:

```bibtex
@article{megachat2025,
  title={MegaChat: A Synthetic Q\&A Dataset for High-Quality Sales Chatbot Evaluation},
  author={[Your Name] and [Co-authors]},
  journal={arXiv preprint arXiv:XXXX.XXXXX},
  year={2025},
  url={https://arxiv.org/abs/XXXX.XXXXX}
}
```

**Paper:** [arXiv:XXXX.XXXXX](https://arxiv.org/abs/XXXX.XXXXX) *(Link to be updated)*

---

## 🤝 Contributing

We welcome contributions to improve the dataset! If you:

- Find errors or inconsistencies
- Have suggestions for improvements
- Want to extend the dataset to new domains
- Develop baseline models

Please open an issue or submit a pull request.

---

## 📧 Contact

For questions, collaborations, or commercial inquiries:

- **Author:** [Your Name]
- **Email:** [your.email@domain.com]
- **Organization:** eSmart Innovators (نوآوران هوشمندگستر شرق)
- **Website:** [Your website or company website]

---

## 🙏 Acknowledgments

This dataset was developed at:
- **University of Kashan** - Department of Computer Engineering
- **eSmart Innovators** - North Khorasan Science and Technology Park

Special thanks to the Iranian SME community on Telegram for providing the foundation for this research.

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

## 📊 Dataset Statistics & Visualizations

### Channel Distribution
![Channel Distribution](images/channel_distribution.png)
*Distribution of collected posts across 48 Telegram channels*

### Question Generation Pipeline
![Pipeline](images/pipeline.png)
*Multi-agent architecture for synthetic Q&A generation*

---

## 🔬 Related Work

### Persian Dialogue Datasets
- **PerSHOP** (2024): First Persian shopping dialogue dataset using crowdsourcing
- **MegaChat** (2025): First fully synthetic Persian sales Q&A dataset

### Multi-Domain Dialogue Datasets
- **MultiWOZ 2.2** (2020): English task-oriented dialogue
- **SalesBot 2.0** (2023): Synthetic sales conversations
- **MG-ShopDial** (2023): Multi-goal e-commerce dialogues

See our paper for comprehensive comparison.

---

## 🌟 Star History

If you find this dataset useful, please consider giving it a star ⭐!

[![Star History Chart](https://api.star-history.com/svg?repos=YOUR_USERNAME/megachat-dataset&type=Date)](https://star-history.com/#YOUR_USERNAME/megachat-dataset&Date)

---

<p align="center">
  Made with ❤️ for the Persian NLP Community
</p>

<p align="center">
  <sub>© 2025 eSmart Innovators. Released under CC BY 4.0 License.</sub>
</p>
