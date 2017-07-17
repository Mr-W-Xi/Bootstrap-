# Bootstrap-
快速的上手
#Bootstrap
	Bootstrap 是一个用于快速开发 Web 应用程序和网站的前端框架。
	Bootstrap 是基于 HTML、CSS、JAVASCRIPT 的
###Bootstrap 包括的内容
	
- __基本结构__：Bootstrap 提供了一个带有网格系统、链接样式、背景的基本结构。  
- __CSS__：Bootstrap 自带以下特性：全局的 CSS 设置、定义基本的 HTML 元素样式、可扩展的 class，以及一个先进的网格系统。  
- **组件**：Bootstrap 包含了十几个可重用的组件，用于创建图像、下拉菜单、导航、警告框、弹出框等等。  
- **JavaScript** 插件：Bootstrap 包含了十几个自定义的 jQuery 插件。您可以直接包含所有的插件，也可以逐个包含这些插件。  
- **定制**：您可以定制 Bootstrap 的组件、LESS 变量和 jQuery 插件来得到自己的版本。  

###下载 Bootstrap
	可以从 http://getbootstrap.com/ 上下载 Bootstrap 的最新版本  
####bootstrap是基于JQuery开发，要先引入jquery，再引入bootstrap.js  
###Bootstrap栅格布局 （网格系统）  
	Bootstrap 包含了一个响应式的、移动设备优先的、不固定的网格系统，可以随着设备或视口
	大小的增加而适当地扩展到 12 列。它包含了用于简单的布局选项的预定义类，也包含了用于
	生成更多语义布局的功能强大的混合类  
###媒体查询  
	Bootstrap 中的媒体查询允许基于视口大小移动、显示并隐藏内容。
	下面的媒体查询在 LESS 文件中使用，用来创建 Bootstrap 网格系统中的关键的分界点阈值。 
  
	/* 超小设备（**手机**，小于 768px） */
	/* Bootstrap 中默认情况下没有媒体查询 */
	
	/* 小型设备（**平板电脑**，768px 起） */
	@media (min-width: @screen-sm-min) { ... }
	
	/* 中型设备（**台式电脑**，992px 起） */
	@media (min-width: @screen-md-min) { ... }
	
	/* 大型设备（**大台式电脑**，1200px 起） */
	@media (min-width: @screen-lg-min) { ... }
+我们有时候也会在媒体查询代码中包含 max-width，从而将 CSS 的影响限制在更小范围的屏幕大小之内。

	/*1200以上*/
	@media all and (min-width:1200px){...}
	/* 小屏电脑 */
	@media all and (min-width:992px) and (max-width:1199px){
		body{...}
	}
	/* 平板设备 */
	@media all and (min-width:768px) and (max-width:991px){
		body{...}
	}
	/* 移动设备 */
	@media all and (max-width:767px){
		body{...}
	}

####栅格布局怎么分？
	container-flud 包裹 container 包裹 row 包裹 col-xxx
#####注意点
- 不要使用系统类名
- 要学习bootstrap的命名规范
- 栅格布局中的一行只能排12格，没有0.5格。
####栅格布局响应
<table>
  <tr>
      <td>..................</td>
      <td>超小设备手机（<768px）</td>
	  <td>小型设备平板电脑（≥768px）</td>
	  <td>中型设备台式电脑（≥992px）</td>
	  <td>大型设备台式电脑（≥1200px）</td>
  </tr>
  <tr>
      <td>网格行为</td>
      <td>一直是水平的</td>
      <td>以折叠开始，断点以上是水平的</td>
      <td>以折叠开始，断点以上是水平的</td>
      <td>以折叠开始，断点以上是水平的</td>
  </tr>
<tr>
      <td>最大容器宽度</td>
      <td>None (auto)</td>
      <td>750px</td>
      <td>	970px</td>
      <td>1170px</td>
  </tr>
<tr>
      <td>Class 前缀</td>
      <td>.col-xs-</td>
      <td>.col-sm-</td>
      <td>.col-md-</td>
      <td>.col-lg-</td>
  </tr>
