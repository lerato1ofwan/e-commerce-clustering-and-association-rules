# COS781: E-commerce User Behavior Analysis (using Clustering and Association Rule Mining)

**Course:** COS781 - Data Mining  
**University:** University of Pretoria  
**Year:** 2025

---

## Project Overview

This project is an academic implementation for the COS781 Data Mining course. The primary objective is to replicate the two-stage data mining methodology proposed in the paper "Flow Classification Using Clustering And Association Rule Mining" [https://ieeexplore.ieee.org/abstract/document/5686959] on a real-world e-commerce dataset. We analyze user online data to first discover distinct behavioral segments through unsupervised clustering, and then uncover the unique purchasing patterns within each segment using association rule mining. The goal is to transform raw event data into actionable insights about different customer personas and their buying habits.

---

## Methodology

Our approach follows a two-stage unsupervised learning pipeline:

1.  **EDA & Data Preprocessing**: The raw event logs are cleaned, explored, and aggregated into distinct user sessions. Features are engineered to numerically describe the behavior within each session.
2.  **Unsupervised Clustering**: We apply clustering algorithms to the session-feature matrix to automatically group user sessions into meaningful behavioral segments (e.g., "Determined Buyers," "Window Shoppers").
3.  **Association Rule Mining**: For each discovered segment, we apply the Apriori algorithm to market baskets created from transaction data. This allows us to discover high-strength product association rules that are unique to each user group.

---

## Dataset

This project uses the **Retailrocket E-commerce Dataset**, which contains raw event data from a real-world e-commerce website. The data is anonymized and includes user events, item properties, and a category tree structure.

-   **Source**: [Kaggle - Retailrocket Ecommerce Dataset](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset)

---

## How to Run

The primary analysis is contained within the main Jupyter Notebook.

1.  Clone the repository.
2.  Ensure the dataset files (`events.csv`, `item_properties.csv`, `category_tree.csv`) are placed in a `data/` directory at the root of the project.
3.  Open the Jupyter Notebook and run the cells sequentially. It is recommended to use an environment like Google Colab for this purpose.

---

## Team Members

* Lerato Letsepe
* Nothando Nkambule
* Kamohelo Makaaka
* Mbofho Mamatsharaga