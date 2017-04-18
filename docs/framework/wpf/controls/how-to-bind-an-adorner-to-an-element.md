---
title: "방법: 요소에 표시기 바인딩 | Microsoft Docs"
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
  - "표시기(adorner), 지정된 UIElements에 바인딩"
  - "UIElements, 표시기 바인딩"
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 요소에 표시기 바인딩
이 예제에서는 지정한 <xref:System.Windows.UIElement>에 표시기를 프로그래밍 방식으로 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 표시기를 특정 <xref:System.Windows.UIElement>에 바인딩하려면 다음 단계를 수행합니다.  
  
1.  `static` 메서드인 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>를 호출하여 표시할 <xref:System.Windows.UIElement>의 <xref:System.Windows.Documents.AdornerLayer> 개체를 가져옵니다.  <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>는 지정된 **UIElement**에서부터 시각적 트리를 검색하여 발견하는 첫 번째 표시기 계층을 반환하며  표시기 계층이 없으면 null을 반환합니다.  
  
2.  <xref:System.Windows.Documents.AdornerLayer.Add%2A> 메서드를 호출하여 대상 **UIElement**에 표시기를 바인딩합니다.  
  
 다음 예제에서는 위의 SimpleCircleAdorner를 *myTextBox*라는 <xref:System.Windows.Controls.TextBox>에 바인딩합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 표시기를 다른 요소에 바인딩하는 기능은 현재 지원되지 않습니다.  
  
## 참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)