# 第一课：建立你的第一个网页

如果可以的话，想象一下互联网发明之前的时代。网站不存在，印刷在纸上并紧密绑定的书籍是你的主要信息来源。这花费了大量的精力和阅读量来查获你所寻找的准确信息。

现在你可以打开网络浏览器，跳转到你所选择的搜索引擎，然后进行搜索。你可以找到任何你所想象到的信息。并且很可能某个地方已经建立了一个网站，考虑到了你的准确搜索。

在这本书中，我将向你展示如何使用两种最主要的计算机语言（HTML和CSS）来建立自己的网站。

在我们开始学习如何使用HTML和CSS来构建网站之前，了解两种语言之间的差异、每种语言的语法和一些常用的术语以及是非常重要的。

## 什么是HTML和CSS？

HTML（超文本标记语言）通过将内容定义为标题、段落或图像等来给出内容结构和意含义。CSS（层叠样式表）是一种表示语言，它用来设置内容外观，例如字体、颜色。

这两种语言（HTML和CSS）相互独立，并且应该保持如此。CSS不应该被写在HTML中，反之亦然。通常来说，HTML应该一直表示内容，CSS则应该表示该内容的外观。

带着对HTML和CSS之前差异的理解，让我们深入研究HTML。

## 了解常见的HTML术语

在开始使用HTML时，你可能会遇到新的，通常是奇怪的术语。 随着时间的推移，你将越来越熟悉它们，但你刚开始应该使用的三个常见HTML术语是元素，标签和属性。

### 元素

元素是定义页面内对象的结构和内容的指示符。 一些更常用的元素包括多个级别的标题（标识为&lt;h1&gt;到&lt;h6&gt;元素）和段落（标识为&lt;p&gt;元素）; 还包括&lt;a&gt;，&lt;div&gt;，&lt;span&gt;，&lt;strong&gt;和&lt;em&gt;元素等等。

元素是通过元素名称周围和小于号和大于号&lt;&gt;来标识的。因此一个元素如下所示：

```
<a>
```

### 标签

在元素周围使用小于号或大于号可以创建标签。开始标签和结束标签一般成对出现。

开始标签标记元素的开头。它由一个小于号后跟一个元素名称组成，以一个大于号结尾；例如&lt;div&gt;。

结束标签标记元素的结尾。它由一个小于号后跟一个斜杠和元素名称组成，以一个大于号结尾； 例如&lt;/ div&gt;。

开始标签和结束标签之间的就是元素的内容。例如，链接的开始标签为&lt;a&gt;，结束标签为&lt;/a&gt;。这两个标签之间的内容是链接的内容。因此它的标签如下：

```
<a>...</a>
```

### 属性

属性是用于提供元素其他相关信息的。最常见的属性包括标识元素的id属性；对元素进行分类的class属性；指定嵌入内容来源的src属性和引用连接资源的超链接的href属性。

属性在开始标签内定义，位于元素名称之后。通常，属性包括名称和值。这些属性的格式包括属性名称，后面是等号和带引号的属性值。例如，包含href属性的&lt;a&gt;元素如下所示：

```
<a href="http://shayhowe.com/">Shay Howe</a>
```

上面的代码会在网页上显示文本“Shay Howe”，并在点击“Shay Howe”文本时进入 http:/ /shayhowe.com/。使用包含文本的开始标签&lt;a&gt;和结束标签&lt;/a&gt;围绕文本，并且在开始标签中用href="http:/ /shayhowe.com"说明超链接的引用属性和值。

既然你已经了解了HTML元素、标签和属性，那么来看看我们的第一个网页。如果遇到新东西，不用担心，我们会一一解读它。

## 设置HTML文档结构

HTML文档是使用.html文件扩展名而不是.txt文件扩展名保存的纯文本文档。开始编写HTML时，你首先需要一个习惯使用的纯文本编辑器。其中并不包括Microsoft Word或Pages，它们是富文本编辑器。两个比较流行的编写HTML和CSS的纯文本编辑器是Dreamweaver和Sublime Text。免费替代品还包括适用于Windows的Notepad ++和适用于Mac的TextWrangler。

