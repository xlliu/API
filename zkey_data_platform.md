# web_service

    启动： web_services_run.sh
    关闭： web_services_kill.sh

#### edy_web_services (微信相关)

```
微信公众号展示
url: /app/weixin/five_list/<int:num>_<string:sort>
    
    params: num 展示数目
    params: sort 排序字段

return: {"result": [...]}
```

#### edy_web_services.1 (zkey平台相关)

```
问卷有效版本枚举
url: /app/exis_changelog/<string:pid>
    
    params: pid 问卷id
    
return: {"data": ...}
```

```
下载spss文件
url: /app/generator_spss/<int:version>_<string:pid>

    params: version 问卷版本
    params: pid 问卷id
    
return: xxx.spss
```

```
下载Excel文件(内部接口)
url: /app/generator_excel_zkey/<int:version>_<string:pid>_<int:skip>_<int:limit>

    params: skip 跳过多少行纪录
    params： limit 切割多少行纪录
    
return xxx.excel
```

```
下载Excel文件
url: /app/generator_excel/<int:version>_<string:pid>_<int:skip>_<int:limit>

    params: skip 跳过纪录
    params： limit 切割纪录
    
return xxx.excel
```

```
数据分析数据预览详情
url: /app/show_excel_info/<int:version>_<string:pid>_<int:skip>_<int:limit>

    params: skip 跳过记录
    params: limit 切割记录
    
return {"data": ...}
```
