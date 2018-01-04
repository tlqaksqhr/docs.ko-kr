---
title: "방법: 줄 또는 세그먼트 끝에서 끝 모양 수정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d2cd55de403b766344749259068ccd313558f89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>방법: 줄 또는 세그먼트 끝에서 끝 모양 수정
시작 또는 끝 열린의 모양을 수정 하는 방법을 보여 주는이 예제 <xref:System.Windows.Shapes.Shape> 요소입니다. 열려 있는 맨 앞에 cap를 변경 하려면 <xref:System.Windows.Shapes.Shape>를 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> 속성입니다. 열린의 끝에서 끝 모양 변경 하려면 <xref:System.Windows.Shapes.Shape>를 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> 속성입니다. 사용 가능한 선 끝을 보려면 참조는 <xref:System.Windows.Media.PenLineCap> 열거형입니다.  
  
> [!NOTE]
>  이 속성이 영향을 주는지 열린 도형에 같은 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, 또는 열린 <xref:System.Windows.Shapes.Path> 요소입니다.  
  
 다음 예제에서는 네 개의 <xref:System.Windows.Shapes.Polyline> 요소 다양 한 셰이프를 사용 하 여 각각의 끝에 있습니다.  
  
## <a name="example"></a>예  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
