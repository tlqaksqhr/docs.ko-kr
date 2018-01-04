---
title: "방법: 윤곽선이 있는 텍스트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41254d8f93174c896923b1c070e6bf9b5b7c863c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="3f33b-102">방법: 윤곽선이 있는 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="3f33b-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="3f33b-103">대부분의 경우 장식을의 텍스트 문자열에 추가할 때 프로그램 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 불연속 문자 또는 문자 모양의 컬렉션과 관련 된 텍스트를 사용 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="3f33b-104">예를 들어 만들고 하는 선형 그라데이션 브러시에 적용 된 <xref:System.Windows.Controls.Control.Foreground%2A> 속성은 <xref:System.Windows.Controls.TextBox> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="3f33b-105">을 표시 하거나 텍스트 상자를 편집할 때 선형 그라데이션 브러시 현재 텍스트 문자열의 문자 집합에 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 <span data-ttu-id="3f33b-106">![선형 그라데이션 브러시로 표시 되는 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")</span><span class="sxs-lookup"><span data-stu-id="3f33b-106">![Text displayed with a linear gradient brush](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")</span></span>  
<span data-ttu-id="3f33b-107">텍스트 상자에 적용 하는 선형 그라데이션 브러시의 예</span><span class="sxs-lookup"><span data-stu-id="3f33b-107">Example of a linear gradient brush applied to a text box</span></span>  
  
 <span data-ttu-id="3f33b-108">그러나 텍스트를 또한 변환할 수 <xref:System.Windows.Media.Geometry> 개체를 다른 유형의 시각적 서식 있는 텍스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-108">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="3f33b-109">예를 들어, 만들 수는 <xref:System.Windows.Media.Geometry> 텍스트 문자열의 윤곽선을 기반으로 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-109">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 <span data-ttu-id="3f33b-110">![선형 그라데이션 브러시를 사용 하 여 텍스트 윤곽선](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")</span><span class="sxs-lookup"><span data-stu-id="3f33b-110">![Text outline using a linear gradient brush](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")</span></span>  
<span data-ttu-id="3f33b-111">텍스트의 개요 기 하 도형에 적용 된 선형 그라데이션 브러시의 예</span><span class="sxs-lookup"><span data-stu-id="3f33b-111">Example of a linear gradient brush applied to the outline geometry of text</span></span>  
  
 <span data-ttu-id="3f33b-112">에 변환 된 텍스트는 <xref:System.Windows.Media.Geometry> 문자의 컬렉션은 더 이상 개체-텍스트 문자열의에서 문자를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-112">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="3f33b-113">그러나 스트로크와 채우기 속성을 수정하여 변환된 텍스트의 모양에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-113">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="3f33b-114">스트로크는 변환된 텍스트의 윤곽선을 나타내고, 채우기는 변환된 텍스트의 윤곽선 내부에 있는 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-114">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="3f33b-115">다음 예제에는 변환 된 텍스트의 흑백 수정 하 여 시각적 효과 만드는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-115">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 <span data-ttu-id="3f33b-116">![채우기와 스트로크에 다른 색으로 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")</span><span class="sxs-lookup"><span data-stu-id="3f33b-116">![Text with different colors for fill and stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")</span></span>  
<span data-ttu-id="3f33b-117">스트로크와 채우기를 다른 색상으로 설정하는 예</span><span class="sxs-lookup"><span data-stu-id="3f33b-117">Example of setting stroke and fill to different colors</span></span>  
  
 <span data-ttu-id="3f33b-118">![스트로크에 이미지 브러시가 적용 된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")</span><span class="sxs-lookup"><span data-stu-id="3f33b-118">![Text with image brush applied to stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")</span></span>  
<span data-ttu-id="3f33b-119">스트로크에 적용한 이미지 브러시의 예</span><span class="sxs-lookup"><span data-stu-id="3f33b-119">Example of an image brush applied to the stroke</span></span>  
  
 <span data-ttu-id="3f33b-120">경계 상자 사각형 또는 변환된 된 텍스트의 강조 표시를 수정 하는 것도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-120">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="3f33b-121">다음 예제에서는 스트로크 및 변환 된 텍스트의 강조 표시를 수정 하 여 시각 효과를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-121">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 <span data-ttu-id="3f33b-122">![스트로크에 이미지 브러시가 적용 된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")</span><span class="sxs-lookup"><span data-stu-id="3f33b-122">![Text with image brush applied to stroke](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")</span></span>  
<span data-ttu-id="3f33b-123">스트로크와 강조 표시에 적용된 이미지 브러시의 예</span><span class="sxs-lookup"><span data-stu-id="3f33b-123">Example of an image brush applied to the stroke and highlight</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f33b-124">예</span><span class="sxs-lookup"><span data-stu-id="3f33b-124">Example</span></span>  
 <span data-ttu-id="3f33b-125">텍스트를 변환 하는 <xref:System.Windows.Media.Geometry> 는 사용 하 여 <xref:System.Windows.Media.FormattedText> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-125">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="3f33b-126">이 개체를 만든 후 사용할 수 있습니다는 <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> 및 <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> 텍스트를 변환 하는 메서드 <xref:System.Windows.Media.Geometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-126">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="3f33b-127">첫 번째 메서드는 서식 있는 텍스트;의 기 하 도형을 반환합니다. 두 번째 방법은 경계 상자의 서식 있는 텍스트의 기 하 도형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-127">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="3f33b-128">다음 코드 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Media.FormattedText> 개체 서식 있는 텍스트와 해당 경계 상자의의 기 하 도형이 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-128">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="3f33b-129">검색을 표시 하기 위해는 <xref:System.Windows.Media.Geometry> 개체에 액세스 해야는 <xref:System.Windows.Media.DrawingContext> 변환된 된 텍스트를 표시 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-129">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="3f33b-130">이 코드 예제에서이 사용자 지정 렌더링을 지원 되는 클래스에서 파생 된 사용자 지정 컨트롤 개체를 만들어 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-130">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="3f33b-131">표시 하려면 <xref:System.Windows.Media.Geometry> 에 대 한 재정의 제공 하는 사용자 지정 컨트롤의 개체는 <xref:System.Windows.UIElement.OnRender%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="3f33b-131">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="3f33b-132">재정의 된 메서드를 사용할지는 <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> 를 그리는 메서드는 <xref:System.Windows.Media.Geometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3f33b-132">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a><span data-ttu-id="3f33b-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f33b-133">See Also</span></span>  
 [<span data-ttu-id="3f33b-134">서식 있는 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="3f33b-134">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
