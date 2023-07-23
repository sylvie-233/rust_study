# Rust

> Author: Sylvie233
>
> Date: 23/7/23
>
> Point:

[TOC]

## 基础介绍

### rustc

```
rustc:
	-V:
	
```



### cargo

```
cargo:
	build:
		--bin:
	check:
	clean:
	generate:
	new: 新建项目
		--lib:
	run:
		-p: 指定包
		
	test:
	tree:
	update: 更新依赖
	version:
```

包管理工具







#### Cargo.toml

```
[workspace]: 项目工作空间
members = []

[package]
name =
version = 
edition =

[dependencies]


[[bin]]
name = "xxx"
```











## 核心内容

```
std:
	assert_eq!():
	env!():
	format!():
	panic!():
	print!():
	println!():
	vec![]:
	write!():
	str:
		from_utf8():
		---
		split():
		split_whitespace():
		to_string():
		
	Duration:
		from_millis():
		---
	Iterator:
		---
		next():
	Option:
		Some():
		None:
		---
	Result:
		OK():
		Err():
		---
		expect():
		unwrap():
	String:
		from():
		new():
		---
		as_str():
		chars():
		len():
		lines():
		push():
		push_str():
		replace():
		split():
		trim():
	Vec:
		new(): 
		---
		into_iter():
		iter():
		iter_mut():
		len():
		push():
		remove():
	---
	collections:
		HashMap:
			new():
			---
			contains_key():
			get():
			insert():
			iter():
			len():
			remove():
		HashSet:
			new():
			---
			contains():
			get():
			insert():
			iter():
			len():
			remove():
		---
	convert:
		TryFrom:
	env:
		args():
		var():
	fmt:
		---
    fs:
    	read_to_string():
    	remove_file():
    	File:
    		craete():
    		open():
    		---
    		read_to_string():
    		write():
    		write_all():
    	OpenOptions:
	io:
		prelude:
			
		stdin():
			read_line():
		stdout():
        	write():
        Read:
        Result:
        	ok():
        	OK:
        	Err:
        Write:
		---
    net:
    	TcpListener:
    		bind()
    		---
    		accept():
    		incoming():
    	TcpStream:
    		connect():
    		---
    		read():
    		write():
    	---   
	ops:
		Box:
			new():
			---
		Deref:
		Drop:
		---
	sync:
		Mutex:
			---
			lock():
	thread:
		sleep():
		spawn():
		JoinHandle:
			---
			join():
		---
	time:
		Duration:
			from_millis():
			---
	
```





### 变量

```
let xxx = xxx
```

默认变量不可变

可变变量：`mut`

常量：`const`

变量的隐藏

静态变量：`static`

类型转换：`as`

类型别名：`type`

变量引用：`ref`









#### 生命周期

```
:
	'static:
```

生命周期注解是为了保证依赖有效







##### 所有权

所有权移动只发生在堆上分配的变量



###### 借用

`&`：暂时借用所有权，使用后归还（borrow）

常用于函数传参



















#### 切片

```
&str:

let v1 = &v[1 .. 3]
```

指向**一段连续内存的指针**，array、string、vector可与切片一起使用



可变切片





#### 类型转换

`From`：trait（实现from()方法 ）

`Into`：实现into()方法



as基础类型转换







#### 基础数据类型

```
:
	i32:
	isize:
	u32:
	usize:
	f32:
	f64:
	bool:
	char:
	&str:
```

整形、浮点型、布尔型、字符型、







#### 字符串

```
let xxx: &str = "xxx" ：字符串切片



```



字符串切片



#### 数组

```
let xxx : [xxx; x] = [x, x, ...]


--- xxx
	iter():
	len():
```

固定长度













#### 枚举

```
enum xxx {
	
}
```

带数据类型的枚举







#### 元组

```
let xxx: (xxx, xxx) = (xxx, xxx)

xxx
	.0:
	.1:
```

元组解构























### 函数

```
fn xxx() -> xxx {}
```

默认返回最后一条语句执行结果

引用传递：`&`（传递地址，不影响所有权）



#### 闭包

```
|xxx| {
	
}
```

Closure

`Fn`函数声明

`move`转移



















### 流程控制

```
:
	if ... else if ... else ...
	match _ 
	for ... in ...
	while
	loop break
	if let ... else ... ：常与Option连用解构
		while let ...
	
```



#### 异常处理

`?`：尝试从Result中取出成功的值



#### match匹配











### 宏





### 属性

```
#[]:
	allow: 关闭编译警告
	cfg: 条件变异
		target_os: 
	derive: 为数据类型生成Trait实现
	doc:
	link:
	macro_use:
	main: 主函数
	no_std:
	plugin_registrar: 编译器插件
	should_panic:
	start: 入口函数
	test: 单元测试函数
	
	
#![]:
	feature: 为该crate开启特性
		box_syntax:
	
```

内部属性、外部属性









### 结构体

```
pub struct xxx {
	xxx: xxx	
}

impl xxx { // 结构体方法实现
	fn xxx(&self, xxx) -> xxx {} // 实例方法
	fn xxx(xxx) -> xxx {} // 静态方法
}
```



#### 特质

```
trait xxx {
	fn xxx();
}

// 为结构体实现特质
impl Xxx for Xxx {
	fn xxx() {}
}
```



类似接口的实现



##### 智能指针

`Box`：装箱（把数据存储到堆上）

解引用：`Deref`

析构：`Drop`









#### 元组结构体





#### 单元结构体









### 集合

迭代器





#### Vector





#### HashMap



#### HashSet













### 模块

```
pub mod xxx {
	
}
```

默认私有

`use`：使用模块

模块的嵌套

`crate`自定义模块











#### 包管理

`cargo`









### 泛型

#### 泛型限定

```
fn xxx<F>() where F:xxx {}
```

`where`关键字

函数：`Fn`

复制：`Copy`





#### 特质



#### 泛型结构体





#### 泛型函数









### 多线程















## API

### async_std

```
async_std:
	
```

`async`关键字、`await`关键字

`Future`对象	





### chrono

```
chrono:
	
```



### dotenv

```
dotenv:
	
```







### serde

```
serde:
	Deserialize:
	Serialize:
		
serde_json:
	from_str():
	to_string():
```

json序列化

































