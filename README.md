# COS781: E-commerce User Behavior Analysis (using Clustering and Association Rule Mining)

**Course:** COS781 - Data Mining  
**University:** University of Pretoria  
**Year:** 2025

---

## Team Members

* Lerato Letsepe
* Nothando Nkambule
* Kamohelo Makaaka
* Mbofho Mamatsharaga


## Table of Contents
- [Project Overview](#project-overview)
- [Project Structure](#project-structure)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [How to Run](#how-to-run)
- [Technologies Used](#technologies-used) 
- [References](#references)

---

## Project Overview

This project is an academic implementation for the COS781 Data Mining course. The primary objective is to replicate the two-stage data mining methodology proposed in the paper "Flow Classification Using Clustering And Association Rule Mining" [https://ieeexplore.ieee.org/abstract/document/5686959] on a real-world e-commerce dataset. We analyze user online data to first discover distinct behavioral segments through unsupervised clustering, and then uncover the unique purchasing patterns within each segment using association rule mining. The goal is to transform raw event data into actionable insights about different customer personas and their buying habits.

---


## Project Structure

e-commerce-clustering-and-association-rules/
│
├── classification/           
│   └── Transductive_Classification_and_Comparisons.ipynb
├── clustering-and-association-rule-mining/       # Clustering and association rule mining notebooks for both MiniBatchKmeans and GMM
│   ├── GaussianMixtureModel_Clustering_&_Association_Rule_Mining.ipynb
|    ├── MiniBatchKMeans_Clustering_&_Association_Rule_Mining.ipynb                  
│
├── dataset/                   
│   ├── events.csv
│   ├── item_properties.csv
|   ├── item_properties.csv
│   ├── category_tree.csv
│
├── eda/                       # Exploratory Data Analysis notebooks
|    ├── eda-notebook-combined.ipynb
│
├── outputs/                   # Generated outputs (figures, clusters, reports, etc.)
│
├── .gitattributes             # Git attributes configuration
├── .gitignore                 # Files and folders to ignore in git tracking
├── README.md                  # Project overview and instructions


## Dataset

This project uses the **Retailrocket E-commerce Dataset**, which contains raw event data from a real-world e-commerce website. The data is anonymized and includes user events, item properties, and a category tree structure.

-   **Source**: [Kaggle - Retailrocket Ecommerce Dataset](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset)

---

## Methodology

Our approach follows a two-stage pipeline:

## Stage 1: Clustering & Classification

### Feature Engineering
- Aggregated raw event logs into user sessions  
- Engineered behavioral features from session data  
- Normalized features for clustering algorithms  

### Clustering Algorithms
- **MiniBatchKMeans** - is a fast, scalable variant of **K-Means** that uses small data subsets (*mini-batches*) to quickly partition and identify hard customer segments in very large datasets.  
- **Gaussian Mixture Model (GMM)** – Probabilistic approach allowing soft cluster assignments  

### Model Comparison
- Evaluated clustering quality using **silhouette scores**, **elbow method**, and **BIC**  
- Compared **MiniBatchKMeans vs GMM** performance on user segmentation  

### Classification
- Built a supervised classifier using Random Forest to predict future user clusters  
- Trained on discovered cluster labels to enable real-time user classification  

---

## Stage 2: Association Rule Mining

### Market Basket Analysis
- Applied **Apriori algorithm** to transaction data within each cluster  
- Discovered **high-confidence and lift product association rules**  
- Identified **unique purchasing patterns** for each customer segment  

### Metrics Used
- **Support**, **Confidence**, and **Lift** for rule evaluation  
- Segment-specific rule strength analysis  

---

## How to Run

The project contains several Jupyter Notebooks organized by analysis type:

- **Exploratory Data Analysis**  
  - `eda/eda-notebook-combined.ipynb`

- **Classification**  
  - `classification/Transductive_Classification_and_Comparisons.ipynb`

- **Clustering and Association Rule Mining**  
  - `clustering-and-association-rule-mining/GaussianMixtureModel_Clustering_&_Association_Rule_Mining.ipynb`  
  - `clustering-and-association-rule-mining/MiniBatchKMeans_Clustering_&_Association_Rule_Mining.ipynb`


1. **Unzip the archive**  
2. **Install dependencies**  
   ```bash
   pip install -r requirements.txt

3. **Verify dataset files are present in the `dataset/` directory**  
   - `events.csv`  
   - `item_properties_part1.csv`
   - `item_properties_part2.csv`   
   - `category_tree.csv`  
4. **Open the  desired Jupyter Notebook** and run the cells sequentially  
    - `eda/`  
    - `classification/`  
    - `clustering-and-association-rule-mining/`  
Open the desired notebook in **Jupyter Notebook** or **Google Colab**, and run the cells sequentially.

---

## Technologies Used

- **Language:** Python 3.8+  
- **Environment:** Jupyter Notebook, Google Colab  
- **Data Processing:** pandas, numpy  
- **Machine Learning & Classification:** scikit-learn  
- **Clustering:** MiniBatchKMeans, GaussianMixture (from scikit-learn)  
- **Association Rules:** mlxtend (Apriori algorithm, association_rules)  
- **Preprocessing:** imbalanced-learn (RandomUnderSampler), scikit-learn (StandardScaler, KBinsDiscretizer, train_test_split)  
- **Visualization:** matplotlib, seaborn  
- **Model Persistence:** joblib  
- **Notebook Utilities:** IPython (for display functions)  

---


## References

- [Flow Classification Using Clustering and Association Rule Mining](https://ieeexplore.ieee.org/abstract/document/5686959)
- [Kaggle Retailrocket Ecommerce Dataset](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset)

---