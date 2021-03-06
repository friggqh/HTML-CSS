# 了解CSS

CSS允许我们为页面添加布局和设计，允许我们在元素和元素、页面和页面之间共享这些样式。

首先，确切地了解样式的呈现方式至关重要。具体来说，我们需要知道不同类型的选择器如何工作，以及这些选择器的顺序如何影响样式的呈现方式。我们还想了解CSS中不断出现的一些常见属性值，特别是那些处理颜色和长度的属性值。

## 级联

在CSS中，所有样式从样式表的顶部级联到底部，允许在样式表进行时添加或覆盖不同的样式。

例如，假设我们选择样式表顶部的所有段落元素，并将背景颜色设置为橙色，将字体大小设置为24像素。然后在样式表的底部，我们再次选择所有段落元素并将其背景颜色设置为绿色，如此处所示。

```
p {
  background: orange;
  font-size: 24px;
}
p {
  background: green;
}
```

因为将背景颜色设置为绿色的段落选择器位于将背景颜色设置为橙色的段落选择器之后，所以它将优先于级联。所有段落都将以绿色背景显示。字体大小将保持24像素，因为第二段选择器未标识新的字体大小。

### 级联属性

级联还可以处理各个选择器内的属性。例如我们选择所有段落元素并将其背景颜色设置为橙色。然后在橙色背景属性和值声明的正下方，我们添加另一个属性和值声明，将背景颜色设置为绿色，如此处所示。

```
p {
  background: orange;
  background: green;
}
```

因为绿色背景颜色声明在橙色背景颜色声明之后，它将否决橙色背景，段落将以绿色背景显示。

所有样式将从样式表的顶部级联到样式表的底部。然而，当使用不同类型的选择器并且这些选择器的特异性打破级联时，级联不能很好地发挥作用。

## 计算特异性

CSS中的每个选择器都具有特异性权重。选择器的特异性权重及其在级联中的位置标识了其样式的呈现方式。

类型选择器具有最低的特异性权重，并且保持点值0-0-1。类选择器具有中等特异性权重并且保持0-1-0的点值。ID选择器具有高特异性权重并且保持1-0-0的点值。我们可以看到，使用三列计算特异性点。第一列计数ID选择器，第二列计数类选择器，第三列计数类型选择器。

这里要注意的重要一点是ID选择器具有比类选择器更高的特异性权重，并且类选择器具有比类型选择器更高的特异性权重。

> #### 特异性要点
>
> 特殊点是有意连字的，因为它们的值不是从10的基数计算的。类选择器不保持点值10，ID选择器不保持点值100。相反，这些点应该读为0 分别为-1-0和1-0-0。 当我们组合选择器时，我们将仔细研究为什么这些点值被连字。

选择器的特异性权重越高，发生样式冲突时选择器的优越性就越大。 例如，如果在一个位置使用类型选择器而在另一个位置使用ID选择器选择了段落元素，则ID选择器将优先于类型选择器，无论ID选择器在级联中出现在哪里。

HTML：

```
<p id="food">...</p>
```

CSS：

```
#food {
  background: green;
}
p {
  background: orange;
}
```

这里我们有一个段落元素，其id属性值为food。在CSS中，该段落由两种不同的选择器选择：类型选择器和ID选择器。虽然类型选择器位于级联中的ID选择器之后，但ID选择器优先于类型选择器，因为它具有更高的特异性权重；因此该段落将以绿色背景显示。

不同类型的选择器的特异性权重是非常重要的。有时样式可能不会按预期出现在元素上，并且选择器的特异性权重可能会破坏级联，因此样式不能正确显示。

了解级联和特异性如何工作是一个难题，我们将继续讨论这个主题。

## 组合选择器

目前为止，我们已经研究了如何单独使用不同类型的选择器，但还需要知道如何将它们一起使用。通过组合选择器，可以更具体地说明我们想要选择哪个元素或元素组。

例如，假设我们要选择位于具有类属性值hotdog的元素中的所有段落元素，并将其背景颜色设置为棕色。但是，如果其中一个段落碰巧具有mustard属性值，我们希望将其背景颜色设置为黄色。 我们的HTML和CSS可能如下所示：

HTML：

```
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>
```

CSS：

```
.hotdog p {
  background: brown;
}
.hotdog p.mustard {
  background: yellow;
}
```

