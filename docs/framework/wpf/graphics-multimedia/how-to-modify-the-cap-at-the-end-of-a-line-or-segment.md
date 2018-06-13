---
title: '방법: 줄 또는 세그먼트 끝에서 끝 모양 수정'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: e69f461d426fc6a587263cea7a18478da53b5b09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559839"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="db3a1-102">방법: 줄 또는 세그먼트 끝에서 끝 모양 수정</span><span class="sxs-lookup"><span data-stu-id="db3a1-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="db3a1-103">시작 또는 끝 열린의 모양을 수정 하는 방법을 보여 주는이 예제 <xref:System.Windows.Shapes.Shape> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="db3a1-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="db3a1-104">열려 있는 맨 앞에 cap를 변경 하려면 <xref:System.Windows.Shapes.Shape>를 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="db3a1-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="db3a1-105">열린의 끝에서 끝 모양 변경 하려면 <xref:System.Windows.Shapes.Shape>를 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="db3a1-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="db3a1-106">사용 가능한 선 끝을 보려면 참조는 <xref:System.Windows.Media.PenLineCap> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="db3a1-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db3a1-107">이 속성이 영향을 주는지 열린 도형에 같은 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, 또는 열린 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="db3a1-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="db3a1-108">다음 예제에서는 네 개의 <xref:System.Windows.Shapes.Polyline> 요소 다양 한 셰이프를 사용 하 여 각각의 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db3a1-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db3a1-109">예제</span><span class="sxs-lookup"><span data-stu-id="db3a1-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="db3a1-110">이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="db3a1-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3a1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db3a1-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
