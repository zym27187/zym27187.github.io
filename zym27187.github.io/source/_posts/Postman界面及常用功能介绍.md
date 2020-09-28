---
title: "Postman界面及常用功能介绍"
categories: "技术"
time: 2019-7-22 17:09:01
preview_text: 迟来的咕咕（最近终于腾出时间了），Postman界面及常用功能介绍，基于之前公司非保密性的培训文件内容，我看写的比较清晰，就放在这里了。
tags: ["Postman"]
preview: https://i.loli.net/2019/07/22/5d3580065700a19738.png
---
[Postman]: https://www.getpostman.com/ "Postman官网"

## 技术相关 ##
[Postman][postman]

以及你可能需要了解:
[JavaScript](https://www.liaoxuefeng.com/wiki/1022910821149312 "教程")

## 前言 ##
#### **&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;迟来的咕咕（最近终于腾出时间了），Postman界面及常用功能介绍，基于之前公司非保密性的培训文件内容，我看写的比较清晰，就放在这里了。** ####

## 接口基本知识简介 ##
**接口测试定义**：测试系统组件间接口的一种测试。接口测试主要用于检测外部系统与系统之间以及内部各个子系统之间的交互点。测试的重点是要检查数据的交换，传递和控制管理过程，以及系统间的相互逻辑依赖关系等。
1. **接口测试-目的**
测试接口的正确性和稳定性
2. **接口测试-原理**
模拟客户端向服务器发送请求报文，服务器接收请求报文后对相应的报文做处理并向客户端返回应答，客户端接收应答的一个过程
3. **接口测试-优点**
为高复杂性的平台带来高效的缺陷监测和质量监督能力；平台越复杂，系统越庞大，接口测试的效果越明显（提高测试效率，提升用户体验，降低研发成本）
4. **接口测试-常见接口**
    * 1.webService接口：走soap协议通过http传输，请求报文和返回报文都是xml格式的。
    * 2.**Http Api接口（应用程序编程接口）**：走http协议，通过路径来区分调用的方法，请求报文都是key-value形式的，返回报文一般都是json串。
5. **接口测试-Http请求构成**
    * 1.请求方法URL协议/版本
    * 2.请求头
    * 3.请求体
6. **接口测试-常用的请求方法**
    * **GET**：向特定的资源发出请求。（数据展示在URL上）
    * **POST**：向指定资源提交数据进行处理请求（数据包含在请求体中，可能会导致新的资源的建立或已有资源的修改）
    * **PUT**：向指定资源位置上传其最新内容。（请求方式类似POST）
    * **DELETE**：请求服务器删除请求URL所标识的资源。（请求方式类似GET）

## Postman界面常用介绍 ##

![img1](https://i.loli.net/2019/07/22/5d3585111ea6c80212.png)

## Postman界面高级介绍 ##

![img2](https://i.loli.net/2019/07/22/5d358634e482590962.png)

## Postman常用操作介绍 ##

![图片3.png](https://i.loli.net/2019/07/23/5d36749e0caec90857.png)
1.使用File -> New Tab 或者工作台中的“+”图标创建一个新的工作台；

![图片4.png](https://i.loli.net/2019/07/23/5d36749dc177083260.png)
2.根据研发提供的接口数据实际情况，选择相应的接口请求方法和请求路径；
**例：全民营销后台管理，个体推广员查询接口，请求方法：POST，接口路径/marketing/platform/promoter/user/queryPage**

![图片5.png](https://i.loli.net/2019/07/23/5d36749de15f095970.png)
3.根据研发提供的接口数据实际情况，根据需求添加Cookies、Token等认证数据，传输数据类型，浏览器版本等配置。**一般只是需要根据需求添加Cookies或Token，其他会自动在发送时添加。**
**例：通过登录全民营销抓包获取Cookies，复制添加到Headers中。（Content-Type会在添加Body时自动添加可忽略）**

![图片6.png](https://i.loli.net/2019/07/23/5d36749ded81e19419.png)
4.根据研发提供的接口数据实际情况，在Body中添加请求数据（**常用情况适合post、put请求**），请求数据类型必须严格按照接口所需类型，通常情况下选择x-www-form-urlencoded、raw。
x-www-form-urlencoded：会将表单内的数据转换为键值对，
raw：可以上传任意格式的文本，可以上传text、json、xml、html等。
**例：个体推广员查询接口数据类型为x-www-form-urlencoded，故使用图1的方式添加请求数据**

![图片7.png](https://i.loli.net/2019/07/23/5d36749dd3f1738158.png)
5.为了提高效率，可在Tests中设置断言，减少人工检验的步骤（**需一定的学习成本，可以通过代码在Tests功能中实现更多的功能，例如：将当前接口响应返回的数据加入测试集的环境变量中等**）
**例：对个体推广员查询接口设置响应断言，断言响应状态码为200。**

![图片8.png](https://i.loli.net/2019/07/23/5d36749e1ff8083419.png)
![图片40.png](https://i.loli.net/2019/07/23/5d3675fa5e8dc35417.png)
![图片41.png](https://i.loli.net/2019/07/23/5d3675fa7197212626.png)
6.根据研发提供的接口数据实际情况，填好相应的数据后，点击Send便向服务器发送请求。在Response处可查看服务器返回结果，结合数据库与研发提供的接口数据进行人工测试校验。
**Body**：响应数据，**一般使用默认的Pretty（格式化json/xml格式的内容）即可**，Pretty可根据需求选择格式化内容。
**Cookies**：常用于调用登录接口获取Cookies时查看，相对在Headers中获取直观。
**Headers**：返回的响应头，很少关注。
**Test Results**：在设置断言后有效，查看测试结果。**（通过PASS，失败FAIL，并展示断言描述及失败原因）**
**Status**：服务器返回的状态码，**2开头的状态码说明请求是成功的，3开头的状态码说明请求被重定向了，4开头的状态码说明请求端发送的请求存在问题，5开头的状态码说明服务器处理请求存在问题。详情通过百度搜索查阅。**
**Time**：服务器该接口的响应时间，衡量接口性能的其中一个标准。
**Size**：返回请求的大小，很少关注。

## Postman高级功能简介 ##
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;上面简单介绍了常用的postman进行接口测试的操作，主要以人工测试接口为主，当然Postman也拥有自动化接口测试的持续集成功能，**但缺点是需要一定的JS语言基础，进行断言的编写，变量参数的测试脚本编写，并需要搭建三方程序环境与数据库进行交互。**

这里简单介绍下一些高级功能：
1. Tests：断言，自动化实现的关键，根据预期数据进行接口正确性的判断，将接口的返回数据添加到环境变量，为下个接口提供数据等，节省了人工时间。
2. 测试集Collections：根据接口测试用例，对测试接口进行分类。执行测试集，根据排序从上到下执行所有接口测试。
3. Cookies：为整个测试集提供Cookies，多用于用户登陆后调用的接口。
4. Environment：为整个测试集提供环境变量，如基础的Url、Token、Cookies等。
5. Import：从外部导入现成测试集，测试接口，环境变量，认证数据等，需json格式。
6. Pre-request Script:设置发起请求的前置条件，需使用JS编写。
7. Mocks：模拟服务器返回自定义的数据进行接口测试。
8. Code：生成选择语言相应的接口请求的基础代码……

![img8](https://i.loli.net/2019/07/23/5d3662951b4c540826.png)
![img9](https://i.loli.net/2019/07/23/5d36629531e5d34518.png)
1.点击添加图标，添加根据需求添加测试集。
**例：以个体推广员接口为例，创建测试集。**

![图片12.png](https://i.loli.net/2019/07/23/5d3662957889544185.png)
2.点击“…”图标，使用**Add Folder**可继续细分测试集，使用**Add Request**可新创建一个请求工作台。（**不推荐按使用**）

![图片14.png](https://i.loli.net/2019/07/23/5d3662959159748781.png)
![图片15.png](https://i.loli.net/2019/07/23/5d3662956953b47698.png)
3.推荐使用在工作台预先设置好请求接口相关数据，然后点击**Save添加接口测试用例至测试集**。

![图片16.png](https://i.loli.net/2019/07/23/5d3662959dcf738405.png)
4.点击测试集右上方箭头展开，点击Run，进入测试集运行设置。

![图片17.png](https://i.loli.net/2019/07/23/5d3662958916d93436.png)
5.一般默认即可即可，点击蓝色按钮运行测试。
**Environment：环境变量**
**Lterations：循环次数**
**Delay：启动时间**
**Log Responses：记录响应信息，可选择所有、失败、不记录**
**Data：测试数据，支持从外部导入数据**

![图片18.png](https://i.loli.net/2019/07/23/5d366295af89e42951.png)
![图片20.png](https://i.loli.net/2019/07/23/5d36629558d9143086.png)
6.测试集运行结束后的测试报告，**绿色为PASS，红色为FAIL，点击有详细的请求信息**。
可通过Retry，重新进行测试集测试，**Export Results可导出json格式的测试数据**。

![图片21.png](https://i.loli.net/2019/07/23/5d367a91820c817766.png)
![图片22.png](https://i.loli.net/2019/07/23/5d367a91a2eb921674.png)
7.添加全局Cookies：点击**Add Cookie**，根据接口实际情况替换**cookie_XX=value**，根据续期替换**domain**。（cookies的作用域，所有该域名的接口都可直接使用添加的cookies）

![图片23.png](https://i.loli.net/2019/07/23/5d367a91ccfda19539.png)
![图片24.png](https://i.loli.net/2019/07/23/5d367a916f78d55137.png)
![图片25.png](https://i.loli.net/2019/07/23/5d367a91aa83541401.png)
![图片26.png](https://i.loli.net/2019/07/23/5d367a9128a9589473.png)
8.点击**齿轮**，可添加环境变量。
例：图三中添加了所有接口的基础Url。
**Variable：变量名**
**INITIAL VALUE：初始值**
**CURRENT VALUE：最新值**
设置环境变量后，对应的Url需使用参数化替换，参数变量名需与添加Variable时一致。

![图片27.png](https://i.loli.net/2019/07/23/5d367a910b4f138414.png)
![图片28.png](https://i.loli.net/2019/07/23/5d367a91bfc8820614.png)
9.点击**code**，可以生成基础的接口请求代码语句，
根据需求，可选择不同的语言，并使用**Copy to Clipboard**复制到剪贴板。

![图片29.png](https://i.loli.net/2019/07/23/5d367a911dd2051324.png)
![图片30.png](https://i.loli.net/2019/07/23/5d367a91dc3ab66345.png)
![图片31.png](https://i.loli.net/2019/07/23/5d368010868ef44899.png)
10.Postman还具有接口自动录制功能，点击**雷达图标**，进入代理设置。
**Port：代理端口（默认5555）**
**Target：自动录制接口的保存目录**
**Filters选项：通过正则表达式来筛选关心，不关心的Url，以及请求方法。**
开启代理功能后，在浏览器中设置代理服务器，便可通过访问网站自动录制接口集了。

![图片32.png](https://i.loli.net/2019/07/23/5d368010b904485561.png)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Postman可以通过三方工具xmysql连接mysql数据库，对mysql数据库进行增删查改，并提取数据作为断言依据。安装xmysql前**需安装nodejs，并配置环境变量。**使用**npm –g install xmysql**进行安装**使用xmysql -h host_name -u user_name -p user_password -d database_name**命令连接mysql数据库。

![图片33.png](https://i.loli.net/2019/07/23/5d368010abfe769756.png)
Postman的输入Url：
**http://(数据库IP):3000/api/(数据表名)**
**GET：**查询该表数据
**POST：**该表新增行数据
**DELETE：**该表删除数据
**PATCH：**更新行数据
连接Mysql数据库后，可以在Tests中使用JS语言编写脚本，通过获取数据库的数据设置断言等等。**（细节用法有兴趣的小伙伴可以自行研究）**


除以上描述的功能外，Postman可以结合其他工具，执行API持续集成测试。
例：**Postman+Newman+Jenkins**，下面做下简单的介绍。
Newman是专门用来运行Postman编写好的脚本的工具，需要额外安装。**（安装Newman前需保证已安装nodejs，并配置好nodejs的环境变量。）**
1.在Jenkins分布服务器A下使用**npm install –g newman**进行安装，并使用**newman --version**确认newman安装成功。
2.导出Postman中所需的测试集文件，如下：
![图片34.png](https://i.loli.net/2019/07/23/5d3680106301052802.png)
![图片35.png](https://i.loli.net/2019/07/23/5d36801076fa825780.png)
选择测试集，点击“…”，点击**Export**，建议按照推荐以**Collection v2.1**导出测试集的json文件，并放入Jenkins分布服务器A的A文件夹中

![图片36.png](https://i.loli.net/2019/07/23/5d368010d06e578193.png)
![图片37.png](https://i.loli.net/2019/07/23/5d3680109d20091676.png)
如图所示，下载测试集所需的环境变量及全局变量，同样放入Jenkins分布服务器A的A文件夹中

![图片38.png](https://i.loli.net/2019/07/23/5d36801093c3687409.png)
在Jenkins中构建器中，构建newman的运行任务。
基本命令：**newman run 测试集json文件路径**
常用命令参数：
**-e** 指定环境变量文件的路径        **--reporters-html-export** 指定生成Html报告路径
**-g** 指定全局变量文件路径          **-n case** 运行次数，默认为1
**-folder** 运行测试集中指定的子集   **-reporters** 指定生成报告格式

![图片39.png](https://i.loli.net/2019/07/23/5d368010c409e99562.png)
在构建后操作中，对生成报告的路径，名字等进行配置。Jenkins运行该任务后，便可在查看相应的测试报告了。
**（很多细节部分，有兴趣的小伙伴可自行研究。）**