# Web技术中心代码规范

# 前言

软件的长期价值直接源于其编码质量。在它的整个生命周期里，一个程序可能会被许多人阅读或修改。如果一个程序可以清晰的展现出它的结构和特征，那就能减少在以后对其进行修改时出错的可能性，编程规范可以帮助程序员们增加程序的健壮性。基本所有的前端代码都是暴露给公众的，所以我们更应该保证其质量。

# 规范理念

Any violation to this guide is allowed if it enhances readability.

所有的代码都要变成可供他人容易阅读的。

--引用自Dojo Javascript 语法规范

# 规范详解

**JS**** 命名规范**

1. 1必须使用Tab 键进行代码缩进，以节约代码大小，建议设置编辑器的tab为4个空格的宽度（而不是4个空格）
2. 2接口风格

| 结构 | 规则 | 例如 |
| --- | --- | --- |
| 类 | 驼峰式 | ModuleClass() |
| 公有方法 | 混合式 | getPosition() |
| 公有变量 | 混合式 | frameStyle |
| 常量 | 大写式 | DEFAULT\_FRAME\_LAYOUT |

1. 3其他建议风格，非必要

| 结构 | 规则 |
| --- | --- |
| 公有方法和属性 | 混合，例子：mixedCase |
| 私有方法和属性 | 混合，例子：\_mixedCase |
| 方法（method）参数 | 混合，例子：mixedCase |
| 本地（local）变量 | 混合，例子：mixedCase        |

1. 4所有语句结束后，必须使用; 号结束
2. 5所有变量必须是有意义的英文，严厉禁止拼音
3. 6变量允许使用公认英文缩写
4. 7类命名必须是驼峰式
5. 8常量必须所有单词大写，并且每个单词间加下划线
6. 9枚举类型时，枚举的命名必须有意义，枚举与枚举成员必须以驼峰式
7. 10常量和枚举必须在最前端定义，merge 时注意，必须把常量与枚举定义的文件放在文件列表的第一位
8. 11变量内的简写单词如果在开头则全小写：xmlDocument，如果不在开头则全大写：loadXML！！！
9. 12&quot;on&quot;只能用作事件的命名
10. 13函数开头必须是有意义的动词或动词短语
11. 14私有类的变量属性成员建议使用混合式命名，并前面下下划线
12. 15临时的全局变量放到一个全局的哈希表里，方便变量回收
13. 16所有全局变量必须初始化，尽量少用全局变量
14. 17大括号前面不能有换行符
15. 18保留字以及特有的dom属性不能作为变量名

特殊命名约定

1. 19前面加 &quot;is&quot; 的变量名应该为布尔值，亦可使用 &quot;can&quot; &quot;has&quot; &quot;should&quot;
2. 20前面加 &quot;str&quot; 的变量名应该为字符串
3. 21前面加 &quot;arr&quot; 的变量名应该为数组
4. 22前面加 &quot;num&quot; 或 &quot;count&quot; 的变量名应该为数字
5. 23&quot;o&quot; 作为局部变量或参数，表示为Object
6. 24&quot;e&quot; 作为局部变量或参数，表示为Element
7. 25&quot;evt&quot; 作为局部变量或参数，表示为event
8. 26&quot;err&quot; 作为局部变量或参数，表示为error
9. 27重复变量建议使用&quot;i&quot;, &quot;j&quot;, &quot;k&quot; （依次类推）等名称的变量(全世界公认)
10. 28能缩写的单词尽量缩写
11. 29避免产生令人误解的布尔值isNotNumber isNan
12. 30处理错误的变量，必须在后面跟着 &quot;Error&quot;
13. 31初始化用的函数必须使用 &quot;init&quot; 开头，如果一个页面只有初始化可以单独使用init()
14. 32尽量做有意义的代码折行，不要让一行代码过长。(HTML 字符串除外)
15. 33操作符建议使用空格隔开
16. 34函数调用和方法避免使用空白
17. 35逗号（,）建议使用空白隔开。
18. 36不允许频繁使用previousSibling 和nextSibling

词法结构

1. 37普通代码段应该看起来如下：

while(!isDone){
        doSomething();
        isDone =moreToDo();
}

1. 38变量定义方法如下：

var a = null,
   b = 1,
   c = 0;

1. 39函数定义方法如下：

var funcA = function(){
   var a = 0;
   ...
}

1. 40if 语句应该看起来像这样：

if(someCondition){
        statements;
}else if(someOtherCondition){
        statements;
}else{
        statements;
}

1. 41for 语句应该看起来像这样：

for(initialization;condition;update){
        statements;
}

1. 42while 语句应该看起来像这样：

while(!isDone){
        doSomething();
        isDone =moreToDo();
}

1. 43do ... while 语句应该看起来像这样：

do{
        statements;
}while(condition);

1. 44switch 语句应该看起来像这样：

switch(condition){
        case&quot;A&quot;:
                statements;                //注释
        case &quot;B&quot;:
                statements;
                break;
        default:
                statements;
                break;
}

1. 45try ... catch 语句应该看起来像这样：

try{
        statements;
}catch(ex){
        statements;
}finally{
        statements;
}

1. 46单行的if - else，while 或者for 语句也必须加入括号：

