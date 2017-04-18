---
title: "방법: RichTextBox에서 텍스트 콘텐츠 추출 | Microsoft Docs"
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
  - "내용, 추출"
  - "텍스트 콘텐츠 추출"
  - "RichTextBox 컨트롤, 텍스트 콘텐츠 추출"
  - "텍스트 내용, 추출"
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: RichTextBox에서 텍스트 콘텐츠 추출
이 예제에서는 <xref:System.Windows.Controls.RichTextBox>의 콘텐츠를 일반 텍스트로 추출하는 방법을 보여 줍니다.  
  
## 예제  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드에서는 간단한 콘텐츠가 있는 이름이 지정된 <xref:System.Windows.Controls.RichTextBox> 컨트롤을 설명합니다.  
  
 [!code-xml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## 예제  
 다음 코드에서는 <xref:System.Windows.Controls.RichTextBox>를 인수로 사용하고 <xref:System.Windows.Controls.RichTextBox>의 일반 텍스트 콘텐츠를 나타내는 문자열을 반환하는 메서드를 구현합니다.  
  
 이 메서드는 <xref:System.Windows.Documents.FlowDocument.ContentStart%2A>와 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>로 추출할 콘텐츠의 범위를 지정하여 <xref:System.Windows.Controls.RichTextBox>의 콘텐츠에서 새 <xref:System.Windows.Documents.TextRange>를 만듭니다.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A>와 <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> 속성은 각각 <xref:System.Windows.Documents.TextPointer>를 반환하며 <xref:System.Windows.Controls.RichTextBox>의 콘텐츠를 나타내는 기본 FlowDocument에서 액세스할 수 있습니다.  <xref:System.Windows.Documents.TextRange>는 <xref:System.Windows.Documents.TextRange>의 일반 텍스트 부분을 문자열로 반환하는 Text 속성을 제공합니다.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## 참고 항목  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)   
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)