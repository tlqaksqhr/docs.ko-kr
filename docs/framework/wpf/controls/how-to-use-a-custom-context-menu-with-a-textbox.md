---
title: "방법: TextBox에 사용자 지정 컨텍스트 메뉴 사용 | Microsoft Docs"
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
  - "상황에 맞는 메뉴, 사용자 지정"
  - "사용자 지정 상황에 맞는 메뉴"
  - "메뉴, 사용자 지정"
  - "TextBox 컨트롤, 사용자 지정 콘텐츠 메뉴"
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: TextBox에 사용자 지정 컨텍스트 메뉴 사용
이 예제에서는 <xref:System.Windows.Controls.TextBox>에 대한 간단한 사용자 지정 컨텍스트 메뉴를 정의하고 구현하는 방법을 보여 줍니다.  
  
## 예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 사용자 지정 컨텍스트 메뉴를 포함하는 <xref:System.Windows.Controls.TextBox> 컨트롤을 정의합니다.  
  
 컨텍스트 메뉴는 <xref:System.Windows.Controls.ContextMenu> 요소를 사용하여 정의됩니다.  컨텍스트 메뉴 자체는 일련의 <xref:System.Windows.Controls.MenuItem> 요소 및 <xref:System.Windows.Controls.Separator> 요소로 구성됩니다.  각 <xref:System.Windows.Controls.MenuItem> 요소는 컨텍스트 메뉴의 명령을 정의합니다. <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 특성은 메뉴 명령의 표시 텍스트를 정의하고, <xref:System.Windows.Controls.MenuItem.Click> 특성은 각 메뉴 항목의 처리기 메서드를 지정합니다.  <xref:System.Windows.Controls.Separator> 요소는 이전 메뉴 항목과 이후 메뉴 항목 사이에 분리선이 렌더링되도록 하는 역할을 합니다.  
  
 [!code-xml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## 예제  
 다음 예제에서는 컨텍스트 메뉴를 사용 및 사용 중지하는 코드와 앞의 컨텍스트 메뉴 정의에 대한 구현 코드를 보여 줍니다.  <xref:System.Windows.Controls.ContextMenu.Opened> 이벤트를 사용하여 <xref:System.Windows.Controls.TextBox>의 현재 상태에 따라 특정 명령이 동적으로 사용되거나 사용되지 않도록 합니다.  
  
 기본 컨텍스트 메뉴를 복원하려면 <xref:System.Windows.DependencyObject.ClearValue%2A> 메서드를 사용하여 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성의 값을 지웁니다.  컨텍스트 메뉴를 함께 사용 중지하려면 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성을 null 참조\(Visual Basic에서는 `Nothing`\)로 설정합니다.  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## 참고 항목  
 [상황에 맞는 메뉴로 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)