if(condition){
        statement;
}
while(condition){
        statement;
}
for(intialization;condition;update){
        statement;
}

注释规范

1. 47一些你不打算给其他人使用的函数，建议添加@ignore 让文档输出时可以忽略这段注释
2. 48一些相关的功能相关的函数，建议加上@see Function 来对上下文做索引
3. 49对于一些函数不建议或则需要注意的使用方法，必须加上@deprecated作为提醒
4. 50每个js文件的文件头都必须包含@fileoverview @author, 建议加上@version
5. 51每个函数都必须使用JsDoc 来注释他的用意
6. 52每个带参数的函数必须包含@param
7. 53每个有返回值的函数必须包含@return
8. 54构造函数必须加上@constructor
9. 55继承函数建议加上@base 表示其继承于哪个类
10. 56常用全局变量建议使用JsDoc 的注释方式
11. 57一般的变量及局部变量才用// 方式进行注释，建议在需要做注释的语句的上一行
12. 58其他详情请参考JsDoc 注释方法

其他

1. 59String 优化

循环体内的字符串累加使用join方式。例如:

varr=[];
for(vari=0;i&lt;100;i++){
        r.push(&quot;hello&quot;);
}
vark=r.join(&quot;&quot;);

1. 60Switch 建议采用hash-table

switch 可以才用Object代替例如:

vara={
        &quot;1&quot;:doAction1,
        &quot;2&quot;:doAction2,
}
functiondoAction1(){
}

functiondoAction2(){
}
a[1]();

1. 61不建议使用eval

不推荐使用eval来执行脚本。除非用来解释已经确定安全的json数据。

1. 62不要使用Function构造器。
2. 63不要给setTimeout或者setInterval传递字符串参数。
3. 64注意IE 的内存泄露问题
4. 65JavaScript代码独立

Javascript不应该被包含在HTML文件中,除非这是段特定只属于此部分的代码。在HTML中的JavaScript代码会明显增加文件大小，而且也不能对其进行缓存和压缩。

CSS命名规范

1. 1id和class命名采用该版块的英文单词或组合命名，并第一个单词小写，第二个单词首个字母大写，如：newRelease（最新产品/new+Release)
2. 2CSS样式表各区块用注释说明
3. 3尽量使用英文命名原则
4. 4不用加中杠
5. 5尽量不缩写，除非一看就明白的单词

经过组员激烈的讨论后，大家都比较偏向的命名方法如下：

**ID：** 统一采用驼峰式：　单字之间不以空格断开（例：camel case）或连接号（-，例：camel-case）、底线（\_，例：camel\_case）连结，

**Class 命名法：** 驼峰式或下划线

常见的CSS命名规则如下：

主要的mian.css

模块module.css

基本共用base.css

布局，版面layout.css

主题themes.css

专栏columns.css

文字font.css

表单forms.css

补丁mend.css

打印print.css

头：header

内容：content/container

尾：footer

导航：nav

侧栏：sidebar

栏目：column

页面外围控制整体布局宽度：wrapper

左右中：left right center

登录条：loginbar

标志：logo

广告：banner

页面主体：main

热点：hot

新闻：news

下载：download

子导航：subnav

菜单：menu

子菜单：submenu

搜索：search

友情链接：friendlink

页脚：footer

版权：copyright

滚动：scroll

内容：content

标签页：tab

文章列表：list

提示信息：msg

小技巧：tips

栏目标题：title

加入：joinus

指南：guild

服务：service

注册：regsiter

状态：status

投票：vote

合作伙伴：partner

(二)注释的写法:

/\* Footer \*/

内容区

/\* End Footer \*/

(三)id的命名:

(1)页面结构

容器: container

页头：header

内容：content/container

页面主体：main

页尾：footer

导航：nav

侧栏：sidebar

栏目：column

页面外围控制整体布局宽度：wrapper

左右中：left right center

(2)导航

导航：nav

主导航：mainbav

子导航：subnav

顶导航：topnav

边导航：sidebar

左导航：leftsidebar

右导航：rightsidebar

菜单：menu

子菜单：submenu

标题: title

摘要: summary

(3)功能

标志：logo

广告：banner

登陆：login

登录条：loginbar

注册：regsiter

搜索：search

功能区：shop

标题：title

加入：joinus

状态：status

按钮：btn

滚动：scroll

标签页：tab

文章列表：list

提示信息：msg

当前的: current

小技巧：tips

图标: icon

注释：note

指南：guild

服务：service

热点：hot

新闻：news

下载：download

投票：vote

合作伙伴：partner

友情链接：link

版权：copyright

(四)class的命名:

(1)颜色:使用颜色的名称或者16进制代码,如

.red { color: red; }

.f60 { color: #f60; }

.ff8600 { color: #ff8600; }

（2）字体大小,直接使用&quot;font+字体大小&quot;作为名称,如

.font12px { font-size: 12px; }

.font9pt {font-size: 9pt; }

(3)对齐样式,使用对齐目标的英文名称,如

.left { float:left; }

.bottom { float:bottom; }

(4)标题栏样式,使用&quot;类别+功能&quot;的方式命名,如

.barnews { }

.barproduct { }