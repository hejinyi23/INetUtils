# INetUtils
一款网络请求的框架（Rxjava1 + okhttp3 + retrofit2），基本满足日常开发。提供请求时用户交互的dialog加载框，以及针对常用的请求场景的方法、错误处理、拦截器、cookie。<br><br>
## 简单请求效果图<br>
![](https://github.com/SSuperYe/INetUtils/blob/master/screenshots/example.jpg)

## 使用方法<br>
[networks包](https://github.com/SSuperYe/INetUtils/tree/master/networks)是一个module。<br>
将[networks包](https://github.com/SSuperYe/INetUtils/tree/master/networks)import到项目中，如何import module就不说了，不懂的还请自行百度<br>
之后需要将[NetWorks](https://github.com/SSuperYe/INetUtils/blob/master/networks/src/main/java/com/dangdailife/networks/network/NetWorks.java)
中的url改为各自的域名，对一些header的操作也在[NetWorks](https://github.com/SSuperYe/INetUtils/blob/master/networks/src/main/java/com/dangdailife/networks/network/NetWorks.java)的NetWorkInterceptor中<br>

具体的api[请点击](https://github.com/SSuperYe/INetUtils/blob/master/networks/src/main/java/com/dangdailife/networks/network/api/ApiService.java)

[完整的请求](https://github.com/SSuperYe/INetUtils/blob/master/app/src/main/java/com/dangdailife/test/MainActivity.java)

## something<br>
提供文件下载(支持断点续传)，参见[FileSubscriber](https://github.com/SSuperYe/INetUtils/blob/master/networks/src/main/java/com/dangdailife/networks/network/subscriber/FileSubscriber.java)
以及[startDownLoadFile方法](https://github.com/SSuperYe/INetUtils/blob/master/networks/src/main/java/com/dangdailife/networks/network/NetWorks.java)<br>

将[networks包](https://github.com/SSuperYe/INetUtils/tree/master/networks)导入后，东西都可以修改的，dialog样式、请求的设置、各自的错误处理<br>


## 新增空布局subscriber[EmptyTxtSubscriber](https://github.com/SSuperYe/INetUtils/blob/master/networks/src/main/java/com/dangdailife/networks/network/subscriber/EmptyTxtSubscriber.java)<br>
用于点击切换界面后还未请求到数据时暂时覆盖layout，需要传入Activity的layout中的TextView，该TextView应宽高覆盖显示界面，TextView具体展示可自行更改，建议在layout中include一个空布局的TextView。<br><br>

## 空布局demo[EmptyActivity](https://github.com/SSuperYe/INetUtils/blob/master/app/src/main/java/com/dangdailife/inetutils/EmptyActivity.java)<br>
同时增加了progressBar形式的加载，对比dialog形式，它无需处理dialog被主动dismiss的情景，但是需要对progressBar位置有一定的要求，比如需要在界面正上方，有需要的可以看一下demo，仅供参考<br>


## API接口更改
api接口改为自定义，否则module内使用api接口无法调用外部java bean。可以使用一个api接口，也可一个模块分配一个接口

## 初始化
使用该module前，请先执行[NetWorks](https://github.com/SSuperYe/INetUtils/blob/master/networks/src/main/java/com/dangdailife/networks/network/NetWorks.java)
中的init方法

框架正持续使用和不断完善，内部集成Rx系列相关的库(Rx的权限请求和下载)，感谢相关库的作者，还有前同事的建议，以及好友的协作[LovelyBoyXSZ](https://github.com/LovelyBoyXSZ)<br>

部分代码有做相对应的注释，仅供参考，欢迎随手star。<br>
