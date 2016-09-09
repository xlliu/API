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



