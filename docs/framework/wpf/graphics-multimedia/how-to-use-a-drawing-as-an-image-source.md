---
title: "방법: 그림을 이미지 소스로 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e0fe8f7d3633143348693c95d92dd2715bd0442
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>방법: 그림을 이미지 소스로 사용
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Drawing> 로 <xref:System.Windows.Controls.Image.Source%2A> 에 대 한 프로그램 <xref:System.Windows.Controls.Image> 제어 합니다. 표시 하는 <xref:System.Windows.Media.Drawing> 와 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하 여는 <xref:System.Windows.Media.DrawingImage> 로 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A> 설정는 <xref:System.Windows.Media.DrawingImage> 개체의 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 속성을 표시 하려는 드로잉을 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 컨트롤을 표시 한 <xref:System.Windows.Media.GeometryDrawing>합니다. 이 예제는 다음과 같은 출력을 생성합니다.  
  
 ![개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [ImageDrawing을 사용하여 이미지 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [PresentationOptions:Freeze 특성](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
