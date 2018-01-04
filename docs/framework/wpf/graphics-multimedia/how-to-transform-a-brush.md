---
title: "방법: 브러시 변환"
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
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ee517eb76877bb4e02c021061055b328597c517
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-transform-a-brush"></a>방법: 브러시 변환
변환 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Brush> 변환 속성을 사용 하 여 개체: <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A>합니다.  
  
 다음 예에서는 사용 된 <xref:System.Windows.Media.RotateTransform> 의 콘텐츠를 회전 하는 <xref:System.Windows.Media.ImageBrush> 으로 45도 합니다.  
  
 다음 그림에서는 <xref:System.Windows.Media.ImageBrush> 없이 <xref:System.Windows.Media.RotateTransform>와 <xref:System.Windows.Media.RotateTransform> 에 적용는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성을 가진는 <xref:System.Windows.Media.RotateTransform> 에 적용는 <xref:System.Windows.Media.Brush.Transform%2A> 속성입니다.  
  
 ![Brush RelativeTransform 및 Transform 설정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>예  
 적용 하는 첫 번째 예제는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성은 <xref:System.Windows.Media.ImageBrush>합니다. <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성의는 <xref:System.Windows.Media.RotateTransform> 모두이 콘텐츠의 중심점의 상대 좌표 0.5로 설정 되어 있습니다. 결과적으로 <xref:System.Windows.Media.ImageBrush> 콘텐츠 가운데를 중심으로 회전 합니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 두 번째 예제도 적용 됩니다는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.Media.ImageBrush>이지만 사용 하 여이 예제는 <xref:System.Windows.Media.Brush.Transform%2A> 속성 대신는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성입니다.  
  
 중심을 관통 하는 방법에 대 한 브러시를 회전 하려면이 예제에서는 설정는 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 의 속성은 <xref:System.Windows.Media.RotateTransform> 개체 절대 좌표입니다. 브러시는 175 x 90 셀 사각형을 그리기 때문에 사각형의 중심점은 (87.5, 45)입니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 에 대 한 설명은 방법을 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성 작업를 참조 하십시오.는 [브러시 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)합니다.  
  
 전체 샘플을 보려면 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하세요. 브러시에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [브러시 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
