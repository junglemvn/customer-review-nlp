# McDonald's Customer Review NLP Analysis

This portfolio project turns 33,396 customer reviews into structured insight about sentiment and recurring service themes. It combines VADER sentiment scoring with Latent Dirichlet Allocation (LDA) topic modeling in an end-to-end Python analysis.

## Project overview

- Prepared unstructured review text through cleaning, tokenization, stopword removal, phrase detection, and lemmatization.
- Compared VADER sentiment scores across one- to five-star customer ratings.
- Evaluated 540 LDA configurations across topic counts and prior parameters using coherence.
- Used pyLDAvis to examine the separation, prevalence, and vocabulary of the resulting topics.

## Key findings

- Customer ratings are polarized: 10,274 reviews have five stars and 9,431 have one star.
- Average VADER compound sentiment rises with the reported star rating.
- A two-topic model achieved the highest recorded coherence (`0.7296`), broadly separating positive and negative experiences.
- A six-topic alternative retained similar coherence (`0.7226`) while providing more detailed themes around staff interactions, service and location, menu items, and waiting time.

The six-topic model is presented as an interpretability-focused alternative, not as a superior mathematical optimum.

## What this project demonstrates

- Practical NLP preprocessing and exploratory text analysis
- Lexicon-based sentiment analysis and comparison with observed ratings
- Unsupervised topic modeling and systematic hyperparameter tuning
- Interpretation and communication of model trade-offs
- Reproducible project organization with saved analytical outputs

## Explore the project

- [Complete analysis notebook](notebooks/01_nlp_review_analysis.ipynb)
- [LDA tuning results](results/lda_tuning_results.csv)
- [Two-topic interactive visualization](reports/interactive/lda_topics_2.html)
- [Six-topic interactive visualization](reports/interactive/lda_topics_6.html)

## Technical notes

The project uses Python, pandas, NLTK, spaCy, Gensim, VADER, Matplotlib, Seaborn, WordCloud, and pyLDAvis. Dependencies are recorded in `requirements.txt`.

The source dataset is not committed. It can be obtained from the [McDonald's Store Reviews dataset on Kaggle](https://www.kaggle.com/datasets/nelgiriyewithana/mcdonalds-store-reviews) and placed at `data/raw/mcdonalds_reviews.csv`. The saved tuning table allows the analysis to be reviewed without repeating the expensive 540-model search.

## Limitations

This is an exploratory analysis. VADER is a rule-based sentiment method, topic labels require analyst judgment, and coherence alone does not establish that a topic solution is operationally useful. The findings describe patterns in this review dataset and are not causal conclusions.
