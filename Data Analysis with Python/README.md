- Each line in a dataset is a row, and commas separate the values.

- To understand the data, you must analyze the attributes for each column of data.

- Python libraries are collections of functions and methods that facilitate various functionalities without writing code from scratch and are categorized into Scientific Computing, Data Visualization, and Machine Learning Algorithms.

- Many data science libraries are interconnected; for instance, Scikit-learn is built on top of NumPy, SciPy, and Matplotlib.

- The data format and the file path are two key factors for reading data with Pandas.

- The read_CSV method in Pandas can read files in CSV format into a Pandas DataFrame.

- Pandas has unique data types like object, float, Int, and datetime.

- Use the dtype method to check each column’s data type; misclassified data types might need manual correction.

- Knowing the correct data types helps apply appropriate Python functions to specific columns.

- Using Statistical Summary with describe() provides count, mean, standard deviation, min, max, and quartile ranges for numerical columns.

- You can also use include='all' as an argument to get summaries for object-type columns.

- The statistical summary helps identify potential issues like outliers needing further attention.

- Using the info() Method gives an overview of the top and bottom 30 rows of the DataFrame, useful for quick visual inspection.

- Some statistical metrics may return "NaN," indicating missing values, and the program can’t calculate statistics for that specific data type.

- Python can connect to databases through specialized code, often written in Jupyter notebooks.

- SQL Application Programming Interfaces (APIs) and Python DB APIs (most often used) facilitate the interaction between Python and the DBMS.

- SQL APIs connect to DBMS with one or more API calls, build SQL statements as a text string, and use API calls to send SQL statements to the DBMS and retrieve results and statuses.

- DB-API, Python's standard for interacting with relational databases, uses connection objects to establish and manage database connections and cursor objects to run queries and scroll through the results.

- Connection Object methods include the cursor(), commit(), rollback(), and close() commands.

- You can import the database module, use the Connect API to open a connection, and then create a cursor object to run queries and fetch results. 

- Remember to close the database connection to free up resources.

|Package/Method|Description|Code Example|
|-------|-----|------|
|Read CSV data set|Read the CSV file containing a data set to a pandas data frame |`df = pd.read_csv(<CSV_path>, header = None)` <br /> # load without header `df = pd.read_csv(<CSV_path>, header = 0)` <br /> # load using first row as header <br /> Note: The labs in this course run in JupyterLite environment. In JupyterLite environment, you'll need to download the required file to the local environment and then use the local path to the file as the CSV_path. However, in case you are using JupyterLabs, or any other Python compiler on your local machine, you can use the URL of the required file directly as the CSV_path.
|Print first few entries|Print first few entries	Print the first few entries (default 5) of the pandas data frame|`df.head(n) #n=number of entries; default 5`|
|Print last few entries|Print the last few entries (default 5) of the pandas data frame|`df.tail(n) #n=number of entries; default 5`|
|Assign header names| Assign appropriate header names to the data frame | `df.columns = headers`|
|Replace "?" with NaN | Replace the entries "?" with NaN entry from Numpy library | `df = df.replace("?", np.nan)`|
|Retrieve data types | Retrieve the data types of the data frame columns | `df.dtypes` |
| Retrieve statistical description | Retrieve the statistical description of the data set. Defaults use is for only numerical data types. Use include="all" to create summary for all variables | `df.describe() #default use df.describe(include="all")` |
| Retrieve data set summary | Retrieve the summary of the data set being used, from the data frame | `df.info()`|
|Save data frame to CSV | Save the processed data frame to a CSV file with a specified path | `df.to_csv(<output CSV path>)`|



- Data formatting is critical for making data from various sources consistent and comparable.

- Master the techniques in Python to convert units of measurement, like transforming "city miles per gallon" to "city-liters per 100 kilometers" for ease of comparison and analysis.

- Acquire skills to identify and correct data types in Python, ensuring the data is accurately represented for subsequent statistical analyses.

- Data normalization helps make variables comparable and helps eliminate inherent biases in statistical models.

- You can apply Feature Scaling, Min-Max, and Z-Score to normalize data and apply each technique in Python using pandas’ methods.

- Binning is a method of data pre-processing to improve model accuracy and data visualization.

- Run binning techniques in Python using numpy's "linspace" and pandas' "cut" methods, particularly for numerical variables like "price."

- Utilize histograms to visualize the distribution of binned data and gain insights into feature distributions.

- Statistical models generally require numerical inputs, making it necessary to convert categorical variables like "fuel type" into numerical formats.

- You can implement the one-hot encoding technique in Python using pandas’ get_dummies method to transform categorical variables into a format suitable for machine learning models.
  
|Package/Method|Description|Code Example|
|-------|-----|------|
|Replace missing data with frequency | Replace the missing values of the data set attribute with the mode common occurring entry in the column.|`MostFrequentEntry = df['attribute_name'].value_counts().idxmax() ` <br /> `df['attribute_name'].replace(np.nan,MostFrequentEntry,>df['attribute_name'].replace(np.nan,MostFrequentEntry, inplace=True)` |
|Replace missing data with mean | Replace the missing values of the data set attribute with the mean of all the entries in the column. | `AverageValue=df['attribute_name'].astype(<data_type>).mean(axis=0)` <br />  `df['attribute_name'].replace(np.nan, AverageValue, inplace=True)`|
| Fix the data types | Fix the data types of the columns in the dataframe. | `df[['attribute1_name', 'attribute2_name', ...]] = df[['attribute1_name', 'attribute2_name', ...]].astype('data_type')` <br />  #data_type is int, float, char, etc. |
| Data Normalization | Normalize the data in a column such that the values are restricted between 0 and 1. |` df['attribute_name']= df['attribute_name']/df['attribute_name'].max()`|
| Binning | Create bins of data for better analysis and visualization. | `bins = np.linspace(min(df['attribute_name'])`  <br /> `max(df['attribute_name'],n)` <br /> # n is the number of bins needed  <br /> `GroupNames = ['Group1','Group2','Group3,...]`  <br /> `df['binned_attribute_name'] =pd.cut(df['attribute_name'], bins, labels=GroupNames, include_lowest=True)` |
| Change column name | Change the label name of a dataframe column.|` df.rename(columns={'old_name':\'new_name'}, inplace=True)`|
| Indicator Variables| Create indicator variables for categorical data.| `dummy_variable = pd.get_dummies(df['attribute_name'])` <br /> `df = pd.concat([df, dummy_variable],axis = 1)`|




