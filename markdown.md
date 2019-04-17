## Markdown语法整理：

Markdown是一门比html更简单的标记语言，其主要用于日常写作,最终通过相应的编辑器或者脚本转换成html用于页面渲染。由于markdown基础语法的限制，出现了一些加强版的语法设计，如下文提到的markdown plus。不同的写作工具或平台采用的标准不一样，可能会有一些语法差异。

### 目录{#index}

[TOC]

### 1、标题 Headers

​	几级标题就使用几个"#"，最多支持六级标题，注意 # 和文字中间的空格不可缺

```
# this is a <h1> tag（一级标题）
## This is an <h2> tag（二级标题）
###### This is an <h6> tag（六级标题）
```



### 2、强调 Emphasis

​	通过在文字两侧加入星号 (*)或者下划线(_)或者波浪线(~)来实现文本的强调，注意符号和文本之间没有空格

```
*斜体 italic* 或者 _斜体 italic_
**粗体 bold** 或者 _粗体 bold_
~~删除线~~
以上格式可以混合使用
```

### 3、列表 List

列表项目标记通常是放在最左边，但是其实也可以缩进，在创造嵌套列表时，如果在一级列表下要添加二级列表、引用或者段落、代码块等，需要在下一行使用制表符Tab。

**1) 无序列表 unordered list**

无序列表使用 - + * 任何一种单字符都可以，注意符号和文本之间有空格

```
* item 1
* item 2
	* item2a
	* item2b
```

**2) 顺序列表 ordered list**

使用阿拉伯数字加点号的方式，注意数字和点号之间没有空格，而点号和文本之间有空格

```
1. item1
2. item2
	* item2a
	* item2b
3. item3
```

**4) 使用HTML格式插入列表，markdown的格式是可以转换成HTML的，不止是列表，其他的一切元素比如图像、链接的插入，你都可以使用HTML的格式来写作，这是完全允许的，直接再文章中写就行。**

比如：

```HTML
<Ol>
	<li> item1 </li>
    <li> item2 </li>
    <ul>
        <li> item2a </li>
        <li> item2b </li>
    </ul>

    <li> item3 </li>
<ol>
```

显示效果如下：

<Ol>
	<li> item1 </li>
    <li> item2 </li>
    <ul>
        <li> item2a </li>
        <li> item2b </li>
    </ul>
    <li> item 3</li>
</Ol>

这和我们直接使用Markdown语法是完全一样的。

### 3、引用

再引用区块内，可以使用其他的markdown语法元素，包括标题、列表、代码块等

3.1 普通引用

引用的内容可以使用 > 来表示，符号和文本之间可以有空格也可以没有

```
> 秦时明月
```

3.2.嵌套引用

在当前引用层再加上 '>' 即可，示例：

```
> 得到了不该得到的，就会失去不该失去的
	> 星星为什么这么渺小? 那是因为他们把自己放的太高了
		> 天下皆白，唯我独黑，非攻墨门，兼爱平生
```

预览效果：

> 得到了不该得到的，就会失去不该失去的
>
> > 星星为什么这么渺小? 那是因为他们把自己放的太高了
> >
> > > 天下皆白，唯我独黑，非攻墨门，简爱平生



### 4、代码块 code

* 行内代码

  用一个反引号将代码包裹 ( ` ) 包起来，空格随意

  ```
  ` print 'hello world' `
  ```

* 代码块

* 连用三个反引号将代码包起来 ( ``` )，注意当输入左边的三个反引号后，换行才能显示代码块,本文中所有的示例都是用的代码块书写

  ``` 
  def f(x):
  	return x**2 + x**(1/2)
  	"`"re"`"
  ```

* 使用不同语言的语法，如，使用javascript风格，再typora中生成代码块后会自动提示

  ```
  ​```javascript
  var num = 0;
  for (var i = 0; i < 5; i++) {
      num+=i;
  }
  console.log(num);
  ​```
  ```

***

### 5、分割线 horizontal rules

三个或者三个以上的 - 或者 * 就可以实现分割线的效果，效果如下

### 6、插入表格 table

按照如下语法画出表格的形状即可，在编辑代码时不需要考虑对齐（但是为了美观和逻辑的直观，建议代码整齐）。竖线 ( | ) 用来分栏，短横线 ( - ) 用来分割表头和其他部分，冒号( : )用于标记表格内容的对齐方式，默认左对齐。所有符号之间的空格会被忽略，不影响布局。表格的语句上一行必须为空行，不然表格不生效。但是在Typora等一些工具中会自动补全。例如下：

```
| 左对齐标题 | 右对齐标题 | 居中标题 |
| :----- 	| -----:	| :-----: |
| 老板啊，蛋炒饭 ! 好嘞，来咯| 七块钱，不用找 |
| 老板啊，再涨点| 能干干，不能滚 | 好嘞，了解 |
```

