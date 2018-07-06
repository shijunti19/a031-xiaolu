# 介绍

界面化的项目管理

# 安装

- 按 f1 输入 a031，随便选择，你也可以右键选择项目管理，然后会弹出输入框要求输入目录
- 弹出填写配置保存目录，你要保存到哪个磁盘的文件夹，例如 D:\vscode，这样下次重装都不会丢失配置

# 使用教程

- [https://translate.google.cn](https://translate.google.cn)

# 截图

![界面截图](https://github.com/shijunti19/a031-xiaolu/blob/master/images/demo.png?raw=true)

# 联系

- 有任何问题联系 QQ：[527528007](http://sighttp.qq.com/authd?IDKEY=718ba7bf0e155f2ca65d5fc7646c324d9e7f2a8a8f2f20f9)    
- 在线状态：![在线状态](http://wpa.qq.com/imgd?IDKEY=718ba7bf0e155f2ca65d5fc7646c324d9e7f2a8a8f2f20f9&pic=53)     

- QQ群：[50470895](//shang.qq.com/wpa/qunwpa?idkey=c79ed4cc09a3082766690d2ea3a5f5674cb1b02d4652b9b5ef421e3f190d215e)    

## 更新

- 2018-7-6

修复初始化错误，导致无法正常运行（已经安装但是无法运行的用户，把配置目录下的 a031.json 打开看下，如果是它是一个空数组，删了）    

- 2018-7-5
  a031.json

```json
{
  "debug": true,
  "manager": {
    "theme": "default",
    "max_nav": 10 //新增了这个，控制导航里显示多少个，全部都显示在组里，默认10个
  }
}
```

如果你想导航排序，就在文件名前面加 1.用数字来控制，用 sort()排序的

## 配置说明

### 系统配置（a031.json）

- filezilla 的下载地址https://filezilla-project.org
- cmd>ftp>exe 填写 filezilla 的安装位置
- 为什么不内置 ftp 上传，因为 nodejs 全世界好像都不支持主动上传模式！
- cmd>ftp>arg 这里是启动参数
- --local={{file_path}}是固定的，当前打开文件的地址
- 其他命令：https://wiki.filezilla-project.org/Command-line_arguments_(Client)
- arg 里一条命令一行，系统会解析成数组，作为程序启动附加命令
- 当然你也可以换成其他任何 ftp 程序
- 这个文件也可以存在.vscode/a031.json 下面，这样每个项目对应一个账号

```json
{
  "manager": {
    "theme": "default"
  },
  "cmd": {
    "ftp": {
      "exe": "E:/Program Files/FileZilla FTP Client/filezilla.exe",
      "arg": ["ftp://FTP的账号:FTP密码@FTP的IP:21", "--local={{file_path}}"]
    }
  }
}
```

### 项目管理配置文件（manager）

- 都放在 manager 文件夹里
- 全部使用读取文件处理，影响 IO，上固态硬盘
- manager/default.json 这个文件是默认的，如果不存在，系统会强制生成一个
- default 文件名是项目组，中文也支持，至于出错没怎么测试！
- 例如存日记，就 manager/日记.json
- arg 存 filezilla 的启动参数，你其他程序要加启动命令都加在里面，一行一个
- content 日记内容
- path 存放目录，网址，程序目录，根据 type 类型定！
- pic_url 项目图片，本地的话放在 manager/images 下面放 1.png，就写 images/1.png，也支持远程https://www.a031.com/favicon.ico
- title 项目标题

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

- 点击创建项目
- 图片的在配置目录新建 images 文件夹然后放文件进去，然后填写 images/1.png
- 项目组就是文件名，例如写：网址,就会创建网址.json 保存这个组的项目

### 建议和 DEBUG

- **定期把配置文件夹压缩成压缩包，防止意外**
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

- **email:vscode@a031.com**
