---
title: "방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용 | Microsoft Docs"
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
  - "애니메이션, Opacity 속성"
  - "불투명도, 애니메이션 적용"
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용
뷰에서 프레임워크 요소를 페이드 인하고 페이드 아웃하려면 요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성에 애니메이션 효과를 적용하거나 요소를 그리는 데 사용되는 <xref:System.Windows.Media.Brush>\(또는 브러시\)의 <xref:System.Windows.Media.Brush.Opacity%2A> 속성에 애니메이션 효과를 적용합니다.  요소의 불투명도에 애니메이션 효과를 적용하면 요소와 요소의 자식을 뷰에서 페이드 인하고 페이드 아웃할 수 있지만 요소를 그리는 데 사용되는 브러시에 애니메이션 효과를 적용하면 요소에서 페이드 효과를 적용할 부분을 더욱 세밀하게 선택할 수 있습니다.  예를 들어 단추의 배경을 그리는 데 사용되는 브러시의 불투명도에 애니메이션 효과를 적용하면  단추 텍스트는 완전히 불투명한 상태로 남고 단추의 배경이 뷰에서 페이드 인되고 페이드 아웃됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Brush>의 <xref:System.Windows.Media.Brush.Opacity%2A>에 애니메이션 효과를 적용할 경우 요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성에 애니메이션 효과를 적용하는 것보다 성능상의 이점이 있습니다.  
  
 다음 예제에서는 두 단추에 애니메이션 효과를 적용하여 뷰에서 두 단추를 페이드 인하고 페이드 아웃합니다.  첫 번째 <xref:System.Windows.Controls.Button>의 불투명도는 5초의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 동안 `1.0`부터 `0.0`까지 변합니다.  두 번째 단추에도 애니메이션 효과가 적용되지만 전체 단추의 불투명도가 아니라 단추의 <xref:System.Windows.Controls.Control.Background%2A>를 그리는 데 사용되는 SolidColorBrush의 불투명도에 애니메이션 효과가 적용됩니다.  이 예제를 실행하면 첫 번째 단추가 뷰에서 완전히 페이드 인되고 페이드 아웃되는 동안 두 번째 단추의 배경만 뷰에서 페이드 인되고 페이드 아웃됩니다.  텍스트와 테두리는 완전히 불투명한 상태를 유지합니다.  
  
## 예제  
 [!code-xml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 이 예제는 코드가 생략된 예제입니다.  전체 샘플에서는 <xref:System.Windows.Media.LinearGradientBrush> 내에서 <xref:System.Windows.Media.Color>의 불투명도에 애니메이션 효과를 적용하는 방법도 보여 줍니다.  전체 샘플을 보려면 [Animating the Opacity of an Element 샘플](http://go.microsoft.com/fwlink/?LinkID=159968)을 참조하십시오.