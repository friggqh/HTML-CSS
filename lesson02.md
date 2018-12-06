# 了解HTML

随着我们对HTML和CSS的介绍，是时候深入研究HTML并检查构成这种语言的不同组件。

为了开始构建网站，我们需要了解哪些HTML元素适用于显示不同类型的内容。了解元素在网页上的可视化显示方式以及不同元素在语义上的含义也很重要。

学会使用适当的元素是漫长的过程，我们希望在此过程中做出正确的选择。

## 语义概述

究竟什么是语义？ HTML中的语义是通过使用适当的元素为页面含义和结构赋予含义。语义代码描述页面上内容的值，无论该内容的样式或外观如何。使用语义元素有几个好处，包括使计算机、屏幕阅读器、搜索引擎和其他设备充分阅读和理解网页上的内容。此外，语义HTML更易于管理和使用，因为它清楚地显示了每个内容的含义。

随着新元素的引入，我们将讨论这些元素的实际含义以及它们最能代表的内容类型。然而，在此之前，让我们看看两个元素——&lt;div&gt;s和&lt;span&gt; s——它们实际上没有任何语义值，仅用于样式。

## 识别分区和跨度

分区，&lt;div&gt; s和&lt;span&gt;s是HTML元素，仅作为样式用途的容器。作为通用容器，它们没有任何总体意义或语义价值。段落是语义的，包含在&lt;p&gt;元素中的内容是已知的并且被理解为段落。 &lt;div&gt; s和&lt;span&gt; s没有类似的含义，只是容器。

> #### 块与内联元素
>
> 大多数元素是块级或内联级元素。它们有什么不同？
>
> 块级元素从新行开始，将一个层叠在另一个顶部，并占用任何可用的宽度。块级元素可以嵌套，并且可以包含内联元素。最常见的是用于较大内容的块级元素，例如段落。
>
> 内联元素不会从新行开始。它们在文档的正常流程中，一个接一个地排列，并且只保持其内容的宽度。内联元素可以嵌套，但它们无法包含块级元素。我们通常会看到具有较小内容的内联元素，例如几个单词。

然而，&lt;div&gt;和&lt;span&gt;在构建网站时非常有价值，它们使我们能够将目标样式应用于包含的内容集。

&lt;div&gt;是一个块级元素，通常用于标识大型内容分组，这有助于构建网页的布局和设计。&lt;span&gt;是一个内联元素，通常用于识别块级元素中较小的文本分组。

我们通常会看到带有class或id属性的&lt;div&gt; s和&lt;span&gt;s用于样式目的。选择class或id属性值或名称需要格外注意。我们想选择一个引用元素内容的值，而不一定是元素的外观。

例如，如果我们的&lt;div&gt;具有包含社交媒体链接的橙色背景，我们首先想到的可能是给&lt;div&gt;一个类值orange。如果把橙色背景改为蓝色呢？具有橙色的类值不再有意义。对于类值而言，更明智的选择是social，因为它与&lt;div&gt;的内容有关，而不是样式。

```
<!-- Division -->
<div class="social">
  <p>I may be found on...</p>
  <p>Additionally, I have a profile on...</p>
</div>

<!-- Span -->
<p>Soon we'll be <span class="tooltip">writing HTML</span> with the best of them.</p>
```

> #### HTML＆CSS中的注释
>
> 前面的代码中的感叹号不是元素，而是注释。
>
> HTML和CSS使我们能在代码中留下注释，并且注释中的内容不会显示在网页上。注释有助于保持文件的条理性，允许我们设置提醒，并为我们提供更有效地管理代码的方法。当有多个人在处理相同的文件时，注释变得特别有用。
>
> HTML注释以&lt;！-- 开头，以 -- &gt;结尾。 CSS注释以/ \*开头，以\* /结尾。

## 文本元素的使用

网络上存在许多不同形式的媒体和内容，其中文本是主要的。因此，许多不同的元素用于在网页上显示文本。现在，我们将重点介绍更流行的元素，包括标题、段落、显示重要性的文本以及强调的斜体。在第6课中，我们将更深入地研究如何对文本进行样式化。

### 标题

标题是块级元素，从&lt;h1&gt;到&lt;h6&gt;。标题有助于快速分解内容并建立层次结构，它们是用户阅读页面的关键标识符。它们还可以帮助搜索引擎索引并确定页面上的内容。

标题应按照与页面内容相关的顺序使用。页面或节的主标题应使用&lt;h1&gt;元素标记，后续标题应根据需要使用&lt;h2&gt;，&lt;h3&gt;，&lt;h4&gt;，&lt;h5&gt;和&lt;h6&gt;元素。

