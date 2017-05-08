---
title: "방법: TextBox에서 텍스트가 변경되는 시점 감지 | Microsoft Docs"
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
  - "텍스트 변경 감지"
  - "텍스트 변경, 검색"
  - "TextBox 컨트롤, 텍스트 변경 감지"
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: TextBox에서 텍스트가 변경되는 시점 감지
이 예제에서는 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트를 사용하여 <xref:System.Windows.Controls.TextBox> 컨트롤의 텍스트가 변경될 때마다 메서드를 실행하는 한 가지 방법을 보여 줍니다.  
  
 변경 내용을 모니터링할 <xref:System.Windows.Controls.TextBox> 컨트롤이 포함된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 코드 숨김 클래스에서 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트가 발생할 때마다 호출할 메서드를 삽입합니다.  이 메서드에는 <xref:System.Windows.Controls.TextChangedEventHandler> 대리자에 필요한 시그니처와 일치하는 시그니처가 있어야 합니다.  
  
 <xref:System.Windows.Controls.TextBox> 컨트롤의 내용이 변경될 때마다 사용자에 의해 또는 프로그래밍 방식으로 이벤트 처리기가 호출됩니다.  
  
 **참고:** 이 이벤트는 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어져 텍스트로 처음 채워질 때 발생합니다.  
  
## 예제  
 <xref:System.Windows.Controls.TextBox> 컨트롤이 정의된 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 이벤트 처리기 메서드 이름과 일치하는 값으로 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 특성을 지정합니다.  
  
 [!code-xml[TextBox_MiscCode#_TextChangedXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## 예제  
 변경 내용을 모니터링할 <xref:System.Windows.Controls.TextBox> 컨트롤이 포함된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 코드 숨김 클래스에서 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 이벤트가 발생할 때마다 호출할 메서드를 삽입합니다.  이 메서드에는 <xref:System.Windows.Controls.TextChangedEventHandler> 대리자에 필요한 시그니처와 일치하는 시그니처가 있어야 합니다.  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <xref:System.Windows.Controls.TextBox> 컨트롤의 내용이 변경될 때마다 사용자에 의해 또는 프로그래밍 방식으로 이벤트 처리기가 호출됩니다.  
  
 **참고:** 이 이벤트는 <xref:System.Windows.Controls.TextBox> 컨트롤이 만들어져 텍스트로 처음 채워질 때 발생합니다.  
  
 설명  
  
## 참고 항목  
 <xref:System.Windows.Controls.TextChangedEventArgs>   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)   
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)