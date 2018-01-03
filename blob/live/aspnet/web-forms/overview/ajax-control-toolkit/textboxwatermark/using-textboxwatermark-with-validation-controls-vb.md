---
uid: web-forms/overview/ajax-control-toolkit/textboxwatermark/using-textboxwatermark-with-validation-controls-vb
title: "使用验证控件 (VB) TextBoxWatermark |Microsoft 文档"
author: wenz
description: "AJAX 控件工具包中的 TextBoxWatermark 控件扩展的文本框中，使得在框中显示文本。 当用户单击到框中，它我..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/02/2008
ms.topic: article
ms.assetid: e6c2cb98-f745-4bc8-973a-813879c8a891
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/textboxwatermark/using-textboxwatermark-with-validation-controls-vb
msc.type: authoredcontent
ms.openlocfilehash: 09236481b6e51cc22a4034aa22e7c491ce27a510
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2017
---
<a name="using-textboxwatermark-with-validation-controls-vb"></a><span data-ttu-id="4a148-104">TextBoxWatermark 使用验证控件 (VB)</span><span class="sxs-lookup"><span data-stu-id="4a148-104">Using TextBoxWatermark With Validation Controls (VB)</span></span>
====================
<span data-ttu-id="4a148-105">通过[Christian Wenz](https://github.com/wenz)</span><span class="sxs-lookup"><span data-stu-id="4a148-105">by [Christian Wenz](https://github.com/wenz)</span></span>

<span data-ttu-id="4a148-106">[下载代码](http://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/TextBoxWatermark2.vb.zip)或[下载 PDF](http://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/textboxwatermark2VB.pdf)</span><span class="sxs-lookup"><span data-stu-id="4a148-106">[Download Code](http://download.microsoft.com/download/9/3/f/93f8daea-bebd-4821-833b-95205389c7d0/TextBoxWatermark2.vb.zip) or [Download PDF](http://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/textboxwatermark2VB.pdf)</span></span>

> <span data-ttu-id="4a148-107">AJAX 控件工具包中的 TextBoxWatermark 控件扩展的文本框中，使得在框中显示文本。</span><span class="sxs-lookup"><span data-stu-id="4a148-107">The TextBoxWatermark control in the AJAX Control Toolkit extends a text box so that a text is displayed within the box.</span></span> <span data-ttu-id="4a148-108">当用户单击到框中时，它将被清空。</span><span class="sxs-lookup"><span data-stu-id="4a148-108">When a user clicks into the box, it is emptied.</span></span> <span data-ttu-id="4a148-109">如果用户离开而无需输入文本框中，再次显示已预先的文本。</span><span class="sxs-lookup"><span data-stu-id="4a148-109">If the user leaves the box without entering text, the prefilled text reappears.</span></span> <span data-ttu-id="4a148-110">这可能与在同一页上，ASP.NET 验证控件发生冲突，但可以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="4a148-110">This may collide with ASP.NET Validation Controls on the same page, but these issues may be overcome.</span></span>


## <a name="overview"></a><span data-ttu-id="4a148-111">概述</span><span class="sxs-lookup"><span data-stu-id="4a148-111">Overview</span></span>

<span data-ttu-id="4a148-112">`TextBoxWatermark` AJAX 控件工具包中的控件扩展文本框中，以便在框中显示文本。</span><span class="sxs-lookup"><span data-stu-id="4a148-112">The `TextBoxWatermark` control in the AJAX Control Toolkit extends a text box so that a text is displayed within the box.</span></span> <span data-ttu-id="4a148-113">当用户单击到框中时，它将被清空。</span><span class="sxs-lookup"><span data-stu-id="4a148-113">When a user clicks into the box, it is emptied.</span></span> <span data-ttu-id="4a148-114">如果用户离开而无需输入文本框中，再次显示已预先的文本。</span><span class="sxs-lookup"><span data-stu-id="4a148-114">If the user leaves the box without entering text, the prefilled text reappears.</span></span> <span data-ttu-id="4a148-115">这可能与在同一页上，ASP.NET 验证控件发生冲突，但可以解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="4a148-115">This may collide with ASP.NET Validation Controls on the same page, but these issues may be overcome.</span></span>

## <a name="steps"></a><span data-ttu-id="4a148-116">步骤</span><span class="sxs-lookup"><span data-stu-id="4a148-116">Steps</span></span>

<span data-ttu-id="4a148-117">此示例的基本设置为以下：`TextBox`控件打水印使用`TextBoxWatermarkExtender`控件。</span><span class="sxs-lookup"><span data-stu-id="4a148-117">The basic setup of the sample is the following: a `TextBox` control is watermarked using a `TextBoxWatermarkExtender` control.</span></span> <span data-ttu-id="4a148-118">按钮触发回发，并将更高版本可用于触发页上的验证控件。</span><span class="sxs-lookup"><span data-stu-id="4a148-118">A button triggers a postback and will later be used to trigger the validation controls on the page.</span></span> <span data-ttu-id="4a148-119">此外，`ScriptManager`初始化 ASP.NET AJAX 所需的控件：</span><span class="sxs-lookup"><span data-stu-id="4a148-119">Also, a `ScriptManager` control is required to initialize ASP.NET AJAX:</span></span>

[!code-aspx[Main](using-textboxwatermark-with-validation-controls-vb/samples/sample1.aspx)]

<span data-ttu-id="4a148-120">现在添加`RequiredFieldValidator`检查是否存在文本字段中提交表单时的控件。</span><span class="sxs-lookup"><span data-stu-id="4a148-120">Now add a `RequiredFieldValidator` control that checks whether there is text in the field when the form is submitted.</span></span> <span data-ttu-id="4a148-121">`InitialValue`验证程序的属性必须设置为相同的值中使用`TextBoxWatermarkExtender`控件： 提交表单时，不变的文本框中的值时，在其中的水印值：</span><span class="sxs-lookup"><span data-stu-id="4a148-121">The `InitialValue` property of the validator must be set to the same value that is used in the `TextBoxWatermarkExtender` control: When the form is submitted, the value of an unchanged textbox is the watermark value within it:</span></span>

[!code-aspx[Main](using-textboxwatermark-with-validation-controls-vb/samples/sample2.aspx)]

<span data-ttu-id="4a148-122">但是没有使用此方法的一个问题： 如果客户端禁用 JavaScript，文本字段不预先填入使用的水印文本，因此`RequiredFieldValidator`不会触发一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="4a148-122">However there is one problem with this approach: If the client disables JavaScript, the text field is not prefilled with the watermark text, therefore the `RequiredFieldValidator` does not trigger an error message.</span></span> <span data-ttu-id="4a148-123">因此，第二个`RequiredFieldValidator`需要进行控制的检查的空文本框 (省略`InitialValue`属性)。</span><span class="sxs-lookup"><span data-stu-id="4a148-123">Therefore, a second `RequiredFieldValidator` control is required which checks for an empty text box (omitting the `InitialValue` attribute).</span></span>

[!code-aspx[Main](using-textboxwatermark-with-validation-controls-vb/samples/sample3.aspx)]

<span data-ttu-id="4a148-124">因为这两个验证程序使用`Display` = `"Dynamic"`，最终用户不能区分这两个验证程序已激发的可视外观从; 相反，它似乎没有其中只有一。</span><span class="sxs-lookup"><span data-stu-id="4a148-124">Since both validators use `Display`=`"Dynamic"`, the end user cannot distinguish from the visual appearance which of the two validators was fired; instead, it looks like there was only one of them.</span></span>

<span data-ttu-id="4a148-125">最后，添加一些服务器端代码以输出字段中的文本，如果没有验证程序发出一条错误消息：</span><span class="sxs-lookup"><span data-stu-id="4a148-125">Finally, add some server-side code to output the text in the field if no validator issued an error message:</span></span>

[!code-aspx[Main](using-textboxwatermark-with-validation-controls-vb/samples/sample4.aspx)]


<span data-ttu-id="4a148-126">[![验证程序错误报告的字段中没有任何文本](using-textboxwatermark-with-validation-controls-vb/_static/image2.png)](using-textboxwatermark-with-validation-controls-vb/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="4a148-126">[![The validator complains that there is no text in the field](using-textboxwatermark-with-validation-controls-vb/_static/image2.png)](using-textboxwatermark-with-validation-controls-vb/_static/image1.png)</span></span>

<span data-ttu-id="4a148-127">验证程序错误报告的字段中没有任何文本 ([单击以查看实际尺寸的图像](using-textboxwatermark-with-validation-controls-vb/_static/image3.png))</span><span class="sxs-lookup"><span data-stu-id="4a148-127">The validator complains that there is no text in the field ([Click to view full-size image](using-textboxwatermark-with-validation-controls-vb/_static/image3.png))</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="4a148-128">上一篇</span><span class="sxs-lookup"><span data-stu-id="4a148-128">Previous</span></span>](using-textboxwatermark-in-a-formview-vb.md)