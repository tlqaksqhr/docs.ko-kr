---
title: "방법: 패널의 자식 표시 | Microsoft Docs"
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
  - "표시기(adorner), Panel의 자식에 바인딩"
  - "Panel 컨트롤, 자식에 표시기 바인딩"
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 패널의 자식 표시
이 예제에서는 지정한 <xref:System.Windows.Controls.Panel>의 자식에 표시기를 프로그래밍 방식으로 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 표시기를 <xref:System.Windows.Controls.Panel> 자식에 바인딩하려면 다음 단계를 수행합니다.  
  
1.  새 <xref:System.Windows.Documents.AdornerLayer> 개체를 선언하고 `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 메서드를 호출하여 표시될 자식을 가진 요소에 대한 표시기 계층을 찾습니다.  
  
2.  부모 요소의 자식을 열거하고 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 메서드를 호출하여 표시기를 각 자식 요소에 바인딩합니다.  
  
 다음 예제에서는 위의 SimpleCircleAdorner를 *myStackPanel*라는 <xref:System.Windows.Controls.StackPanel>의 자식에 바인딩합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 표시기를 다른 요소에 바인딩하는 기능은 현재 지원되지 않습니다.  
  
## 참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)