---
title: "방법: 명령 사용 | Microsoft Docs"
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
  - "CommandBindings"
  - "명령"
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 명령 사용
다음 예제에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 명령을 사용하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.Input.RoutedCommand>를 <xref:System.Windows.Controls.Button>에 연결하고 <xref:System.Windows.Input.CommandBinding>을 만들고 <xref:System.Windows.Input.RoutedCommand>를 구현하는 이벤트 처리기를 만드는 방법을 보여 줍니다.  명령에 대한 자세한 내용은 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)를 참조하십시오.  
  
## 예제  
 첫 번째 코드 섹션에서는 <xref:System.Windows.Controls.Button>과 <xref:System.Windows.Controls.StackPanel>로 구성된 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 만들고 <xref:System.Windows.Input.RoutedCommand>에 명령 처리기를 연결하는 <xref:System.Windows.Input.CommandBinding>을 만듭니다.  
  
 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성을 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 명령에 연결합니다.  
  
 <xref:System.Windows.Input.CommandBinding>을 루트 <xref:System.Windows.Window>의 <xref:System.Windows.Input.CommandBindingCollection>에 추가합니다.  <xref:System.Windows.Input.CommandBinding.Executed> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트 처리기를 이 바인딩에 연결한 후 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 명령에 연결합니다.  
  
 <xref:System.Windows.Input.CommandBinding>이 없으면 명령 논리는 없고 명령을 호출하는 메커니즘만 있게 됩니다.  <xref:System.Windows.Controls.Button>을 클릭하면 명령 대상에서 <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent>가 발생한 후 <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>가 발생합니다.  이러한 이벤트는 해당 특정 명령에 대한 <xref:System.Windows.Input.CommandBinding>을 찾아 요소 트리를 이동합니다.  <xref:System.Windows.RoutedEvent>는 요소 트리를 터널링 및 버블링하므로 <xref:System.Windows.Input.CommandBinding>을 배치할 위치를 신중하게 선택해야 합니다.  <xref:System.Windows.Input.CommandBinding>이 명령 대상의 형제 대상에 있거나 이 <xref:System.Windows.RoutedEvent>의 경로에 없는 다른 노드에 있으면 <xref:System.Windows.Input.CommandBinding>이 액세스되지 않습니다.  
  
 [!code-xml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 다음 코드 섹션에서는 <xref:System.Windows.Input.CommandManager.Executed> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트 처리기를 구현합니다.  
  
 <xref:System.Windows.Input.CommandManager.Executed> 처리기는 열려 있는 파일을 닫기 위해 메서드를 호출합니다.  <xref:System.Windows.Input.CommandBinding.CanExecute> 처리기는 파일이 열려 있는지 여부를 확인하기 위해 메서드를 호출합니다.  파일이 열려 있으면 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A>가 `true`로 설정되고, 그렇지 않으면 `false`로 설정됩니다.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## 참고 항목  
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)