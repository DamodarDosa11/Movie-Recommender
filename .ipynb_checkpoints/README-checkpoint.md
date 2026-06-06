# Movie Recommendation System

A Content-Based and Popularity-Based Movie Recommendation System built in Python. This system uses textual features such as genres, keywords, taglines, cast, and directors to calculate similarity confidence scores between films and suggest the top 30 most relevant movies based on a user's favorite input.

---

## 📌 Features

- **Text Feature Engineering**: Translates combined textual attributes into numerical feature vectors using **TF-IDF Vectorization** (`TfidfVectorizer`).
- **Similarity Computation**: Leverages **Cosine Similarity** to construct a geometric relationship matrix across all movies.
- **Fuzzy String Matching**: Implements Python's native `difflib` library (`get_close_matches`) to intelligently match structural alignments even if the user introduces minor typos or spelling errors.
- **Top Suggestions**: Generates a descending-order ranked list of 30 recommended films using a custom `lambda` sorting routine over the similarity vector map.

---

## 🏗️ Workflow

1. **Data Preprocessing**: Load the TMDB dataset via `pandas`, select core descriptive columns (`genres`, `keywords`, `tagline`, `cast`, `director`), and clean missing instances safely with empty null strings.
2. **Feature Extraction**: Linearly concatenate all selected descriptive strings and map token frequencies using `TfidfVectorizer`.
3. **Similarity Mapping**: Compute pairwise geometry metrics with `cosine_similarity`.
4. **Recommendation Output**: Match raw query strings to dataset titles via `difflib`, look up its index, extract the similarity score pairs, sort them in descending order, and return the top recommendations.

---

## 🔧 Prerequisites

Ensure you have Python installed along with the following required libraries:

```bash
pip install numpy pandas scikit-learn