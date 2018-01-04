---
title: "방법: 합성 그리기 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 424f77b076344ad86db992614175243d1473886d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-composite-drawing"></a>방법: 합성 그리기 만들기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.DrawingGroup> 다중 결합 하 여 복잡 한 드로잉을 만드는 데 <xref:System.Windows.Media.Drawing> 단일 복합 그리기 개체입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 한 <xref:System.Windows.Media.DrawingGroup> 합성 그리기를 만들려는 <xref:System.Windows.Media.GeometryDrawing> 및 <xref:System.Windows.Media.ImageDrawing> 개체입니다. 다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
DrawingGroup를 사용 하 여 만든 복합 그리기  
  
 Note 회색 테두리 드로잉의 경계를 나타냅니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 사용할 수는 <xref:System.Windows.Media.DrawingGroup> 적용 하는 <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> 설정을 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, 또는 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 포함 된 그리기를 합니다. 때문에 <xref:System.Windows.Media.DrawingGroup> 이기도 한 <xref:System.Windows.Media.Drawing>, 다른 포함 될 수 있습니다 <xref:System.Windows.Media.DrawingGroup> 개체입니다.  
  
 추가 사용 하 여 다음 예제는 앞의 예제와 유사 <xref:System.Windows.Media.DrawingGroup> 일부 그리기에 불투명 마스크 및 비트맵 효과 적용할 개체입니다. 다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
합성 있는 그리기에 여러 DrawingGroup 개체  
  
 Note 회색 테두리 드로잉의 경계를 나타냅니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체 참조 [그리기 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
