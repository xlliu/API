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

# 目录结构
```
web_services
├── edy_web_services
│   ├── common
│   │   ├── __init__.py
│   │   ├── __init__.pyc
│   │   ├── mongodb_conn.py
│   │   ├── mongodb_conn.pyc
│   │   ├── mysql_conn.py
│   │   └── mysql_conn.pyc
│   ├── edy_web_services.py
│   ├── edy_web_services.pyc
│   ├── logger.conf
│   ├── nohup.out
│   ├── requirements.txt
│   ├── server
│   │   └── __init__.py
│   └── tornado_server.py
├── edy_web_services.1
│   ├── common
│   │   ├── __init__.py
│   │   ├── __init__.pyc
│   │   ├── mongodb_conn.py
│   │   ├── mongodb_conn.pyc
│   │   ├── mysql_conn.py
│   │   ├── mysql_conn.pyc
│   │   ├── utils.py
│   │   └── utils.pyc
│   ├── db.conf
│   ├── edy_web_services.py
│   ├── edy_web_services.pyc
│   ├── logger.conf
│   ├── nohup.out
│   ├── requirements.txt
│   ├── server
│   │   └── __init__.py
│   └── tornado_server_1.py
├── edy_web_services_1.pid
├── edy_web_services.pid
├── temp_excel
│   ├── 57ce5c320f29eb9f258b4592.xlsx
│   └── 57ce8beb606f071c5e8b4875.xlsx
├── temp_spss
│   └── 57ce4ebe0f29eb73258b4586.sav
├── web_services_kill.sh
└── web_services_run.sh


# 数据库相关
    数据库：
        mongoDB
    数据库地址：
        master: 10.10.0.2
        slave: 10.10.0.5
        slave: 10.10.0.7
    端口：27017

    数据库结构：
        xyt_survey_data_two     //excel结构数据
        xyt_survey_data_two_spss        //spss option 数据
        xyt_survey_data_two_spss_format         //spss结构数据
        
    数据库表字段注解：
        1. xyt_survey_data_two：
            _id
            v_list      //value值
            k_list      //title
            用户
            开始时间
            版本
            序号        //答案aid
            结束时间
        2. xyt_survey_data_two_spss_format：
            _id
            q_type      //题型
            k_pid       //spss变量
            options     //spss选项值关系
            v_list      //spss值
            k_list      //spss变量标签
            用户
            开始时间
            版本
            序号        //答案aid
            结束时间
