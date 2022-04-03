
# HTML重难点标签

## a标签元素：
a元素（或称锚元素）是可以通过它的href属性创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他URL的超链接。其常用属性有href，target和download。
### href属性
href的值有四种情况：
1. 外部网址：可以跳转到外部的页面。
2. 内部路径：可以链接计算机里面的资源，包括图片、html文件等。
3. 伪协议：mailto：邮箱跳转到邮箱页面，tel：手机号跳转拨号页面等。
4. 内部id：可以跳转到内部锚点。
### target属性
target的值有五种情况：
1. _blank：新页面会在新窗口加载。
2. _self：默认值，新页面在当前页面加载。
3. _parent：新页面会在父框架中加载，一般在内联框架中使用。
4. _top：新页面在最顶级的框架打开。
5. 自定义：当两个a标签target自定义的属性（window.name）相同时，只打开一个新窗口，来回切换；当自定义属性与内联属性（frame.name）相同时,会显示在对应的内联页面上。
### download属性
download属性是浏览器下载URL是，它的值是下载文件的预留文件名。
## table标签元素
table元素（或称表格元素）是表示表格数据的元素，相关的标签还有thead，tbody，tfoot，th，tr和td。一般会使用border-spacing：0和border-collapse：collapse来重置默认样式。
* thead，tbody和tfoot标签分别表示表格中表头行，正文和最底部的汇总行。
* th，tr和td标签分别表示表格中单元格的头部，行和正文单元格的内容。
## img标签元素
img元素的作用是发送get请求，展示一张图片。它的常用属性有alt，height，width和src。使用max-width：100%可以达到响应式的效果。
* alt属性：表示图片未加载成功时，为用户提示的文字内容。
* height和width属性分别表示可以设置的高度和宽度。
* src属性：表示嵌入图片的文件链接。
## form标签元素
form元素的作用是向服务器发送get或post请求，然后刷新页面。它的常用属性有action，autocomplete，method和target。
* action属性：表示发送的服务器地址。
* autocomplete属性：表示input元素有默认的值。
* method属性：值有get和post两种。
* target属性类似于a标签中的target属性。
## input标签元素
input元素是让用户输入内容，一般和form元素一起使用。它的常用属性有type，name，value。
* type属性：常见值有text，password，submit，button，hidden，file，radio和checkbox，分别表示文本输入框，密码输入框，提交按钮，按钮，隐藏按钮，上传按钮，单选框，复选框。
* name属性：表示服务器接收到的名词。
* value属性：文本框的提示内容。当type是submit时，使用value属性可以改变按钮的名称。
## select+option标签属性
select+option标签属性展示一个下拉菜单栏。
## textarea标签属性
textarea标签属性展示一个多行输入框，可以用style属性resize：none去除大小调节的效果。

以上是HTML的入门内容第二部分。
=======
# HTML重难点标签

## a标签元素：
a元素（或称锚元素）是可以通过它的href属性创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他URL的超链接。其常用属性有href，target和download。
### href属性
href的值有四种情况：
1. 外部网址：可以跳转到外部的页面。
2. 内部路径：可以链接计算机里面的资源，包括图片、html文件等。
3. 伪协议：mailto：邮箱跳转到邮箱页面，tel：手机号跳转拨号页面等。
4. 内部id：可以跳转到内部锚点。
### target属性
target的值有四种情况：
1. _blank：新页面会在新窗口加载。
2. _self：默认值，新页面在当前页面加载。
3. _parent：新页面会在父框架中加载，一般在内联框架中使用。
4. _top：新页面在最顶级的框架打开。
### download属性
download属性是浏览器下载URL是，它的值是下载文件的预留文件名。
## table标签元素
table元素（或称表格元素）是表示表格数据的元素，相关的标签还有thead，tbody，tfoot，th，tr和td。一般会使用border-spacing：0和border-collapse：collapse来重置默认样式。
* thead，tbody和tfoot标签分别表示表格中表头行，正文和最底部的汇总行。
* th，tr和td标签分别表示表格中单元格的头部，行和正文单元格的内容。
## img标签元素
img元素的作用是发送get请求，展示一张图片。它的常用属性有alt，height，width和src。使用max-width：100%可以达到响应式的效果。
* alt属性：表示图片未加载成功时，为用户提示的文字内容。
* height和width属性分别表示可以设置的高度和宽度。
* src属性：表示嵌入图片的文件链接。
## form标签元素
form元素的作用是向服务器发送get或post请求，然后刷新页面。它的常用属性有action，autocomplete，method和target。
* action属性：表示发送的服务器地址。
* autocomplete属性：表示input元素有默认的值。
* method属性：值有get和post两种。
* target属性类似于a标签中的target属性。
## input标签元素
input元素是让用户输入内容，一般和form元素一起使用。它的常用属性有type，name，value。
* type属性：常见值有text，password，submit，button，hidden，file，radio和checkbox，分别表示文本输入框，密码输入框，提交按钮，按钮，隐藏按钮，上传按钮，单选框，复选框。
* name属性：表示服务器接收到的名词。
* value属性：文本框的提示内容。当type是submit是，使用value属性可以改变按钮的名称。
## select+option标签属性
select+option标签属性展示一个下拉菜单栏。
## textarea标签属性
textarea标签属性展示一个多行输入框，可以用style属性resize：none去除大小调节的效果。

以上是HTML的入门内容第二部分。

