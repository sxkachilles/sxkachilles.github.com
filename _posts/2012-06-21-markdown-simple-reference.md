---
layout: post
title: Markdown Simple Reference
tags: [Markdown, Blog]
---
# Markdown
* Markdown 是易读易写的 HTML 方言

* Zencoding 是 HTML 的缩写工具，用于生成 HTML

# 语法
* 行末加两个或多个空格才能换行，否则标准 Markdown 引擎会把前后连接起来；

* 空行分段；

* 标题下面有任意数量的=或-符号，分别标记一级和二级标题；或者在行首添加#标记，#的数量表示标题的级别；

* 区块引用，在一个段落的第一行首加上>；可嵌套其他 Markdown 标记；将产生 `<blockquote>` 标签，可通过 Blog 系统自定义样式；

* 列表，使用*, +, -任意一种符号，**没有多级列表！！！一个列表项目中仅能用开头4个空格来产生换行 `</br>`，而不能分段**；
* 有序列表，使用1.这样的符号，使用的具体数字与 HTML 的实际输出无关；
* 分隔线，可使用*, -, _任意一种符号，数量达3个以上，且行内不能有其他字符；
* 代码区块，每行开头缩进一个TAB或4个空格；
* 链接，inline link：`[content-with-url](http://example.com/ "Title")` 或  
    reference-style-link：`[content-with-url][id]`  
    `[id]: http://example.com/  "Optional Title Here"` 可以是双引号、单引号、圆括号
* 强调，用 \*content\*、\*\*content\*\* 或 \_content\_，将生成 `<em>` 或 `<strong>` 标签；
* \`code-content\` 将产生 `<code>` 标签，同样可通过 Blog 系统自定义样式；
* `list-style:outside` 配合跨 `<li>` 分段显示效果很好；

# Github Flavored Markdown
* 普通换行即是换行，GFM 保证有换行符的位置不会被连接起来
* 文字两端的下划线不会被用于表示强调，而是输出 plain 字符
* 除了每行缩进4个空格，也支持用 \`\`\` 包围代码段，并支持语法高亮（在开始的 \`\`\` 后面添加语言名，如\`\`\`ruby）










