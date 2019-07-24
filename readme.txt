
https://www.cnblogs.com/loyung/p/6879917.html


C#使用ITextSharp操作pdf
在.NET中没有很好操作pdf的类库，如果你需要对pdf进行编辑，加密，模板打印等等都可以选择使用ITextSharp来实现。

第一步：可以点击这里下载，新版本的插件升级和之前对比主要做了这几项重大改变

1.初始化对汉字的支持

2.对页眉页脚的加载形式

第二步：制作pdf模板

可以下载Adobe Acrobat DC等任意一款pdf编辑工具，视图——工具——准备表单，可以在需要赋值的地方放上一个文本框，可以把名称修改为有意义的名称，后面在赋值时要用到。

第三步：建项目引入各个操作类

介于前段时间项目所需特意把ITextSharp进行了二次封装，使我们对pdf操作起来更加方便。

列一下各文件的作用：

CanvasRectangle.cs对Rectangle对象的基类支持，可以灵活定义一个Rectangle。

PdfBase.cs主要继承PdfPageEventHelper，并实现IPdfPageEvent接口的具体实现，其实也是在pdf的加载，分页等事件中可以重写一些具体操作。

PdfImage.cs对图像文件的操作

PdfPageMerge.cs对pdf文件及文件、各种文件格式文件内容进行合并。

PdfTable.cs对表格插入做支持，可以在表格插入时动态生成新页并可以为每页插入页眉页脚

PdfText.cs对pdf模板上的表单进行赋值，并生成新的pdf

PdfWatermark.cs可以为pdf文档添加文字和图片水印

PdfPage.aspx.cs页面调用

