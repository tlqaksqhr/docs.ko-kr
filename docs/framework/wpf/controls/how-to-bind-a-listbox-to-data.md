---
title: "방법: 데이터에 ListBox 바인딩 | Microsoft Docs"
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
  - "데이터 바인딩, ListBox 컨트롤에"
  - "데이터 바인딩(data binding), ListBox 컨트롤"
  - "ListBox 컨트롤, 데이터 바인딩"
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 데이터에 ListBox 바인딩
응용 프로그램 개발자는 각 <xref:System.Windows.Controls.ListBoxItem>의 콘텐츠를 개별적으로 지정하지 않고 <xref:System.Windows.Controls.ListBox> 컨트롤을 만들 수 있습니다.  데이터 바인딩을 사용하여 데이터를 개별 항목에 바인딩할 수 있습니다.  
  
 다음 예제에서는 *Colors*라는 데이터 소스에 데이터 바인딩하여 <xref:System.Windows.Controls.ListBoxItem> 요소를 채우는 <xref:System.Windows.Controls.ListBox>를 만드는 방법을 보여 줍니다.  이 경우 <xref:System.Windows.Controls.ListBoxItem> 태그를 사용하여 각 항목의 콘텐츠를 지정할 필요가 없습니다.  
  
## 예제  
 [!code-xml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.Controls.ListBoxItem>   
 [컨트롤](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)