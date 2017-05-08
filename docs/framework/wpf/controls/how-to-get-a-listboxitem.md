---
title: "방법: ListBoxItem 가져오기 | Microsoft Docs"
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
  - "ListBox 컨트롤, ListBoxItem 가져오기"
  - "ListBoxItem"
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ListBoxItem 가져오기
<xref:System.Windows.Controls.ListBox>에서 특정 색인의 특정 <xref:System.Windows.Controls.ListBoxItem>을 가져오려면 <xref:System.Windows.Controls.ItemContainerGenerator>를 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ListBox> 및 해당 항목을 보여 줍니다.  
  
 [!code-xml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ItemContainerGenerator>의 <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> 속성에 항목의 색인을 지정하여 항목을 검색하는 방법을 보여 줍니다.  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 목록 상자 항목을 검색한 뒤에는 다음 예제에서처럼 항목의 내용을 표시할 수 있습니다.  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]