**效果如下：**

| 左对齐标题     |     右对齐标题 |    居中标题    |
| :------------- | -------------: | :------------: |
| 老板啊，蛋炒饭 |     好嘞，来咯 | 七块钱，不用找 |
| 老板啊，再涨点 | 能干干，不能滚 |   好嘞，了解   |

这里有个[神奇网站](https://www.tablesgenerator.com/markdown_tables "title")，可以自动生成你想要的表格代码，以及HTML和LaTex代码

**或者使用HTML写作：**

```
<table>
    <tr>
        <th rowspan="2">值班人员</th>
        <th>星期一</th>
        <th>星期二</th>
        <th>星期三</th>
    </tr>
    <tr>
        <td>李强</td>
        <td>张明</td>
        <td>王平</td>
    </tr>
</table>
```

**效果：**

<table>
    <caption>值日表</caption>
	<tr>
        <th>星期一</th>
        <th>星期二</th>
        <th>星期三</th>
    </tr>    
    <tr>
        <td>小明</td>
        <td>小红</td>
        <td>小虎</td>
    </tr>
</table>

### 7、插入图像

用 **\!\[图片名\](图片地址 "标题")** 来插入图片， 标题为可选项，它是当鼠标悬浮在图片时所显示的文本。在typora中可以直接拖拽本地图片到编辑器中。

* 行内式：

  语法说明： \!\[图片\]("图片地址 Title")，示例

  ```
  ![happy coding](https://github.com/the-awakend/photos/blob/master/timg.jpg "Scarlett Johansson")
  ```

  显示效果：

  ! [happy coding](https://github.com/the-awakend/photos/blob/master/timg.jpg "Scarlett Johansson")

* 参考式:

  在文档中要插入图片的地方，写 \!\[图片名\][title]

  在文档的最后写上[title]:图片地址 " 图片名"

  示例：

  ```
  ![happy coding][Scarlett Johansson]
  ......文本内容......
  ......文本内容......
  [Scarlett Johansson]:https://github.com/the-awakend/photos/blob/master/timg.jpg  "Scarlett Johansson"
  
  ```

  显示效果：

  ![happy coding][Scarlett Johansson]  

#### 另外关于图像插入：

1. 可以插入在线图片或者本地图片，注意在使用jupyter lab的时候，图片必须放在当前文件夹或当前文件夹的子文件夹下

```
![Github](url "title")（添加在线图片）
![Github](/images/logo.png "title")（添加本地图片）
```

2.  直接插入的图片，会自动靠在左侧，大小也无法由自己决定  

   我们可以使用类似HTML标签属性设置的方法来设置图片大小，

   * 按照像素大小设置，直接插入一下代码，显示效果如下

     ```
     <img src="https://img-blog.csdn.net/20151129213701642" width=50 height=50/>
     ```

     

     <img src="https://img-blog.csdn.net/20151129213701642" width=256 height=256 />

     

* 按照一定比例显示，图在下面(反正就是可以按照HTML的语法来)：

  ```
  <img src="https://img-blog.csdn.net/20151129213701642" width="50%" height="50%" />
  ```

  <img src="https://img-blog.csdn.net/20151129213701642" width="50%" height="50%" />

* 给图像加个标注，显示如下：

  ```
  <center>
  <img src="https://img-blog.csdn.net/20151129213701642" width="25%" height="25%" />
  Figure 1. Lena
  </center>
  ```

  <center>
  <img src="https://img-blog.csdn.net/20151129213701642" width="25%" height="25%" />
  Figure 1. Lena
  </center>

使用Mou编辑器语法：

```
![Mou icon](http://25.io/mou/Mou_128.png)
```

* 原图：

![Mou icon](http://25.io/mou/Mou_128.png)

* 更改大小(不知道为啥显示不出来)：

  ```
  ![Mou icon](http://25.io/mou/Mou_128.png =200x300)
  ```

  ![Mou icon](http://25.io/mou/Mou_128.png =200x300)

  或者：

  ```
  ![Mou icon](http://25.io/mou/Mou_128.png =200x)
  ```

  ![Mou icon](http://25.io/mou/Mou_128.png =200x)

### 7、插入超链接

Markdown 支持两种形式的链接语法： 行内式和参考式两种形式，行内式一般使用较多。

* 行内式:

  使用\[链接文字\]\[链接地址 "链接标题"\]的方式

  ```
  欢迎来到[我的主页](https://the-awakend.github.io/)
  
  欢迎来到[我的主页](https://the-awakend.github.io/ "他的个人主页")
  ```

  显示效果如下：

  欢迎来到[我的主页](https://the-awakend.github.io/)

  欢迎来到[我的主页](https://the-awakend.github.io/)

* 参考式:

  和图像插入的参考式一样，一般学术论文多用，在插入位置写\[链接文字\]\[标记字符\]，在文末写

  \[标记字符\]:链接地址 "链接标题"，如：

  ```
  我常去的几个网站[GitHub][1]、[知乎][2]以及[简书][3]
  ......文本内容......
  ......文本内容......
  
  [1]:https://github.com "GitHub"
  [2]:https://www.zhihu.com "知乎"
  [3]:http://www.jianshu.com "简书"
  ```

  显示效果：

  我常去的几个网站[GitHub][1]、[知乎][2]以及简书[3]    

#### 自动链接

Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用<>;包起来， Markdown 就会自动把它转成链接。一般网址的链接文字就和链接地址一样，例如：

```
<http://example.com>
<address@example.com>
```

显示效果：

<example@outlook.com>

<http://example.com>

### 8、锚点

这和web王爷中的锚点是一样的性质，网页中，锚点其实就是页内超链接，也就是链接本文档内部的某些元素，实现当前页面中的跳转。比如我这里写下一个锚点，点击回到目录，就能跳转到目录。 在目录中点击这一节，就能跳过来。还有下一节的注脚。这些根本上都是用锚点来实现的。

**注意**： Markdown Extra 只支持在标题后插入锚点，其它地方无效。

语法描述：
在你准备跳转到的指定标题后插入锚点{#标记}，然后在文档的其它地方写上连接到锚点的链接。

示例：

```
## 0. 目录{#index}
跳转到[目录]{#index}
```

显示效果：

跳转到[目录](#index)

### 9、脚注

在文字后面添加形如\[^脚注名字\]的文本，称为加注，而脚注内容一般放在文章末尾

例如：

```
“五步之内，百人不当；十年磨剑，一孤侠道”月儿[^3]率先开口念道。
“千里挥戈，万众俯首；四海江湖，百世王道”少羽[^4]紧跟着念道。
........
........
[^1]:月儿，燕国公主，墨家弟子，精通七国语言和医学药理。
[^2]:少羽，楚将项燕之孙，天赋异禀，力能拔鼎
```

效果：

“五步之内，百人不当；十年磨剑，一孤侠道”月儿[^3]率先开口念道。
“千里挥戈，万众俯首；四海江湖，百世王道”少羽[^4]紧跟着念道。

### 10、高效绘图

对于简单的图形比较容易绘制

#### 1)流程图

只适合画简单的流程图流程图方向有下面几个值

- TB 从上到下
- BT 从下到上
- RL 从右到左
- LR 从左到右
- TD 同TB  

示例代码(在pytora中提示很多，直接写入代码块，选择语言：flow即可)：

```
​```flow
st=>start: 开始 
e=>end: 登录 
io1=>inputoutput: 输入用户名密码 
sub1=>subroutine: 数据库查询子类 
cond=>condition: 是否有此用户 
cond2=>condition: 密码是否正确 
op=>operation: 读入用户信息

st->io1->sub1->cond 
cond(yes,right)->cond2 
cond(no)->io1(right) 
cond2(yes,right)->op->e 
cond2(no)->io1 
​```
```

**效果如下：**

```flow
st=>start: 开始
e=>end: 登陆
io1=>inputoutput: 输入用户名密码
sub1=>subroutine: 数据库查询子类
cond=>condition: 是否拥有该用户
cond2=>condition: 密码是否正确
op=>operation: 读入用户信息
st->io1->sub1->cond
cond(yes,right)->cond2
cond(no)->io1(right)
cond2(yes,right)->op->e
cond2(no)->io1
```

**流程图元素：**

* 开始，圆角矩形	   st=>start: 开始
* 操作，平行四边形       op=>operation: 操作说明
* 判定条件，菱形           cond=>condition: 是否?
* 文档                          
* 子流程                          sub=>subroutine: 子程序操作描述
* 用户输入输出 ，矩形   io1=>inputoutput: 输入密码
* 数据库，圆柱形 
* 注释
* 页内引用

复杂的流程图还是使用visio、X mind等专业软件比较直观，或者使用一些在线编辑器，比如[processon][https://www.processon.com/ ""]

等。

#### 2)时序图

```
​```sequence
Title:连接建立的过程
客户主机->服务器主机: 连接请求 (SYN=1,seq=client_isn）
服务器主机->客户主机: 授予连接（SYN=1,seq=client_isn）\n ack=client_isn+1
客户主机->服务器主机: 确认（SYN=0,seq=client_isn+1）\nack=server_isn+1
​```
```

**效果：**

```sequence
Title:连接建立的过程
客户主机->服务器主机: 连接请求 (SYN=1,seq=client_isn）
服务器主机->客户主机: 授予连接（SYN=1,seq=client_isn）\n ack=client_isn+1
客户主机->服务器主机: 确认（SYN=0,seq=client_isn+1）\nack=server_isn+1
```

#### 3) 甘特图

**代码：**

```
​```gantt
dateFormat YYYY-MM-DD
title 产品计划表
section 初期阶段
明确需求: 2016-03-01, 10d
section 中期阶段
跟进开发: 2016-03-11, 15d
section 后期阶段
走查测试: 2016-03-20, 9d
​```
```

**显示：**

​	不知道为什么typora不支持。

#### 4) mermaid

类markdown风格的脚本语言，以写作的方式生成图形，可以方便的绘制流程图、结构图、协作图、甘特图、鱼骨图多种图形。

支持多款编辑器，比如atom、jekyll、vim、vs code。

官网提供了在线作图的接口和一个在线的markdown编辑器，请参照：

[mermaid][https://mermaidjs.github.io/[]

[markdown plus][https://mdp.tylingsoft.com/#]

### 11、特殊符号处理

在写作的时候，如果我们要书写的内容包含 "1\." 或者 "\[\]“ 等与markdown语法元素冲突的时候，可以使用反斜杠 ”\" 来插入需要的字符，相当于转义符，主要有以下几种特殊符号需要处理：

```
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号
```

如果需要反斜杠，就连续输入两个反斜杠"\\\\\"即可

### 12、数学公式  Equations

公式需要使用Latex语法，一款在线的latex公式编辑器：[网站][https://www.codecogs.com/latex/eqneditor.php]

* 行内公式

  ​	

  ```
  这是质能守恒方程：$E=mc^2$（E=mc^2）
  ```

  显示效果：

  这是质能守恒方程：$ E=mc^2 $ (在简书中是可以渲染出来的。。。)

  

* 公式块(默认居中显示)

  ```
  {% raw %}
  $$
  e^{i\theta} = \cos \theta +i\sin \theta \
  e^z = 1 + \frac{z}{1!} + \frac{z^2}{2!} + \frac{z^3}{3!} + \cdots = \sum_{n=0}^{\infty}\frac{z^n}{n!}
  $$
  {% endraw %}
  ```
  **显示效果：**
  $$
    e^{i\theta} = \cos\theta + i\sin\theta  
  $$
  $$
    e^z = 1 + \frac{z}{1!} + \frac{z^2}{2!} + \frac{z^3}{3!} + \cdots = 
    \sum_{n=0}^{\infty}\frac{z^n}{n!}
  $$


### 13、todo list格式 (待办事项列表)

大家的手机中都会有以恶记事本，它可以用简洁的格式记录待办事项，以作备忘，PC上可能会有oneNote。而todo list这款软件t可以帮你把要做的事情列出来，一项一项，类似[思维导图](https://baike.baidu.com/item/%E6%80%9D%E7%BB%B4%E5%AF%BC%E5%9B%BE)。markdown可以语法支持书写类todo list格式的文本，在typora中这么做是很方便的。

**示例：**

```
近期任务安排:
- [x] 整理Markdown手册
- [ ] 改善项目
   - [x] 优化首页显示方式
   - [x] 修复闪退问题
   - [ ] 修复视频卡顿
- [ ] A3项目修复
   - [x] 修复数值错误
```

**效果：**

近期任务安排：

- [x] 刷题
- [ ] 准备组会内容
  - [x] 整理论文
  - [ ] 准备演示PPT
- [ ] 去医院看病

### 14、字体颜色

markdown是为文本写作而生的，它并没有考虑文字颜色这点，所以单纯的使用markdown语法是无法做到颜色的设置的。所以一般的做法就是将在写作中使用HTML语言来设置文本颜色，或者将markdown文件导出为html格式，使用html语法来渲染字体和颜色。

**如：**

```
<font face="黑体"> 我是黑体字</font>
<font color=gray size=5>我是灰色字</font>
<font color=#0099ff size=3 face="黑体">蓝色，黑体字</font>
```

**效果：**

<font face="黑体"> 我是黑体字</font>
<font color=gray size=5>我是灰色字</font>
<font color=#0099ff size=3 face="黑体">蓝色，黑体字</font>

### 15、生成目录

在你需要生成目录的地方插入"[TOC]"即可，注意：markdown只能生成标题的目录，所以你需要合理安排你的标题。



**到此结束，笔记备用！**

[Scarlett Johansson]:https://github.com/the-awakend/photos/blob/master/timg.jpg  "happy coding"
[1]:https://github.com "GitHub"
[2]:https://www.zhihu.com "知乎"
[3]:http://www.jianshu.com "简书"

[^1]: 月儿，燕国公主，墨家弟子，精通七国语言和医学药理。
[^2]: 少羽，楚将项燕之孙，天赋异禀，力能拔鼎