所有HTML文档都具有必需的结构，包括以下声明和元素：&lt;！DOCTYPE html&gt;，&lt;html&gt;，&lt;head&gt;和&lt;body&gt;。

文档类型声明或，&lt;！DOCTYPE html&gt;，通知Web浏览器正在使用HTML的哪个版本，并且放在HTML文档的最开头。由于我们使用的是最新版本的HTML，所以文档类型声明就是&lt;！DOCTYPE html&gt;。在文档类型声明之后，&lt;html&gt;元素表示文档的开头。

在&lt;html&gt;元素内，&lt;head&gt;元素标识文档的顶部，包括任何元数据（有关页面的附带信息）。&lt;head&gt;元素内的内容不会显示在网页上。相反，它可能包括文档标题（显示在浏览器窗口的标题栏上），指向任何外部文件的链接或任何其他有益的元数据。

网页中的所有可见内容都在&lt;body&gt;元素之内。典型HTML文档结构的细分如下所示：

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Hello World</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a web page.</p>
  </body>
</html>
```

上面的代码显示了以文档类型声明开头的文档&lt;！DOCTYPE html&gt;，后面直接跟着&lt;html&gt;元素。&lt;html&gt;元素内部是&lt;head&gt;和&lt;body&gt;元素。 &lt;head&gt;元素包括通过&lt;meta charset="utf-8"&gt;标记对页面进行字符编码，以及通过&lt;title&gt;元素对文档的标题进行字符编码。&lt;body&gt;元素包括通过&lt;h1&gt;元素的标题和通过&lt;p&gt;元素的段落。因为标题和段落都嵌套在&lt;body&gt;元素中，所以它们在网页上可见。

当一个元素放在另一个元素（也称为嵌套元素）内部时，最好缩进该元素以使文档结构保持条理清晰。 在前面的代码中，&lt;head&gt;和&lt;body&gt;元素都嵌套在&lt;html&gt;元素内并缩进。 在&lt;head&gt;和&lt;body&gt;元素内添加新元素时，元素也会继续缩进模式。

> #### 自闭元素
>
> 在前面的例子中，&lt;meta&gt;元素只有一个标签，并且不包含结束标签。别怕，这是有原因的。 并非所有元素都包含开始和结束标签。 有些元素只是从单个标签内的属性接收内容或行为。&lt;meta&gt;元素是其中之一，使用charset属性和值分配前一个&lt;meta&gt;元素的内容。 其他常见的自闭元素有  
> ：
>
> &lt;br&gt; &lt;embed&gt; &lt;hr&gt; &lt;img&gt; &lt;input&gt; &lt;link&gt; &lt;meta&gt; &lt;param&gt; &lt;source&gt; &lt;wbr&gt;
>
> 这里略述的结构使用&lt;！DOCTYPE html&gt;文档类型和&lt;html&gt;、&lt;head&gt;和&lt;body&gt;元素，是很常见的。我们希望保持这种文档结构的便利，因为我们在创建新的HTML文档时经常使用它。
>
> #### 代码验证
>
> 无论我们在编写代码时多么小心，我们都不可避免地会犯错误。庆幸的是，在编写HTML和CSS时，我们有验证器来检查我们的工作。 W3C已经构建了HTML和CSS验证器，可以扫描代码的错误之处。验证代码不仅有助于它在正确呈现在所有浏览器中，也时有助于我们编写代码的最佳实践方法。

## 实践

作为网页设计师和前端开发人员，我们可以参加一系列专注于技术的大型会议。我们将开展自己的会议、样式会议，并在下面的课程中构建一个网站。开始了！

* 打开文本编辑器，创建一个名为index.html的新文件，并保存到一个不会忘记的位置。我要在桌面上创建一个名为“styles-conference”的文件夹并将其保存在那里；自行做出相同的事。

* 在index.html文件中添加文档结构，包括&lt;！DOCTYPE html&gt;文档类型和&lt;html&gt;、&lt;head&gt;和&lt;body&gt;元素。

```
<!DOCTYPE html>
<html lang="en">
  <head>
  </head>
  <body>
  </body>
