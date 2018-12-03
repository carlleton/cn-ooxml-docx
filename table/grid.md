# 网格/列定义
表的列由`<w:tblGrid>`元素定义。每个`<w:tblGrid>`元素包含若干`<w:gridCol>`单元尺寸（有时称为逻辑列）在表中。元素的数量是通过扩展每个单元格的总列数来确定的。例如，下表中有三列，其`<w:tblGrid>`中需要3个`<w:tblGrid>`元素。

![](http://officeopenxml.com/images/wp-tableGrid-3.gif)

该表的`<w:tblGrid>`如下：
```
<w:tblGrid>
  </w:gridCol w:w="2880"/>
  </w:gridCol w:w="2880"/>
  </w:gridCol w:w="2880"/>
</w:tblGrid>
```
_**参考：**ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.49。_

当单元格在行与行之间的长度不相等时，事情会变得更加复杂。例如，下表有五列，因此在`<w:tblGrid>`元素中需要5 `<w:gridCol>`元素。
![](http://officeopenxml.com/images/wp-tableGrid-1.gif)

该表的`<w:tblGrid>`如下：
```
<w:tblGrid>
  </w:gridCol w:w="1638"/>
  </w:gridCol w:w="1242"/>
  </w:gridCol w:w="2880"/>
  </w:gridCol w:w="2178"/>
  </w:gridCol w:w="702"/>
</w:tblGrid>
```
>注意：每个单元格的宽度(`<w:tcW>`)将等于`<w:gridCol>`元素值之一，或者当表格未自动调整大小时，它将是两个或更多个元素的总和。

考虑上面表格中的第一行。它看起来像这样：
```
<w:tr>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="2880" w:type="dxa"/>
      <w:gridSpan w:val="2"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>AAA</w:t>
      </w:r>
    </w:p>
  </w:tc>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="5058" w:type="dxa"/>
      <w:gridSpan w:val="2"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>BBB</w:t>
      </w:r>
    </w:p>
  </w:tc>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="702" w:type="dxa"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>CCC</w:t>
      </w:r>
    </w:p>
  </w:tc>
</w:tr>
```
## 内容
`<w:tblGrid>`元素包含一个或多个`<w:gridCol>`元素(用于跟踪修订的`<w:tblGridChange>`元素已被忽略)

|元素|描述|
|---|---|
|gridCol|指定有关单个网格列的详细信息。属性是：<br>`<w:w>`指定列的二十分之一的宽度。然而，仅这一点并不能确定实际宽度。当表格布局算法显示表格时，或者作为列的一部分的特定单元格的首选宽度时，可以覆盖它。<br>_**参考：** ECMA-376，第3版（2011年6月），基础和标记语言参考§17.4.16。_|

## 跨单元格
内容为“AAA”的第一个单元格跨越前两个逻辑列，因此宽度是第一个和第二个`<w:gridCol>`元素值的总和(1638 + 1242 = 2880)。请注意，`<w:gridSpan>`值为2，表示单元格跨越两个逻辑列。内容为“BBB”的第二个单元格跨越第三个和第四个逻辑列，因此宽度是第三个和第四个`<w:gridCol>`元素值(2880 + 2178 = 5058)的总和。所述`<w:gridSpan>`的值也为2。

所述`<w:gridSpan>`表示水平地横跨多个逻辑单元(由定义的小区`<w:tblGrid>` 。，很像放置在电池中的HTML跨度属性细胞也跨越垂直使用`<w:vMerge>`元件/属性在`<w:tcPr>`元素中的属性。
![](http://officeopenxml.com/images/wp-tableGrid-5.gif)

最后两行如下所示:
```
<w:tr>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="1638" w:type="dxa"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>DDD</w:t>
      </w:r>
    </w:p>
  </w:tc>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="4122" w:type="dxa"/>
      <w:gridSpan w:val="2"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>EEE</w:t>
      </w:r>
    </w:p>
  </w:tc>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="2880" w:type="dxa"/>
      <w:vMerge w:val="restart"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>FFF</w:t>
      </w:r>
      </w:p>
    <w:p>
      <w:r>
       <w:t>III</w:t>
      </w:r>
    </w:p>
  </w:tc>
</w:tr>
<w:tr>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="2880" w:type="dxa"/>
      <w:gridSpan w:val="2"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>GGG</w:t>
      </w:r>
    </w:p>
  </w:tc>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="2880" w:type="dxa"/>
    </w:tcPr>
    <w:p>
      <w:r>
        <w:t>HHH</w:t>
      </w:r>
    </w:p>
  </w:tc>
  <w:tc>
    <w:tcPr>
      <w:tcW w:w="2880" w:type="dxa"/>
      <w:gridSpan w:val="2"/>
      <w:vMerge/>
    </w:tcPr>
  <w:p/>
  </w:tc>
</w:tr>
```

# 对应HTML/CSS属性：
可以使用宽度 css属性设置单元格宽度。单元格可以分别与单元格上的rowspan和colspan属性跨越行或列。请注意，虽然HTML 中也有colgroup和col元素，但它们用于将单元格分组以用于相似性，并不意味着像OOXML tblGrid这样的结构分组。
```
<table style="width:100%;">
  <tr>
    <td style="width:10%">AAA</td>
    <td rowspan="2" style="width:20%">BBB</td>
    <td style="width:70%">CCC</td>
  </tr>
  <tr>
    <td>DDD</td>
    <td>FFF</td>
  </tr>
  <tr>
    <td>GGG</td>
    <td colspan="2">HHH</td>
  </tr>
</table>
```
![](http://officeopenxml.com/images/wp-tableGrid-5.gif)