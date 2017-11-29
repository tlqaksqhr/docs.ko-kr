---
title: "방법: 리플렉션 만들기"
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
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3032f46843c6d8efc53c45a927feae7068c3eb5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-reflection"></a>방법: 리플렉션 만들기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.VisualBrush> 반사를 만들려고 합니다. 때문에 <xref:System.Windows.Media.VisualBrush> 기존의 시각적을 표시할 수 있으며,이 기능을 사용 하 여 리플렉션 및 확대 같은 흥미로운 시각적 효과 생성 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.VisualBrush> 의 반사 만들기를 <xref:System.Windows.Controls.Border> 여러 요소가 들어 있는입니다. 다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.  
  
 ![A 시각적 개체를 반영](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
반사된 표시 개체  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 화면의 부분을 확대 하는 방법 및 반사를 만드는 방법을 보여 주는 예제를 포함 하는 전체 샘플을 참조 하십시오. [VisualBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160049)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.VisualBrush>  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
