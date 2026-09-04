# AI Internship Tasks

This repository contains completed tasks from my AI internship, covering natural language processing and search/optimization algorithms.

## Repository Structure

```
AI_internship_tasks/
├── README.md
├── Task_2_NLP_Sentiment_Classifier.ipynb
├── Task_3_Heuristic_Pathfinding_Agent.ipynb
└── pathfinding_logs/
    ├── maze_easy.png
    ├── maze_medium.png
    ├── maze_hard.png
    ├── maze_custom.png
    ├── maze_challenge.png
    ├── maze_detour.png
    ├── random_maze_10x10.png
    ├── expanded_nodes_comparison.png
    ├── runtime_comparison.png
    └── benchmark_results.csv
```

---

## Task 2: Intelligent Multi-Class NLP Sentiment Classifier

**Objective:** Build a text classification model to map and group unstructured student feedback into sentiment categories (Negative, Positive, Neutral).

**Approach:**
- Preprocessed text via lowercasing, stopword removal, and lemmatization.
- Vectorized comments using TF-IDF (unigrams + bigrams).
- Engineered a custom "suggestion-marker" feature to capture request/suggestion-style phrasing common in the Neutral class.
- Trained and compared Naive Bayes, Logistic Regression, SVM, and SMOTE oversampling.
- Validated results using 5-fold cross-validation rather than a single train/test split.

**Result:** Final model (Logistic Regression, balanced class weights, TF-IDF + suggestion-marker feature) achieved a cross-validated macro F1-score of 0.596, a substantial improvement over the baseline's 0.00 F1-score on the Neutral class.

**Tech stack:** Python, scikit-learn, NLTK, pandas, matplotlib

---

## Task 3: Heuristic Graph Pathfinding Agent

**Objective:** Implement a search-based agent that navigates grid mazes efficiently using heuristic pathfinding.

**Approach:**
- Implemented A* Search (Manhattan-distance heuristic) and Dijkstra's Algorithm from scratch using a priority-queue-based approach.
- Tested both algorithms on 6 hand-designed mazes of increasing complexity, plus randomly generated, solvability-checked mazes across 3 sizes (10×10 to 30×30) and 3 obstacle densities.
- Tracked path length, expanded node count, and runtime for every run.
- Exported path visualizations and benchmark metrics as reviewable output files.

**Result:** A* consistently expanded fewer nodes than Dijkstra across all obstacle-containing mazes while finding identical, optimal-length paths — confirming the practical benefit of heuristic guidance, with the advantage growing on larger, denser mazes.

**Tech stack:** Python, heapq, matplotlib, pandas

---

## How to Run

Each task is contained in its own Jupyter/Colab notebook. Open the `.ipynb` file in Google Colab or Jupyter and run all cells sequentially. Task 3 additionally saves visualizations and metrics into the `pathfinding_logs/` folder on execution.
