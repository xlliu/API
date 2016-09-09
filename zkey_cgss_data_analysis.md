# analysis

    服务器启动: ./server.py
    celery启动: sh celery_workB.sh
    
    服务器及celery_work关闭: ./get_pid.py && ./kill.py
    
```python
单因素方差分析
url: /single_factor_variance_analysis/(.*)

    params: <tablename>*_<cid>|<tablename>*_<cid>...
    
return: IO(svg)
```

```
卡方检验
url: /chisquaretest/(.*)

    params: <tablename>*_<cid>|<tablename>*_<cid>...
    
return: IO(svg)
```

```
频率
url: /frequency/(.*)

    params: <tablename>*_<cid>|<tablename>*_<cid>...
    
return: IO(svg)
```

```
均值
url: /meanvalue/(.*)

    params: <tablename>*_<cid>|<tablename>*_<cid>...
    
return: IO(svg)
```

```
交叉表
url: /crosstable/(.*)

    params: <tablename>*_<cid>|<tablename>*_<cid>...
    
return: IO(svg)
```

```
相关分析
url: /correlationanalysis/(.*)

    params: <tablename>*_<cid>|<tablename>*_<cid>...
    
return: IO(svg)
```

```
一般线性分析
url: /generallinearregressionanalysis/(.*)

    params: <tablename>*_<cid>|<tablename>*_<cid>...
    
return: Html(string)
```

```
详情统计接口
url: /valuesummany/(.*)
    params: cid
    
return: json
```



# 目录结构
```
analysis
├── analysis.py
├── celery.pid
├── celery_workB.sh
├── celery_work.sh
├── com
│   ├── analysis
│   │   ├── common
│   │   │   ├── convent.py
│   │   │   └── __init__.py
│   │   ├── core
│   │   │   ├── base.py
│   │   │   ├── base.pyc
│   │   │   ├── chi_square_test.py
│   │   │   ├── chi_square_test.pyc
│   │   │   ├── correlation_analysis.py
│   │   │   ├── correlation_analysis.pyc
│   │   │   ├── cross_table.py
│   │   │   ├── cross_table.pyc
│   │   │   ├── data_pivot_table.py
│   │   │   ├── data_pivot_table.pyc
│   │   │   ├── frequency.py
│   │   │   ├── frequency.pyc
│   │   │   ├── general_linear_regression_analysis.py
│   │   │   ├── general_linear_regression_analysis.pyc
│   │   │   ├── __init__.py
│   │   │   ├── __init__.pyc
│   │   │   ├── mean_value.py
│   │   │   ├── mean_value.pyc
│   │   │   ├── single_factor_varance.py
│   │   │   ├── single_factor_varance.pyc
│   │   │   ├── value_summany.py
│   │   │   └── value_summany.pyc
│   │   ├── db
│   │   │   ├── conf.config
│   │   │   ├── db_engine.py
│   │   │   ├── db_engine.pyc
│   │   │   ├── db_operation.py
│   │   │   ├── __init__.py
│   │   │   └── __init__.pyc
│   │   ├── handlers
│   │   │   ├── data_analysis_handlers.py
│   │   │   ├── data_analysis_handlers.pyc
│   │   │   ├── data_summany_handlers.py
│   │   │   ├── data_summany_handlers.pyc
│   │   │   ├── defaulthandler.py
│   │   │   ├── defaulthandler.pyc
│   │   │   ├── __init__.py
│   │   │   └── __init__.pyc
│   │   ├── __init__.py
│   │   ├── __init__.pyc
│   │   ├── tasks
│   │   │   ├── data_analysis.py
│   │   │   ├── data_analysis.pyc
│   │   │   ├── __init__.py
│   │   │   └── __init__.pyc
│   │   └── utils
│   │       ├── config.py
│   │       ├── config.pyc
│   │       ├── conn.py
│   │       ├── conn.pyc
│   │       ├── err.py
│   │       ├── err.pyc
│   │       ├── __init__.py
│   │       ├── __init__.pyc
│   │       ├── log.py
│   │       └── log.pyc
│   ├── __init__.py
│   ├── __init__.pyc
│   ├── test_xlliu
│   │   ├── __init__.py
│   │   ├── test_cof
│   │   └── test_utils.py
│   ├── transfer
│   │   ├── convert
│   │   │   ├── common.py
│   │   │   ├── common.pyc
│   │   │   ├── __init__.py
│   │   │   ├── __init__.pyc
│   │   │   ├── theme.py
│   │   │   └── theme.pyc
│   │   ├── core
│   │   │   ├── __init__.py
│   │   │   ├── __init__.pyc
│   │   │   ├── spss.py
│   │   │   ├── stata.py
│   │   │   └── stata.pyc
│   │   ├── db
│   │   │   ├── conf.config
│   │   │   ├── db_engine.py
│   │   │   ├── db_engine.pyc
│   │   │   ├── db_operation.py
│   │   │   ├── __init__.py
│   │   │   └── __init__.pyc
│   │   ├── extry.py
│   │   ├── __init__.py
│   │   ├── __init__.pyc
│   │   ├── log
│   │   │   ├── applog.debug.20160908.log
│   │   │   ├── applog.error.20160908.log
│   │   │   └── applog.info.20160908.log
│   │   ├── nohup.out
│   │   └── utils
│   │       ├── config.py
│   │       ├── config.pyc
│   │       ├── conn.py
│   │       ├── conn.pyc
│   │       ├── err.py
│   │       ├── err.pyc
│   │       ├── __init__.py
│   │       ├── __init__.pyc
│   │       ├── log.py
│   │       └── log.pyc
│   └── transfer.rar
├── get_pid.py
├── kill.py
├── log
│   ├── applog.debug.20160819.log
│   └── applog.info.20160908.log
├── nohup.out
├── server.pid
├── server.py
├── static
└── templates
```