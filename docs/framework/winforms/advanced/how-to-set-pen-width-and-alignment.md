---
title: "방법: 펜 굵기 및 맞춤 설정"
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
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e5858da25174c8bc1de18d534023b57b58253e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="bd211-102">방법: 펜 굵기 및 맞춤 설정</span><span class="sxs-lookup"><span data-stu-id="bd211-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="bd211-103">만들 때 한 <xref:System.Drawing.Pen>, 생성자의 인수 중 하나로 펜 너비를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="bd211-104">펜 너비를 변경할 수도 있습니다는 <xref:System.Drawing.Pen.Width%2A> 의 속성은 <xref:System.Drawing.Pen> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="bd211-105">이론적인 선의 너비는 0에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="bd211-106">1 픽셀 너비에 있는 줄을 그릴 때 이론적인 줄에 있는 픽셀 가운데 맞춤 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="bd211-107">둘 이상의 픽셀 너비에 있는 줄을 그릴 경우 픽셀은 하거나 선 가운데에 이론적인 또는 이론적인 선의 한쪽으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="bd211-108">펜 맞춤 속성을 설정할 수 있습니다는 <xref:System.Drawing.Pen> 이론적인 선을 기준으로 해당 펜을 사용 하 여 그린 픽셀 배치 되는 방식을 결정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="bd211-109">값 <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, 및 <xref:System.Drawing.Drawing2D.PenAlignment.Inset> 다음에 나타나는 컴퓨터의 멤버인 코드 예제는 <xref:System.Drawing.Drawing2D.PenAlignment> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="bd211-110">다음 코드 예제에서는 한 줄을 두 번 그립니다: 고 한 번의 너비가 10 녹색 펜 너비 1의 검은색 펜으로 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="bd211-111">펜의 너비를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="bd211-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="bd211-112">값을 설정할는 <xref:System.Drawing.Pen.Alignment%2A> 속성을 <xref:System.Drawing.Drawing2D.PenAlignment.Center> (기본값) 녹색 펜을 사용 하 여 그린 픽셀 이론적인 줄에 가운데 맞춤 될 됩니다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="bd211-113">다음 그림에서는 결과 선을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="bd211-114">![펜](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="bd211-114">![Pens](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="bd211-115">다음 코드 예제에서는 두 번 사각형을 그립니다: 고 한 번의 너비가 10 녹색 펜 너비 1의 검은색 펜으로 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="bd211-116">펜의 맞춤을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="bd211-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="bd211-117">값을 설정할는 <xref:System.Drawing.Pen.Alignment%2A> 속성을 <xref:System.Drawing.Drawing2D.PenAlignment.Center> 픽셀 녹색 펜을 사용 하 여 그린 사각형의 경계에서 가운데 맞춤 될 됩니다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="bd211-118">다음 그림에서는 결과 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="bd211-119">![펜](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="bd211-119">![Pens](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="bd211-120">삽입 펜을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bd211-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="bd211-121">이전 코드 예제에서 세 번째 문을 다음과 같이 수정 하 여 녹색 펜의 맞춤을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="bd211-122">이제 다음 그림에 나와 있는 것 처럼 굵은 녹색 줄의 픽셀 사각형의 내부에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bd211-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="bd211-123">![펜](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="bd211-123">![Pens](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd211-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd211-124">See Also</span></span>  
 [<span data-ttu-id="bd211-125">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="bd211-125">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="bd211-126">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="bd211-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
