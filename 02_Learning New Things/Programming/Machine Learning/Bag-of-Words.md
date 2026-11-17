## Simple Analogy
Imagine taking a sentence, printing it on paper, cutting out every word with scissors, and tossing them all into a literal paper bag.
- **What you lose:** Word order, sentence structure, and grammar.
- **What you keep:** A simple frequency tally (e.g., `"poor": 1`, `"good": 0`, `"movie": 2`). This process is called [[Tokenization]].
- **How it predicts:** A classifier looks at the overall word counts inside the bag. If words like `"poor"`, `"terrible"`, or `"waste"` show up frequently, it predicts a negative sentiment.

## In Practice
With already cleaned data:
```
from sklearn.feature_extraction.text import CountVectorizer
cv = CountVectorizer(max_features = n_of_most_frequent_words or total_n_of_X)
X = cv.fit_transform(cleaned_data).toarray()
y = dataset.iloc[:, -1].values
```

## Pros and Cons
