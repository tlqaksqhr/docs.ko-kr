---
title: "방법: 개체 회전"
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
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b9b6212ed6c50faf73a6d3531f001a1b7e72d33
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-rotate-an-object"></a>방법: 개체 회전
이 예제에서는 개체를 회전하는 방법을 보여 줍니다. 이 예에서는 먼저 만듭니다는 <xref:System.Windows.Media.RotateTransform> 만든 다음 해당 <xref:System.Windows.Media.RotateTransform.Angle%2A> 각도입니다.  
  
 다음 예제에서는 회전는 <xref:System.Windows.Shapes.Polyline> 45도 왼쪽 위 모퉁이 대 한 개체입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 의 속성은 <xref:System.Windows.Media.RotateTransform> 열리는데 회전 될 지점을 지정 합니다. 이 중심점은 변환되는 요소의 좌표 공간으로 표현됩니다. 기본적으로 회전은 변환할 개체의 왼쪽 위 구석에 해당하는 (0,0)에 적용됩니다.  
  
 회전 하는 다음 예제는 <xref:System.Windows.Shapes.Polyline> 개체를 시계 반대 방향으로 45도 지점 (25, 50)에 대 한 합니다.  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 다음 그림과 적용 한 결과 <xref:System.Windows.Media.Transform> 두 개체에 있습니다.  
  
 ![여러 중심점을 사용한 45도 회전](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
서로 다른 회전 중심에서 45도로 회전하는 두 개체  
  
 <xref:System.Windows.Shapes.Polyline> 은 앞의 예제에는 <xref:System.Windows.UIElement>합니다. 적용 하는 경우는 <xref:System.Windows.Media.Transform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성의는 <xref:System.Windows.UIElement>, 사용할 수 있습니다는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성의 원본을 지정 하려면 모든 <xref:System.Windows.Media.Transform> 요소에 적용 하는입니다. 때문에 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 상대 좌표를 사용 하는 속성, 크기로 알 수 없는 경우에 변환을 요소의 가운데에 적용할 수 있습니다. 자세한 정보 및 예제 참조 [변환 사용 하 여 상대 값의 원본을 지정할](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)합니다.  
  
 전체 샘플을 보려면 [2차원 변환 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Transform>  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
