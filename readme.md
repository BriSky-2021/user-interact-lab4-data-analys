
## Overview

User Interaction Technical Job 4
**data processing**

The data is a **black-friday** dataset

Displayed using **python dash**, plotly.express drawing


You can view the impact of gender, age, occupation, and length of residence on sales and sales volume, which is displayed in a pie chart.

You can view the pie chart of total sales, sales box plot, and column chart of the proportion of sales amount for men and women under different product categories.


![](https://pic1.imgdb.cn/item/646b4620e03e90d874edd07a.jpg)

You can view the sales of top20 sales goods, bar chart

![](https://pic1.imgdb.cn/item/646b466fe03e90d874ee2580.jpg)

## data analysis task

The Black Friday dataset is a dataset containing about 540,000 transaction sample data on Black Friday in retail stores. Black Friday is the second day after Thanksgiving in the United States, and it is also the first day of big purchases for Americans. Shopping malls will launch a large number of discounts and promotions. The data set contains the user's demographic information (age, gender, marital status, city category, and residence time), detailed information of the product (product id and product category), and the total purchase amount. Analyzing this data set can help merchants better understand users' purchasing behavior and provide relevant intelligence and reference for the next Black Friday.

The analysis objects of the Black Friday data set are mainly users and products, and the main characteristics are as follows:

In terms of users, users' purchasing behavior and preferences can be analyzed from dimensions such as gender, age, occupation, marital status, city category, and length of residence. For example, the number and amount of consumption of male users is much higher than that of female users, the age group of 26-35 is the main force of shopping, and the users with occupation number 4 are the most.

The analysis objects of the Black Friday data set are mainly users and products, and the main characteristics are as follows:

In terms of users, users' purchasing behavior and preferences can be analyzed from dimensions such as gender, age, occupation, marital status, city category, and length of residence.

For example, the number and amount of consumption of male users is much higher than that of female users, the age group of 26-35 is the main force of shopping, and the users with occupation number 4 are the most.

In terms of commodities, the sales and popularity of commodities can be analyzed from dimensions such as commodity id and commodity category.

For example, product category 1 has the highest sales volume, product id P00265242 has the highest sales volume 2, etc.

There are about 540,000 pieces of data in the dataset, including 12 fields. Among them, Product_Category_1 cannot be empty, and Product_Category_2 and Product_Category_3 can be empty. There are no missing values in the dataset.

## layout

the layout file is as below, which is simple:

Divide the screen into 3 parts and place 3 diagrams respectively, top left, top right, and bottom

```python
app.layout = html.Div(
    children=[
        html.H1(
            children='BlackFriday Dash',
            style={
                'textAlign': 'center'
            }
        ),
        # 创建一个包含两个子Div的Div，作为上方的行
        html.Div([
            # 创建一个包含图形组件的Div，作为左上方的列
            html.Div([
                dcc.Markdown(),# 卡片布局
                # 添加单选框组件
                dcc.Dropdown(),
                dcc.Graph(),
            ], className="six columns"),  # 使用six columns类来指定宽度为一半
            # 创建一个包含图形组件的Div，作为右上方的列
            html.Div([
                dcc.Markdown(),# 卡片布局
                # 添加单选框组件
                dcc.Dropdown(),
                dcc.Graph(),
            ], className="six columns"),  # 使用six columns类来指定宽度为一半
        ], className="row"),  # 使用row类来指定布局为水平排
        # 创建一个包含图形组件的Div，作为下方的行
        html.Div([
            dcc.Markdown(),# 卡片布局
            dcc.Graph(),
        ], className="row"),# 使用row类来指定布局为水平排
    ], className="row twelve columns")
```

![](https://pic1.imgdb.cn/item/646b4a20e03e90d874f37782.jpg)


In the upper left and upper right corners, I use radio boxes to change the specific categories and data of the displayed figures