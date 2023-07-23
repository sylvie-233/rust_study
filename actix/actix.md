# Actix

> Author: Sylvie233
>
> Date: 23/7/23
>
> Point: 

[TOC]

## 基础介绍

web框架







## 核心内容

```
artix_web:
	error:
		ResponseError:
	http:
		StatusCode:
	web:
		delete():
		get():
		post():
			to():
		resource():
			route():
		scope():
			service():
        Data:
        Json:
        Path:
		ServiceConfig:
			---
			route():
            service():
	App:
		new():
		---
		app_data():
		configure():
	HttpResponse:
		Ok:
		build():
		---
		body():
		content_type():
		json():
	HttpServer:
		new():
		---
		bind():
		run():
	Responder:
	Result:


artix_rt:
	main: 属性（标注main函数）
	test: 单元测试
	
artix-files:
	Files:
		new():
		---
		
artix-cors:
```













## API

### sqlx

```
sqlx:
	query!():
	query_as!():
		execute():
		fetch_all():
		fetch_one():
		fetch_optional():
	error:
		Error:
	postgres:
		pgPool:
		PgPoolOptions:
			new():
			---
```

数据库连接操作







### tera

```
tera:
	Context:
		new():
		---
		insert():
	Tera:
		---
		render():
```



模板引擎























