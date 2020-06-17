# SQL-
SQL数据分析
![star]( https://visitor-badge.glitch.me/badge?page_id=ministep_sql_dataanalysis)

## Issues
在issues记录数据分析问题，供参考解答

## 高效率快速解决问题
- 目标: 抛出问题的目的，最终效果？
- 难点: 现在遇到的困哪是什么？
- 数据: 请提供一份数据集，便于问题重现，解决问题。
> 提供一份问题数据集，可以把问题的回答率提高到90%；问题描述清楚，目标清洗，解答率98%。

## 如果提供数据集？
- python的问题数据集，请使用Colaboratory（简称 Colab），它是一个 Jupyter 笔记本环境，在浏览器中编写和执行 Python 代码，不需要进行任何设置就可以使用，并且完全在云端运行,存储在 Google 云端硬盘，并且可以共享，免费使用。[欢迎使用 Colaboratory - Colaboratory](https://colab.research.google.com/notebooks/intro.ipynb#scrollTo=5fCEDCU_qrC0 )]
- SQL的问题数据集，可直接使用共享的SQL账号密码提供问题描述
- Issues直接复制粘贴数据集，方便解决问题的直接使用；

## Python读取剪贴板数据
```python
import pandas as pd
df = pd.read_clipboard(sep='\t')
df.head()
```

## sql数据集
```python
## python读取本地数据集
## excel文件读取
import re
import pandas  as pd
from datetime import datetime
import time

def read_xlsx(path,sheet_name):
    xlsx_file = pd.ExcelFile(path) ##路径
    table = xlsx_file.parse(sheet_name) ##选取表
    return table

if __name__ == "__main__":
    start_time = time.time() # 开始时间
    path = '/Users/username/Downloads'
    file_name ='数据.xlsx'
    path = path+"/"+file_name
    sheet_name_list = {
    'hive':'Sheet',
    'mysql':'Sheet4'
    }
    sheet_name = sheet_name_list['hive']
    #sheet_name = sheet_name_list['email']    
    #df = read_xlsx(path,sheet_name)
    #print(df.head())
    end_time = time.time() #结束时间
    print("程序耗时%f秒." % (end_time - start_time))

## 将数据集上传到Mysql数据库
import pymysql
from sqlalchemy import create_engine
#import mysql.connector as sql
def py_mysql(table,table_name):
    try:
        engine = create_engine("mysql+pymysql://ministep:datastep@111.230.56.74:3306/temp_db?charset=utf8mb4")
        table.to_sql(name=table_name,con=engine,if_exists='replace',index=False,chunksize=10000)
        #dtype={'消费金额binned':sqlalchemy.types.NVARCHAR(255)}
        print('数据库写入成功')
    except :
        print ('数据库写入失败')
if __name__ == "__main__":
    start_time = time.time() # 开始时间
    try:
        py_mysql(df,'tmp_save_data')
    except:
        print('sql查询失败')
    end_time = time.time() #结束时间
    print("程序耗时%f秒." % (end_time - start_time))
```




