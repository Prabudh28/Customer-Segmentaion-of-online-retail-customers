
# Online Retail Customer Segmentation

This project performs customer segmentation on the "Online Retail II" dataset from the UCI Machine Learning Repository. The primary goal is to group customers based on their purchasing habits across different product categories.

A key challenge with this dataset is the absence of pre-defined product categories. This project addresses that by using Natural Language Processing (NLP) techniques, specifically **TF-IDF Vectorization** and **K-Means Clustering**, to generate product categories from their descriptions.

---

## 📝 Project Methodology

The project is divided into two main parts:

### Part 1: Product Category Creation (Topic Modeling)
Since the raw data only contains product descriptions, we first need to create meaningful categories.
1.  **Preprocessing**: Text data from the 'Description' column is cleaned and common English words (stopwords) are removed.
2.  **Vectorization**: Product descriptions are converted into numerical vectors using **TfidfVectorizer**.
3.  **Clustering**: **MiniBatchKMeans** clustering is applied to the vectors. The "elbow method" was used to determine the optimal number of clusters, resulting in **4 distinct product categories**:
    * **Category 0**: General items
    * **Category 1**: Bags
    * **Category 2**: Christmas decorations
    * **Category 3**: Other decorations

### Part 2: Customer Segmentation
With product categories established, customers are segmented based on their spending patterns.
1.  **Data Aggregation**: The total amount spent by each customer in each of the 4 categories is calculated.
2.  **Normalization**: The spending is converted into percentages of each customer's total spending to ensure fair comparisons.
3.  **Clustering**: **K-Means** and **Agglomerative Hierarchical Clustering** are used to group customers. Based on dendrograms and the elbow method, **4 customer segments** were identified.

---

## 📊 Dataset

* **Name**: Online Retail II Data Set
* **Source**: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Online+Retail+II)
* **Note**: The notebook (`Online_retail_Segmentation_by_buying_category.ipynb`) automatically downloads the required `online_retail_II.xlsx` file.



## Dependencies
* pandas
* numpy
* matplotlib
* seaborn
* scikit-learn
* scipy
* wordcloud
* openpyxl