每个标题级别都应该在语义上有价值的地方使用，并且不应该用于使文本加粗或放大，因为还有其他更好的方法。

以下是所有不同标题级别的HTML示例。

```
<h1>Heading Level 1</h1>
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
```

### 段落

标题之后通常就是段落。段落是使用&lt;p&gt;块级元素定义的。段落可以一个接一个地出现，根据需要向页面添加信息。

以下是如何设置段落的示例。

```
<p>Steve Jobs was a co-founder and longtime chief executive officer at Apple. On June 12, 2005, Steve gave the commencement address at Stanford University.</p>

<p>In his address Steve urged graduates to follow their dreams and, despite any setbacks, to never give up&ndash;advice which he sincerely took to heart.</p>
```

### 加粗强调文本

我们使用&lt;strong&gt;内联元素来加粗并强调文本。有两个元素可以加粗文字：&lt;strong&gt;和&lt;b&gt;元素。理解两者之间的语义差异非常重要。

&lt;strong&gt;元素在语义上用于强调文本，因此是粗体文本的最常用选项。另一方面，&lt;b&gt;元素在语义上意味着在风格上偏离文本，这对于需要强调的文本来说并不是最佳选择。我们必须衡量待强调文本的重要性，并相应地选择一个元素。

以下是用于创建操作粗体文本的两个HTML选项：

```
<!-- Strong importance -->
<p><strong>Caution:</strong> Falling rocks.</p>

<!-- Stylistically offset -->
<p>This recipe calls for <b>bacon</b> and <b>baconnaise</b>.</p>
```

### 重点突出文本

使用&lt;em&gt;内联元素来使文本变为斜体，从而起到强调作用。与粗体文本的元素一样，有两个不同的元素使文本斜体化，每个元素的语义含义略有不同。

&lt;em&gt;元素在语义上用于强调文本；因此，它是最流行的文本斜体选项。&lt;i&gt;元素在语义上用于以另一种语音或音调传达文本，几乎就像它被放在引号中一样。同样，我们需要衡量我们想要斜体化的文本，相应地选择一个元素。

这是斜体的HTML代码：

```
<!-- Stressed emphasis -->
<p>I <em>love</em> Chicago!</p>

<!-- Alternative voice or tone -->
<p>The name <i>Shay</i> means a gift.</p>
```

这些文本元素便于我们将内容变为现实。除此之外，还有结构元素。文本元素可以标识标题和段落，而结构元素标识内容的分组，例如标题，文章，页脚等。

## 构建结构

网页的结构往往是用分区构建的。然而分区没有提供语义价值，而且确定这些分区的意图相当困难。幸运的是，HTML5引入了新的基于结构的元素，包括&lt;header&gt;，&lt;nav&gt;，&lt;article&gt;，&lt;section&gt;，&lt;aside&gt;和&lt;footer&gt;元素。

这些元素旨在为页面赋予意义并改进我们的结构语义。它们都是块级元素，没有任何隐含的位置或样式。另外，这些元素可以每页多次使用，只要每次使用都反映了正确的语义含义。

### header（头）

&lt;header&gt;元素用于标识页面、文章、或页面其他部分的顶部。通常，&lt;header&gt;元素可以包括标题、介绍性文本，甚至导航。

```
<header>...</header>
```

> #### &lt;header&gt;、&lt;head&gt;、&lt;h1&gt;到&lt;h6&gt;元素
>
> 我们很容易将&lt;header&gt;元素与&lt;head&gt;元素或标题元素&lt;h1&gt;到&lt;h6&gt;混淆。它们都有不同的语义含义，应根据其含义使用。
>
> &lt;header&gt;元素是一个结构元素，它概述了页面段的标题，属于&lt;body&gt;元素。
>
> &lt;head&gt;元素不显示在页面上，用于概述元数据，包括文档标题和外部文件的链接。 它直接落在&lt;html&gt;元素中。
>
> 标题元素&lt;h1&gt;到&lt;h6&gt;用于在整个页面中指定多个级别的文本标题。

### navigation（导航）

&lt;nav&gt;元素标识页面上的主要导航链接的一部分。&lt;nav&gt;元素应仅为主导航部分保留，例如全局导航、目录、上一个/下一个链接或其他导航链接组。

最常见的是，&lt;nav&gt;元素中包含的链接将链接到同一网站内的其他页面或同一网页的某些部分。其他一次性链接不应包含在&lt;nav&gt;元素中，他们应该单独使用锚元素&lt;a&gt;。

