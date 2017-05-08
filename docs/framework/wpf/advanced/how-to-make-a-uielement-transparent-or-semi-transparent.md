---
title: "방법: UIElement를 투명하거나 반투명하게 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "불투명도, UIElements"
  - "UIElements의 투명도"
  - "UIElements, 불투명도"
  - "UIElements, 투명도(transparency)"
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: UIElement를 투명하거나 반투명하게 만들기
이 예제에서는 <xref:System.Windows.UIElement>를 투명하게 또는 반투명하게 만드는 방법을 보여 줍니다.  요소를 투명하게 또는 반투명하게 만들려면 해당 요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성을 설정하면 됩니다.  값이 `0.0`이면 요소가 완전히 투명해지고 값이 `1.0`이면 요소가 완전하게 불투명해집니다.  값이 `0.5`이면 요소가 50% 불투명해집니다.  요소의 <xref:System.Windows.UIElement.Opacity%2A>는 기본적으로 `1.0`으로 설정됩니다.  
  
## 예제  
 다음 예제에서는 단추의 <xref:System.Windows.UIElement.Opacity%2A>를 `0.25`로 설정하여 단추와 그 콘텐츠\(이 경우 단추의 텍스트\)를 25% 불투명하게 만듭니다.  
  
 [!code-xml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 요소의 콘텐츠에 자체적인 <xref:System.Windows.UIElement.Opacity%2A> 설정이 있는 경우 이 값과 포함 요소의 <xref:System.Windows.UIElement.Opacity%2A>를 곱합니다.  
  
 다음 예제에서는 단추의 <xref:System.Windows.UIElement.Opacity%2A>를 `0.25`로 설정하고 단추에 포함된 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.UIElement.Opacity%2A>를 `0.5`로 설정합니다.  그 결과 이미지가 12.5% 불투명해집니다\(0.25 \* 0.5 \= 0.125\).  
  
 [!code-xml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 요소의 불투명도를 제어하는 다른 방법은 요소를 칠하는 <xref:System.Windows.Media.Brush>의 불투명도를 설정하는 것입니다.  이 방법을 사용하면 요소 일부의 투명도를 선택적으로 변경할 수 있으며 요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성을 사용할 때보다 성능이 향상됩니다.  다음 예제에서는 단추의 <xref:System.Windows.Controls.Control.Background%2A>를 칠하는 데 사용되는 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.Brush.Opacity%2A>를 `0.25`로 설정합니다.  그 결과 브러시의 배경은 25% 불투명해지지만 콘텐츠\(단추의 텍스트\)는 100% 불투명한 상태로 남습니다.  
  
 [!code-xml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 브러시 내의 개별 색의 불투명도도 제어할 수 있습니다.  색 및 브러시에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.  요소의 불투명도에 애니메이션 효과를 적용하는 방법을 보여 주는 예제를 보려면 [요소 또는 브러시의 불투명도에 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md)을 참조하십시오.