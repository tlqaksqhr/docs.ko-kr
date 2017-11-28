---
title: "방법: 선 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4911aea91416fb84e9a18d54c145b494737ef9dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="42f42-102">방법: 선 그리기</span><span class="sxs-lookup"><span data-stu-id="42f42-102">How to: Draw a Line</span></span>
<span data-ttu-id="42f42-103">이 예제를 사용 하 여 선을 그리는 방법을 보여 줍니다.는 <xref:System.Windows.Shapes.Line> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="42f42-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="42f42-104">줄을 그리려면 만들기는 <xref:System.Windows.Shapes.Line> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="42f42-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="42f42-105">사용 하 여 해당 <xref:System.Windows.Shapes.Line.X1%2A> 및 <xref:System.Windows.Shapes.Line.Y1%2A> 시작점; 설정 및 사용 하는 속성의 <xref:System.Windows.Shapes.Line.X2%2A> 및 <xref:System.Windows.Shapes.Line.Y2%2A> 끝점을 설정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="42f42-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="42f42-106">마지막으로 설정 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 획 줄에 표시 되지 않으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="42f42-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="42f42-107">설정의 <xref:System.Windows.Shapes.Shape.Fill%2A> 선에 대 한 요소에는 줄 없는 내부에 있기 때문에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42f42-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="42f42-108">다음 예제에서는 내 세 개의 선을 그립니다는 <xref:System.Windows.Controls.Canvas> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="42f42-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42f42-109">예제</span><span class="sxs-lookup"><span data-stu-id="42f42-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="42f42-110">이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="42f42-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f42-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42f42-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Line>  
 [<span data-ttu-id="42f42-112">셰이프 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="42f42-112">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)