<tr>
      <td>列（column）数</td>
      <td>12</td>
      <td>12</td>
      <td>12</td>
      <td>12</td>
  </tr>
<tr>
      <td>最大列（column）宽</td>
      <td>自动</td>
      <td>~62px</td>
      <td>~81px</td>
      <td>~97px</td>
  </tr>
<tr>
      <td>槽（gutter）宽</td>
      <td>30px （每列左右均有 15px）</td>
      <td>30px （每列左右均有 15px）</td>
      <td>30px （每列左右均有 15px）</td>
      <td>30px （每列左右均有 15px）</td>
  </tr>
<tr>
      <td>是</td>
      <td>是</td>
      <td>是</td>
      <td>是</td>
      <td>是</td>
  </tr>
<tr>
      <td>是</td>
      <td>是</td>
      <td>是</td>
      <td>是</td>
      <td>是</td>
  </tr>
<tr>
      <td>是</td>
      <td>是</td>
      <td>是</td>
      <td>是</td>
      <td>是</td>
  </tr>

</table>
#####布局思想
	以父级容器来控制响应的内容
####列偏移
	使用 .col-md-offset-* 类可以将列向右侧偏移。这些类实际是通过使用 * 选择器为当前
	元素增加了左侧的边距（margin）。例如，.col-md-offset-4 类将 .col-md-4 元素向右侧
	偏移了4个列（column）的宽度。
<table>
 <tr>
  <td>col-lg-oggset-1</td>
  <td>从左向右推，会把div挤下去</td>
 </tr>
 <tr>
  <td>col-lg-push-1</td>
  <td>从左向右推，不会把div挤下去</td>
 </tr>
 <tr>
  <td>col-lg-pull-1</td>
  <td>从右向左推，不会把div挤下去</td>
 </tr>
</table>
####图片/字体布局
<table>
 <tr>
  <td>text-left</td>
  <td>图片/字体 靠左</td>
 </tr>
 <tr>
  <td>text-center</td>
  <td>居中</td>
 </tr>
 <tr>
  <td>text-right</td>
  <td>图片/字体 靠右</td>
 </tr>
 <tr>
  <td>text-justify</td>
  <td>换行</td>
 </tr>
 <tr>
  <td>text-nowrap</td>
  <td>不换行</td>
 </tr>
</table>
##可用的类
通过单独或联合使用以下列出的类，可以针对不同屏幕尺寸隐藏或显示页面内容。
需要谨慎使用这些工具，避免在同一个站点创建完全不同的版本。**响应式实用工具目前只适用于块和表切换。**
<table>
  <tr>
      <td>......................</td>
      <td>超小设备手机（<768px）</td>
	  <td>小型设备平板电脑（≥768px）</td>
	  <td>中型设备台式电脑（≥992px）</td>
	  <td>大型设备台式电脑（≥1200px）</td>
  </tr>
  <tr>
      <td>.visible-xs-*</td>
      <td>可见</td>
      <td>隐藏</td>
      <td>隐藏</td>
      <td>隐藏</td>
  </tr>
<tr>
      <td>.visible-sm-*</td>
      <td>隐藏</td>
      <td>可见</td>
      <td>隐藏</td>
      <td>隐藏</td>
  </tr>
<tr>
      <td>.visible-md-*</td>
      <td>隐藏</td>
      <td>隐藏</td>
      <td>可见</td>
      <td>隐藏</td>
  </tr>
<tr>
      <td>.visible-lg-*</td>
      <td>隐藏</td>
      <td>隐藏</td>
      <td>隐藏</td>
      <td>可见</td>
  </tr>
<tr>
      <td>.hidden-xs</td>
      <td>隐藏</td>
      <td>可见</td>
      <td>可见</td>
      <td>可见</td>
  </tr>
<tr>
      <td>.hidden-sm</td>
      <td>可见</td>
      <td>隐藏</td>
      <td>可见</td>
      <td>可见</td>
  </tr>
<tr>
      <td>.hidden-md</td>
      <td>可见</td>
      <td>可见</td>
      <td>隐藏</td>
      <td>可见</td>
  </tr>
