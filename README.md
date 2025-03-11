import pandas as pd
import numpy as np
import plotly.express as px
import plotly.graph_objects as go 
import statsmodels.api as sm
data = pd.read_csv("apple_products.csv")
data
print (data.head())
data.isnull().sum()
The dataset dose not have any missing value
data.describe()
Top ten highest_rated Iphones  on Flipkart in India
data.head()
highest_rated = data.sort_values(by = ["Star Rating"], ascending = False)

highest_rated = highest_rated.head(10)

print(highest_rated["Product Name"])
print(highest_rated)
How many ratings do the highest-rated iphones on Flipkart have?
iphones = highest_rated["Product Name"].value_counts()
label = iphones.index
count = highest_rated["Number Of Ratings"]
figure = px.bar(highest_rated ,x=label,y=count)
figure.show()
The highest number of reviews on flipkart
data.head()
iphones = highest_rated["Product Name"].value_counts()
label = iphones.index
count = highest_rated["Number Of Reviews"]
figure = px.bar(highest_rated ,x=label,y=count)
figure.show()
Relationship between the sale price of iphone and the number of rating on flipkart

figure = px.scatter(data_frame= data,x="Number Of Ratings",y="Sale Price",size = "Discount Percentage",trendline="ols",title="relationship between sales price and number of rating ")
figure.show()
The relationship between discount prencentage and the number of ratings of iphone

figure = px.scatter(data_frame= data,x="Number Of Ratings",y="Discount Percentage",size = "Sale Price",trendline="ols",title="relationship between discount and number of rating ")
figure.show()
Most expensive iphone 
most_expensive = data.loc[data["Sale Price"].idxmax()]
least_expensive = data.loc[data["Sale Price"].idxmin()]

# Display the reslut 
print("Most expensive Product:")
print(most_expensive)
print("\nleast Expensive Product:")
print(least_expensive)

