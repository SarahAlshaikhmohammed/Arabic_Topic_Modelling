
# Arabic Topic Modelling

This project demonstrates how to perform topic modeling on Arabic business-related texts using the Latent Dirichlet Allocation (LDA) algorithm. It utilizes libraries like `gensim`, `nltk`, and `pyarabic` to preprocess the text and extract key topics.

## Features

- Preprocesses Arabic text by tokenizing and removing stopwords.
- Implements topic modeling using the LDA algorithm.
- Extracts and displays the top words associated with each topic.

## Installation

To use this project, you need to install the required libraries. You can do so using the following commands:

```bash
pip install gensim nltk pyarabic matplotlib pyLDAvis
```

## How to Use

1. Clone or download this repository.
2. Replace the sample Arabic documents with your own text data.
3. Run the script to preprocess the text and perform topic modeling.
4. The script will display the top words for each identified topic.

### Example:

```python
# Sample Data
documents = [
    "الذكاء الاصطناعي يحلل البيانات الضخمة لاتخاذ قرارات استراتيجية في الأعمال",
    "تستخدم الشركات المساعدات الذكية لتحسين خدمة العملاء وزيادة الكفاءة",
    "يمكن للذكاء الاصطناعي التنبؤ بالاتجاهات السوقية وتحليل سلوك المستهلكين بدقة"
]

# Process and create dictionary, corpus
texts = [preprocess(document) for document in documents]
dictionary = corpora.Dictionary(texts)
corpus = [dictionary.doc2bow(text) for text in texts]

# Apply LDA
ldamodel = models.ldamodel.LdaModel(corpus, num_topics=3, id2word=dictionary, passes=15)
```

In this example, the script will generate 3 topics from the sample Arabic business-related documents and display the top words for each topic.

## License

This project is open-source and available under the MIT License.
