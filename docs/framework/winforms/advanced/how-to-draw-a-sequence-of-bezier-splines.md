---
title: "방법: &#233;시퀀스로 Draw; zier 곡선 스플라인"
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
- splines [Windows Forms], drawing Bezier
- Bezier splines [Windows Forms], drawing sequence of
ms.assetid: 37a0bedb-20c2-4cf0-91fa-a5509e826b30
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76a0ab96f40c1b8d9db6f61d19ece82066b63eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-sequence-of-b233zier-splines"></a><span data-ttu-id="194d3-102">방법: &#233;시퀀스로 Draw; zier 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="194d3-102">How to: Draw a Sequence of B&#233;zier Splines</span></span>
<span data-ttu-id="194d3-103">사용할 수는 <xref:System.Drawing.Graphics.DrawBeziers%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스 일련의 그릴를 베 지 어 스플라인을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="194d3-103">You can use the <xref:System.Drawing.Graphics.DrawBeziers%2A> method of the <xref:System.Drawing.Graphics> class to draw a sequence of connected Bézier splines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="194d3-104">예제</span><span class="sxs-lookup"><span data-stu-id="194d3-104">Example</span></span>  
 <span data-ttu-id="194d3-105">다음 예제에서는 두 개의 연결 된 베 지 어 스플라인을 구성 된 곡선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="194d3-105">The following example draws a curve that consists of two connected Bézier splines.</span></span> <span data-ttu-id="194d3-106">첫 번째 베 지 어 스플라인의 끝점에는 두 번째 베 지 어 스플라인의 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="194d3-106">The endpoint of the first Bézier spline is the start point of the second Bézier spline.</span></span>  
  
 <span data-ttu-id="194d3-107">다음 그림에서는 연결 된 스플라인 7 개의 점이 및 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="194d3-107">The following illustration shows the connected splines along with the seven points.</span></span>  
  
 <span data-ttu-id="194d3-108">![베 지 어 스플라인을](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span><span class="sxs-lookup"><span data-stu-id="194d3-108">![Bezier Spline](../../../../docs/framework/winforms/advanced/media/bezierspline2.png "BezierSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="194d3-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="194d3-109">Compiling the Code</span></span>  
 <span data-ttu-id="194d3-110">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="194d3-110">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="194d3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="194d3-111">See Also</span></span>  
 [<span data-ttu-id="194d3-112">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="194d3-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="194d3-113">GDI+의 3차원 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="194d3-113">Bézier Splines in GDI+</span></span>](../../../../docs/framework/winforms/advanced/bezier-splines-in-gdi.md)  
 [<span data-ttu-id="194d3-114">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="194d3-114">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
