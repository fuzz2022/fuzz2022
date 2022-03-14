欢迎讨论:
https://t.me/cffuzz

CFfuzz一句话测试工具说明

	本质上 cf工具是一款一句话模糊测试工具,因为在很多情况下,不同操作系统,不同的操作系统版本,不同web环境版本,不同的动态语言,再加上不同的防火墙,以及不同的WEB配置,webshell的通讯会面临各种奇奇怪怪的问题,带来的直观结果就是看起来一切正常,但是"连不上".

例1:
这是chopper 20131215版本在php7环境下的一个连接实例
 

例2:
某Waf设置UserAgent为BaiduSpider则直接白名单.
恰好其他WAF设置了UserAgent为BaiduSpider若请求为POST则直接拦截
这样工具就形成了冲突,难以解决.
例3:
某Waf设置了整站不允许任何POST请求.

例4:
assert函数
PHP7.2中不再支持此函数,那么PHP7中的一句话服务端将不可使用,但是PHP5是可以
所以,通讯流量使用assert的服务端和工具在PHP7+都不可使用,但在PHP5中仍是最好的选择(随意变形,超强免杀),用它不兼容,不用又可惜.

除这些情况外,还有很多PHP内置函数方面的问题,而且发现不同的版本中都有大小不一的区别,这些细小的区别,仍旧影响着一句话通讯的稳定性.大多数工具实现通讯稳定的办法是采用兼容性较好的函数(eval语言结构),因为兼容好的函数太少了,全世界都在用,大量使用带来的问题就是免杀困难.所以,解决这个问题的根本办法就是给每个环境都配一套”专属”的模板,在不同的版本环境,用不同的模板进行通讯;
Cf主要解决了webshell通讯版本之间的不兼容问题,cf可以以连接模板为准,在不同的动态语言版本,不同的防火墙都可以配置一版专属的通讯模板,最大程度的保证通讯正常.同时Cf还支持各种奇葩一句话: GET形式的一句话,Cookie形式的一句话,自定义协议头形式的一句话...
	Cf有独特的执行脚本和批量执行脚本功能,回显支持HTML和源码模式查看,操作简单,修改方便,任何相关的脚本只需要加以修改即可使用.

和传统webshell工具相比优势在于以下几点
		
		1 :  兼容传统chopper eval 一句话,且支持多达几十种chopper Eval连接方式,大大加强了传统一句话的兼容能力.也可以自己添加模板,操作简单,只要有简单的代码基础(vb)自己可以写出N多.
		
		2 :	兼容多种形式的各类新型webshell通讯模式,例如AES加密,异或加密,GET形式,Cookie形式等等,更多模式需要自己开发
		
		3 :  支持自定义加密脚本(vbs),通过标签形式对核心流量内容进行编码(标签为vb语言,可自定义).
		
		4 :  支持编码器和解码器功能
		
		5 :  通过连接模板进行循环连接,大大加强了连接的兼容性;
		
		6 :  cf有自己的调试器(包括标签和模板),很轻松就可以调试绕过拦截的连接模板(通信层高度自定义化,可自行进行调试绕过拦截).

 


7:	执行脚本功能:
cf有超强的执行脚本功能,操作简单易用且都是明文模式,支持HTML模式和源码模式显示,可任意修改代码,囊括了常用的大多数功能模块;


Phpinfo执行脚本示例:
 
Command执行脚本示例:
 

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



执行命令,
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
