---
title: "방법: 여러 줄 TextBox 컨트롤 만들기 | Microsoft Docs"
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
  - "TextBox 컨트롤, 여러 텍스트 줄"
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 여러 줄 TextBox 컨트롤 만들기
이 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 여러 줄의 텍스트를 수용하도록 자동으로 확장되는 <xref:System.Windows.Controls.TextBox> 컨트롤을 정의하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.TextBox.TextWrapping%2A> 특성을 **Wrap**으로 설정하면 <xref:System.Windows.Controls.TextBox> 컨트롤의 가장자리에 도달할 때 텍스트가 새 줄로 바뀌고, 필요한 경우 <xref:System.Windows.Controls.TextBox> 컨트롤이 자동으로 늘어나 새 줄을 위한 공간이 확보됩니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> 특성을 **true**로 설정하면 Return 키를 눌렀을 때 새 줄이 삽입되고 한 번 더 누르면 필요한 경우 <xref:System.Windows.Controls.TextBox> 컨트롤이 자동으로 늘어나 새 줄을 위한 공간이 확보됩니다.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> 특성은 스크롤 막대를 <xref:System.Windows.Controls.TextBox>에 추가하므로 둘러싼 프레임이나 창의 크기를 초과하여 <xref:System.Windows.Controls.TextBox>가 늘어날 경우에도 <xref:System.Windows.Controls.TextBox>의 내용을 스크롤할 수 있습니다.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## 참고 항목  
 <xref:System.Windows.TextWrapping>   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)