```
<nav>...</nav>
```

### article（文章）

&lt;article&gt;元素用于标识可独立分发或重用的独立包含内容的一部分。我们经常使用&lt;article&gt;元素来标记博客文章、报纸文章、用户提交的内容等。

在使用&lt;article&gt;元素前，必须确定元素中的内容是否可以在其他地方复制而不会产生混淆。如果&lt;article&gt;元素中的内容已从页面上下文中删除并放置在例如电子邮件或印刷作品中，该内容仍应有意义。

```
<article>...</article>
```

### section（部分）

&lt;section&gt;元素用于标识内容的主题分组，通常但不总是包括标题。 &lt;section&gt;元素内的内容分组在本质上可能是通用的，但将所有内容标识为相关内容很有用。

&lt;section&gt;元素通常用于分解并为页面提供层次结构。

```
<section>...</section>
```

### 在&lt;article&gt;，&lt;section&gt;或&lt;div&gt;元素之间选择

有时根据语义含义决定&lt;article&gt;，&lt;section&gt;或&lt;div&gt;哪一个是最佳元素相当困难。与每个语义的判断一样，这里的诀窍是查看内容。

&lt;article&gt;和&lt;section&gt;元素都有助于文档的结构并有助于概述文档。如果内容仅为样式目的而分组，并且不为文档大纲提供值，使用&lt;div&gt;元素。

如果内容添加到文档大纲中并且可以单独重新分发或联合，使用&lt;article&gt;元素。

如果内容添加到文档大纲并表示内容的主题组，使用&lt;section&gt;元素。

### aside（旁边）

&lt;aside&gt;元素包含与其周围内容相切的内容，例如侧边栏、插入内容或简要说明。例如，当在&lt;article&gt;元素中使用时，&lt;aside&gt;元素可以标识与文章作者相关的内容。

我们可以将&lt;aside&gt;元素视为出现在页面左侧或右侧的元素。但是必须记住，所有结构元素（包括&lt;aside&gt;元素）都是块级元素，因此会出现在新行上，占据页面或元素的完整可用宽度。 嵌套在其中，也称为其父元素。

```
<aside>...</aside>
```

### footer（页脚）

&lt;footer&gt;元素标识页面、文章、部分或页面的其他部分的结束。通常，&lt;footer&gt;元素位于父元素的底部。&lt;footer&gt;元素中的内容应该是相对信息，不应与其中包含的文档或部分不同。

```
<footer>...</footer>
```

随着结构元素和文本元素，我们的HTML知识真正开始融合在一起。现在是重新访问我们样式会议网站的好时机，看看我们是否可以为它提供更好的结构。

## 实践

目前，我们的样式会议网站缺乏真实的结构和内容。我们花一些时间来充实我们的主页。

* 使用现有的index.html文件，添加一个&lt;header&gt;元素。我们的&lt;header&gt;元素应该包含现有的&lt;h1&gt;元素；再添加一个&lt;h3&gt;元素作为标语来支持我们的&lt;h1&gt;元素。

```
<header>
  <h1>Styles Conference</h1>
  <h3>August 24&ndash;26th &mdash; Chicago, IL</h3>
</header>
```

* 在&lt;header&gt;元素之后，使用引入我们会议的&lt;section&gt;元素添加一组新内容。我们将使用新的&lt;h2&gt;元素开始本节，并以现有段落结束。

```
<section>
  <h2>Dedicated to the Craft of Building Websites</h2>
  <p>Every year the brightest web designers and front-end developers descend on Chicago to discuss the latest technologies. Join us this August!</p>
</section>
```

* 会议介绍之后，添加另一组内容来梳理我们将要添加的几个页面，特别是演讲者、日程表和场地页面。我们整理的每个页面也应该位于相应的部分中，并包含支持文本。
  我们将结果分组到&lt;section&gt;元素中，单独的梳理也将包含在&lt;section&gt;元素中。 总之，我们在另一个&lt;section&gt;元素中有三个&lt;section&gt;元素。

```
<section>

  <section>
    <h5>Speakers</h5>
    <h3>World-Class Speakers</h3>
    <p>Joining us from all around the world are over twenty fantastic speakers, here to share their stories.</p>
  </section>

  ...

</section>
```

* 最后，让我们在末尾的&lt;footer&gt;元素中添加我们的版权。为此，我们使用&lt;small&gt;元素，它在语义上代表了侧面注释和小版本，
  通常，&lt;small&gt;元素中的内容将呈现为小，但我们的CSS重置将阻止这种情况发生。

