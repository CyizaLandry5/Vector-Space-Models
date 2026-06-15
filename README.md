# AVectors Space Models

## Course Information
- **Course:** Course - Natural Language Processing (Classification & Vector Spaces)
- **Platform:** DeepLearning.AI
- **Assignment:** #3 - Word Vectors & Analogies

## 📌 Overview
This assignment served as an introduction to the wonderful world of **word vectors** (word embeddings). In natural language processing, we represent each word as a vector consisting of numbers that encode the meaning of the word. Rather than training these embeddings from scratch (which we'll explore later), I learned how to **use pre-trained word embeddings** to solve interesting problems.

The main tasks included:
- Predicting analogies between words (e.g., "Athens is to Greece as Bangkok is to ___")
- Using PCA to reduce word embeddings from 300 dimensions to 2D for visualization
- Comparing word embeddings using cosine similarity and Euclidean distance
- Understanding how vector space models capture semantic relationships

## 🎯 What I Learned
- **Cosine Similarity:** Implemented the cosine similarity metric to measure how similar two word vectors are (1 = identical direction, 0 = orthogonal, -1 = opposite).
- **Euclidean Distance:** Used Euclidean distance as an alternative similarity measure (closer distance = more similar).
- **Word Analogies:** Learned the famous vector arithmetic relationship: `King - Man + Woman ≈ Queen`. Applied this to predict countries from capitals.
- **Principal Component Analysis (PCA):** Implemented PCA from scratch to reduce 300-dimensional word vectors to 2 dimensions for visualization.
- **Data Exploration:** Worked with a subset of Google News word embeddings (243 words, each 300-dimensional).
- **Semantic Clustering:** Observed how semantically similar words cluster together when visualized in 2D.

## ⚙️ Key Skills Practiced
- Vector arithmetic with word embeddings
- Similarity metrics (cosine, Euclidean)
- Dimensionality reduction with PCA
- Eigenvalue decomposition
- Data visualization with matplotlib
- Working with pandas DataFrames

## 🚧 Challenges Faced
1. **Understanding Vector Analogies:** Grasping that `country1 - city1 + city2` gives a vector close to `country2` required visualizing the geometric interpretation of word vectors.
2. **Cosine Similarity Implementation:** Ensuring the denominator didn't become zero (dividing by zero) and handling floating-point precision.
3. **PCA Implementation Details:** 
   - Mean-centering the data correctly (axis=0 vs axis=1)
   - Using `eigh()` instead of `eig()` for symmetric matrices (performance)
   - Sorting eigenvectors by decreasing eigenvalues
   - Understanding the matrix multiplication order for transformation
4. **Avoiding Overlap in Predictions:** Making sure the predicted country wasn't one of the input words (city1, country1, or city2).
5. **Accuracy Calculation:** Iterating through the DataFrame correctly and matching predicted countries with actual ones.

## 📋 Important Submission Notes (AutoGrader)
To avoid `Grader Error: Grader feedback not found` or similar unexpected errors from the DeepLearning.AI AutoGrader, I made sure NOT to:
- Add any extra `print` statements in the assignment
- Add any extra code cells
- Change any of the function parameters
- Use global variables inside graded exercises (unless specifically instructed)
- Change the assignment code where not required (like creating extra variables)

> 💡 **Tip:** If you run into unexpected grader errors, check the above points first. You can always get a fresh copy of the assignment by following the workspace refresh instructions on DeepLearning.AI.

## 🛠️ Technologies & Tools
- Python 3
- NumPy (linear algebra operations)
- Pandas (data manipulation)
- Matplotlib (visualization)
- Pickle (loading pre-trained embeddings)
- Google News word embeddings (300-dim, subset)

## 📈 Results
- **Cosine Similarity Example:** `cosine_similarity(king, queen)` ≈ 0.651
- **Euclidean Distance Example:** `euclidean(king, queen)` ≈ 2.48
- **Analogy Accuracy:** Achieved **92% accuracy** on predicting countries from capitals!
- **PCA Visualization:** Successfully reduced 300-dim vectors to 2D, revealing semantic clusters:
  - Energy-related words: oil, gas, petroleum clustered together
  - Emotion words: happy, sad, joyful grouped nearby
  - Geographic terms: city, town, village, country, continent formed their own cluster

### Sample Output

Input: get_country('Athens', 'Greece', 'Cairo', word_embeddings)
Output: ('Egypt', 0.7626822)

## 🔗 Related Concepts
- Word2Vec (Mikolov et al., 2013)
- GloVe embeddings (Pennington et al., 2014)
- Distributional semantics
- Vector space models for NLP
- Principal Component Analysis (PCA)
- Analogical reasoning with word vectors

## 📚 Key Formulas
- **Cosine Similarity:** `cos(A,B) = (A·B) / (||A||·||B||)`
- **Euclidean Distance:** `d(A,B) = sqrt(Σ(Ai - Bi)²)`
- **Analogy Vector:** `vec(country2) ≈ vec(country1) - vec(city1) + vec(city2)`
- **PCA Transformation:** `X_reduced = (X - μ) · W_k` where `W_k` are top k eigenvectors

## 📚 Acknowledgments
This assignment was completed as part of the Natural Language Processing specialization on **DeepLearning.AI**. The word embeddings used are a subset of the Google News pre-trained vectors (Word2Vec). The analogy task and PCA visualization follow standard practices in exploring word embedding spaces.

---
