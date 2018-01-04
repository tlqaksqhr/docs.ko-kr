---
title: "방법: Windows Form에 채워진 사각형 그리기"
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
- cpp
f1_keywords: Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17d143c0c265fea876d084ebc21663d93553fe9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="55fd5-102">방법: Windows Form에 채워진 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="55fd5-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="55fd5-103">이 예제에서는 폼에 채워진된 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="55fd5-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55fd5-104">예</span><span class="sxs-lookup"><span data-stu-id="55fd5-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55fd5-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="55fd5-105">Compiling the Code</span></span>  
 <span data-ttu-id="55fd5-106">이 메서드를 호출할 수 없습니다는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="55fd5-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="55fd5-107">그려지는 콘텐츠 활성 및 비활성 폼 크기를 조정 하거나 다른 형식으로 가려진 경우.</span><span class="sxs-lookup"><span data-stu-id="55fd5-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="55fd5-108">자동으로 다시 그려야 하 여 콘텐츠를 재정의 해야 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="55fd5-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="55fd5-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="55fd5-109">Robust Programming</span></span>  
 <span data-ttu-id="55fd5-110">항상 호출 해야 <xref:System.IDisposable.Dispose%2A> 와 같은 시스템 리소스를 사용 하는 개체에 <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="55fd5-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55fd5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55fd5-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.FillRectangle%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="55fd5-112">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="55fd5-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="55fd5-113">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="55fd5-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="55fd5-114">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="55fd5-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="55fd5-115">GDI+의 브러시 및 채워진 도형</span><span class="sxs-lookup"><span data-stu-id="55fd5-115">Brushes and Filled Shapes in GDI+</span></span>](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