</html>
```

* 在&lt;head&gt;元素内添加&lt;meta&gt;和&lt;title&gt;元素。&lt;meta&gt;元素应该包含正确的charset属性和值，而&lt;title&gt;元素应该包含页面的标题——比例如“样式会议”。

```
<head>
  <meta charset="utf-8">
  <title>Styles Conference</title>
</head>
```

* 在&lt;body&gt;元素内添加&lt;h1&gt;和&lt;p&gt;元素。&lt;h1&gt;元素应该包括我们希望包含的标题——再次使用“样式会议”。&lt;p&gt;元素应该包含一个简单的段落来介绍我们的会议。

```
<body>
  <h1>Styles Conference</h1>
  <p>Every year the brightest web designers and front-end developers descend on Chicago to discuss the latest technologies. Join us this August!</p>
</body>
```

是时候看看我们做得如何了。我们找到index.html文件（我的文件位于桌面上的“styles-conference”文件夹中），双击此文件或将其拖入Web浏览器，打开它以供我们查看。

让我们稍微改变一下，离开HTML，看看CSS。请记住，HTML将定义网页的内容和结构，而CSS将定义网页的样式和外观。

## 了解常见的CSS术语

除了HTML术语之外，还有一些常见的CSS术语，你需要熟悉它们。这些术语包括选择器、属性和值。与HTML术语一样，使用CSS越多，这些术语就会越熟悉。

### 选择

器

当元素添加到网页时，可以使用CSS设置样式。选择器准确地指定HTML中要定位的元素，并应用样式（如颜色，大小和位置）。选择器可以包括不同限定符的组合以选择独特元素，这些都取决于我们的希望程度。例如，我们想选择页面上的每个段落，或者只想在页面上选择一个特定段落。

选择器通常以属性值为目标，例如id或类值，或者以元素类型为目标，例如&lt;h1&gt;或&lt;p&gt;。

在CSS中，选择器后跟大括号{}，其中包含要应用于所选元素的样式。 此处的选择器定位所有&lt;p&gt;元素。

```
p { ... }
```

### 属性

选择元素后，属性会确定应用于该元素的样式。属性名称位于选择器之后，在大括号{}内，冒号：之前。我们可以使用许多属性，例如背景、颜色，字体大小，高度和宽度，并且通常会添加新属性。下面的代码定义了要应用于所有&lt;p&gt;元素的颜色和字体大小属性。

```
p {
  color: ...;
  font-size: ...;
}
```

### 值

目前我们已经选择了一个带选择器的元素，并确定了我们想要使用的属性的样式。现在我们可以使用值来确定该属性的表现。值可以标识为冒号和分号之间的文本。这里我们选择所有&lt;p&gt;元素，并将color属性的值设置为橙色，将font-size属性的值设置为16像素。

```
p {
  color: orange;
  font-size: 16px;
}
```

回顾一下，在CSS中，我们的规则集以选择器开始，紧接着是大括号。在这些大括号中是由属性和值的声明。每个声明都以一个属性开头，后面跟一个冒号，属性值，最后是一个分号。

在大括号内缩进属性和值对是一种常见的做法。与HTML一样，这些缩进有助于保持我们的代码条理清晰。

了解一些常用术语和CSS的一般语法是一个很好的开始，但我们还有一些项目需要了解，然后才能深入学习。具体来说，我们需要仔细研究选择器如何在CSS中工作。

## 使用选择器

像前面所说的，选择器指示设置样式的HTML元素。充分了解如何使用选择器以及如何利用选择器非常重要。第一步是熟悉不同类型的选择器。我们会从最常见的选择器开始：类型、类和ID选择器。

### 类型选择器

类型选择器按元素类型定位元素。例如，如果我们想要定位所有的除法元素&lt;div&gt;，我们将使用div的类型选择器。以下代码显示了除法元素的类型选择器以及它选择的相应HTML。

CSS：

```
<div>{...}
```

HTML：

```
<div>...</div>          
<div>...</div>
```

### 类选择器

类选择器允许我们根据元素的类属性值选择元素，比类型选择器更加具体，因为它们选择特定的元素组而不是一种类型的所有元素。

类选择器允许我们通过在多个元素中使用相同的类属性值，一次将相同的样式应用于不同的元素。

在CSS中，类由一个先导句点来表示，接着是类属性值。在这里，类选择器将选择包含awesome的类属性值的任何元素，包括division和parameter元素。

CSS：

```
.awesome { ... }
```

HTML：

```
<div class="awesome">...</div>
<p class="awesome">...</p>
```

### ID选择器

ID选择器比类选择器更加精确，因为它们一次只针对一个元素。就像类选择器使用元素的类属性值作为选择器一样，ID选择器使用元素的id属性值作为选择器。

无论它们出现在哪种类型的元素上，id属性值每页只能使用一次。如果使用它们，应该用于重要的元素。

在CSS中，ID选择器由符号＃表示，后跟id属性值。这里ID选择器只会选择包含shayhowe的id属性值的元素。

CSS：

```
#shayhowe { ... }
```

HTML：

```
<div id="shayhowe">...</div>
```

### 其他选择器

选择器功能非常强大，这里列出的选择器是我们遇到的最常见的选择器。这些选择器只是一个开始。有许多更先进并且容易获得的选择器。当你习惯选择器时，不要害怕查看一些更高级的选择器。

现在一切都走到一起了。我们在HTML中的页面中添加元素，然后选择这些元素并使用CSS样式。现在让我们连接HTML和CSS之间的点，并让这两种语言一起工作。

## 引用CSS

为了使我们的CSS与HTML交谈，我们需要在HTML中引用CSS文件。引用CSS的最佳实践是将所有样式包含在单个外部样式表中，该样式表从HTML文档的&lt;head&gt;元素中引用。使用单个外部样式表，我们可以在整个网站上使用相同的样式，并在整个网站上快速进行更改。

> #### 添加CSS的其他选项
>
> 引用CSS的其他选项包括使用内部和内联样式。你可能会遇到这些选项，但他们通常不赞成，因为他们使更新网站繁琐和笨拙。

要创建外部CSS样式表，我们将再次使用我们选择的文本编辑器来创建具有.css文件扩展名的新的纯文本文件。我们的CSS文件应保存在HTML文件所在的同一文件夹或子文件夹中。

在HTML文档的&lt;head&gt;元素中，&lt;link&gt;元素用于定义HTML文件和CSS文件之间的关系。因为我们链接到CSS，所以我们使用带有样式表值的rel属性来指定它们的关系。此外，href（或超链接引用）属性用于标识CSS文件的位置或路径。

请考虑以下引用单个外部样式表的HTML文档&lt;head&gt;元素的示例。

```
<head>
  <link rel="stylesheet" href="main.css">
