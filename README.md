# DATA-PIPELINE-DEVELOPMENT

COMPANY: CODTECH IT SOLUTIONS

NAME: GURRALA LAXMI PARIMAL

INTERN ID: CT12RER

DURATION: 8 WEEKS

MENTOR: NEELA SANTHU

##Description:This Python script performs an automated ETL (Extract, Transform, Load) pipeline designed to clean and prepare raw CSV data for further analysis or machine learning. The task involves loading data from a CSV file, preprocessing the data through cleaning and transformation, and saving the processed data to a new file. It uses several tools from the Python data science ecosystem, primarily pandas for data handling and scikit-learn for preprocessing tasks.
In the extraction phase, the script uses the pandas.read_csv() function to load the dataset into a DataFrame. This structure allows easy manipulation of tabular data and serves as the base for all further processing. Once the data is loaded, the script identifies numerical and categorical columns using df.select_dtypes(), distinguishing columns by their data types: numeric types like int64 and float64, and categorical types typically labeled as object.
The transformation phase involves two separate preprocessing pipelines: one for numeric data and one for categorical data. The numeric pipeline uses SimpleImputer with a "mean" strategy to fill in missing values and StandardScaler to scale features so they have zero mean and unit variance. This is a standard step in preparing numeric features for many machine learning algorithms that are sensitive to feature scales.
The categorical pipeline also begins with SimpleImputer, but uses the "most_frequent" strategy to fill in missing values with the most common category. Then, it applies OneHotEncoder to convert categorical values into binary vectors. One-hot encoding prevents machine learning models from interpreting categorical labels as having an ordinal relationship, which could otherwise introduce bias.
These two pipelines are combined using ColumnTransformer, which applies the appropriate transformation to each column based on its type. This allows a clean, modular design where different preprocessing steps are applied automatically to different subsets of features.
After the transformations are applied, the script uses fit_transform to apply the combined pipeline to the entire dataset. Since the transformed output is a NumPy array, the script reconstructs a new pandas DataFrame using the original numeric column names and the newly generated one-hot encoded feature names. These encoded names are obtained using get_feature_names_out() from the OneHotEncoder object, ensuring the transformed dataset remains interpretable.
In the loading phase, the final cleaned and transformed dataset is saved to a new CSV file using DataFrame.to_csv(). This allows for the processed data to be reused or passed into machine learning models.
This script runs in any standard Python 3 environment, including local IDEs, Jupyter Notebooks, or cloud-based platforms like Google Colab or AWS SageMaker. It requires the pandas, numpy, and scikit-learn libraries. Overall, this ETL pipeline automates and modularizes essential data preparation steps, making it a practical tool for data preprocessing in real-world machine learning workflows.
