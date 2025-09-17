

# Skill Clustering Engine 🔍✨

This project was built during my internship to solve the challenge of **normalizing and clustering technical skills** from resumes, job postings, and large datasets.
It uses **Sentence-BERT embeddings** combined with **HDBSCAN clustering** to group semantically similar skills (e.g., *React*, *ReactJS*, *React.js* → **React**).

The goal is to help **HR teams, recruiters, and data platforms** clean and organize unstructured skill data into a structured taxonomy for better search, matching, and analytics.

---

## 🚀 Features

* **Text Normalization**
  Cleans raw skills and standardizes formatting (handles cases like *“React.js Developer”* → *React*).

* **Bigram Protection**
  Prevents multi-word terms (*“Spring Boot”*, *“AWS S3”*) from being split apart.

* **Semantic Embeddings**
  Uses the `multi-qa-mpnet-base-cos-v1` Sentence-BERT model to capture contextual meaning of skills.

* **Unsupervised Clustering**
  Groups skills into clusters with **HDBSCAN**, which adapts to dataset density (better than k-means for text).

* **Exportable Results**
  Outputs a CSV with original skills, normalized forms, and cluster labels.

---

## 📂 Project Structure

```
skill-clustering-engine/
│── src/
│   ├── prototype model.py      # normalization functions
│   
│  
│── data/
│   ├── Mega_Skills_List__full_.csv   # example dataset
│   ├── skills(new).json              # example input
│── requirements.txt
│── README.md
```

---

## 🛠 Tech Stack

* **Python 3.8+**
* **NLP**: [Sentence-Transformers](https://www.sbert.net/)
* **Clustering**: HDBSCAN, scikit-learn
* **Data Handling**: Pandas, NumPy

---

## ▶️ Quickstart

1. **Clone the repo**

   ```bash
   git clone https://github.com/pushtishah11/skill-clustering-engine.git
   cd skill-clustering-engine
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the pipeline**

   ```bash
   python src/main.py
   ```

4. **Check the output**

   * Results are saved to `clustered_skills.csv`.
   * Each row shows:

     * Original skill
     * Normalized skill
     * Cluster label

---

## 📊 Example Output

| original        | normalized       | cluster |
| --------------- | ---------------- | ------- |
| ReactJS         | react            | 0       |
| React.js        | react            | 0       |
| Spring Boot     | spring\_boot     | 1       |
| AWS EC2         | aws\_ec2         | 2       |
| Google BigQuery | google\_bigquery | 3       |

---

## 🔮 Use Cases

* **Resume Parsing** → standardize candidate skills.
* **Job Posting Analysis** → normalize requirements across postings.
* **Skill Taxonomy Building** → group related skills into structured categories.
* **HR Analytics** → reduce redundancy in talent databases.

---

## 📌 Future Improvements

* Add support for **Doc2Vec / OpenAI embeddings** for comparison.
* Build a small **Streamlit dashboard** for interactive exploration.
* Visualize clusters with **t-SNE / UMAP plots**.

---

⭐️ *Built during my internship to improve skill data pipelines. Open to contributions and ideas!*

---
