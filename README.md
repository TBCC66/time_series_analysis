One time series analysis tool
===============


Organization
--------------------
    .
    ├── LICENSE
    ├── README.md
    ├── data
    │   └── futures
    │       └── raw
    │           └── intraday_data
    │               └── index300_main_430-510.parquet
    ├── docs
    │   ├── backtest
    │   └── log.txt
    ├── requirements.txt
    └── src
        ├── __init__.py
        ├── backtest
        │   ├── __init__.py
        │   └── jab.py
        ├── factor
        │   ├── __init__.py
        │   └── factor.py
        ├── main.py
        └── visualization
            ├── __init__.py
            └── rich_visual.py

--------

##Install

    python3 -m pip install -r requirements.txt

##Guide 

使用本回测框架很简单：
1. 在factor.py中编写需要测试的因子（注意返回格式统一）
2. 在main.py中配置测试用的数据参数，and run that shit.

回测结果会分为两部分呈现：
1. 在运行窗口会以logger的形式呈现部分回测信息，
2. 在docs/backtest文件夹下会生成每一次测试的记录文件，包括：
   
   2.1 累计收益率走势图， 处理过后的行情数据，回测的详细信息记录；
   
   2.2 如果回测结果满足一定的条件，则生成一个基于pyecharts的可视化页面。


* 我本地用的是Clickhouse，为了简单方便，数据库部分可以按需求自行搭建，factor.py和backtest.py中的数据来源改成了data中的文件


