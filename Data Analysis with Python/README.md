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


- Tools like the 'describe' function in pandas can quickly calculate key statistical measures like mean, standard deviation, and quartiles for all numerical variables in your data frame. 

- Use the 'value_counts' function to summarize data into different categories for categorical data. 

- Box plots offer a more visual representation of the data's distribution for numerical data, indicating features like the median, quartiles, and outliers.

- Scatter plots are excellent for exploring relationships between continuous variables, like engine size and price, in a car data set.

- Use Pandas' 'groupby' method to explore relationships between categorical variables.

- Use pivot tables and heat maps for better data visualizations.

- Correlation between variables is a statistical measure that indicates how the changes in one variable might be associated with changes in another variable.

- When exploring correlation, use scatter plots combined with a regression line to visualize relationships between variables.

- Visualization functions like regplot, from the seaborn library, are especially useful for exploring correlation.

- The Pearson correlation, a key method for assessing the correlation between continuous numerical variables, provides two critical values—the coefficient, which indicates the strength and direction of the correlation, and the P-value, which assesses the certainty of the correlation.

- A correlation coefficient close to 1 or -1 indicates a strong positive or negative correlation, respectively, while one close to zero suggests no correlation.

- For P-values, values less than .001 indicate strong certainty in the correlation, while larger values indicate less certainty. Both the coefficient and P-value are important for confirming a strong correlation.

## Importing libraries
### matplotlib
`from matplotlib import pyplot as plt` <br /> 
Alternatively, the command can also be written as: <br /> 
`import matplotlib.pyplot as plt`

Note that most of the plots that are of interest to us in this library are contained in the pyplot subfolder of the package.

matplotlib functions return a plot object which requires additional statements to display. While using matplotlib in Jupyter Notebooks, we require the graph to be displayed inside the notebook interface itself. It is, therefore, essential to add the following 'magic' statement after loading the library.

`%matplotlib inline`

### seaborn
`import seaborn as sns`

## matplotlib functions
1. Standard Line Plot

The simplest and most fundamental plot is a standard line plot. The function expects two arrays as input, x and y, both of the same size. x is treated as an independent variable and y as the dependent one. The graph is plotted as shortest line segments joining the x,y point pairs ordered in terms of the variable x.

`plt.plot(x,y)`

2. Scatter plot

Scatter plots are graphs that present the relationship between two variables in a data set. It represents data points on a two-dimensional plane. The independent variable or attribute is plotted on the X-axis, while the dependent variable is plotted on the Y-axis.

Scatter plots are used in either of the following situations:

- When we have paired numerical data
- When there are multiple values of the dependent variable for a unique value of an independent variable
- In determining the relationship between variables in some scenarios

`plt.scatter(x,y)`

3. Histogram

A histogram is an important visual representation of data in categorical form. To view the data in a "Binned" form, we may use the histogram plot with a number of bins required or even with the data points that mark the bin edges. The x-axis represents the data bins, and the y-axis represents the number of elements in each of the bins.

`plt.hist(x,bins)`

4. Bar plot
A bar plot is used for visualizing catogorical data. The y-axis represents the average value of data points belonging to a particular category, while the x-axis represents the number of elements in the different categories.

`plt.bar(x,height)`

5. Pseudo Color Plot
A pseudocolor plot displays matrix data as an array of colored cells (known as faces). This plot is created as a flat surface in the x-y plane. The surface is defined by a grid of x and y coordinates that correspond to the corners (or vertices) of the faces. Matrix C specifies the colors at the vertices. The color of each face depends on the color of one of its four surrounding vertices. Of the four vertices, the one that comes first in the x-y grid determines the color of the face.

In this course, you use the pcolor plot for visualizing the contents of a pivot table that has been grouped on the basis of 2 parameters. Those parameters then represent the x and y-axis components that create the grid. The values in the pivot table are the average values of a third parameter. These values act as the code for the color the cell is going to take.

`plt.pcolor(C)`

You can define an additional cmap argument to specify the color scheme of the plot.

## seaborn functions
1. Regression plot

A regression plot draws a scatter plot of two variables, x and y, and then fits the regression model and plots the resulting regression line along with a 95% confidence interval for that regression. The x and y parameters can be shared as the dataframe headers to be used, and the data frame itself is passed to the function as well.

`sns.regplot(x = 'header_1',y = 'header_2',data= df)`

2. Box and whisker plot

A box plot (or box-and-whisker plot) shows the distribution of quantitative data in a way that facilitates comparisons between variables or across levels of a categorical variable. The box shows the quartiles of the dataset while the whiskers extend to show the rest of the distribution, except for points that are determined to be "outliers".

3. Residual Plot

A residual plot is used to display the quality of polynomial regression. This function will regress y on x as a polynomial regression and then draw a scatterplot of the residuals.
Residuals are the differences between the observed values of the dependent variable and the predicted values obtained from the regression model. In other words, a residual is a measure of how much a regression line vertically misses a data point, meaning how far off the predictions are from the actual data points.

`sns.residplot(data=df,x='header_1', y='header_2')`

Alternatively:

`sns.residplot(x=df['header_1'], y=df['header_2'])`


4. KDE plot

A Kernel Density Estimate (KDE) plot is a graph that creates a probability distribution curve for the data based upon its likelihood of occurrence on a specific value. This is created for a single vector of information. It is used in the course in order to compare the likely curves of the actual data with that of the predicted data.

`sns.kdeplot(X)`

5. Distribution Plot

This plot has the capacity to combine the histogram and the KDE plots. This plot creates the distribution curve using the bins of the histogram as a reference for estimation. You can optionally keep or discard the histogram from being displayed. In the context of the course, this plot can be used interchangeably with the KDE plot.

`sns.distplot(X,hist=False)`

|Package/Method|Description|Code Example|
|-------|-----|------|
| Complete dataframe correlation | Correlation matrix created using all the attributes of the dataset. |` df.corr()`|
