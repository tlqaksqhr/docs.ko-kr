---
title: "방법: RoutedCommand 만들기 | Microsoft Docs"
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
  - "클래스, RoutedCommand, 만들기"
  - "만들기, RoutedCommand 클래스"
  - "RoutedCommand 클래스, 만들기"
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: RoutedCommand 만들기
이 예제에서는 사용자 지정 <xref:System.Windows.Input.RoutedCommand>를 만드는 방법과 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler>를 만든 다음 <xref:System.Windows.Input.CommandBinding>에 연결하여 사용자 지정 명령을 구현하는 방법을 보여 줍니다.  명령에 대한 자세한 내용은 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)를 참조하십시오.  
  
## 예제  
 <xref:System.Windows.Input.RoutedCommand>를 만드는 첫 번째 단계는 명령을 정의하고 인스턴스화하는 단계입니다.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 응용 프로그램에서 명령을 사용하려면 명령이 수행할 작업을 정의하는 이벤트 처리기를 만들어야 합니다.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 그런 다음 명령을 이벤트 처리기와 연결하는 <xref:System.Windows.Input.CommandBinding>을 만듭니다.  <xref:System.Windows.Input.CommandBinding>은 특정 개체에서 만들어집니다.  이 개체는 요소 트리에서 <xref:System.Windows.Input.CommandBinding>의 범위를 정의합니다.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 마지막 단계에서는 명령을 호출합니다.  명령을 호출하는 한 가지 방법은 명령을 <xref:System.Windows.Controls.Button>과 같은 <xref:System.Windows.Input.ICommandSource>와 연결하는 것입니다.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 단추를 클릭하면 사용자 지정 <xref:System.Windows.Input.RoutedCommand>에서 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드가 호출됩니다.  <xref:System.Windows.Input.RoutedCommand>에서는 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 및 <xref:System.Windows.Input.CommandManager.Executed> 라우트된 이벤트를 발생시킵니다.  이러한 이벤트는 해당 특정 명령에 대한 <xref:System.Windows.Input.CommandBinding>을 찾아 요소 트리를 이동합니다.  <xref:System.Windows.Input.CommandBinding>이 발견되면 <xref:System.Windows.Input.CommandBinding>과 연결된 <xref:System.Windows.Input.ExecutedRoutedEventHandler>가 호출됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Input.RoutedCommand>   
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)