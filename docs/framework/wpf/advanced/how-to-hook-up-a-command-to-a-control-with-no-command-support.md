---
title: "방법: 명령을 지원하지 않는 컨트롤에 명령 후크 | Microsoft Docs"
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
  - "클래스, 컨트롤, RoutedCommand 연결"
  - "클래스, RoutedCommand, 컨트롤에 연결"
  - "Control 클래스, RoutedCommand 연결"
  - "RoutedCommand 클래스, 컨트롤에 연결"
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 명령을 지원하지 않는 컨트롤에 명령 후크
다음 예제에서는 명령을 기본적으로 지원하지 않는 <xref:System.Windows.Controls.Control>에 <xref:System.Windows.Input.RoutedCommand>를 후크하는 방법을 보여 줍니다.  여러 소스에 명령을 후크하는 방법을 보여 주는 전체 샘플은 [Create a Custom RoutedCommand 샘플](http://go.microsoft.com/fwlink/?LinkID=159980)을 참조하십시오.  
  
## 예제  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]은 응용 프로그램 프로그래머가 흔히 사용하는 일반 명령이 포함된 라이브러리를 제공합니다.  이 명령 라이브러리를 구성하는 클래스는 <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> 및 <xref:System.Windows.Documents.EditingCommands>입니다.  
  
 이러한 클래스를 구성하는 정적 <xref:System.Windows.Input.RoutedCommand> 개체는 명령 논리를 제공하지 않습니다.  명령 논리는 <xref:System.Windows.Input.CommandBinding>을 통해 명령에 연결됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공하는 대부분의 컨트롤은 명령 라이브러리의 일부 명령을 기본적으로 지원합니다.  예를 들어 <xref:System.Windows.Controls.TextBox>는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> 및 <xref:System.Windows.Input.ApplicationCommands.Undo%2A>와 같은 대부분의 응용 프로그램 편집 명령을 지원합니다.  따라서 응용 프로그램 개발자는 컨트롤에서 이러한 명령이 작동하도록 하기 위해 특별한 작업을 수행할 필요가 없습니다.  명령이 실행될 때 명령 대상이 <xref:System.Windows.Controls.TextBox>인 경우 컨트롤에 기본적으로 제공된 <xref:System.Windows.Input.CommandBinding>을 사용하여 명령을 처리합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button>을 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령의 명령 소스로 사용하는 방법을 보여 줍니다.  지정된 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler>를 <xref:System.Windows.Input.RoutedCommand>에 연결하는 <xref:System.Windows.Input.CommandBinding>을 만듭니다.  
  
 먼저 명령 소스를 만듭니다.  <xref:System.Windows.Controls.Button>을 명령 소스로 사용합니다.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 그런 다음 <xref:System.Windows.Input.ExecutedRoutedEventHandler>와 <xref:System.Windows.Input.CanExecuteRoutedEventHandler>를 만듭니다.  <xref:System.Windows.Input.ExecutedRoutedEventHandler>는 단순히 <xref:System.Windows.MessageBox>를 열어 명령이 실행되었음을 보여 줍니다.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler>는 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 속성을 `true`로 설정합니다.  일반적으로 CanExecute 처리기는 현재 명령 대상에서 명령을 실행할 수 있는지 여부를 확인하기 위해 보다 강력한 확인 작업을 수행합니다.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 마지막으로, 라우트된 이벤트 처리기를 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령에 연결하는 응용 프로그램의 루트 <xref:System.Windows.Window>에 <xref:System.Windows.Input.CommandBinding>을 만듭니다.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## 참고 항목  
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [명령을 지원하는 컨트롤에 명령 후크](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)