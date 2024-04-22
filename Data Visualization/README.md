### Data Preprocessing Tasks in Pandas & Plot Libraries

| Task | 	Syntax | Description | Example |
|--|--|---|---|
| Load CSV data | `pd.read_csv('filename.csv')` | Read data from a CSV file into a Pandas DataFrame | `df_can=pd.read_csv('data.csv')` |
| Handling Missing Values | `df.dropna()` | Drop rows with missing values | `df_can.dropna()` |
|  | 	`df.fillna(value)`| Fill missing values with a specified value | `df_can.fillna(0) `|
| Removing Duplicates | `df.drop_duplicates()` |  Remove duplicate rows | `df_can.drop_duplicates()` |
| Renaming Columns |` df.rename(columns={'old_name': 'new_name'})` | Rename one or more columns | `df_can.rename(columns={'Age': 'Years'})`|
| Selecting Columns | `df['column_name']` or `df.column_name` | Select a single column | `df_can.Age` or `df_can['Age]'` |
|  | `df[['col1', 'col2']]` | Select multiple columns | `df_can[['Name', 'Age']]` |
| Filtering Rows | `df[df['column'] > value]` | Filter rows based on a condition | `df_can[df_can['Age'] > 30]`|
|  Applying Functions to Columns | `df['column'].apply(function_name)`| Apply a function to transform values in a column | `df_can['Age'].apply(lambda x: x + 1)`|
| Creating New Columns | `df['new_column'] = expression` | Create a new column with values derived from existing ones | `df_can['Total'] = df_can['Quantity'] * df_can['Price']`|
| Grouping and Aggregating | `df.groupby('column').agg({'col1': 'sum', 'col2': 'mean'})` | Group rows by a column and apply aggregate functions | `df_can.groupby('Category').agg({'Total': 'mean'})`|
|  Sorting Rows |`df.sort_values('column', ascending=True/False)`|	Sort rows based on a column	| `df_can.sort_values('Date', ascending=True)`|
| Displaying First n Rows |	`df.head(n)` |	Show the first n rows of the DataFrame |	`df_can.head(3)`|
| Displaying Last n Rows	|` df.tail(n)` |	Show the last n rows of the DataFrame	| `df_can.tail(3)`|
|Checking for Null Values	| `df.isnull()`|	Check for null values in the DataFrame	|` df_can.isnull()`|
| Selecting Rows by Index	| `df.iloc[index]`|	Select rows based on integer index	| `df_can.iloc[3]`|
| |`df.iloc[start:end]`|	Select rows in a specified range	| `df_can.iloc[2:5]`|
|Selecting Rows by Label	| `df.loc[label]` |	Select rows based on label/index name	|` df_can.loc['Label']`|
|  |`df.loc[start:end]` | Select rows in a specified label/index range |	`df_can.loc['Age':'Quantity']` |
|Summary Statistics |	`df.describe()` |	Generates descriptive statistics for numerical columns |	`df_can.describe()`|

### Plotting with Matplotlib using Pandas
| Plot Type | Description | Pandas Function | Example | 
|--|--|---|---|
| Line Plot |	Shows trends and changes over time |	`DataFrame.plot.line() `| `DataFrame.plot(kind = ‘line’)	df.plot(x=’year’, y=’sales’, kind=’line’)	`| 
|Area Plot |	Displays data series as filled areas, showing the relationship between them |	`DataFrame.plot.area()`  `DataFrame.plot(kind = ‘area’)` |` df.plot(kind='area')`|
| Histogram	| Displays bars representing the data count in each interval/bin	|` Series.plot.hist()` `Series.plot(kind = ‘hist’, bins = n)` |` s.plot(kind='hist', bins=10)`  `df[‘age’].plot(kind='hist', bins=10)` |	
| Bar Chart | Displays data using rectangular bars	| `DataFrame.plot.bar()` `DataFrame.plot(kind = ‘bar’)` |	`df.plot(kind='bar')	`|
| Pie Chart |	Displays data as a circular plot divided into slices, representing proportions or percentages of a whole |	`Series.plot.pie()` `Series.plot(kind = ‘pie’)` `DataFrame.plot.pie(y, labels)` `DataFrame.plot(kind = ‘pie’)`	`s.plot(kind='pie’,autopct='%1.1f%%')`  `df.plot(x='Category',y='Percentage',kind='pie')	` |
| Box Plot	| Displays the distribution of a dataset along with key statistical measures |	`DataFrame.plot.box()` `DataFrame.plot(kind = ‘box’)`	| `df_can.plot(kind='box')	`|
| Scatter Plot	| Uses Cartesian coordinates to display values for two variables	| `DataFrame.plot.scatter()` `DataFrame.plot(x, y, kind = ‘scatter’)` |	`df.plot(x='Height', y='Weight', kind='scatter')	`|


### Plotting directly with Matplotlib
| Plot Type | Description | Matplotlib Function | Example |
|--|--|--|--|
| Line Plot |	Shows trends and changes over time	|` plt.plot()` |`	plt.plot(x, y, color='red', linewidth=2)` |
| Area Plot	| Display data series as filled areas	| `plt.fill_between()`	| `plt.fill_between(x, y1, y2, color='blue', alpha=0.5)` |	
| Histogram	| Displays bars representing the data count in each interval/bin	| `plt.hist()` |	`plt.hist(data, bins=10, color='orange', edgecolor='black')`|
| Bar Chart |	Displays data using rectangular bars |	`plt.bar()` |`	plt.bar(x, height, color='green', width=0.5)	`|
| Pie Chart |	Displays data as a circular plot divided into slices, representing proportions or percentages of a whole	| `plt.pie()	`| `plt.pie(sizes, labels=labels, colors=colors, explode=explode)`|
| Box Plot |	Displays the distribution of a dataset along with key statistical measures	| `plt.boxplot()` | `plt.boxplot(data, notch=True)` |
| Scatter Plot |	Uses Cartesian coordinates to display values for two variables	| `plt.scatter()`|	`plt.scatter(x, y, color='purple', marker='o', s=50)	` |
| Subplotting	| Creating multiple plots on one figure	| `plt.subplots() `|	`fig, axes = plt.subplots(nrows=2, ncols=2)`	
| Customization	| Customizing plot: adding labels, title, legend, grid |	Various customization|	`plt.title('Title')`  `plt.xlabel('X Label')` `plt.ylabel('Y Label')`` plt.legend()` `plt.grid(True)` |

