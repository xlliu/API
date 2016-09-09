# mongo2mysql

    服务器启动:
        tornado_run.sh
    
    celery启动:
        celery_run.sh
        
    flower启动:
        flower_run.sh
        

```
结构化单个问卷所有结果(excel)
url: /api/pid/<string:pid>_<int:skip>_<int:limit>
    
    params: num 展示数目
    params: sort 排序字段

return: {"data": "ok"}
```

```
结构化单个问卷所有结果(spss)
url: /api/spss_pid/<string:pid>_<int:skip>_<int:limit>
    
    params: num 展示数目
    params: sort 排序字段

return: 回掉 + {"code": "ok"}
注: (佳琪)前端有相关生成页面
```

```
结构化所有问卷所有结果(spss)
url: /api/pid/all_pid
return:  {"data": "ok"}
注: 重新洗库，会丢失历史版本。慎重
```

```
结构化单个问卷单个结果(excel)
url: /api/aid/<string:aid>
    
    params: aid answer_id

return:  {"data": "ok"}
注: 点击问卷提交触发
```

```
结构化单个问卷单个结果(spss)
url: /api/spss_aid/<string:aid>
    
    params: aid answer_id

return:  {"data": "ok"}
注: 点击问卷提交触发
```

```
结构化单个问卷所有结果(excel)(同步版测试接口)
url: /api_1/pid/<string:pid>_<int:skip>_<int:limit>
    
    params: num 展示数目
    params: sort 排序字段

return: {"data": "ok"}
```

```
结构化单个问卷所有结果(spss)(同步版测试接口)
url: /api_1/spss_pid/<string:pid>_<int:skip>_<int:limit>
    
    params: num 展示数目
    params: sort 排序字段

return: 回掉 + {"code": "ok"}
注: (佳琪)前端有相关生成页面
```
