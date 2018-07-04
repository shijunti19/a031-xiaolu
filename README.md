# 介绍

界面化的项目管理

# 安装
* 按f1输入a031，随便选择，然后会弹出输入框要求输入目录
* 你也可以右键选择项目管理
* 弹出填写配置保存目录，你要保存到哪个磁盘的文件夹，例如D:\vscode，这样下次重装都不会丢失配置

# 使用教程

## 配置说明
### 系统配置（a031.json）
* filezilla的下载地址https://filezilla-project.org
* cmd>ftp>exe填写filezilla的安装位置
* 为什么不内置ftp上传，因为nodejs全世界好像都不支持主动上传模式！
* cmd>ftp>arg这里是启动参数
* --local={{file_path}}是固定的，当前打开文件的地址
* 其他命令：https://wiki.filezilla-project.org/Command-line_arguments_(Client)
* arg里一条命令一行，加载数组里
* 当然你也可以换成其他任何ftp程序
* 这个文件也可以存在.vscode/a031.json下面这样每个项目对应一个账号ftp
```json
{
	"manager": {
		"theme": "default"
	},
	"cmd": {
		"ftp": {
			"exe": "E:/Program Files/FileZilla FTP Client/filezilla.exe",
			"arg": [
				"ftp://FTP的账号:FTP密码@FTP的IP:21",
				"--local={{file_path}}"
			]
		}
	}
}
```
### 项目管理配置文件（manager）
* 都放在manager文件夹里
* 全部使用读取文件处理，影响IO，上固态硬盘
* manager/default.json
* default文件名是项目组，中文也支持，至于出错没怎么测试！
* 例如存日记，就manager/日记.json
* arg存filezilla的启动参数，你其他程序要加启动命令都加在里面，一行一个
* content日记内容
* path存放目录，网址，程序目录，根据type类型定！
* pic_url项目图片，本地的话放在manager/images下面放1.png，就写images/1.png，也支持远程https://www.a031.com/favicon.ico
* title项目标题
```json
[
	{
		"arg": "ftp://FTP的账号:FTP密码@FTP的IP:21\n--local={{file_path}}",
		"content": "内容",
		"path": "目录",
		"pic_url": "图片名",
		"title": "标题",
		"type": "1"
	},
	{
		"title": "配置目录",
		"path": "E:/zhongyao/vscode/config",
		"type": 1
	}
]
```

### 使用教程

* 点击创建项目
* 图片的在配置目录新建images文件夹然后放文件进去，然后填写images/1.png
* 项目组就是文件名，例如写：网址,就会创建网址.json保存这个组的项目

### 建议和DEBUG

[提交建议](https://github.com/shijunti19/a031-xiaolu)

### 请吃水果

微信扫一扫   
![微信扫一扫](https://github.com/shijunti19/a031-xiaolu/blob/master/images/weixin.jpg?raw=true)   
支付宝扫一扫   
![支付宝扫一扫](https://github.com/shijunti19/a031-xiaolu/blob/master/images/alipay.jpg?raw=true)   

# License

闭源 &copy; xiaolu

---
侵权或者其他任何问题联系
* **email:vscode@a031.com**
