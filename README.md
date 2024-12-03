# Solar Flare Prediction using SWAN-SF dataset

The SWAN-SF dataset is a multivariate time series dataset designed for classifying solar flares into five categories: X, M, C, B, and FQ. It consists of five partitions, with a total volume exceeding 5 gigabytes, making it quite large in size. Each sample within the dataset has 24 unique attributes and a sequence length of 60, contributing to its high dimensionality. The current methodology for time series slicing in the SWAN-SF dataset involves using a sliding window with steps of 1 hour, where each slice has an observation period of 12 hours and a prediction span of 24 hours. Within this framework, each multivariate time series slice is assigned a category based on the most intense solar flare observed during its corresponding prediction window. For our analysis, we utilize only the first two partitions, which together comprise approximately 150,000 samples. However, this dataset presents significant challenges. These include class imbalance, multi-scaled attributes, missing values, and class overlap, all of which make achieving high classification performance particularly difficult. To simplify the task, we group the FQ, B, and C classes as “minor-flaring” and the M and X classes as “major-flaring,” transforming the classification task into a binary classification problem, distinguishing between minor- and major-flaring samples.

**PROJECT OBJECTIVES:**

1. The first step is to load the SWAN-SF dataset by iterating through each file, converting the data into pickle format. The dataset will then be split and saved into two files: one for the data and another for the binary labels associated with each sample. 

2. The next step involves applying various imputation and normalization techniques, including mean imputation, forward fill imputation, Min-Max scaling, and Z-score normalization, to assess their impact on improving solar flare classification accuracy using a GRU classifier.

3. Oversampling techniques such as SMOTE and ADASYN, along with random undersampling, will be incorporated to balance the dataset. The effect of these sampling methods on classification performance will be analyzed. 

4. In addition, statistical feature engineering and deep learning-based feature selection methods will be compared to determine which approach yields better classification accuracy. Several classifiers, including SVM, k-NN, GRU, and LSTM, will be used to evaluate which model performs best on the SWAN-SF dataset.

5. Data distribution analysis, and correlation analysis will be conducted to provide deeper insights into the dataset.

Box plots and bar charts will be used to visualize and assess the experimental results. The True Skill Statistic (TSS) will serve as the evaluation metric, as conventional metrics such as accuracy and F1-score are not appropriate for imbalanced datasets.



### Prerequisites

Before you start, make sure you have the following:

- **SWAN-SF Dataset**: Download it from [Harvard Dataverse](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/EBCFKM).
- **Python Packages**: Ensure you have these packages installed: `pandas`, `numpy`, `matplotlib`, `seaborn`, `tensorflow`, `tqdm`, `pickle`, `sklearn`, `scipy`, `imblearn`. The code for `timegan` is included in the repository, so no additional installation is required for this package.
