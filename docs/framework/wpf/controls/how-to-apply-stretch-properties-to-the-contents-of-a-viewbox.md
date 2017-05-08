---
title: "방법: Viewbox의 콘텐츠에 Stretch 속성 적용 | Microsoft Docs"
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
  - "컨트롤, Viewbox"
  - "Stretch 속성"
  - "StretchDirection 속성"
  - "Viewbox 컨트롤"
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Viewbox의 콘텐츠에 Stretch 속성 적용
## 예제  
 이 예제에서는 <xref:System.Windows.Controls.Viewbox>의 <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> 및 <xref:System.Windows.Controls.Viewbox.Stretch%2A> 속성 값을 변경하는 방법을 보여 줍니다.  
  
 첫 번째 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 <xref:System.Windows.Controls.Viewbox> 요소를 정의합니다.  그런 다음 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A>에 400을 할당합니다.  이 예제에서는 <xref:System.Windows.Controls.Image> 요소를 <xref:System.Windows.Controls.Viewbox> 내부에 중첩시킵니다.  <xref:System.Windows.Controls.Viewbox.Stretch%2A> 및 <xref:System.Windows.Controls.StretchDirection> 열거형의 속성 값에 해당하는 <xref:System.Windows.Controls.Button> 요소가 중첩된 <xref:System.Windows.Controls.Image>의 늘이기 동작을 조작합니다.  
  
 [!code-xml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 다음 코드 숨김 파일은 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제에서 정의한 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리합니다.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Viewbox>   
 <xref:System.Windows.Media.Stretch>   
 <xref:System.Windows.Controls.StretchDirection>