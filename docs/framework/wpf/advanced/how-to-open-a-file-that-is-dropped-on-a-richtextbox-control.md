---
title: "방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기 | Microsoft Docs"
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
  - "끌어서 놓기[WPF], 끌어 놓은 파일을 열려면"
  - "끌어서 놓기[WPF], RichTextBox"
  - "RichTextBox[WPF], 끌어서 놓기"
ms.assetid: 6bb8bb54-f576-41db-a9a7-24102ddeb490
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: RichTextBox 컨트롤에 끌어 놓은 파일 열기
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> 및 <xref:System.Windows.Documents.FlowDocument> 컨트롤에는 모두 기본 제공 끌어서 놓기 기능이 있습니다.  이 기본 제공 기능이 있으면 컨트롤 내에서 및 컨트롤 간에 텍스트를 끌어서 놓을 수 있습니다.  그러나 컨트롤에 파일을 놓는 방법으로 파일을 열 수는 없습니다.  또한 이러한 컨트롤에서는 끌어서 놓기 이벤트를 처리된 것으로 표시합니다.  따라서 기본적으로는 놓인 파일을 여는 기능을 제공하기 위해 사용자 고유의 이벤트 처리기를 추가할 수 없습니다.  
  
 이러한 컨트롤에 끌어서 놓기 이벤트에 대한 다른 처리를 추가하려면 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 메서드를 사용하여 끌어서 놓기 이벤트에 대한 이벤트 처리기를 추가합니다.  `handledEventsToo` 매개 변수를 `true`로 설정하여 이벤트 경로를 따라 다른 요소에 의해 이미 처리된 것으로 표시된 라우트된 이벤트에 대해 지정된 처리기가 호출되도록 합니다.  
  
> [!TIP]
>  끌어서 놓기 이벤트의 미리 보기 버전을 처리하고 미리 보기 이벤트를 처리된 것으로 표시하여 <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox> 및 <xref:System.Windows.Documents.FlowDocument>의 기본 제공 끌어서 놓기 기능을 바꿀 수 있습니다.  그러나 이 경우 기본 제공 끌어서 놓기 기능을 사용할 수 없게 되므로 이 방법은 권장되지 않습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.RichTextBox>에 <xref:System.Windows.DragDrop.DragOver> 및 <xref:System.Windows.DragDrop.Drop> 이벤트에 대한 처리기를 추가하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 메서드를 사용하고 `handledEventsToo` 매개 변수를 `true`로 설정하여 <xref:System.Windows.Controls.RichTextBox>가 이러한 이벤트를 처리된 것으로 표시하는 경우에도 해당 이벤트 처리기가 호출되도록 합니다.  이벤트 처리기의 코드에서는 <xref:System.Windows.Controls.RichTextBox>에 놓인 텍스트 파일을 여는 기능을 추가합니다.  
  
 이 예제를 테스트하려면 Windows 탐색기에서 텍스트 파일이나 RTF\(서식 있는 텍스트\) 파일을 <xref:System.Windows.Controls.RichTextBox>로 끌어옵니다.  그러면 파일이 <xref:System.Windows.Controls.RichTextBox>에서 열립니다.  파일을 놓기 전에 Shift 키를 누르면 파일이 일반 텍스트로 열립니다.  
  
 [!code-xml[DragDropSnippets#RtbXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml#rtbxaml)]  
  
 [!code-csharp[DragDropSnippets#RtbHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/dragdropsnippets/cs/mainwindow.xaml.cs#rtbhandlers)]
 [!code-vb[DragDropSnippets#RtbHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/dragdropsnippets/vb/mainwindow.xaml.vb#rtbhandlers)]