组合选择器时，应从右向左阅读。最靠近右侧的选择器，直接位于开口花括号之前，称为键选择器。键选择器确切地标识将应用样式的元素。键选择器左侧的任何选择器都将用作预分配器。

上面的第一个组合选择器.hotdog p包括两个选择器：类和类型选择器。这两个选择器由一个空格分隔。键选择器是一个针对段落元素的类型选择器。因为这个类型选择器是使用hotdog的类选择器进行资格预审的，所以完整的组合选择器将只选择驻留在具有类属性值hotdog的元素中的段落元素。

上面的第二个选择器.hotdog p.mustard，包括三个选择器：两个类选择器和一个类型选择器。第二个选择器和第一个选择器之间的唯一区别是，在段落类型选择器的末尾添加了mustard的类选择器。因为新的类选择器mustard落到组合选择器的右侧，所以它是键选择器，并且它之前的所有单个选择器现在都是预均衡器。

> #### 选择器中的空格
>
> 在上一个组合选择器.hotdog p.mustard中，hotdog类选择器和段落类型选择器之间有一个空格，但段落类型选择器和mustard类选择器之间没有空格。空格的使用和遗漏在选择器中产生很大的差异。
>
> 由于段落类型选择器和mustard类选择器之间没有空格，选择器只会选择具有mustard类的段落元素。如果删除了段落类型选择器，并且mustard类选择器在其两侧都有空格，则它将选择具有mustard类的任何元素，而不仅仅是段落。
>
> 最佳做法是不使用类型选择器为类选择器添加前缀。通常我们想要选择具有给定类的任何元素，而不仅仅是一种类型的元素。按照这个来事件，我们的新组合选择器.hotdog .mustard会更好。

从右到左阅读组合选择器，它的目标是具有类属性值为mustard的段落，该属性值位于具有mustard类属性值的元素中。

### 组合选择器内的特异性

当选择器被组合时，个体选择器的特异性权重也是如此。可以通过计算组合选择器内每种不同类型的选择器来计算这些组合的特异性权重。

查看之前的组合选择器，第一个选择器.hotdog p包括类选择器和类型选择器。类选择器的点值是0-1-0，类型选择器的点值是0-0-1，总组合点值将是0-1-1。

第二个选择器.hotdog p.mustard，有两个类选择器和一个类型选择器。组合后，选择器的特异性点值为0-2-1。第一列中的0表示0ID选择器，第二列中的2表示两个类选择器，最后一列中的1表示一个类型选择器。

比较两个选择器，第二个选择器及其两个类具有明显更高的特异性权重和点值。因此，它将优先于级联。如果我们要在样式表中翻转这些选择器的顺序，将较高权重的选择器放在较低权重的选择器上方，如此处所示，由于每个选择器的特异性权重，它们的样式的外观不会受到影响。

```
.hotdog p.mustard {
  background: yellow;
}
.hotdog p {
  background: brown;
}
```

一般来说，我们要一直注意选择器的特异性权重。特异性权重越高，级联被破坏的可能性就越大。

## 具有多个类的分层样式

保持选择器的特异性权重较低的一种方法是尽可能模块化，在元素和元素之间共享相似的样式。尽可能模块化的一种方法是使用多个类来分层不同的样式。

HTML中的元素可以具有多个类属性值，只要每个值以空格分隔即可。这样我们就可以将某些样式放在一种类型的所有元素上，同时只将其他样式放在该类别的特定元素上。

我们可以将想要让其不断重用的样式与另一个类中的其他样式的一个类和层相关联。

比如按钮。假设我们希望所有按钮的字体大小为16像素，但我们希望按钮的背景颜色根据按钮的使用位置而有所不同。 我们可以根据需要创建一些类并将它们分层，以应用所需的样式。

HTML：

```
<a class="btn btn-danger">...</a>
<a class="btn btn-success">...</a>
```

CSS：

```
.btn {
  font-size: 16px;
}
.btn-danger {
  background: red;
}
.btn-success {
  background: green;
}
```

你可以看到两个锚元素，它们都具有多个类属性值。 第一个类btn用于为每个元素应用16像素的字体大小，然后使用另一类btn-danger来应用红色背景色，而第二个锚元素使用另一类btn-success来应用绿色背景色，这样使页面很简洁。

使用多个类，我们可以根据需要对任意样式进行分层，从而保持代码精简，并且我们的特定性权重较低。很像理解级联和计算特异性，这是需要时间来吸收的，但会随着课程越来越好。

## 常见的CSS属性值

