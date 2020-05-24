# Markdown 语法学习

[toc]

## Block Elements

### Paragraph and line breaks

- **换段**：敲击`Enter`键得到新一段

- **软换行**：`Shift+Enter`在编辑界面可见，但是在文档导出时被省略

- **硬换行**：`Space+Space+Shift+Enter`. 在文档导出时被保留，  
  而且没有换段的段后距。



### Headers

每行开始处添加1-6个hash(`#`)字符，表示1-6级标题。*注意`#`字符后要空格*

比如：

```markdown
# This is an H1

## This is an H2

###### This is an H6
```



### Blockquotes

加字符`>`表示引用

> 在Typora中，输入'>'可以起到引用的效果
>
> 换行时Typora会自动插入'>'维持引用
>
> > 在引用中继续输入'>'可以进入新一层引用

比如：

```markdown
> This is a blockquote with two paragraphs. This is first paragraph.
>
> This is second pragraph. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.



> This is another blockquote with one paragraph. There is three empty line to seperate two blockquote.
```

显示效果：

> This is a blockquote with two paragraphs. This is first paragraph.
>
> This is second pragraph. Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.



> This is another blockquote with one paragraph. There is three empty line to seperate two blockquote.



### Lists

- 输入`* list item 1`会创建一个无序列表，其中`*`可以被`+`和`-` 代替

- 输入`1. list item 1`会创建一个有序列表

比如：

```markdown
#### un-ordered list
*   Red
*   Green
*   Blue

#### ordered list
1.  Red
2. 	Green
3.	Blue
```

显示效果：

#### un-ordered list
*   Red
*   Green
*   Blue

#### ordered list
1.  Red
2. 	Green
3.	Blue



### Task List

`- [ ]`和`- [x]`分别表示完成的和没完成的任务

比如：

```markdown
- [ ] a task list item
- [ ] list syntax required
- [ ] normal **formatting**, @mentions, #1234 refs
- [ ] incomplete
- [x] completed
```

显示效果：

- [ ] a task list item
- [ ] list syntax required
- [ ] normal **formatting**, @mentions, #1234 refs
- [ ] incomplete
- [x] completed

可以通过点击checkbox改变完成/未完成状态



### (Fenced) Code Blocks

输入```+语言名+Enter

比如： 

```markdown
​```
function test() {
  console.log("notice the blank line before this function?");
}
​```

syntax highlighting:
​```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
​```
```

显示效果

```
function test() {
  console.log("notice the blank line before this function?");
}
```

syntax highlighting:
```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```



### Math Blocks

输入`$`+公式+`$`创建行内数学公式，如$\sin^2(\alpha)+\cos^2(\alpha)=1$

输入`$$+Enter`创建一个数学公式块，如
$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\
\end{vmatrix}
$$
[more details](https://support.typora.io/Math/)



### Tables

输入`| First Header  | Second Header |`然后按`Enter`创建双栏表格

| First Header | Second Header |
| ------------ | ------------- |
|              |               |

可点击该表右上角省略号标志继续为表格添加行/列

或者直接右键插入表格

源码：

```markdown
| First Header  | Second Header |
| ------------- | ------------- |
| *Content Cell*  | **Content Cell**  |
| Content Cell  | Content Cell  |
```

显示效果：

| First Header   | Second Header    |
| -------------- | ---------------- |
| *Content Cell* | **Content Cell** |
| Content Cell   | Content Cell     |

另外，通过`:`可以定义列中文字的对齐方式。比如：

```markdown
| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
```

显示效果：

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ | :-------------: | ------------: |
| col 3 is      | some wordy text |         $1600 |
| col 2 is      |    centered     |           $12 |
| zebra stripes |    are neat     |            $1 |



### Footnotes

```markdown
You can create footnotes like this[^footnote].

[^footnote]: Here is the *text* of the **footnote**.
```

You can create footnotes like this[^footnote].

[^footnote]: Here is the *text* of the **footnote**.

考虑硬件约束和面向任务的ADC设计[^1]

[^1]: Hardware-limited and task-based quantization



### Horizontal Rules

输入 `***` 或 `---` + `Enter` 会画出一条水平线

---



### Table of Contents (TOC)

输入`[toc]`+`Enter`即可创建目录列表。TOC会自动提取文件中的标题，而且会随编辑而自动更新。



## Span Elements

### Links

Markdown支持2种链接：inline和reference

*使用时按住`CTRL`再点击*

输入`[name of link](URL)`创建inline链接，比如：

```markdown
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
```

显示效果：

This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.

#### Internal Links

输入`[name of the link](#name of the header)`可以创建指向文章内部标题的链接

比如：

```markdown
[This link](#Links) will jump to header `Links`
```

[This link](#Links) will jump to header `Links`

#### Reference Links

输入`[name of the link][id]`创建reference链接，比如：

```markdown
This is [an example][id] reference-style link.

Then, anywhere in the document, you define your link label on a line by itself like this:

[id]: http://example.com/  "Optional Title Here"
```

显示效果：

This is [an example][id] reference-style link.

Then, anywhere in the document, you define your link label on a line by itself like this:

[id]: http://example.com/  "Optional Title Here"

也可以直接`[name of the link][]`：

```markdown
[Google][]
And then define the link:

[Google]: http://google.com/
```

显示效果：

[Google][]

[Google]: http://google.com/



### URLs

可以用`<`brackets`>`插入URLs.

`<i@typora.io>`即为<i@typora.io>

标准的URLs会被自动链接，比如www.google.com



### Images

输入`![name of the picture](path)`插入图片

或者右键选择插入图片

或者直接把图片拖到编辑界面

![tardis](C:\Users\31601\Pictures\Saved Pictures\438676.jpg)

You can find more details [here](https://support.typora.io/Images/).



### Emphasis

`*`和`_`可用来表示斜体

```markdown
*single asterisks*

_single underscores_
```

*single asterisks*

_single underscores_

词内部的下划线会被忽略，比如wow_great_stuff

若`*`是需要正常显示的一部分，需要加转义符`\`：

```mark
\*this text is surrounded by literal asterisks\*
```

\*this text is surrounded by literal asterisks\*



### Strong

`**`和`__`可用来表示粗体

```mark
**double asterisks**

__double underscores__
```

**double asterisks**

__double underscores__



### Code

用一对`括住行内代码

```mark
Use the `printf()` function.
```

Use the `printf()` function.



### Strikethrough

用一对`~~`括住 （该特性不属于standard markdown）

`~~Mistaken text.~~` 即为 ~~Mistaken text.~~



### Underlines

`<u>Underline</u>` 即为 <u>Underline</u>.



### Emoji:smile:

用 `:smile:`输入笑脸



### Subscript

用一组`~`括起来，比如`H~2~O`, H~2~O



### Superscript

用一组`^`括起来，比如`x^2^`, x^2^



### Highlight

用一组`==`括起来，比如`==highlight==`, ==highlight==



## HTML

可以用HTML语句设置markdown不支持的内容风格

比如，用 `<span style="color:red">this text is red</span>` 将文字变成红色

 <span style="color:red">this text is red</span>

### Embed Contents

一些网站提供的iframe-based embed code可以复制进Typora

```markdown
<iframe height='265' scrolling='no' title='Fancy Animated SVG Menu' src='http://codepen.io/jeangontijo/embed/OxVywj/?height=265&theme-id=0&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'></iframe>
```



### Video

可以用`<video>`HTML tag插入视频，比如：

```mark
<video src="xxx.mp4" />
```



### Other HTML Support

可以在[这里][GFM]找到更多细节



[GFM]: https://help.github.com/articles/github-flavored-markdown/