## Phase 1 

Get ready to train a tiny sentiment model locally and layer plug it into a FastAPI app

### What is Sentiment Analysis?
[Sentiment analysis](https://aws.amazon.com/what-is/sentiment-analysis/) is the process of analyzing digital text to determine if the emotional tone of the message is positive, negative, or neutral.
- It is also known as *opinion mining*. 
- It is a powerful business intelligence tool that helps companies improve their products and services. 
- It belongs to the broader field of **Natural Language Processing (NLP)**
- In simpler terms, *"Given a sentence, how the writer feels"*

### How can Sentiment Analysis be done?

There are 3 broad generations of methods:

#### 1. Rule-Based Methods (Oldest)

The systems rely on manually written rules, patterns, or lexicons. 

🔠 Examples:
- List of positive/negative words ("good", "bad", "love", "hate")
- Hand-crafted rules ("if word contains NOT, flip sentiment")
- Regex-like patterns

✅ Pros:
- Simple to understand
- No training data needed

❌ Cons:
- Very brittle
- Doesn't generalize
- Fails on sarcasm, domain shifts, modern slang, etc.

#### 2. Classical ML Methods (Pre-Deep Learning Era)

Text is converted to fixed-size numerical features &rarr; fed into a simple ML classifier. 

Common feature representations:
- Bag-of-words (BoW)
- TF-IDF (Term Frequency-Inverse Document Frequency)
- n-grams (word sequences)

Common ML algorithms:
- Logistic Regression
- Naive Bayes
- Support Vector Machines (SVMs)
- Random Forests
- Linear SVM / Linear classifiers

Workflow:
1. Convert text into numeric vectors
2. Train an ML model on labelled examples
3. Predict sentiment on new text

Advantages of these models:
- train fast
- are interpretable
- work well for small projects
- run easily on CPU

*This is the approach I am using here.*

#### 3. Deep Learning & LLM-Based Methods (Modern Era)

Models learn richer language patterns using neural networks. 

1. Word Embeddings (Word2Vec, GloVe)
2. CNN/LSTM-based classifiers
3. Transformers
    - BERT
    - RoBERTa
    - DistilBERT
4. LLMs
    - GPT-4/5, Claude, Gemini, etc.

✅ Pros:
- Best accuracy on complex tasks
- Understands context deeply
- Handles sarcasm, nuance, long text

❌ Cons:
- Expensive
- Harder to deploy
- Requires GPU for training
- Not ideal for micro projects

### Why we are using TF-IDF + Logistic Regression

1. Perfect for small custom projects
    - No GPU required
    - Little training time
    - Easy to save as a file
    - Fast to load in FastAPI
2. Good accuracy for simple sentiment tasks
    - TF-IDF captures which words appear
    - how important they are in the sentence
    - ignores unimportant common words
    - emphasize discriminative words ("awesome", "terrible")
3. Model in interpretable
    - You can see which words push the prediction positive and which push it negative
4. Small file size
    - A TF-IDF logistic regression model is usually 1-5 MB and loads instantly
5. Keeps the project focused on learning the pipeline
    - TF-IDF keeps the ML portion simple and understandable, so the focus can be on the full workflow
6. Builds foundational intuition
    - Understanding vectorization + classical ML makes it easier later to upgrade to - embeddings, transformers, finetuning, etc.