# Assessment of Jakarta’s Air Pollution Profiles through Hybrid Clustering-Classification Models-mini_project_003

## 📌 Project Overview
This project provides a comprehensive analysis of the Air Quality Index (ISPU) in Jakarta, Indonesia.The data can be access via this link: https://satudata.jakarta.go.id/open-data/detail?kategori=dataset&page_url=data-indeks-standar-pencemar-udara-ispu-di-provinsi-dki-jakarta&data_no=1. The project integrates Unsupervised and Supervised Learning to identify distinct pollution characteristic across various monitoring stations and build a robust model to cluster and classify air quality levels.

## 🚀 Key Features
- **Advanced Preprocessing:** Implementation of **Yeo-Johnson Transformation** to handle skewed data, followed by **UMAP (Uniform Manifold Approximation and Projection)** to reduce the dimensionality of the data.
- **Clustering:** A comparative approach using **KMeans** cluster as a baseline model and using **Gaussian Mixture Models (GMM)** to outcome the traditional model.
- **Classifying:**  Using **Random Forest**, **SVM**, **KNN**, **XGBoost**, and **Naive Bayes** and see which one has the best performance in classifying.
- **Robust Validation**
  **Clustering:** Using the **Silhouette Score**, **Davies-Bouldin Index**, and **Calinski-Harabasz Score** to  ealuates the cluster.
  **Classifying:** Utilizing **StratifiedKFold** cross-validation as the final step for classifying to prevent imbalanced data and ensure model generalizability.

![UMAP Dimension Reduction](Image/UMAP.png)
![Cluster](Image/Cluster.png)


## 🌫️ Pollution Clusters
Through the clustering analysis (validated with a **DB Score of 0.53795** and **CH Score of 8511.80175**) outperforming **KMeans** which has poor performance. The model has identified 5 unique pollution profiles in Jakarta:
![Pollution Clusters Analysis (Radar Chart)](Image/Radar%20Chart.png)
1. **The Fossil-Fuel Combustion Zone:** High level of $SO_2$ and $NO_2$ which produced through the combustion of fossil fuels,such as coal and petroleum, as well as industrial processes.
2. **The Dust Bowl:** High levels of $PM_10$ and $PM_2.5$ indicate high concentrations of dust.
3. **The Gridlock Zone:** High levels of CO and $NO_2$ levels are strong indicators of high traffic density and vehicle emissions.
4. **The Urban Lung:** Low pollutant index, reflecting residential areas with low traffic density.
5. **The Sun Struck Zone:** High level of ozone (O3) which produced by a photochemical reactions between \nsunlight and ozone precursor gases.

## 🛠️ Tech Stack
- **Languages:** Python
- **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn, Plotly, umap
- **Models:** KMeans, Gaussian Mixture Model (GMM), Random Forest, Support Vectore Machine (SVM), K Nearest Neighbors (KNN), XGBoost, and Naive Bayes

## 🎯 Classification Performance
Among the 5 models, the SVM has outperform the others. Random Forest, KNN, and XGBoost has overfitting and the Naive Bayes has underfitting performance. The classification of SVM model achieved a robust performance:
- **Average Accuracy:** ~94% (via Stratified CV)
- **Macro Average F1-Score:** 0.89