```
<footer>
  <small>&copy; Styles Conference</small>
</footer>
```

> #### 编码特殊字符
>
> &lt;header&gt;元素中的&lt;h3&gt;元素，以及&lt;footer&gt;元素中的&lt;small&gt;元素，都会有一些有趣的事情发生。具体地说，这些元素中的特殊字符正在编码。
>
> 特殊字符包括各种标点符号、重音字母和符号。 直接输入HTML时，它们可能会被误认为是错误的字符，因此需要对它们进行编码。
>
> 每个编码字符以＆符号开头，以分号结尾。＆符号和分号之间的区别是字符的唯一编码，无论是名称还是数字编码。
>
> 例如，将“resumé”这个词编码为resum＆eacute;。 在我们的标题中，我们编码了en和em，在页脚中，我们编码了版权符号。

随着主页的形成，让我们来创建超链接，以便添加其他页面并构建我们网站的其余部分。

## 创建超链接

超链接也是互联网的核心组件之一，它提供从一个网页或资源链接到另一个网页或资源的能力。使用锚点&lt;a&gt;（内联元素）建立超链接。为了创建从一个页面（或资源）到另一个页面（或资源）的链接，需要href属性（称为超链接引用）。href属性值标识链接的目标。

例如，单击文本“Shay”，其中包含href属性值为http:/ /shayhowe.com的anchor元素，将用户带到相应网站。

```
<a href="http://shayhowe.com">Shay</a>
```

> #### 用锚点包含块级元素
>
> 本质上，锚元素&lt;a&gt;是内联元素，并且根据Web标准，内联元素不会包含块级元素。但是，随着HTML5的引入，锚元素特别具有包装块，内联或任何其他级别元素的权限。这是对标准约定的中断，但使页面上的整个内容块成为链接是允许的。

### 相对和绝对路径

两种最常见的链接类型是指向同一网站的其他页面的链接，以及指向其他网站的链接。这些链接由其href属性值标识，也称为其路径。

指向同一网站的其他页面的链接具有相对路径，该路径不包括href属性值中的域（.com，.org，.edu等）。由于链接指向同一网站上的另一个页面，href属性值只需要包含链接到的页面的文件名：about.html。

如果链接的页面在不同的目录或文件夹中，则href属性值也需要反映这一点。假设about.html页面位于pages目录中，相对路径将是pages / about.html。

链接到当前网站之外的其他网站需要绝对路径，其中href属性值必须包括完整域。指向Google的链接需要http:/ /google.com的href属性值，从http开始并包含域名.com。

例如，点击“关于”文本，将打开浏览器中的about.html页面。单击文本“Google”将在我们的浏览器中打开http:/ /google.com/。

```
<!-- Relative Path -->
<a href="about.html">About</a>

<!-- Absolute Path -->
<a href="http://www.google.com/">Google</a>
```

### 链接电子邮件地址

有时我们可能想要创建一个指向电子邮件地址的超链接，例如，“Email Me”的超链接文本，当点击该文本时，会打开用户的默认电子邮件客户端，并预先填充部分电子邮件。至少填充发送电子邮件的电子邮件地址，还可以包括诸如主题行和正文的其他信息。

要创建电子邮件链接，href属性值需要以mailto：开头，后跟邮件将发送到的电子邮件地址。例如，要创建到shay@awesome.com的电子邮件链接，href属性值将为mailto：shay@awesome.com。

另外，可以填充电子邮件的主题、正文和其他信息。要添加主题行，我们要在电子邮件地址后面加上subject =参数。电子邮件地址后面的第一个参数必须以问号“？”开头，以将其绑定到超链接路径。主题行中的多个单词要求使用％20对空格进行编码。

添加正文文本的方式与主题相同，使用href属性值中的body =参数。因为我们将一个参数绑定到另一个参数，所以我们需要使用＆符号来分隔两者。与主题一样，空格必须使用％20进行编码，并且必须使用％0A对换行符进行编码。

总而言之，链接到shay@awesome.com的主题为“伸出”和正文“你好吗”需要一个href属性值：

mailto:shay@awesome.comsubject=Reaching%20Out&body=How%20are%20you.

这是完整的细分：

```
<a href="mailto:shay@awesome.com?subject=Reaching%20Out&body=How%20are%20you">Email Me</a>
```

### 在新窗口中打开链接

超链接可用的一个功能是确定单击时链接打开的位置。 通常，链接在同一网页打开，但是，链接也可以在新窗口中打开。

