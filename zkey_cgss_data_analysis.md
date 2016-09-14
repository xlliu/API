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

# 数据库设计结构
    一. 数据库
    1. 
        地址：112.126.70.69
        端口：3306
        用户名：zkdp
        密码：Ttmster77Hj
        
        备用:
        用户名2=datapl
        密码2=Rome78Uj
    
    二. 数据库结构
    1. 树
        库: 
            data_index
            表: 
                data_index_default
                data_theme
                data_index_theme
                
            data_base
            表：
            uuid随机table名(data_index.data_index_default中列uuid+cid定位找到)
            ...
            
            data_option
            表：
            uuid随机table名(data_index.data_index_default中列uuid+cid定位找到)
            ...
注: 数据分析以data_index_default为基础定位表，

```
2. 表内部结构
data_index_default:

    CREATE TABLE `data_index_default` (
      `id` int(11) NOT NULL AUTO_INCREMENT,
      `cid` text,
      `created` text,
      `created_at` double DEFAULT NULL,
      `time` text,
      `title` text,
      `uuid` text,
      PRIMARY KEY (`id`)
    ) ENGINE=MyISAM AUTO_INCREMENT=43521 DEFAULT CHARSET=utf8;

data_index_theme:
    CREATE TABLE `data_index_theme` (
      `id` bigint(20) NOT NULL AUTO_INCREMENT,
      `cid` text,
      `created` text,
      `created_at` double DEFAULT NULL,
      `time` text,
      `title_x` text,
      `uuid` text,
      `index` double DEFAULT NULL,
      `type` text,
      `title_y` text,
      `title_name` text,
      `样本信息` double DEFAULT NULL,
      `家庭成员关系` double DEFAULT NULL,
      `社会人口属性` double DEFAULT NULL,
      `健康` double DEFAULT NULL,
      `迁移` double DEFAULT NULL,
      `生活方式` double DEFAULT NULL,
      `社会态度` double DEFAULT NULL,
      `阶层认同` double DEFAULT NULL,
      `政治参与行为与态度` double DEFAULT NULL,
      `个体认知能力` double DEFAULT NULL,
      `劳动力市场` double DEFAULT NULL,
      `社会保障` double DEFAULT NULL,
      `家庭` double DEFAULT NULL,
      `十年回顾` double DEFAULT NULL,
      `EASS模块` double DEFAULT NULL,
      `ISSP模块` double DEFAULT NULL,
      `能源模块` double DEFAULT NULL,
      `法律规范体系` double DEFAULT NULL,
      `行政执法` double DEFAULT NULL,
      `司法适用` double DEFAULT NULL,
      `社会治理` double DEFAULT NULL,
      `法治监督体系` double DEFAULT NULL,
      `法治保障体系` double DEFAULT NULL,
      `党内法规体系` double DEFAULT NULL,
      `法治效果指标` double DEFAULT NULL,
      `公民道德状况` double DEFAULT NULL,
      `公共教育` double DEFAULT NULL,
      `医疗卫生` double DEFAULT NULL,
      `住房保障` double DEFAULT NULL,
      `社会管理` double DEFAULT NULL,
      `社会网络与社会资本` double DEFAULT NULL,
      `性别与家庭角色` double DEFAULT NULL,
      `社会捐赠与社会服务` double DEFAULT NULL,
      `文化消费` double DEFAULT NULL,
      `农村模块` double DEFAULT NULL,
      `收入与消费` double DEFAULT NULL,
      `社会信任` double DEFAULT NULL,
      `环境` double DEFAULT NULL,
      `宗教` double DEFAULT NULL,
      `教育` double DEFAULT NULL,
      `性格` double DEFAULT NULL,
      `企业改制` double DEFAULT NULL,
      `政治面貌` double DEFAULT NULL,
      `职业编码` double DEFAULT NULL,
      `权重` double DEFAULT NULL,
      PRIMARY KEY (`id`)
    ) ENGINE=MyISAM AUTO_INCREMENT=43521 DEFAULT CHARSET=utf8;

data_theme：

    CREATE TABLE `data_theme` (
      `index` bigint(20) DEFAULT NULL,
      `type` text,
      `cid` text,
      `title` text,
      `title_name` text,
      `样本信息` bigint(20) DEFAULT NULL,
      `家庭成员关系` bigint(20) DEFAULT NULL,
      `社会人口属性` bigint(20) DEFAULT NULL,
      `健康` bigint(20) DEFAULT NULL,
      `迁移` bigint(20) DEFAULT NULL,
      `生活方式` bigint(20) DEFAULT NULL,
      `社会态度` bigint(20) DEFAULT NULL,
      `阶层认同` bigint(20) DEFAULT NULL,
      `政治参与行为与态度` bigint(20) DEFAULT NULL,
      `个体认知能力` bigint(20) DEFAULT NULL,
      `劳动力市场` bigint(20) DEFAULT NULL,
      `社会保障` bigint(20) DEFAULT NULL,
      `家庭` bigint(20) DEFAULT NULL,
      `十年回顾` bigint(20) DEFAULT NULL,
      `EASS模块` bigint(20) DEFAULT NULL,
      `ISSP模块` bigint(20) DEFAULT NULL,
      `能源模块` bigint(20) DEFAULT NULL,
      `法律规范体系` bigint(20) DEFAULT NULL,
      `行政执法` bigint(20) DEFAULT NULL,
      `司法适用` bigint(20) DEFAULT NULL,
      `社会治理` bigint(20) DEFAULT NULL,
      `法治监督体系` bigint(20) DEFAULT NULL,
      `法治保障体系` bigint(20) DEFAULT NULL,
      `党内法规体系` bigint(20) DEFAULT NULL,
      `法治效果指标` bigint(20) DEFAULT NULL,
      `公民道德状况` bigint(20) DEFAULT NULL,
      `公共教育` bigint(20) DEFAULT NULL,
      `医疗卫生` bigint(20) DEFAULT NULL,
      `住房保障` bigint(20) DEFAULT NULL,
      `社会管理` bigint(20) DEFAULT NULL,
      `社会网络与社会资本` bigint(20) DEFAULT NULL,
      `性别与家庭角色` bigint(20) DEFAULT NULL,
      `社会捐赠与社会服务` bigint(20) DEFAULT NULL,
      `文化消费` bigint(20) DEFAULT NULL,
      `农村模块` bigint(20) DEFAULT NULL,
      `收入与消费` bigint(20) DEFAULT NULL,
      `社会信任` bigint(20) DEFAULT NULL,
      `环境` bigint(20) DEFAULT NULL,
      `宗教` bigint(20) DEFAULT NULL,
      `教育` bigint(20) DEFAULT NULL,
      `性格` bigint(20) DEFAULT NULL,
      `企业改制` bigint(20) DEFAULT NULL,
      `政治面貌` bigint(20) DEFAULT NULL,
      `职业编码` bigint(20) DEFAULT NULL,
      `权重` bigint(20) DEFAULT NULL,
      KEY `ix_data_theme_index` (`index`)
    ) ENGINE=MyISAM DEFAULT CHARSET=utf8;

```
            
            
            
            
            