<tr>
      <td>.hidden-lg</td>
      <td>可见</td>
      <td>可见</td>
      <td>可见</td>
      <td>隐藏</td>
  </tr>
</table>
####Bootstrap 表格
为任意 <table> 标签添加 .table 类可以为其赋予基本的样式 — 少量的内补（padding）和水平方向的分隔线。

<table>
 <tr>
  <td>标签</td>
  <td>描述</td>
 </tr>
 <tr>
  <td>< table></td>
  <td>为表格添加基础样式。</td>
 </tr>
 <tr>
  <td>< thead></td>
  <td>表格标题行的容器元素（< tr>），用来标识表格列。</td>
 </tr>
<td>< tbody></td>
  <td>	表格主体中的表格行的容器元素（< tr>）</td>
</tr>
  <td>< thead></td>
  <td>表格标题行的容器元素（< tr>），用来标识表格列。</td>
 </tr>
  <td>< tr></td>
  <td>一组出现在单行上的表格单元格的容器元素（< td> 或 < th>）。</td>
 </tr>
  <td>< td></td>
  <td>默认的表格单元格。</td>
 </tr>
  <td>< th></td>
  <td>特殊的表格单元格，用来标识列或行（取决于范围和位置）。必须在 < thead> 内使用。</td>
 </tr>
  <td>< caption></td>
  <td>关于表格存储内容的描述或总结。</td>
 </tr>
</table>
######表格类
<table>
 <tr>
  <td>类</td>
  <td>描述</td>
 </tr>
 <tr>
  <td>.table</td>
  <td>为任意 < table> 添加基本样式 (只有横向分隔线)</td>
 </tr>
 <tr>
  <td>.table-striped</td>
  <td>在 < tbody> 内添加斑马线形式的条纹 ( IE8 不支持)</td>
 </tr>
<td>.table-bordered</td>
  <td>为所有表格的单元格添加边框</td>
</tr>
  <td>.table-hover</td>
  <td>在 < tbody> 内的任一行启用鼠标悬停状态</td>
 </tr>
  <td>.table-condensed</td>
  <td>让表格更加紧凑。</td>
 </tr>
</table>
######< tr>, < th> 和 < td> 类
<table>
 <tr>
  <td>类</td>
  <td>描述</td>
 </tr>
 <tr>
  <td>.active</td>
  <td>将悬停的颜色应用在行或者单元格上</td>
 </tr>
 <tr>
  <td>.success</td>
  <td>表示成功的操作</td>
 </tr>
<td>.info</td>
  <td>表示信息变化的操作</td>
</tr>
  <td>.warning</td>
  <td>表示一个警告的操作</td>
 </tr>
  <td>.danger</td>
  <td>表示一个危险的操作</td>
 </tr>
</table>
###Bootstrap 表单
#####表单布局
Bootstrap 提供了下列类型的表单布局：

- 垂直表单（默认）
- 内联表单
- 水平表单
#####垂直或基本表单
基本的表单结构是 Bootstrap 自带的，个别的表单控件自动接收一些全局样式。下面列出了创建基本表单的步骤：

- 向父 < form> 元素添加 role="form"。
- 把标签和控件放在一个带有 class .form-group 的 < div> 中。这是获取最佳间距所必需的。
- 向所有的文本元素 < input>、< textarea> 和 < select> 添加 class ="form-control" 。

##按钮
####可作为按钮使用的标签或元素
	为 <a>、<button> 或 <input> 元素添加按钮类（button class）
	即可使用 Bootstrap 提供的样式。

<table>
 <tr>
  <td>类</td>
  <td>描述</td>
 </tr>
 <tr>
  <td>.btn</td>
  <td>为按钮添加基本样式</td>
 </tr>
 <tr>
  <td>.btn-default</td>
  <td>默认/标准按钮</td>
 </tr>
<td>.btn-primary</td>
  <td>原始按钮样式（未被操作）</td>
