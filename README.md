# Topic Modeling with Latent Dirichlet Allocation (LDA)

[![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📋 Overview

This project implements **Topic Modeling** using **Latent Dirichlet Allocation (LDA)** algorithm to discover hidden topics within a collection of NPR (National Public Radio) articles. The project demonstrates how to extract meaningful topics from text data without supervision and classify articles into discovered categories.

## 🎯 Key Features

- **Unsupervised Topic Discovery**: Automatically identify hidden topics in document collections
- **LDA Implementation**: Complete implementation using scikit-learn
- **Text Preprocessing**: Advanced text preprocessing with CountVectorizer
- **Topic Visualization**: Display top words for each discovered topic
- **Article Classification**: Assign topic labels to original articles
- **Comprehensive Analysis**: Detailed analysis of 11,992 NPR articles

## 🧠 What is Topic Modeling?

**Topic Modeling** is a Natural Language Processing (NLP) technique used to discover hidden topics or themes within large collections of text documents using unsupervised learning.

### 📌 Latent Dirichlet Allocation (LDA)

**LDA** is the most popular probabilistic algorithm for topic modeling that assumes:
- Each document contains a mixture of topics
- Each topic is characterized by a distribution of words

### Example:
If we have articles containing words like "cats", "dogs", "sun", "plants":
- **Topic 1**: Pets → (cats, dogs, play, love)
- **Topic 2**: Nature → (sun, plants, light, growth)

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas
pip install scikit-learn
pip install numpy
pip install matplotlib
pip install jupyter
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/mustafasamy28/Topic-Modeling-LDA.git
cd Topic-Modeling-LDA
```

2. **Install required packages**
```bash
pip install -r requirements.txt
```

3. **Launch Jupyter Notebook**
```bash
jupyter notebook Topic-Modeling-LDA.ipynb
```

## 📊 Dataset

The project uses NPR (National Public Radio) articles dataset containing:
- **11,992 articles** from npr.org
- **54,777 unique words** after preprocessing
- **Various topics**: Politics, Health, Business, Education, etc.

## 🔧 Methodology

### 1. Data Preprocessing
- **CountVectorizer** with stop words removal
- **max_df=0.95**: Ignore words appearing in >95% of documents
- **min_df=2**: Ignore words appearing in <2 documents

### 2. LDA Model Training
```python
LDA = LatentDirichletAllocation(n_components=7, random_state=42)
LDA.fit(dtm)
```

### 3. Topic Analysis
Extract top 15 words for each topic to understand themes:
- **Topic 0**: Business/Healthcare
- **Topic 1**: Politics/Government  
- **Topic 2**: Lifestyle/Culture
- **Topic 3**: Health/Medical
- **Topic 4**: Elections/Politics
- **Topic 5**: Entertainment/Music
- **Topic 6**: Education/Science

## 📈 Results

The model successfully identified **7 distinct topics** with clear thematic separation:

| Topic # | Theme | Top Words |
|---------|-------|-----------|
| 0 | Business/Health | companies, money, health, government, million |
| 1 | Politics/Security | military, security, trump, president, government |
| 2 | Lifestyle/Culture | family, home, food, city, people |
| 3 | Medical/Health | medical, patients, children, study, health |
| 4 | Elections | voters, election, obama, clinton, campaign |
| 5 | Entertainment | music, life, time, people, like |
| 6 | Education | student, university, schools, education, science |

## 💻 Code Structure

```
Topic-Modeling-LDA/
│
├── Topic-Modeling-LDA.ipynb    # Main notebook with complete analysis
├── npr.csv                     # NPR articles dataset
├── README.md                   # Project documentation
├── requirements.txt            # Python dependencies
└── LICENSE                     # MIT License
```

## 🔍 Key Functions

### Topic Discovery
```python
# Fit LDA model
LDA.fit(dtm)

# Get topic-word distributions
topics = LDA.components_

# Transform documents to topic space
topic_results = LDA.transform(dtm)
```

### Topic Analysis
```python
# Display top words per topic
for index, topic in enumerate(LDA.components_):
    print(f'Topic #{index}')
    top_words = [cv.get_feature_names_out()[i] for i in topic.argsort()[-15:]]
    print(top_words)
```

## 📚 Learning Outcomes

- Understanding of **unsupervised learning** in NLP
- Implementation of **LDA algorithm** using scikit-learn
- **Text preprocessing** techniques for topic modeling
- **Topic interpretation** and validation methods
- **Document classification** using discovered topics

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

**Mostafa Samy**
- Email: [mustafasamy28@gmail.com](mailto:mustafasamy28@gmail.com)
- GitHub: [@mustafasamy28](https://github.com/mustafasamy28)
- LinkedIn: [Mostafa Samy](https://www.linkedin.com/in/mostafa-samy-9b95711a7/)

## 🙏 Acknowledgments

- **NPR** for providing the article dataset
- **scikit-learn** community for the excellent LDA implementation
- **Pierian Data** for educational resources

---

⭐ If you found this project helpful, please give it a star!
