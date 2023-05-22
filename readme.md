
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