</tr>
  <td>.btn-success</td>
  <td>表示成功的动作</td>
 </tr>
  <td>.btn-info</td>
  <td>该样式可用于要弹出信息的按钮</td>
 </tr>
 </tr>
  <td>.btn-warning</td>
  <td>表示需要谨慎操作的按钮</td>
 </tr>
 </tr>
  <td>.btn-danger</td>
  <td>表示一个危险动作的按钮操作</td>
 </tr>
 </tr>
  <td>.btn-link</td>
  <td>让按钮看起来像个链接 (仍然保留按钮行为)</td>
 </tr>
 </tr>
  <td>.btn-lg</td>
  <td>制作一个大按钮</td>
 </tr>
 </tr>
  <td>.btn-sm</td>
  <td>制作一个小按钮</td>
 </tr>
 </tr>
  <td>.btn-xs</td>
  <td>制作一个超小按钮</td>
 </tr>
 </tr>
  <td>.btn-block</td>
  <td>块级按钮(拉伸至父元素100%的宽度)</td>
 </tr>
</tr>
  <td>.active</td>
  <td>按钮被点击</td>
 </tr>
</tr>
  <td>.disabled</td>
  <td>禁用按钮</td>
 </tr>
</table>
例：

	<!-- 标准的按钮 -->
	<button type="button" class="btn btn-default">默认按钮</button>
	<!-- 提供额外的视觉效果，标识一组按钮中的原始动作 -->
	<button type="button" class="btn btn-primary">原始按钮</button>
	<!-- 表示一个成功的或积极的动作 -->
	<button type="button" class="btn btn-success">成功按钮</button>
	<!-- 信息警告消息的上下文按钮 -->
	<button type="button" class="btn btn-info">信息按钮</button>
	<!-- 表示应谨慎采取的动作 -->
	<button type="button" class="btn btn-warning">警告按钮</button>
	<!-- 表示一个危险的或潜在的负面动作 -->
	<button type="button" class="btn btn-danger">危险按钮</button>
	<!-- 并不强调是一个按钮，看起来像一个链接，但同时保持按钮的行为 -->
	<button type="button" class="btn btn-link">链接按钮</button>

##Bootstrap 下拉菜单（Dropdown）插件
####用法
	可以切换下拉菜单（Dropdown）插件的隐藏内容：
- **通过 data 属性**：向链接或按钮添加 __data-toggle="dropdown"__ 来切换下拉菜单(可以在class中添加dropdown)
- **通过 JavaScript**：通过 JavaScript 调用下拉菜单切换
##Bootstrap 导航栏
###默认的导航栏
- 向 < nav> 标签添加 class .navbar、.navbar-default。
- 向上面的元素添加 __role="navigation"__，有助于增加可访问性。
- 向 < div> 元素添加一个标题 class __.navbar-header__，内部包含了带有 class **navbar-brand** 的 < a> 元素。这会让文本看起来更大一号。
- 为了向导航栏添加链接，只需要简单地添加带有 class **.nav、.navbar-nav** 的无序列表即可。



#响应式的导航栏


- 为了给导航栏添加响应式特性，您要折叠的内容必须包裹在带有 class **.collapse、.navbar-collapse** 的 < div> 中。折叠起来的导航栏实际上是一个带有 class **.navbar-toggle **及两个 data- 元素的按钮。第一个是 **data-toggle**，用于告诉 JavaScript 需要对按钮做什么，第二个是 **data-target**，指示要切换到哪一个元素。三个带有 class **.icon-bar** 的 <span> 创建所谓的汉堡按钮。这些会切换为 **.nav-collapse** <div> 中的元素。为了实现以上这些功能，您必须包含 Bootstrap 折叠（Collapse）插件。

######案例
##滚动监听  
滚动监听（Scrollspy）插件，即自动更新导航插件，会根据滚动条的位置自动更新对应的导航目标。  
####用法  
- **通过 data 属性**：向您想要监听的元素（通常是 body）添加** data-spy="scroll"**。然后添加带有 Bootstrap **.nav** 组件的父元素的 ID 或 class 的属性 **data-target**。为了它能正常工作，您必须确保页面主体中有匹配您所要监听链接的 ID 的元素存在。
- **通过 JavaScript**：您可以通过 JavaScript 调用滚动监听，选取要监听的元素，然后调用 **.scrollspy()** 函数：
	$('body').scrollspy({ target: '.navbar-example' })
