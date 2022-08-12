# SQL-
SQL数据分析
![star]( https://visitor-badge.glitch.me/badge?page_id=ministep_sql_dataanalysis)
[![HitCount](http://hits.dwyl.com/keministep/SQL_DataAnalysis.svg)](http://hits.dwyl.com/keministep/SQL_DataAnalysis)

## 内容已经迁移到：个人网站中，详情访问：
[大数据 - 大数据分析](http://bigdata.ministep.cn/ )


## Issues
在issues记录数据分析问题，供参考解答

## 高效率快速解决问题
- 目标: 抛出问题的目的，最终效果？
- 难点: 现在遇到的困哪是什么？
- 数据: 请提供一份数据集，便于问题重现，解决问题。
> 提供一份问题数据集，可以把问题的回答率提高到90%；问题描述清楚，目标清晰，解答率98%。

## 如果提供数据集？
- python的问题数据集，请使用Colaboratory（简称 Colab），它是一个 Jupyter 笔记本环境，在浏览器中编写和执行 Python 代码，不需要进行任何设置就可以使用，并且完全在云端运行,存储在 Google 云端硬盘，并且可以共享，免费使用。[欢迎使用 Colaboratory - Colaboratory](https://colab.research.google.com/notebooks/intro.ipynb#scrollTo=5fCEDCU_qrC0 )]
- SQL的问题数据集，可直接使用共享的SQL账号密码提供问题描述
- Issues直接复制粘贴数据集，方便解决问题的直接使用；

## Python读取剪贴板数据
```python
## 读取剪贴板数据
import pandas as pd
df = pd.read_clipboard(sep='\t')
df.head()
## 将df数据转换成list
data =df.to_dict('records')
## 将字典列表转成成DataFrame
df_v1 = pd.DataFrame(data)
```





