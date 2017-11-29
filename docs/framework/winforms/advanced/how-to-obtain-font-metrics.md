---
title: "방법: 글꼴 메트릭 얻기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b45f3f903c02d056fc457b652b01fb7b59413a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="a3426-102">방법: 글꼴 메트릭 얻기</span><span class="sxs-lookup"><span data-stu-id="a3426-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="a3426-103"><xref:System.Drawing.FontFamily> 클래스는 특정 제품군/스타일 조합에 대 한 다양 한 메트릭을 검색 하는 다음 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="a3426-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="a3426-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="a3426-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="a3426-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="a3426-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="a3426-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="a3426-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="a3426-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="a3426-108">크기 및 특정 단위에 종속 되므로 이러한 메서드에 의해 반환 된 숫자는 글꼴 디자인 단위로 <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="a3426-109">다음 그림에서는 다양 한 메트릭을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="a3426-110">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="a3426-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3426-111">예제</span><span class="sxs-lookup"><span data-stu-id="a3426-111">Example</span></span>  
 <span data-ttu-id="a3426-112">다음 예제에서는 Arial 글꼴 패밀리의 일반 스타일에 대 한 메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="a3426-113">코드는 또한 만듭니다는 <xref:System.Drawing.Font> 16 픽셀 크기 및 표시 해당 특정 픽셀 단위로 메트릭 포함 된 개체 (Arial 제품군에 기반) <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="a3426-114">다음 그림에서는 예제 코드의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="a3426-115">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="a3426-115">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="a3426-116">앞의 그림에는 출력의 처음 두 줄 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="a3426-117"><xref:System.Drawing.Font> 16의 크기를 반환 하는 개체 및 <xref:System.Drawing.FontFamily> 2, 048는 em 높이 반환 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="a3426-118">이러한 두 값 (16과 2, 048)은 글꼴 디자인 단위로 단위 (이 예제의 경우 픽셀)의 간에 변환 하는 <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="a3426-119">예를 들어 변환할 수 있습니다 경사가 디자인 단위에서 픽셀 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="a3426-120">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="a3426-120">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="a3426-121">다음 코드 텍스트를 세로로 배치 설정 하 여는 <xref:System.Drawing.PointF.Y%2A> 의 데이터 멤버는 <xref:System.Drawing.PointF> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="a3426-122">에 대 한 y-좌표 만큼 증가 `font.Height` 텍스트의 각 새 줄에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="a3426-123"><xref:System.Drawing.Font.Height%2A> 속성은 <xref:System.Drawing.Font> 해당 특정의 줄 간격 (픽셀 단위)를 반환 하는 개체 <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="a3426-124">이 예제에서 반환 된 수 <xref:System.Drawing.Font.Height%2A> 은 19입니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="a3426-125">줄 간격 메트릭을를 픽셀로 변환 하 여 얻은 (정수로 반올림) क 이것이 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="a3426-126">Em 높이 (크기 또는 em 크기 라고도 함)는 기준선 위와 총 아닌지 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="a3426-127">위와 경사가 합계 셀 높이 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="a3426-128">내부 여백 뺀 셀 높이 em 높이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="a3426-129">셀 높이 및 외부 앞에 오는 줄 간격 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a3426-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a3426-130">Compiling the Code</span></span>  
 <span data-ttu-id="a3426-131">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3426-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3426-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3426-132">See Also</span></span>  
 [<span data-ttu-id="a3426-133">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="a3426-133">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="a3426-134">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="a3426-134">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
