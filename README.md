# superstore-dataset
Analysis about data of a superstore to make business decisions.
Reference link for the data: https://www.kaggle.com/datasets/vivek468/superstore-dataset-final?resource=download

In this Jupyter Notebook I have analysed the dataset of the superstore to answer several questions. For example:
1. what is the best month for sales
2. which products are sold the most
3. which customer segment has received the most discounts
4. relationship between variables: a graphical representation of the relationship between the variables using a scatter plot.
5. Correlation between customer segment and quantity using a heatmap.
6. Total sales and profit per state.

## Context
With growing demands and cut-throat competitions in the market, a Superstore Giant is seeking knowledge in understanding what works best for them. They would like to understand which products, regions, categories and customer segments they should target or avoid.

## Metadata
Row ID => Unique ID for each row.

Order ID => Unique Order ID for each Customer.

Order Date => Order Date of the product.

Ship Date => Shipping Date of the Product.

Ship Mode=> Shipping Mode specified by the Customer.

Customer ID => Unique ID to identify each Customer.

Customer Name => Name of the Customer.

Segment => The segment where the Customer belongs.

Country => Country of residence of the Customer.

City => City of residence of of the Customer.

State => State of residence of the Customer.

Postal Code => Postal Code of every Customer.

Region => Region where the Customer belong.

Product ID => Unique ID of the Product.

Category => Category of the product ordered.

Sub-Category => Sub-Category of the product ordered.

Product Name => Name of the Product

Sales => Sales of the Product.

Quantity => Quantity of the Product.

Discount => Discount provided.

Profit => Profit/Loss incurred.


## Example of code
In this snippet we are going to see how to create barplots about the States and the total sales or profit about a certain state

```python
# Define the comparison variables
comparison_vars = ['Sales', 'Profit']

# Iterate through the list and create scatter plots
for var in comparison_vars:
    # 1. Group by State and calculate total sales
    state_sales = df.groupby('State')[var].sum()

    # 2. Create a bar chart
    plt.figure(figsize=(10, 6))  # Adjust figure size as desired
    state_sales.plot(kind='bar', color='skyblue')
    plt.xlabel('State')
    plt.ylabel('Total Sales [$]')
    plt.title(f'Total {var} per State')
    #plt.xticks(rotationv=45)  # Rotate x-axis labels for better readability (optional)
    plt.tight_layout()  # Adjust layout to prevent overlapping elements
    plt.show()
```
You can see the full code in the Jupyter notebook above (see main.ipynb)

The result of said code snippet, for the Profit part, is as follows:
 ![Example of OS share pie chart](https://github.com/lucalevi/user-agent-parser/blob/main/results/shares_img/piechart_os.png "Example of OS share pie chart")
