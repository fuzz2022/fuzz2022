欢迎讨论:
https://t.me/cffuzz
20220315 2.11update:
	
	1:	更新了php木马查找脚本,使其支持PHP5.0以上版本
	2:	更新了"php5-8(特殊服务端)xor异或加密服务端"的服务端,使其服务端更短,兼容之前服务端
	3:	增加了"php5-7(特殊服务端)更短的服务端",使其变得更短,但流量会多出一段特征码,某些环境可能会用到

20220314 2.11Update

	1: 修复上传BUG
	2: 增加PHP Iconv Bypass 和 ImageMagick Bypass




		CFfuzz一句话测试工具说明

	   	1 :  兼容传统chopper eval 一句话,且支持多达几十种chopper Eval连接方式,大大加强了传统一句话的兼容能力.也可以自己添加模板,操作简单,只要有简单的代码基础(vb)自己可以写出N多.
		
		2 :  兼容多种形式的各类新型webshell通讯模式,例如AES加密,异或加密,GET形式,Cookie形式等等,更多模式需要自己开发
		
		3 :  支持自定义加密脚本(vbs),通过标签形式对核心流量内容进行编码(标签为vb语言,可自定义).
		
		4 :  支持编码器和解码器功能
		
		5 :  通过连接模板进行循环连接,大大加强了连接的兼容性;
		
		6 :  cf有自己的调试器(包括标签和模板),很轻松就可以调试绕过拦截的连接模板(通信层高度自定义化,可自行进行调试绕过拦截).
		
		
		
免杀一句话webshell工具		
执行脚本功能:cf有超强的执行脚本功能,操作简单易用且都是明文模式,支持HTML模式和源码模式显示,可任意修改代码,囊括了常用的大多数功能模块;
		
		
Asp执行脚本功能:
		信息查看,
		基础信息
		组件检测
		Wscript.shell环境信息
		端口扫描,
		执行命令,
		查看服务,
		查看用户,
		注册表读取
		
PHP执行脚本功能:
		Phpinfo();
		信息查看,
		基础信息
		常规函数
		危险函数查看
		禁用函数查看
		数据库支持
		GLOBALS全局信息
		PHP.INI文件信息
		读写执行检测,
		临时目录
		根目录
		当前目录
		端口扫描,
		同服务器站点探测,
		Linux ps
		ZIP压缩&解压
		查找木马
		反弹shell
		Meterpreter
		截屏
		Mysql数据库自动查找密码(测试)
		
		
执行命令:
		常规函数执行:
		system,
		passthru,
		shell_exec,
		exec,popen,
		proc_open
		PHP Bypass DisableFunctions:
		7.0-8.0-Filter Bypass 
		Apache_Cgi
		Windows:
		Com Wscript.Shell 
		Com Shell.Application 
		Linux:
		PHP 5+ LD_Preload
		PHP 5+ Pcntl_Exec
		PHP 5+ FPM
		PHP 5+ Exim_mail
		PHP 7.0-7.3+ GC_UAF
		PHP 7.0-7.4 Backtrace_UAF
		PHP 7.1-7.3 Json_UAF
		PHP 7+ SplDoublyLinkedList UAF
		PHP 7.4-FFI-BUG
		PHP 7.4-FFI-Serializable
		PHP 7+ FFI
		Procfs
		imap_open
		PHP 5+ LD_Preload BypassDisableFunctions
		
ASPX执行脚本功能:
		信息查看,
		基础信息
		Com组件
		启动项
		驱动
		查看进程,
		查看用户,
		查看服务,
		IISSPY,
		查看应用程序池,
		读取注册表,
		查看端口,
		扫描端口,
		查看网络,
		命令执行:
		ProcessStartInfo模式
		WScript.Shell模式
		Shell.Application模式
		检测目录执行权限,
		加载c#代码,
		反弹Shell,
		加载ShellCode
		Msf C #Payload上线
		Cobalt Strike C# Payload上线
		Shell.Application

使用注意:
Get请求有长度限制,一般就几K,所以在用GET的时候,上传和写入功能暂时不能使用,若要上传请使用执行脚本的写入功能.
		
		
		
