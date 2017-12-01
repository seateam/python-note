# Python 3 小甲鱼 笔记

Tags：笔记
[Python](https://bigc.cc/note/%E5%A4%A7%E6%B5%B7/3)
 ------
[TOC]

# 模块

### [**pip**](http://blog.csdn.net/liuchunming033/article/details/39578019)

|安装指南|秒懂释义|
|:-|:-:|
|打开：[https://pip.pypa.io/en/latest/installing](https://pip.pypa.io/en/latest/installing/#installing-with-get-pip-py)||
|Ctrl + F，输入 [get-pip.py](https://bootstrap.pypa.io/get-pip.py)|查找|
|\$ python get-pip.py|安装|
|\$ pip --version|检查|
|备注：Win + X 运行命令提示符（管理员）||
|命令||
|\$ pip list|所有包|
|\$ pip list -o|有更新|
|\$ pip install '模块'|安装|
|\$ pip uninstall '模块'|卸载|
|\$ pip install --upgrade `pip`|升级|

> 我的电脑 > 属性 > 高级系统设置 > 环境变量（`Win+R` `Cmd` `Set`）> Path > 编辑
C:
%USERPROFILE%\AppData\Local\Programs\Python\Python35\Scripts
%USERPROFILE%\AppData\Local\Programs\Python\Python35

### **easy_install** [模块管理](https://pypi.python.org/pypi/setuptools)

|安装指南|秒懂释义|
|:-|:-:|
|打开：[https://pypi.python.org/pypi/setuptools](https://pypi.python.org/pypi/setuptools#windows-simplified)||
|Ctrl + F，输入 ez_setup.py|查找|
|\$ python ez_setup.py|下载|
|解压 setuptools-25.2.0.zip 至 `Python`\Python35\Scripts|解压|
|\$ python ez_setup.py|安装|
|\$ easy_install --version|检查|
|备注：Win + X 运行命令提示符（管理员）||
|命令|———|
|\$ easy_install '模块'|安装|
|\$ easy_install -U '模块'|更新|
|\$ easy_install -m '模块'|卸载|

### **pyinstaller** [打包](http://legendtkl.com/2015/11/06/pyinstaller/)
> 官网 www.PyInstaller.org
下载 [PyInstaller-3.2.tar.gz](https://github.com/pyinstaller/pyinstaller/releases/download/v3.2/PyInstaller-3.2.tar.gz)
```python
import os

cmd = r'.\PyInstaller-3.2\pyinstaller.py --onefile Miao.py'
os.system( cmd )

```
### **os** [系统](http://bbs.fishc.com/forum.php?mod=viewthread&tid=45512)
|  属性 |  说明 |
|  :-   |   :-  |
|system( string )|执行系统命令 cmd|
|getcwd( )|返回当前工作目录|
|chdir( path )|改变工作目录|
|listdir( path='.' )|目录中的文件名生成列表|
|rename( old, new )|将文件 old 重命名 new|
### **pickle** 泡菜
```python
import pickle
data= {'大海':'bigc.cc'}

with open( 'FileName' , 'wb' ) as file :
    pickle.dump( data , file ) #倒入

with open( 'FileName' , 'rb' ) as file :
    data = pickle.load( file ) #取出

print( data )
```


### **re** [正则表达式](http://bbs.fishc.com/forum.php?mod=viewthread&tid=57691)

|  属性 |  说明 |
|  :-   |   :-  |
|search( pattern, string )|匹配首个 pattern 用 .group() 访问|
|findall( pattern, string )|查找所有 pattern 返回一个 list|
|finditer( pattern, string )|查找所有 pattern 返回一个 iterable|
|sub( pattern, repl, string )|在 string 中查找 pattern 替换为 repl|
|compile( pattern，re.VERBOSE )|编译 正则表达式 #|

> 元字符

|  字符 |  对应 |   字符  |   对应  |
|  :-:   |   :-:  |   :-:  |   :-:  |
|.|any|+|{1,}|
|*|{0,}| ? |{0,1}|
| \| |or| ^ |start|
| $ |end| \\ |转译|

> 字符类

|   属性  |   说明    |
|  :-:   |   :-:  |
|  [ pattern ]  |   转译， a-z 表示范围  |
|  { a, b }  |   a<=b，匹配 a~b 次  |
|  ( ?: pattern )  |   非捕获组 常用于 findall 方法  |

> 实例

```python
IP = re.compile(r"""        #愉快的举栗时间到了
(
(?: [01]?\d?\d    |   2?[0-4]?\d    |   2?5?[0-4] )\.
(?: [01]?\d?\d    |   2?[0-4]?\d    |   2?5?[0-4] )\.
(?: [01]?\d?\d    |   2?[0-4]?\d    |   2?5?[0-4] )\.
(?: [01]?\d?\d    |   2?[0-4]?\d    |   2?5?[0-4] )
)                           #ip地址范围0到255
(?:    </td>\r\n\ \ \ \ <td>   )
( \d?\d?\d?\d?\d )          #IP端口范围0到65535
                            #测试网站www.xicidaili.com
""", re.VERBOSE)            
```
### **random** [随机生成](http://bbs.fishc.com/thread-59361-1-1.html)
|  属性 |  说明 |
|  :-   |   :-  |
|randint( a, b )|随机生成一个 a 到 b 之间的整数|
|choice( iterable )| 从 iterable 中抽取一项|

### **easygui** [图形用户界面](http://bbs.fishc.com/forum.php?mod=viewthread&tid=46069)
安装 pip install easygui

### **beautifulsoup4** [网页解析](https://www.crummy.com/software/BeautifulSoup/bs4/doc.zh/index.html)

> 安装 pip install BeautifulSoup4
` import bs4`

> Git Bash 安装 pip install wheel 下载 .whl 文件
>
> http://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml
Ctrl + F，输入lxml
>
> 根据Python版本选择下载
>
> pip install `lxml‑3.4.4‑cp35‑none‑win_amd64.whl`

|  属性 |  说明 |
|  :-   |   :-  |
|BeautifulSoup( str, 'lxml' )|解析 str （Python标准库 "html.parser"）|

|  BeautifulSoup|
|  :-   |
|find_all( 'tag' , keyword [,text=''] )|
|返回 所有 网页标签 tag 包含 pattern 的 iterable|
|find( 'tag' , keyword ).attrs|
|返回 第一个 网页标签 tag 包含 pattern 的 字典|

> keyword = { key : pattern }

|  Find |  说明 |
|  :-   |   :-  |
|attrs|返回 字典|
|get_text( )|返回 内容|
|get( key )|返回 key 对应的值


```python
import bs4 , re , urllib.request

url = 'http://baike.baidu.com/view/284853.htm'
html = urllib.request.urlopen( url ).read( ) #读取
soup = bs4.BeautifulSoup( html, 'lxml' ) #解析

>>> soup.find( 'a',{ 'href':re.compile('view') } ).attrs #查找 key
>>> {'title': '锁定', 'target': '_blank', 'href': '/view/10812319.htm', 'class': ['lock-lemma']}

url = soup.find( 'a',{ 'href':re.compile('view') } )

>>> url.get('href') #获取 key 对应的值
>>> '/view/10812319.htm'

>>> url.get_text() #获取 文字内容
>>> '锁定'
```
### **json** 轻量级数据交换

|  属性 |  说明 |
|  :-   |   :-  |
|loads( str )|载入 str 返回 字典|

### **urllib.request** [网页访问](http://bbs.fishc.com/thread-66086-1-1.html)

|  属性 |  秒懂释义 |
|  :-   |   :-  |
|urlopen( url, data=None )|返回文件对象 data 赋值则由 GET 改为 POST|
|urlretrieve( url, file )|下载文件 url 保存到文件路径 file|
|urlopen( ).getcode|返回 HTTP 状态码|

### **urllib.parse** 网址分解
|  属性 |  秒懂释义 |
|  :-   |   :-  |
|quote( string [,safe='/.=:?'] )|URL 编码|
|unquote( string )|URL 解码|

#工厂函数

### **@decorator**  装饰器

```
def decorator( eve ) :
    def tor( *args, **kwargs ) :

        print( '在这里 添加 装饰' )

        return eve( *args, **kwargs )
        '''    eve( *args, **kwargs ) == eve '''
    return tor

def jia( a, b ):
    print( '正在调用 jia 函数' )
    return a+b

@decorator #装饰器
def mer( eve ) :
    return eve
```
> \>\>\> x = mer( jia( 2, 3 ) )
> 正在调用函数 `jia( )`
> 在这里 添加 装饰
> \>\>\> x
> 5
> \>\>\> y = mer( 'everything' )
> 在这里 添加 装饰
> \>\>\> y
> 'everything'

### **yield** [生成器](http://www.cnblogs.com/coder2012/p/4990834.html)
```Python
iterable = [1, 2, 3]
def mer( iterable ):
   for i in iterable :
        yield i
a = mer( iterable )
>>> next(a)
>>> 1
```
### **List** 列表
|  属性 |  秒懂释义 |
|  :-   |   -:  |
|**index( )**|查找 (sub) 并返回参数索引值|
|**append( )**|在末尾添加一个元素|
|**extend( )**|在微末添加一个列表|
|**count( )**|返回元素数量|
|remove( )|删除一个元素|
|pop( [index] )|剪切一个元素 默认最后一个|
|sort( )|顺序排列 由小到大|
|insert( index, value )|在指定位置插入一个元素|
|copy( )|拷贝|
|clear( )|清空|
|reverse( )|原地翻转所有元素|
|备注|加粗 元组Tuple 通用|
### **Str** [字符串](http://bbs.fishc.com/forum.php?mod=viewthread&tid=38992)
>[格式化 / 转译](http://bbs.fishc.com/forum.php?mod=viewthread&tid=39140)
|  属性 |  秒懂释义 |
|  :-   |   -:  |
|lstrip ( )|去掉左边所有空格|
|join ( )|把 (sub) 为分隔符插入字符串中|
|endswith ( )|查找 ( sub,[start,end] ) 是否为结尾 返回True或False|
|center ( )|居中，并用空格填充长度 (width)|
|startswith ( )|检查是否以 (sub) 为开头 可选范围|
|islower ( )|判断是否 只有一个大写 其余小写|
|title ( )|所有单词首字母大写 其余小写|
|rjust ( )|左对齐 并在右边填充长度为 (width) 的空格|
|ljust ( )|左对齐 并在右边填充长度为 (width) 的空格|
|find ( )|查找 (sub) 是否存在 返回 (index) 否则返回 -1|
|lower ( )|所有大写 改为小写|
|index ( )|查找 (sub) 是否存在 返回 (index) 否则报错|
|isnumeric ( )|判断是否都为 数字字符|
|splitlines ( )|以 \n 为分隔符 返回列表|
|isdecimal ( )|判断是否都为 十进制数字|
|isdigit ( )|判断是否都为 数字|
|zfill ( )|右对齐 长度为 (width) ，前面用零填充|
|count ( )|查找 (sub) 出现的次数 ( sub,[start,end] ) 表示范围|
|isalpha ( )|判断是否都为 字母|
|casefold ( )|所有字符小写|
|capitalize ( )|第一个字符改为大写|
|rstrip ( )|删除末尾空格|
|swapcase ( )|翻转大小写|
|partition ( )|将字符串变成一个元组 ( 之前 ,(sub), 之后 ) |
|isspace ( )|判断是否都为 空格|
|expandtabs ( )|将 \t 转换为 空格space 默认为8个空格|
|isalnum ( )|判断是否都为 字母和数字|
|istitle ( )|判断是否都为 标题（首字母大写 其余小写） |
|translate ( )|通过 ( str.maketrans ('a','b') )定制规则，替换字符 |
|replace ( )|全部替换 旧(sub) , 新(sub) |
|isupper ( )|判断是否都为 大写|
|upper ( )|小写为大写|
|split ( )|以 (sub) 为分隔符 默认为空格 返回列表|
|strip ( )|删除前后所有 (sub) 默认为空格|

### **Map** [遍历](http://www.cnblogs.com/longdouhzt/archive/2012/05/19/2508844.html)
```python
map ( function , *iterable )

>>> def a( x , y ) :  return x + y       # a -> function
>>> b = map( a , '1357' , '2468' )       # b -> *iterable
>>> [ i for i in b ]
>>> ['12', '34', '56', '78']
```
### **Filter** [过滤](http://www.cnblogs.com/longdouhzt/archive/2012/05/19/2508844.html)
```python
filter ( function or None , iterable )

>>> def a( x ) :  return x % 2 !=0       # a -> function
>>> b = filter( a , range(15) )          # b -> iterable
>>> [ i for i in b ]
>>> [1, 3, 5, 7, 9, 11, 13]
```
### **Set** [集合](http://bbs.fishc.com/thread-45276-1-1.html)
```python
set ( iterable )
>>> set ( [1,1,2,3,4,5] )
>>> {1,2,3,4,5}
```
### **lambda** 创建匿名函数

```python
a =lambda x : x * 2

>>> a(3)
>>> 6

b = lambda x, y, z : ( x - y ) * z

>>>b(3,1,3)
>>> 6
```
# 参数说明
|  属性 |  秒懂释义 |
|  :-   |   :-  |
|function|函数|
|iterable|可迭代对象|
|path|路径|
|url|网址|
|pattern|正则表达式|
|string|字符串|
|sub|子值|

> [Cmd Markdown 简明语法手册](https://www.zybuluo.com/mdeditor?url=https://www.zybuluo.com/static/editor/md-help.markdown)

### [文件对象](http://bbs.fishc.com/forum.php?mod=viewthread&tid=45279)
|  属性 |  秒懂释义 |
|  :-   |   :-  |
|read( size=-1 )|从当前位置读取 size 字符|
|readline( [size=-1] )|读取一行 如果 size 有定义 返回 size 个字符|
|write( str )|写入字符串 str|
|tell( )|返回当前位置|
|seek( from )|指针移动到 from，0 起始 1 当前 2 末尾|

### [异常总结](http://bbs.fishc.com/forum.php?mod=viewthread&tid=45814)
|  属性 |  秒懂释义 |
|  :-   |   :-  |
|AssertionError|断言语句（assert）失败|
|AttributeError|尝试访问未知的对象属性|
|TypeError|不同类型间的无效操作|
|urllib.error.URLError|网页打不开 或 网络异常|
 ------

# $Flask$ $Web$ [开发](https://read.douban.com/reader/ebook/12186706)
> \$ cd `c:\Flasky`

> \$ python -m venv `venv`

> \$ `c:\Flasky\venv`\Scripts\activate.bat #进入

> \$ deactivate #退出

* Flask Web.bat 启动程序：（venv）$
```python
@echo off

echo python hello.py----Hasaki - 面对疾风吧！

cd c:\Flasky

start /b venv\Scripts\activate.bat
```
* Flask IDLE 启动程序：
新建： > 快捷方式 **Flask IDLE**
位置： > C:\Flasky\
目标： >
```
C:\Flasky\venv\Scripts\pythonw.exe "%UserProFile%\AppData\Local\Programs\Python\Python35\Lib\idlelib\idle.pyw"
```



 ------

|官方文档|英文|
|:-|-:|
|[Flask](http://dormousehole.readthedocs.io/en/latest/index.html) Web框架|[Frame](http://flask.pocoo.org)|
|[Jinja2](http://docs.jinkan.org/docs/jinja2/index.html) 模板引擎|[Template Engine](http://jinja.pocoo.org/)|
|[Werkzeug](http://werkzeug-docs-cn.readthedocs.io/zh_CN/latest/) WSGI 套件|[WSGI Toolkit](http://werkzeug.pocoo.org/)|

# **Git** 分布式版本控制系统

|\$|  命令 |  说明 |
|:-:|:- |:- |
|\$|git init|初始化|
|\$|git commit -am '注释'|提交|
|\$|git status |查看 状态|
|\$|git diff |查看 修改内容|
|\$|git log |历史提交|
|\$|git rm |删除提交|
|\$|git checkout `.`|清空修改|
|\$|git reflog |查看 历史快照|
|\$|git reset --hard `d606daf`|恢复快照|
|\$|git push -u origin `master`|发送 所有内容|
|\$|git push origin `master`|发送 最新修改|
||-|-|
|\$|git branch|查看 分支|
|\$|git branch `dev` |创建|
|\$|git checkout `dev` |切换|
|\$|git merge --no-ff -m '注释' `dev`  |合并|
|\$|git branch -d `dev`|删除|
|\$|git branch -a|查看 远程分支|
|\$|git checkout -b `dev` origin/`dev`|提取 远程分支|
||-|-|
|\$|git tag|查看 标签|
|\$|git tag `v1.0`|创建|
|\$|git tag -d `v1.0`|删除|
|\$|git tag `v1.0` `d606daf`|创建 指定|
|\$|git tag -a `v1.0` -m '注释' `d606daf`|创建 注释|
|\$|git show `v1.0`|查看 说明|
|\$|git push origin `v1.0`|发送 远程标签|
|\$|git push origin --tags|发送 所有标签|
|\$|git push origin :refs/tags/`v1.0`|删除 远程标签|
|||-|
|\$|git log --graph --pretty=oneline --abbrev-commit| 分支合并图|
|\$|git checkout -b|创建并切换|
|\$|git log --pretty=oneline --abbrev-commit|历史提交|

 ------
> Github [远程仓库](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001374385852170d9c7adf13c30429b9660d0eb689dd43a000)
|-|
|  :-  |
|设置 环境变量|
|%ProgramFiles%\Git\cmd|
|设置 [SSH keys](https://github.com/settings/ssh)|
|\$ ssh-keygen -t rsa -C "iwangyang@qq.com"|
|关联一个远程库|
|\$ git remote add origin https://github.com/`BIGC-HUB`/`Python`.git|
|推送所有内容|
|\$ git push -u origin master|
|克隆至本地仓库|
|\$ cd `C:\` |
|\$ git clone git@github.com:`BIGC-HUB`/`Python`.git |

 ------

`.gitignore` [忽略特殊文件](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/0013758404317281e54b6f5375640abbb11e67be4cd49e0000)
|  配置语法 |  说明  |  示例  |
|  :-   |   :-  | :- |
| / |表示目录|/venv|
| * |多个字符|*.egg|
| ? |单个字符|*.py?|
| # |注释|\# Config:|
| [ ] |包含单个字符的列表|*.py[cod]|
| ! |不忽略的文件或目录|!/hello.py|


 ------

|  Linux 命令 |  说明 |
|  :-   |   :-  |
|\$ cd 路径 |改变工作目录|
|\$ mkdir 目录 |创建工作目录|

# Pyhton 实例
### 喵图
```python
import re, urllib.request, os, sys, random

def new ( ) :
    '''获取最新地址'''
    try :
        url = urllib.request.Request('http://jandan.net/ooxx/')
        url.add_header ( 'User-Agent' , 'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/47.0.2526.108 Safari/537.36 2345Explorer/7.2.0.12990' ) #隐藏
        html = urllib.request.urlopen( url )
    except ( urllib.error.URLError ) :
        print( '网页打不开，请稍后 (或检查网络)' )
        sys.exit(0)
    miao = html.read( ).decode( 'UTF-8' )
    miao= re.search( '<span class="current-comment-page">\[(.+?)\]</span>' , miao ).group(1)
    return miao

def img ( url ) :
    '''打开网页并解析'''
    url = urllib.request.Request( url )
    url.add_header ( 'User-Agent' , 'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/47.0.2526.108 Safari/537.36 2345Explorer/7.2.0.12990' ) #隐藏
    miao = urllib.request.urlopen( url ).read( ).decode( 'UTF-8' )

    img = re.findall( '<img src="(.+?)" /></p>' , miao )
    return img

def down ( miao ) :
    '''下载图片并保存'''
    url = r'http://jandan.net/ooxx/page-%s#comments' % miao
    if not os.path.exists( r'.\miao' ) :
        os.makedirs( r'.\miao' )
    for url in img( url ) :
        urllib.request.urlretrieve( url , '.\miao\%s.jpg' % random.choice( range( int(1e+18) -1 ) ) )

def kaishi ( ) :
    '''开始么'''
    miao = int( new( ) )
    print('最新页面地址：%s' % miao )
    while True :
        try :
            miao = int ( input ( '——————————\n第几页开始：' ) )
            x = int( input ( '要下载几页：' ) )
            break
        except ( ValueError ) :
            print( '请输入整数' )
    print( '正在下载 (～￣▽￣)～* 请耐心等候' )
    try :
        for i in range( x ) :
            down( miao - i )
            print( '第 %s 页完成' % ( miao - i ) )
    except ( urllib.error.URLError ) :
        print( '网页打不开 (╯▔皿▔)╯ 请稍后 (或检查网络)' )
        sys.exit(0)

    print( '\n完成 (●ˇ∀ˇ●) 保存在 %s\miao' % os.getcwd( ) )

if __name__ == '__main__' :
    kaishi( )

#本 程 序 用 于 抓 取 页 面 图 片 JianDan.net/OOXX
```

### TS 视频文件下载/合并

[澎湃新闻地址](http://www.thepaper.cn/newsDetail_forward_1499711) [视频地址](http://cloud.quklive.com/cloud/a/embed/1468714424599811)
Google Chrome F12 -> Network -> Copy all as AHR -> TsFile.txt

```python
import urllib.request

with open ('TsFile.txt','w') as tsfile : #解析
    with open ( 'TSdata.txt' ) as file :
        for i in file :
            if '.ts' in i :
                tsfile.write( '%s\n' % i[18:-3] )
```
```python
import urllib.request

with open ('TsFile.txt' ) as ts : #下载
    for url in ts :
        local = r'.\SELF2016\%s' % url[81:-1]
        urllib.request.urlretrieve( url , local )
```
```python
import os #当前目录
cmd = r'copy /b .\SELF2016\*.ts  .\SELF2016.ts'
os.system( cmd )
```

### [有道翻译](http://fanyi.youdao.com/)
Google Chrome F12 -> Network -> Method.POST -> Request URL /  Request Headers / Form Data
```python
import urllib.request , urllib.parse , json

fanyi = input('输入要翻译的内容：')
url = urllib.request.Request('http://fanyi.youdao.com/translate?smartresult=dict&smartresult=rule&smartresult=ugc&sessionFrom=null')
url.add_header ( 'User-Agent' , 'Mozilla/5.0' )
data = {
'type' :                'AUTO' ,
'i' :                   fanyi  ,
'doctype' :             'json' ,
'xmlVersion' :           '1.8' ,
'keyfrom' :        'fanyi.web' ,
'ue' :                 'UTF-8' ,
'action' : 'FY_BY_CLICKBUTTON' ,
'typoResult' :          'true' }

data = urllib.parse.urlencode(data).encode( 'utf-8' )
result = urllib.request.urlopen( url ,data ) #POST 发送请求
result = result.read( ).decode( 'utf-8' ) #读取结果
result = json.loads( result ) #读取 json 数据交换格式

print( result['translateResult'][0][0]['tgt'] )
```

### 素数
```python
def su( n ) :
    num = list(range(n+1)) #初始化列表
    for i in range( 2, n+1 ) :
        for k in num[ i+1 : n+1 ] :
            if k % i == 0 :
                num[k] = 0
    return [ i for i in num[2:] if i != 0 ]

print ( su(100) ) #100以内素数
```

### [网页编码 \ 转译](http://bbs.fishc.com/thread-66086-1-1.html)
文件编码
```python
with open( '123.txt' , 'rb' ) as file : # 二进制读取
    file = file.read().decode() #解码
```
网页编码
```python
import urllib.request , chardet
while True : #查询网页
    try :
        url = input('请输入URL：')
        if url[:4] != 'http' :
            url = 'http://' + url

        url = urllib.request.Request( url ) #隐藏
        url.add_header ( 'User-Agent' , 'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/47.0.2526.108 Safari/537.36 2345Explorer/7.2.0.12990' )

        page = urllib.request.urlopen( url ).read( )
        break
    except ( urllib.error.URLError , NameError ):
        print('网页打不开，请重新输入(或检查网络)')

code = chardet.detect( page )['encoding'] #查询编码
if code == 'GB2312' :
    code = 'GBK'
print( '您输入的网页编码为：' , code )

page = page.decode( code,'ignore' ) #解码
with open('123.txt' ,'w',encoding= code) as file :
    file.write( page )
```
<i class="icon-asterisk icon-3x"></i> [Python 库](https://github.com/jobbole/awesome-python-cn)

- [X] 启蒙
    - [x] 完成 Python 3 小甲鱼 教程
    - [x] 完成 Git 分布式版本控制系统

- [ ] 入门
    - [ ] 完成 Flask Web 开发