</head>
```

为了正确呈现CSS，href属性值的路径必须直接与CSS文件保存位置相关联。在前面的例子中，main.css文件存储在与HTML文件相同的位置，也称为根目录。

如果CSS文件位于子目录或子文件夹中，则href属性值需要相应地与此路径相关联。 例如，如果我们的main.css文件存储在名为stylesheets的子目录中，则href属性值将为stylesheets / main.css，使用正斜杠表示移动到子目录中。

这时我们的页面开始慢慢变得生动。我们还没有深入研究CSS，但你可能已经注意到，某些元素具有我们尚未在CSS中声明的默认样式。这就是浏览器为这些元素强加了自己喜欢的CSS样式。幸运的是，我们可以轻易覆盖这些样式，这就是我们接下来要学习的使用CSS重置的方法。

## 使用CSS重置

每个Web浏览器都有自己的默认样式，用于不同的元素。 Google Chrome浏览器呈现标题、段落、列表等的方式可能与Internet Explorer的方式不同。为确保跨浏览器兼容性，CSS重置已被广泛使用。

CSS重置采用预定义样式的每个常见HTML元素，并为所有浏览器提供统一样式。这些重置通常涉及删除任何大小、边距、填充或其他样式并调低这些值。因为CSS从上到下层层重叠，并会越来越多，所以我们的重置需要位于样式表的最顶部。这样做可确保首先读取这些样式，所有不同的Web浏览器都使用共同的基线。

有许多不同的重置可供使用，所有这些都有自己的特长。最受欢迎的重置之一是Eric Meyer的重置，它已被改编为包含新HTML5元素的样式。

如果您感觉更冒险，还有由Nicolas Gallagher创建的Normalize.css。 Normalize.css不关注对所有常用元素使用硬重置，而是为这些元素设置常用样式。它需要对CSS有更强的理解，以及对你喜欢的风格的认识。

> #### 跨浏览器兼容性和测试
>
> 如前所述，不同的浏览器以不同的方式呈现元素。 认识到跨浏览器兼容性和测试的价值非常重要。网站不需要在每个浏览器中看起来完全相同，但应该很接近。你希望在何种程度上支持哪些浏览器，需要根据最适合您网站的内容做出决定。

总而言之，在编写CSS时有一些注意事项。好消息是任何事情都是可能的，只要有一点耐心，我们就能全力以赴。

## 实践

回过头来看看我们在会议网站上最后停下来的地方，看看是否可以添加一些CSS。

* 在我们的“styles-conference”文件夹中创建一个名为“assets”的新文件夹。我们将在此文件夹中存储我们网站的所有资源，例如样式表、图像、视频等。对于我们的样式表，让我们继续在“assets”文件夹中添加另一个名为“stylesheets”的文件夹。

* 使用文本编辑器创建一个名为main.css的新文件，并将其保存在刚刚创建的“stylesheets”文件夹中。

* 在Web浏览器中查看index.html文件，我们可以看到&lt;h1&gt;和&lt;p&gt;元素都具有默认的CSS样式。具体来说，它们每个都有独特的字体大小和周围的间距。使用Eric Meyer的重置，我们可以调整这些样式，允许每个样式从同一个基础设置。要做到这一点，让我们前往Eric的网站，复制它的重置，并将其粘贴到main.css文件的顶部。

```
/* http://meyerweb.com/eric/tools/css/reset/ 2. v2.0 | 20110126
  License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed,
figure, figcaption, footer, header, hgroup,
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure,
footer, header, hgroup, menu, nav, section {
  display: block;
}
body {
  line-height: 1;
}
ol, ul {
  list-style: none;
}
blockquote, q {
  quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
  content: '';
  content: none;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
```

* 随着main.css文件开始成形，让我们将它连接到我们的index.html文件。在我们的文本编辑器中打开index.html文件，让我们在&lt;head&gt;元素中添加&lt;link&gt;元素，在&lt;title&gt;元素之后。

* 我们将引用&lt;link&gt;元素中的样式表，因此让我们使用样式表的值添加关系属性rel。

* 我们还想使用href属性将超链接引用包含到main.css文件中。请记住我们的main.css文件保存在“stylesheets”文件夹中，该文件夹位于“assets”文件夹中。 因此，href属性值（我们的main.css文件的路径）必须是assets / stylesheets / main.css。

```
<head>
  <meta charset="utf-8">
  <title>Styles Conference</title>
  <link rel="stylesheet" href="assets/stylesheets/main.css">
</head>
```

是时候看看我们的工作，看看HTML和CSS是否相得益彰。现在，在Web浏览器中打开我们的index.html文件（或刷新页面，如果它已经打开）应该显示与以前略有不同的结果。

## 演示和源代码

你可以在下面查看当前状态下的Styles Conference网站，以及下载当前状态的网站源代码。

## 总结

到现在为止都很好。 我们在本课中取得了很大的进步。

试想一下，现在你已经了解了HTML和CSS的基础知识。随着课程继续，你会花费更多时间编写HTML和CSS，将更加熟悉这两种语言。

回顾一下，到目前为止，我们已经涵盖了以下内容：

HTML和CSS之间的区别；

熟悉HTML元素，标签和属性；

设置第一个网页的结构；

熟悉CSS选择器，属性和值；

使用CSS选择器；

在HTML中引用CSS；

CSS的值重置。

现在让我们仔细看看HTML并学习一些关于语义的知识。