要在新窗口中打开链接，请使用值为\_blank的target属性。target属性确切地确定了链接的显示位置，\_ blank属性指定了一个新窗口。

要在新窗口中打开http:/ /shayhowe.com/，代码将如下所示：

```
<a href="http://shayhowe.com/" target="_blank">Shay Howe</a>
```

### 链接到同一页面的部分

我们经常看到链接到同一页面部分的超链接。这些相同页面链接的常见示例是“返回顶部”链接，用于将用户返回到页面顶部。

我们可以通过在我们希望链接到的元素上设置id属性，然后在anchor元素的href属性中使用该id属性的值来创建页面链接。

以“回到顶部”链接为例，我们可以在&lt;body&gt;元素上放置一个id属性值top。 现在我们可以创建一个href属性值为＃top，pound sign和all的锚元素，以链接到&lt;body&gt;元素的开头。

我们这个同页链接的代码如下所示：

```
<body id="top">
  ...
  <a href="#top">Back to top</a>
  ...
</body>
```

超链接非常有用，并彻底改变了我们使用互联网的方式。到目前为止，我们已经介绍了如何链接到其他页面或网站，以及如何创建电子邮件链接和指向同一页面部分的链接。让我们创建一些自己的链接。

## 实践中

现在是时候将样式会议从单页网站带到一个包含多个页面的成熟网站，所有这些网站都将使用超链接链接在一起。

* 我们首先在我们的&lt;header&gt;元素链接中的&lt;h1&gt;元素内部创建“样式会议”文本到index.html页面。  因为我们已经在index.html页面上，所以这看起来有点奇怪，但这是正确的。当标题在其他页面上复制时，链接回主页将是有意义的。

```
<h1>
  <a href="index.html">Styles Conference</a>
</h1>
```

* 为了浏览所有不同的页面，我们将在&lt;header&gt;元素中使用&lt;nav&gt;元素添加导航菜单。我们将创建扬声器、时间表、地点和注册页面，与我们的主页一起使用，因此我们应该为所有这些页面创建链接。

```
<header>

  ...

  <nav>
    <a href="index.html">Home</a>
    <a href="speakers.html">Speakers</a>
    <a href="schedule.html">Schedule</a>
    <a href="venue.html">Venue</a>
    <a href="register.html">Register</a>
  </nav>

</header>
```

* 方便起见，我们还将&lt;header&gt;元素中的相同导航菜单添加到&lt;footer&gt;元素中。

```
<footer>

  ...

  <nav>
    <a href="index.html">Home</a>
    <a href="speakers.html">Speakers</a>
    <a href="schedule.html">Schedule</a>
    <a href="venue.html">Venue</a>
    <a href="register.html">Register</a>
  </nav>

</footer>
```

* 在介绍会议的&lt;section&gt;元素中，标题下方还应该包含一个注册会议的链接。在段落下方放置一个链接。

```
<section>

  ...

  <a href="register.html">Register Now</a>

</section>
```

* 不要忘记添加指向我们其他页面的所有部分的链接。在每个部分中，让我们将&lt;h3&gt;和&lt;h5&gt;元素包含在链接到正确页面的锚元素中。  我们要确保相应地为每个部分执行此操作。

```
<section>

  <section>
    <a href="speakers.html">
      <h5>Speakers</h5>
      <h3>World-Class Speakers</h3>
    </a>
    <p>Joining us from all around the world are over twenty fantastic speakers, here to share their stories.</p>
  </section>

  ...

</section>
```

* 现在我们需要创建一些新页面。 让我们创建speakers.html，schedule.html，venue.html和register.html文件。这些文件应该与index.html文件位于同一文件夹中，并且，因为保存在同一文件夹中，所以所有的链接都应该按预期工作。  为了确保所有页面看起来都一样，这些新文件都应该具有相同的文档结构，&lt;header&gt;和&lt;footer&gt;元素作为index.html文件。

这是官方的，我们不再使用单页，而是一个完整的网站。

## 总结

本课程中讨论的语义对于为HTML提供结构和含义至关重要。我们将定期推出新元素，所有这些元素都具有自己的语义含义，这将为我们的内容提供最大的价值。

在本课中，我们再次讨论了以下内容：

什么是语义？为什么它们很重要？

&lt;div&gt; s和&lt;spans&gt; s，以及块级和内联元素之间的区别；

哪些文本元素最能表示页面的内容；

HTML5结构元素以及如何定义内容和页面的结构和组织；

如何使用超链接在网页或网站之间导航；

还有很多东西值得学习，但基础已经到位。接下来，我们将深入研究CSS。

