---
title: "방법: ScrollChanged 이벤트 처리 | Microsoft Docs"
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
  - "ScrollChanged 이벤트"
  - "ScrollViewer 컨트롤, ScrollChanged 이벤트 발생"
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: ScrollChanged 이벤트 처리
## 예제  
 이 예제에서는 <xref:System.Windows.Controls.ScrollViewer>의 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 이벤트를 처리하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Documents.Paragraph> 부분이 있는 <xref:System.Windows.Documents.FlowDocument> 요소는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의됩니다.  사용자 상호 작용으로 인해 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 이벤트가 발생하면 처리기가 호출되고 이벤트가 발생했음을 나타내는 텍스트가 <xref:System.Windows.Controls.TextBlock>에 기록됩니다.  
  
 [!code-xml[scrollchangedeventargsLayout#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xml[scrollchangedeventargsLayout#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>   
 <xref:System.Windows.Controls.ScrollChangedEventHandler>   
 <xref:System.Windows.Controls.ScrollChangedEventArgs>