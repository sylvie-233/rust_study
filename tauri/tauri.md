# Tauri

> Author: Sylvie233
>
> Date: 23/7/23
>
> Point:

[TOC]

## 基础介绍

`npm create tauri-app`：项目模板





### 项目结构

```
vue+ts:
	/public:
	/src:
		/assets:
		/components:
			HelloWorld.vue:
		App.vue:
		main.ts:
		style.css:
		vite-env.d.ts:
	/src-tauri:
		/icons:
		/src:
			main.rs:
		/target:
		build.rs:
		Cargo.toml:
		tauri.conf.json:
	index.html:
	package.json:
	tsconfig.json:
	tsconfig.node.json:
	vite.config.ts:
```



`npm run tauri dev`：运行项目



#### tauri.conf.json

```
{
	$schema:
	build:
	package:
	tauri:
		alllowlist: 权限列表
			all:
			dialog:
				save:
			fs:
				all:
				scope: []
				readFile:
				writeFile:
				readDir:
			http:
				scope:
			protocol:
				asset:
		bundle:
			active:
			category:
			copyright:
			deb:
				depends:
			externalBin:
			icon:
			identifier:
			macOS:
			resources:
			shortDescription:
			targets:
			windos:
				wix:
					language:
				
		security:
			csp:
		systemTray:
			iconPath:
			iconAsTemplate:
		updater:
			active:
			endpoints:
			dialog:
			pubkey:
		windows:
			center:
			decorations:
			fullscreen:
			height:
			label:
			resizable:
			title:
			width:
			
}
```











## 核心内容

```
tauri:
	generate_context():
	generate_handler![]:
	command:
	Builder:
		default():
			---
			invoke_handle():
			run():
			setup():
				app:
					get_window():
			system_tray(): 系统托盘
	CustomMenuItem:
	Manager:
		
	SystemTray:
		---
		on_system_tray_event():
		with_menu():
	SystemTrayEvent:
		LeftClick:
		RightClick:
	SystemTrayMenu:
		---
		add_item():
		add_native_item():
	SystemTrayMenuItem:
		Separator:
	Window:
		close():
    	emit(): 触发事件
    	get_window():
    		main: 主界面（窗口label）
    		splashscreen: 开屏界面
    	show():	
```



### 后端生成

```
#[tauri::command]
fn xxx() {}


```







### 前端调用

```
import { invoke } from "@tauri-apps/api/tauri"

invoke("xxx_command", { xxx }) // 调用rust生成的函数
```



#### app

#### cli

#### clipboard

#### dialog

```
import {
	ask,
	confirm,
	open,
	
} from "@tauri-aps/api/dialog"
```





#### event

```
import {
	listen
} from "@tauri-aps/api/event"

const unlisten = async () => {
	await listen<string>("evt-name", (event) => {
	
	})
}
```

用于前端与rust通信











#### fs

```
import {
	BaseDirectory,
	copyFile,
	
} from "@tauri-aps/api/fs"

await copyFile("a.txt", "b.txt", {dir: BaseDirectory.App})
```

前端文件系统操作









#### globalShortcut







#### http

```
import {
	fetch,
	getClient,
} from "@tauri-aps/api/http"


const resp = await fetch("xxx/xxx")

const client = await getClient()

```

前端发送http请求









#### mocks

#### notification

#### os

#### path

```
import {
	appDir,
	join,
	resourceDir,
} from "@tauri-aps/api/path"
```







#### process

#### shell

#### tauri

```
import {
	convertFileSrc
} from "@tauri-aps/api/tauri"
```









#### updater

#### window

```
import {
	appWindow:
		close():
		hide():
		minimize():
		toggleMaximize():
	WebviewWindow:
		url: 模板文件路径
		getByLabel():
		---
		once():
			tauri://created:
			tauri://error
		
} from "@tauri-aps/api/window"
```

窗口操作







### 打包

`npm run tauri build`



#### WiX





#### NSIS































