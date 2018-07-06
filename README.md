# 介绍

界面化的项目管理

# 安装

- 按 f1 输入 a031，随便选择，你也可以右键选择项目管理，然后会弹出输入框要求输入目录
- 弹出填写配置保存目录，你要保存到哪个磁盘的文件夹，例如 D:\vscode，这样下次重装都不会丢失配置

# 使用教程

# 截图

![界面截图](https://github.com/shijunti19/a031-xiaolu/blob/master/images/demo.png?raw=true)

# 联系

- 有任何问题联系 QQ：[527528007](http://sighttp.qq.com/authd?IDKEY=718ba7bf0e155f2ca65d5fc7646c324d9e7f2a8a8f2f20f9)
- 在线状态：![在线状态](https://wpa.qq.com/imgd?IDKEY=718ba7bf0e155f2ca65d5fc7646c324d9e7f2a8a8f2f20f9&pic=53)
- QQ 群：[50470895](//shang.qq.com/wpa/qunwpa?idkey=c79ed4cc09a3082766690d2ea3a5f5674cb1b02d4652b9b5ef421e3f190d215e)

## 更新

- 2018-7-6
- 修复组的排序，default 强制排在第一，然后是首字母按数字小到大，接着字母从小到大。
- 修复初始化错误，导致无法正常运行（已经安装但是无法运行的用户，把配置目录下的 a031.json 打开看下，如果是它是一个空数组，删了）

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

#### 使用说明
- ![新建项目](https://github.com/shijunti19/a031-xiaolu/blob/master/images/add_1.png?raw=true)    
- 标题：项目名称
- 项目路径：填写文件夹、网址、程序地址也可以空。
- 项目组：就是要归到manager文件夹下的哪个文件保存，文件名也是顶部的导航名，你可以写中文。
- 项目图片：在用户配置目录（安装的时候填写的目录）新建images，然后把图片放进去，例如01.png，然后这里就写images/01.png，大小是固定的：360px*180px，也支持远程地址：http://www.a031.com/resources/home/images/jingbaotuan.jpg，必须https
- 项目备注：纯粹文字
- 项目类型：文件夹就是网站根目录，执行程序就是exe所在目录，例如可以写QQ的，就会启动QQ。
- 额外参数：是执行程序所需要的额外参数，例如你想要点击ftp上传，就打开当前文件夹，就这样写：     
上面的a031.json里必须填写FileZilla所在目录，如："exe": "E:/Program Files/FileZilla FTP Client/filezilla.exe"
 ftp://FTP的账号:FTP密码@FTP的IP:21     
 --local={{file_path}}     
--local={{file_path}}是固定的，这样就行了    
换一种，你在FileZilla里新建一个文件夹a自己的服务器，然后新建站点1号3服务器   
额外参数你就写：--site=0/a自己的服务器/1号服务器    
其他命令：https://wiki.filezilla-project.org/Command-line_arguments_(Client)     
是不是很方便，这样就可以使用FileZilla的强大功能（其实吧：nodejs不支持主动模式，没人编写相应模块，我才搞成这样的）。
然后点击保存就完成了    
- ![成果图](https://github.com/shijunti19/a031-xiaolu/blob/master/images/add_2.png?raw=true)    
- 上面新建的文件都放在 自己填写的配置保存目录的manager 文件夹里
- 全部使用读取文件处理，想要速度就上固态硬盘
- manager/default.json 这个文件是默认的，如果不存在，系统会强制生成一个。
- 还不懂的话问我，上面有联系QQ和邮箱，我慢慢完善文档。

### 建议和 DEBUG

- **定期把配置文件夹压缩成压缩包，防止意外**
  [提交建议](https://github.com/shijunti19/a031-xiaolu)

### 请吃水果

微信扫一扫  
![微信扫一扫](https://github.com/shijunti19/a031-xiaolu/blob/master/images/weixin.jpg?raw=true)  
支付宝扫一扫  
![支付宝扫一扫](https://github.com/shijunti19/a031-xiaolu/blob/master/images/alipay.jpg?raw=true)

# License

- 闭源 &copy; xiaolu
- 接受付费定制
- 英文自己翻译：[https://translate.google.cn](https://translate.google.cn)

# 侵权或者其他任何问题联系

- **email:vscode@a031.com**