我们已经使用了一些常见的CSS属性值，例如红色和绿色的关键字颜色值。我们现在需要花时间来讨论一些以前使用的属性值，探索我们即将使用的一些更常见的属性值。

### 颜色

CSS中的所有颜色值都是在sRGB（或标准的红色，绿色和蓝色）颜色空间中定义的。 这个空间内的颜色是通过将红色，绿色和蓝色混合在一起形成的，反映了电视和显示器产生所有不同颜色的方式。通过混合不同级别的红色，绿色和蓝色，我们可以创造数百万种颜色，并找到我们想要的几乎任何颜色。

目前，在CSS中主要有四种方式来表示sRGB颜色：关键字、十六进制表示法以及RGB和HSL值。

### 关键字颜色

关键字颜色值是映射到给定颜色的名称（例如红色，绿色或蓝色）。这些关键字名称及其相应的颜色由CSS规范确定。几乎所有颜色都有关键字名称。

可以在CSS规范中找到这些关键字名称的完整列表。

这里我们将maroon背景应用于具有任务类属性值的任何元素，并将黄色背景应用于具有count类属性值的任何元素。

```
.task {
  background: maroon;
}
.count {
  background: yellow;
}
```

虽然关键字颜色值本质上很简单，但它们提供的选项有限，因此不是最好的颜色值选择。

### 十六进制颜色

十六进制颜色值由井号或hash组成，后跟三个或六个字符的数字。这些数字使用数字0到9以及字母a到f，大写或小写都可以。这些值映射到红色，绿色和蓝色。

在六个字符的表示法中，前两个字符代表红色，第三个和第四个字符代表绿色，后两个字符代表蓝色。在三字符表示法中，第一个字符代表红色，第二个字符代表绿色，最后一个字符代表蓝色。

如果用六个字符表示前两个字符是匹配对，则第三个和第四个字符是匹配对，最后两个字符是匹配对，六个字符的数字可以缩短为三个字符的数字。为此，每对中的重复字符应使用一次。例如，由十六进制颜色＃ff6600表示的橙色阴影也可以写为＃f60。

字符对是通过将0到255转换为基16或十六进制格式而获得的。0等于黑色，f等于白色。

> #### 数以百万计的十六进制颜色
>
> 有数百万的十六进制颜色，确切地说超过1670万。 这是如何做到的？
>
> 每个字符有16个选项，十六进制颜色，0到9和a到f。 对于成对分组的字符，每对有256个颜色选项（16乘以16或16平方）。
>
> 有三组256色选项，我们总共有超过1670万种颜色（256乘以256再乘以256，或256立方）。

要创建与以前相同的栗色和黄色背景颜色，我们可以用十六进制颜色值替换关键字颜色值，如下。

```
.task {
  background: #800000;
}
.count {
  background: #ff0;
}
```

大多数图像编辑应用程序（如Adobe Photoshop）都可以定位十六进制颜色值。

RGB和RGBa颜色

RGB颜色值使用rgb（）函数表示，代表红色，绿色和蓝色。该函数接受三个以逗号分隔的值，每个值都是0到255之间的整数。0为纯黑色；255是纯白色。

rgb（）函数中的第一个值表示红色，第二个值表示绿色，第三个值表示蓝色。

如果我们将之前的橙色阴影重新创建为RGB颜色值，则它将表示为rgb（255,102,0）。

此外，如果想使用与之前相同的栗色和黄色背景颜色，我们可以用RGB颜色值替换关键字或十六进制颜色值。

```
.task {
  background: rgb(128, 0, 0);
}
.count {
  background: rgb(255, 255, 0);
}
```

通过使用rgba（）函数，RGB颜色值还可以包括alpha或透明度。rgba（）函数需要第四个值，该值必须是介于0和1之间的数字，包括小数。值0表示完全透明的颜色，表示它是不可见的，值1表示完全不透明的颜色。0到1之间的任何十进制值都将创建半透明颜色。

如果我们希望我们的橙色阴影显示50％不透明，我们将使用RGBa颜色值rgba（255,102,0，.5）。

我们还可以改变栗色和黄色背景颜色的不透明度。以下代码将栗色背景颜色设置为25％不透明，并使黄色背景颜色保持100％不透明。

```
.task {
  background: rgba(128, 0, 0, .25);
}
.count {
  background: rgba(255, 255, 0, 1);
}
```

