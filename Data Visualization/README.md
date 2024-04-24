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

### Maps, Waffles, WordCloud and Seaborn

| Function | Description | Syntax | Example |
|--|--|--|--|
|Folium	 Map	| Create a map object with specified center coordinates and zoom level.	 | `folium.Map(location=[lat, lon], zoom_start=n)`	`world_map = folium.Map() ` |  ` canada =folium.Map(location=[56.130, -106.35], zoom_start=4)`|
| Marker | Add a marker to the map with custom icon, popup, and tiles   Tiles as Stamen Toner	| `folium.Marker(location=[lat , lon ], popup='Marker Popup'`, `tiles='Stamen Toner').add_to(map)`	| `folium.Marker(location=[556.130, -106.35], tooltip='Marker', tiles='Stamen Toner').add_to(world_map) `｜	
|   | Tiles as Stamen Terrain	｜ `folium.Marker(location=[lat , lon ], popup='Marker Popup', tiles='Stamen Terrain').add_to(map)` |`	folium.Marker(location=[556.130, -106.35],  tooltip='Marker', tiles='Stamen Terrain').add_to(world_map)`	|
| Circle |	Add a circle to the map with specified radius, color, and fill opacity. |	`folium.features.CircleMarker(location=[lat, lon], radius=n, color='red', fill_opacity=n).add_to(map)`	| `folium.features.CircleMarker(location=[56.130, -106.35], radius=1000, color='red', fill_opacity=0.5).add_to(world_map)	`|
| Chorpleth |	Create a choropleth map based on a GeoJSON file and a specified data column.	| `folium.Choropleth(geo_data='path/to/geojson_file', data=df, columns=['region', 'value_column'], key_on='feature.properties.id', fill_color='YlGnBu', fill_opacity=0.7, line_opacity=0.2, legend_name='Legend').add_to(map)` |	`world_map.choropleth(geo_data=world_geo, data=df_can, columns=['Country', 'Total'], key_on='feature.properties.name', fill_color='YlOrRd',fill_opacity=0.7,line_opacity=0.2,legend_name='Immigration to Canada')`	|
| PyWaffle	| Waffle	Create a waffle chart based on values and categories.	| `plt.figure(FigureClass = Waffle,rows = 20, columns = 30, values = values) waffle_chart = waffle.Waffle(values=[value1, value2, ...], rows=n, columns=n)	` | plt.figure(FigureClass = Waffle,rows = 20, columns = 30, values = df_dsn['Total'], cmap_name = 'tab20', legend = {'labels': label,'loc': 'lower left','bbox_to_anchor':(0,-0.1),'ncol': 3})	|
| Legend	| Add a legend to the waffle chart. ｜  |	waffle_chart.legend(loc='upper left', bbox_to_anchor=(1, 1))|
|  |Title	Add a title to the waffle chart.|	`waffle_chart.set_title('Waffle Chart Title') `|  |		
| Labels	| Add labels to the waffle chart. |	`waffle_chart.set_labels(['Label 1', 'Label 2', ...]`)	|  |
| WordCloud	| Create a word cloud object based on text data. |  |	`wordcloud = WordCloud().generate(text_data)	alice_wc = WordCloud(background_color='white', max_words=2000, mask=alice_mask, stopwords=stopwords) alice_wc.generate(alice_novel) plt.imshow(alice_wc, interpolation='bilinear')	`|
| Generate	| Generate the word cloud based on the text data. | `wordcloud.generate(text_data)` |  |		
| Display |	Display the word cloud using matplotlib or other plotting libraries.	|   |` plt.imshow(wordcloud, interpolation='bilinear')		 Options	Set various options for the word cloud, such as font, colors, mask, and stopwords.	`wordcloud = WordCloud(font_path='path/to/font_file',
background_color='white', colormap='Blues', mask=mask_image,  stopwords=stopwords).generate(text_data)`	|
| Seaborn ｜ barplot	Create a bar plot to visualize the relationship between a categorical variable and a numeric variable.	| `sns.barplot(x='x_variable', y='y_variable', data=dataframe)`	| `sns.barplot(x='Continent', y='Total', data=df_can1)`	|
| countplot |	Create a count plot to display the frequency of each category in a categorical variable. |	`sns.countplot(x='category', data=dataframe)	sns.countplot(x='Continent', data=df_can)	regplot`	Create a scatter plot with a linear regression line to visualize the relationship between two numeric variables.	| `sns.regplot(x='x_variable',  y='y_variable', data=dataframe)	sns.regplot(x='year', y='total', data=df_tot)`	|

Creating Dashboards with Plotly and Dash

- Dash is an Open-Source User Interface Python library for creating reactive, web-based applications.

- It is easy to build Graphical User Interfaces using Dash as it abstracts all technologies required to make the applications.

- There are two components of Dash: Core and HTML components.

- The dash_core_components describe higher-level interactive components generated with JavaScript, HTML, and CSS through the React.js library.

- The dash_html_components library has a component for every HTML tag.

- A callback function is a python function that is automatically called by Dash whenever an input component's property changes.

- The @app.callback decorator decorates the callback function in order to tell Dash to call it whenever there is a change in the input component value.

- The callback function takes input and output components as parameters and performs operations to return the desired result for the output component.


