---
title: "방법: 텍스트 선택 검색 | Microsoft Docs"
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
  - "텍스트 검색"
  - "텍스트, 검색"
  - "TextBox 컨트롤, 텍스트 검색"
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 텍스트 선택 검색
이 예제에서는 <xref:System.Windows.Controls.TextBox.SelectedText%2A> 속성을 사용하여 사용자가 <xref:System.Windows.Controls.TextBox> 컨트롤에서 선택한 텍스트를 검색하는 한 가지 방법을 보여 줍니다.  
  
## 예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제는 선택할 일부 텍스트가 포함된 <xref:System.Windows.Controls.TextBox> 컨트롤과 지정한 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드가 있는 <xref:System.Windows.Controls.Button> 컨트롤의 정의를 보여 줍니다.  
  
 이 예제에서 연결된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 처리기가 있는 단추는 텍스트 선택을 검색하는 데 사용됩니다.  사용자가 단추를 클릭하면 <xref:System.Windows.Controls.Button.OnClick%2A> 메서드가 텍스트 상자에서 선택한 텍스트를 문자열에 복사합니다.  텍스트 선택이 검색되는 특정 상황\(단추 클릭\)을 비롯하여 해당 선택으로 취해지는 동작\(텍스트 선택을 문자열에 복사\)을 쉽게 수정하여 다양한 시나리오를 수용할 수 있습니다.  
  
 [!code-xml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## 예제  
 다음 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 예제에서는 이 예제에 대해 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의된 단추의 <xref:System.Windows.Controls.Button.OnClick%2A> 이벤트 처리기를 보여 줍니다.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## 참고 항목  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)