---
title: "방법: 이름에 따라 요소 찾기 | Microsoft Docs"
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
  - "요소, 이름으로 찾기"
  - "FindName 메서드"
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 이름에 따라 요소 찾기
이 예제에서는 <xref:System.Windows.FrameworkElement.FindName%2A> 메서드를 사용하여 <xref:System.Windows.FrameworkElement.Name%2A> 값으로 요소를 찾는 방법을 설명합니다.  
  
## 예제  
 이 예제에서는 특정 요소를 이름으로 찾는 메서드를 단추의 이벤트 처리기로 작성합니다.  `stackPanel`은 검색할 루트 <xref:System.Windows.FrameworkElement>의 <xref:System.Windows.FrameworkElement.Name%2A> 입니다. 그런 다음 예제 메서드에서는 찾은 요소를 <xref:System.Windows.Controls.TextBlock>으로 캐스팅하고 <xref:System.Windows.Controls.TextBlock>의 시각적 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 속성 중 하나를 변경하여 시각적으로 나타냅니다.  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]