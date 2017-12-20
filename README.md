# cef2win
本程序是编译好的,可以直接被调用的cef程序,可以实现网页程序的本地化.使用html css js编写本地程序.
# 调用方法   
在你的程序内部调用cef.exe之后，获取进程的标准输入，然后往标准输入写入json字符串的二进制字节数组即可。   
json结构如下，区分大小写。   
golang结构体实例：   
```golang
type Settings struct {   
	SrvURL      string   
	Width       int32   
	Height      int32   
	Title       string   
	URL         string   
	AppPid      int   
	LauncherPid int   
}   
```
参数说明：   
SrvURL：程序初始化之后打开的首页url，   
URL：初始化app的url   
        程序初始化之后，会打开SrvURL?url=URL，这样做的目的是使用SrvURL检查URL的健康，给予友好的显示。   
        当然可以直接设置SrvURL为入口地址，URL留空。   
Width：程序初始化之后的宽度，单位像素。   
Height：程序初始化之后的高度，单位像素。   
Title：程序标题   
AppPid：暂无使用，用0即可。   
LauncherPid：暂无使用，用0即可。   
