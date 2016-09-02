Game Server Architecture

---------------------------------------------------------------------
Skynet: MinNet, Jason, Xml 等等第三方库或者自己写的库
Server: (写你的应用)
---------GamePlatform: 平台服务，所有游戏都通用的服务和框架
---------GamePoker:	扑克平台服务，所有扑克游戏都通用的服务和框架
------------------TexasLogic: 德州扑克游戏
------------------LandlordLogic: 斗地主游戏
------------------BigTwoLogic: 锄大地大老二游戏
------------------ShowHandLogic: 搜哈游戏
------------------SlogGameLogic: 水果机游戏
Build: 工程文件
---------Bin: EXE, 执行文件
---------Etc: configfile, 配置文件
---------Makefile: 
ReadMe.txt: 说明文档
---------------------------------------------------------------------

----------------------------------------------------------------
GameServer :
***********************************
CPlatServer (所有游戏平台)
    | 
CPokerServer  CEchoServer  (具体的游戏类型平台)
    |
CTexasServer  CLandlordServer  (具体的游戏逻辑)
----------------------------------------------------------------

关于登陆：
大厅模式：
	login hall:
		  PA
	C ------------> S 
		  PB
	C <------------ S

	login hall for game:
		  PC
	C ------------> S 
		  PD(token)
	C <------------ S

	login game:
		  PE(token)
	C ------------> S 
		  PF
	C <------------ S

独立模式：
	login game:
		  PA
	C ------------> S 
		  PB
	C <------------ S
		  PF
	C <------------ S
