# Recommendations_with_IBM


## Project Overview
This project analyzes user interactions with articles on the IBM Watson Studio platform and builds multiple recommendation systems:

1. **Exploratory Data Analysis (EDA)**: Understand the distribution of user-article interactions and article metadata.
2. **Rank-Based Recommendations**: Recommend the most popular articles based on interaction counts.
3. **User–User Collaborative Filtering**: Recommend articles by finding similar users (using dot-product similarity) and tie-breaking with interaction counts and article popularity.
4. **Matrix Factorization (SVD)**: Factorize the user–item interaction matrix to uncover latent features, evaluate reconstruction accuracy, and choose the optimal number of latent factors.    

> _Part IV (Content-Based Recommendations) was considered optional and is not included in this submission._

---

## Repository Structure
```
├── data/
│   ├── user-item-interactions.csv    # Raw interaction data
│   └── articles_community.csv        # Article metadata
├── notebooks/
│   └── Recommendations_with_IBM.ipynb # Jupyter notebook with all analysis and code
├── README.md                         # This file
└── requirements.txt                  # Python dependencies
```

---

## Setup & Installation
1. **Clone the repository**:
   ```bash
   git clone <repo_url>
   cd <repo_folder>
   ```
2. **Create a Python environment** (recommended):
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
4. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook notebooks/Recommendations_with_IBM.ipynb
   ```

---

## Usage
- Open the notebook `Recommendations_with_IBM.ipynb` and run cells in order.
- **Part I** performs EDA and calculates descriptive statistics.
- **Part II** implements rank-based recommendations.
- **Part III** builds and evaluates a user–user collaborative filtering model.
- **Part V** applies SVD for matrix factorization, visualizes reconstruction accuracy, and assesses cold-start issues.

---

## Key Findings
- **EDA**: Median user views ~3 articles; top user views >350.
- **Rank-Based**: Top-10 popular articles include 'use deep learning for image classification', etc.
- **Collaborative Filtering**: Improved neighbor ranking by combining similarity and activity; fallback to popularity for new users.
- **SVD**: Optimal latent features ≈10–20 based on test reconstruction accuracy; more features overfit training data.

---

## Next Steps & Improvements
- Develop **content-based** filtering using article metadata (NLP on titles/descriptions).
- Incorporate **cross-validation** and **ranking metrics** (Precision@k, Recall@k) for offline evaluation.
- Deploy **A/B tests** in production to measure real user engagement (click-through rate).
- Implement a **hybrid** approach that seamlessly handles cold-start users/items.

---

## License
This project is released under the MIT License.

---

*For any questions or contributions, feel free to open an issue or submit a pull request.*