RGB颜色值变得越来越流行，特别是由于能够使用RGBa创建半透明颜色。

### HSL和HSLa颜色

HSL颜色值使用hsl（）函数表示，该函数代表色调，饱和度和亮度。括号内函数接受三个以逗号分隔的值，与rgb（）非常相似。

第一个值，即色调，是从0到360的无单位数。数字0到360表示色轮，该值标识色轮上的颜色程度。

第二和第三个值，即饱和度和亮度，是0到100％的百分比值。饱和度值标识色调的色彩饱和度，0为灰度，100％为完全饱和。亮度表示色调值的暗度或亮度，0表示完全黑色，100％表示完全白色。

回到我们的橙色阴影，作为HSL颜色值，它将被写为hsl（24,100％，50％）。

我们的栗色和黄色背景颜色也可以表示为HSL颜色值，如此处所示。

```
.task {
  background: hsl(0, 100%, 25%);
}
.count {
  background: hsl(60, 100%, 50%);
}
```

HSL颜色值（如RGBa）也可以包含使用hsla（）函数的alpha或透明度通道。 alpha通道的行为就像rgba（）函数的行为一样。 必须在函数中添加0到1之间的第四个值（包括小数）以标识不透明度。

橙色作为HSLa颜色设置为50％不透明将表示为hsla（24,100％,50％,.5）。

同样的25%不透明褐色背景颜色和100%不透明黄色背景颜色从前看起来像下面的HSLa颜色值。

```
.task {
  background: hsla(0, 100%, 25%, .25);
}
.count {
  background: hsla(60, 100%, 50%, 1);
}
```

### 长度

CSS中的长度值与颜色类似，因为长度有少量不同类型的值，所有这些值都有不同的用途。长度值有两种不同的形式，绝对值和相对值，每种形式使用不同的测量单位。

### 绝对长度

绝对长度值是最简单的长度值，因为它们固定为物理测量值，例如英寸，厘米或毫米。最流行的绝对测量单位称为像素，由px单位表示法表示。

#### 像素

像素等于1/96英寸；因此，一英寸有96个像素。然而，在高密度和低密度观察设备之间，像素的精确测量可能略有不同。

像素已存在很长时间，并且通常与少数不同的属性一起使用。这里的代码使用像素将所有段落的字体大小设置为14像素。

```
p {
  font-size: 14px;
}
```

随着观看设备的不断变化和不同的屏幕尺寸，像素已经失去了一些适用程度。作为绝对的测量单位，它没有太多灵活性。然而，像素非常适合入门。当我们学习HTML和CSS的规则时将依赖它们。

### 相对长度

除绝对长度值外，还有相对长度值。相对长度值稍微复杂一些，因为它们不是固定的测量单位，而是依赖于另一种测量的长度。

#### 百分比

以％单位表示法表示的百分比是最受欢迎的相对值之一。百分比长度是根据另一个对象的长度定义的。例如，要将元素的宽度设置为50％，我们必须知道其父元素的宽度，它嵌套在其中的元素，然后识别父元素宽度的50％。

```
.col {
  width: 50%;
}
```

这里我们将col的class属性值设置为50％的元素宽度。相对于元素父级的宽度计算50％。

百分比非常有助于设置元素的高度和宽度以及构建网页的布局。 我们经常会依赖它们来解决问题。

#### em

em单位也是一个非常受欢迎的相对价值。em单位由em单位表示法表示，其长度根据元素的字体大小计算。

单个em单元相当于元素的字体大小。例如，如果元素的字体大小为14像素，宽度设置为5em，则宽度将等于70像素（14像素乘以5）。

```
.banner {
  font-size: 14px;
  width: 5em;
}
```

如果没有为元素明确说明字体大小，则em单位将相对于具有规定字体大小的最近父元素的字体大小。

em单元通常用于样式文本，包括字体大小以及文本周围的间距、边距和填充。

绝对和相对测量单位比这里提到的更多。但是，像素，百分比和em单位是最受欢迎的，也是我们主要使用的。

## 总结

简要回顾一下，我们讨论了以下内容：

样式表如何从文件的顶部到底部级联；

具体是什么以及如何计算；

如何组合选择器来定位特定元素或元素组；

如何在单个元素上使用多个类来为不同的样式分层以获得更多模块化代码；

可在CSS中使用的不同颜色值，包括关键字，十六进制，RGB和HSL值；

可在CSS中使用的不同长度值，包括像素，百分比和em单位。

