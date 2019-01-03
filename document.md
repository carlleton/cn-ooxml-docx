# 文档
文档以`<w:document>`元素作为主要内容的根元素。
```
<w:document>
  <w:body>
    <w:p/>
  </w:body>
</w:document>
```
*__参考：__ ECMA-376，第3版（2011年6月），基础和标记语言参考§§17.2.3。*

## 内容
这个`<w:document>`key包含以下元素

|元素|描述|
|--|--|
|background|指定文档每个页面的背景。背景可以是DrawingML对象或已售出的颜色。如果它是DrawingML对象，则background元素包含绘图元素。如果使用纯色，则background是一个空元素，其颜色在以下属性中指定。<table><tr><td>属性</td><td>描述</td></tr><tr><td>color</td><td>指定颜色。可能的值是十六进制编码的RGB值（RRGGBB格式）或auto。例如，&lt;w:background w:color="2C34FF"/&gt;</td></tr><tr><td>themeColor</td><td>指定基本主题颜色（在主题部分中指定）。例如，&lt;w:background w:themeColor="accent5"/&gt;</td></tr><tr><td>themeShade</td><td>指定应用于主题颜色的阴影值（以值为0-255的十六进制编码）。例如， &lt;w:background w:themeColor="accent2" w:themeShade="BF"/&gt;</td></tr><tr><td>themeTint</td><td>指定应用于主题颜色的色调值（以值为0-255的十六进制编码）。例如，&lt;w:background w:themeColor="accent2" w:themeTint="99"/&gt;</td></tr></table>*__参考：__ECMA-376，第3版（2011年6月），基础和标记语言参考§17.2.1。*|
|body|指定文档正文的内容。它没有属性。它可以包含许多元素，这些元素与跟踪更改和添加客户XML有关。核心要素如下。\n **内容** <table><tr><td>元件</td><td>描述</td></tr><tr><td>p</td><td>指定内容段落。见<a href="./paragraph" target="_blank">段落</a><br><i><b>参考：</b> ECMA-376，第3版（2011年6月），基础和标记语言参考§17.3.1.22。</i></td></tr><tr><td>sectPr</td><td>指定最后一节的节属性。见<a href="./section" target="_blank">章节</a>。<br><i><b>参考：</b> ECMA-376，第3版（2011年6月），基础和标记语言参考§17.6.17。</i></td></tr><tr><td>tbl</td><td>指定表。见<a href="./table" target="_blank">表格</a>。<br><i><b>参考：</b> ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.38。</i></td></tr></table>  *__参考：__ ECMA-376，第3版（2011年6月），基础和标记语言参考§17.2.2。*|

属性：
<w:document>有一个属性：
|属性|描述|
|conformance|指定文档符合的一致性类。可能的值是：\n 严格 - 该文档符合Office Open XML Strict \n 过渡 - 文档符合Office Open XML Transitional。这是默认值。|

# 相关HTML元素：
```
<html>
  <head>
  ...
  </head>
  <body>
  ...
  </body>
</html>
```
