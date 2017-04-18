---
title: "명령 개요 | Microsoft Docs"
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
  - "클래스, CommandBinding"
  - "명령 라이브러리"
  - "CommandBindings"
  - "명령"
  - "CommandManager"
  - "명령, 정의"
  - "ICommandSource 인터페이스"
  - "인터페이스, ICommandSource"
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# 명령 개요
<a name="introduction"></a> 명령은 장치 입력보다 더 의미적 수준에서 입력 처리를 제공하는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 입력 메커니즘입니다.  이러한 명령의 예로 여러 응용 프로그램에서 볼 수 있는 **복사**, **잘라내기**, **붙여넣기** 작업이 있습니다.  
  
 이 개요 부분에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 사용하는 명령 및 명령 모델을 구성하는 클래스에 대해 알아보고 응용 프로그램에서 명령을 사용하고 만드는 방법에 대해 설명합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [명령의 정의](#commands_at_10000_feet)  
  
-   [WPF의 간단한 명령 예제](#simple_command)  
  
-   [WPF 명령의 네 가지 주요 개념](#Four_main_Concepts)  
  
-   [명령 라이브러리](#Command_Library)  
  
-   [사용자 지정 명령 만들기](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## 명령의 정의  
 명령에는 몇 가지 목적이 있습니다.  첫 번째 목적은 명령을 실행하는 논리에서 명령을 호출하는 개체와 의미 체계를 분리하는 것입니다.  이와 같은 특징 때문에 서로 다른 여러 소스가 동일한 명령 논리를 호출할 수 있으며 명령 논리를 여러 대상에 대해 사용자 지정할 수 있습니다.  예를 들어 여러 응용 프로그램에서 볼 수 있는 **복사**, **잘라내기** 및 **붙여넣기** 등의 편집 작업은 명령을 사용하여 구현된 경우 서로 다른 사용자 작업을 통해 호출될 수 있습니다.  응용 프로그램에서 사용자는 단추를 클릭하거나, 메뉴에서 항목을 선택하거나, Ctrl\+X와 같은 키 조합을 사용하여 선택한 개체 또는 텍스트를 잘라낼 수 있습니다.  명령을 사용하면 각 사용자 작업 유형을 동일한 논리에 바인딩할 수 있습니다.  
  
 명령의 또 다른 목적은 작업이 사용 가능한지 여부를 표시하는 것입니다.  개체 또는 텍스트 잘라내기의 예를 계속 들자면, 이 작업은 무엇인가가 선택되어 있을 때만 수행 가능합니다.  사용자가 아무 것도 선택하지 않은 상태에서 개체 또는 텍스트를 잘라내려고 하면 아무 작업도 수행되지 않습니다.  사용자에게 이를 알리기 위해 여러 응용 프로그램에서는 작업이 수행 가능한지 여부를 알 수 있도록 단추 및 메뉴 항목을 비활성화합니다.  명령에서는 <xref:System.Windows.Input.ICommand.CanExecute%2A> 메서드를 구현하여 작업이 가능한지 여부를 나타낼 수 있습니다.  단추는 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트에 가입할 수 있으며, <xref:System.Windows.Input.ICommand.CanExecute%2A>가 `false`를 반환하는 경우 비활성화되고 <xref:System.Windows.Input.ICommand.CanExecute%2A>가 `true`를 반환하는 경우 활성화될 수 있습니다.  
  
 명령의 의미 체계는 응용 프로그램과 클래스 전체에서 일관될 수 있지만 작업 논리는 작업 대상 개체마다 다릅니다.  Ctrl\+X 키 조합은 텍스트 클래스, 이미지 클래스 및 웹 브라우저에서 **잘라내기** 명령을 호출하지만 **잘라내기** 작업을 수행하는 실제 논리는 잘라내기를 수행하는 응용 프로그램에 의해 정의됩니다.  <xref:System.Windows.Input.RoutedCommand>는 클라이언트에서 이 논리를 구현할 수 있도록 해 줍니다.  텍스트 개체는 선택된 텍스트를 잘라내 클립보드에 넣는 반면, 이미지 개체는 선택된 이미지를 잘라냅니다.  응용 프로그램에서는 <xref:System.Windows.Input.CommandManager.Executed> 이벤트를 처리할 때 명령의 대상에 액세스한 다음 대상 형식에 따라 적절한 작업을 수행할 수 있습니다.  
  
<a name="simple_command"></a>   
## WPF의 간단한 명령 예제  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 명령을 사용하는 가장 쉬운 방법은 명령 라이브러리 클래스 중 하나에서 미리 정의된 <xref:System.Windows.Input.RoutedCommand>를 사용하는 것입니다. 즉, 명령 처리 및 명령 호출을 기본적으로 지원하는 컨트롤을 사용하면 쉽습니다.  <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령은 <xref:System.Windows.Input.ApplicationCommands> 클래스의 미리 정의된 명령 중 하나입니다.  <xref:System.Windows.Controls.TextBox> 컨트롤에는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령을 처리하는 논리가 기본적으로 포함되어 있습니다.  또한 <xref:System.Windows.Controls.MenuItem> 클래스에는 명령 호출 기능이 기본적으로 포함되어 있습니다.  
  
 다음 예제에서는 클릭하면 <xref:System.Windows.Controls.TextBox>에서 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령을 호출하도록 <xref:System.Windows.Controls.MenuItem>을 설정하는 방법을 보여 줍니다. 이 예제에서는 <xref:System.Windows.Controls.TextBox>에 키보드 포커스가 있다고 가정합니다.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## WPF 명령의 네 가지 주요 개념  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 라우트된 명령 모델은 명령, 명령 소스, 명령 대상 및 명령 바인딩이라는 네 가지 주요 개념으로 나눌 수 있습니다.  
  
-   *명령*은 실행할 작업입니다.  
  
-   *명령 소스*는 명령을 호출하는 개체입니다.  
  
-   *명령 대상*은 명령이 실행되는 개체입니다.  
  
-   *명령 바인딩*은 명령 논리를 명령에 매핑하는 개체입니다.  
  
 앞의 예제에서는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령이 명령이고, <xref:System.Windows.Controls.MenuItem>이 명령 소스이고, <xref:System.Windows.Controls.TextBox>가 명령 대상이며 <xref:System.Windows.Controls.TextBox> 컨트롤이 명령 바인딩을 제공합니다.  명령 대상 클래스가 항상 <xref:System.Windows.Input.CommandBinding>을 제공하는 것은 아니며,  응용 프로그램 개발자가 <xref:System.Windows.Input.CommandBinding>을 직접 만들거나 <xref:System.Windows.Input.CommandBinding>이 명령 대상의 상위 요소에 연결되어 있는 경우도 많습니다.  
  
<a name="Commands"></a>   
### 명령  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 명령은 <xref:System.Windows.Input.ICommand> 인터페이스를 구현하여 만듭니다.  <xref:System.Windows.Input.ICommand>는 <xref:System.Windows.Input.ICommand.Execute%2A> 및 <xref:System.Windows.Input.ICommand.CanExecute%2A>라는 두 개의 메서드와 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트를 노출합니다.  <xref:System.Windows.Input.ICommand.Execute%2A>는 명령과 연결된 동작을 수행하고, <xref:System.Windows.Input.ICommand.CanExecute%2A>는 명령을 현재 명령 대상에 대해 실행할 수 있는지 여부를 결정합니다.  명령 작업을 중앙 관리하는 명령 관리자가 이미 발생했지만 명령 바인딩을 통해 아직 실행되지 않은 명령을 무효화할 수 있는 명령 소스 변경 사항을 발견하면 <xref:System.Windows.Input.ICommand.CanExecuteChanged>가 발생합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Input.RoutedCommand> 클래스가 <xref:System.Windows.Input.ICommand>의 구현이며 이 개요에서는 이 클래스에 대해 중점적으로 설명합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 주요 입력 소스는 마우스, 키보드, 잉크 및 라우트된 명령입니다.  장치에서 발생하는 입력은 <xref:System.Windows.RoutedEvent>를 통해 입력 이벤트가 발생했음을 응용 프로그램 페이지의 개체에 알립니다.  <xref:System.Windows.Input.RoutedCommand>도 마찬가지입니다.  <xref:System.Windows.Input.RoutedCommand>의 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 및 <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> 메서드는 명령에 대한 응용 프로그램 논리를 포함하지 않으며 대신 <xref:System.Windows.Input.CommandBinding>을 가진 개체를 찾을 때까지 요소 트리를 터널링 및 버블링하는 라우트된 이벤트를 발생시킵니다.  <xref:System.Windows.Input.CommandBinding>에는 이러한 이벤트에 대한 처리기가 들어 있어 해당 처리기가 명령을 수행합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 이벤트 라우팅에 대한 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Input.RoutedCommand>의 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드는 명령 대상에서 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 및 <xref:System.Windows.Input.CommandManager.Executed> 이벤트를 발생시킵니다.  <xref:System.Windows.Input.RoutedCommand>의 <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> 메서드는 명령 대상에서 <xref:System.Windows.Input.CommandManager.CanExecute> 및 <xref:System.Windows.Input.CommandManager.PreviewCanExecute> 이벤트를 발생시킵니다.  이러한 이벤트는 해당 명령의 <xref:System.Windows.Input.CommandBinding>을 가진 요소를 찾을 때까지 요소 트리를 통해 터널링 및 버블링됩니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 여러 클래스에 분산된 형태로 공용 라우트된 명령인 <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Documents.EditingCommands>를 제공합니다.  이러한 클래스는 <xref:System.Windows.Input.RoutedCommand> 개체로만 구성되며 명령 논리는 구현하지 않습니다.  명령 논리는 명령이 실행되는 개체에서 구현합니다.  
  
<a name="Command_Sources"></a>   
### 명령 소스  
 명령 소스는 명령을 호출하는 개체입니다.  명령 소스의 예로는 <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Input.KeyGesture>가 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 명령 소스는 일반적으로 <xref:System.Windows.Input.ICommandSource> 인터페이스를 구현합니다.  
  
 <xref:System.Windows.Input.ICommandSource>는 <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 및 <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>라는 세 가지 속성을 노출합니다.  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A>는 명령 소스가 호출될 때 실행할 명령입니다.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>은 명령이 실행될 개체입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Input.ICommand>가 <xref:System.Windows.Input.RoutedCommand>인 경우에만 <xref:System.Windows.Input.ICommandSource>에 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 속성을 적용할 수 있습니다.  <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>이 <xref:System.Windows.Input.ICommandSource>에 설정되어 있고 해당 명령이 <xref:System.Windows.Input.RoutedCommand>가 아니면 명령 대상이 무시됩니다.  <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>이 설정되어 있지 않으면 키보드 포커스가 있는 요소가 명령 대상이 됩니다.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>는 명령을 구현하는 처리기에 정보를 전달하는 데 사용되는 사용자 정의 데이터 형식입니다.  
  
 <xref:System.Windows.Input.ICommandSource>를 구현하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스로는 <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink> 및 <xref:System.Windows.Input.InputBinding>이 있습니다.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem> 및 <xref:System.Windows.Documents.Hyperlink>는 클릭될 때 명령을 호출하고, <xref:System.Windows.Input.InputBinding>은 연결된 <xref:System.Windows.Input.InputGesture>가 수행될 때 명령을 호출합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.ContextMenu>의 <xref:System.Windows.Controls.MenuItem>을 <xref:System.Windows.Input.ApplicationCommands.Properties%2A> 명령의 명령 소스로 사용하는 방법을 보여 줍니다.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 일반적으로 명령 소스는 <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged> 이벤트를 수신합니다.  이 이벤트는 현재 명령 대상에 대해 실행할 명령의 기능이 변경되었을 수 있음을 명령 소스에 알립니다.  명령 소스는 <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> 메서드를 사용하여 <xref:System.Windows.Input.RoutedCommand>의 현재 상태를 쿼리할 수 있습니다.  명령을 실행할 수 없는 경우 명령 소스는 자체적으로 비활성화됩니다.  명령을 실행할 수 없을 때 <xref:System.Windows.Controls.MenuItem>이 회색으로 표시되는 경우가 여기에 해당합니다.  
  
 <xref:System.Windows.Input.InputGesture>를 명령 소스로 사용할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 <xref:System.Windows.Input.KeyGesture> 및 <xref:System.Windows.Input.MouseGesture>라는 두 가지 유형의 입력 제스처가 있습니다.  <xref:System.Windows.Input.KeyGesture>는 Ctrl\+C 같은 바로 가기 키입니다.  <xref:System.Windows.Input.KeyGesture>는 <xref:System.Windows.Input.Key>와 <xref:System.Windows.Input.ModifierKeys>의 집합으로 구성되고,  <xref:System.Windows.Input.MouseGesture>는 <xref:System.Windows.Input.MouseAction>과 <xref:System.Windows.Input.ModifierKeys>의 선택적 집합으로 구성됩니다.  
  
 <xref:System.Windows.Input.InputGesture>를 명령 소스로 사용하려면 여기에 명령을 연결해야 합니다.  이 작업은 몇 가지 방법으로 수행할 수 있습니다.  그 중 하나는 <xref:System.Windows.Input.InputBinding>을 사용하는 것입니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.KeyGesture>와 <xref:System.Windows.Input.RoutedCommand> 사이에 <xref:System.Windows.Input.KeyBinding>을 만드는 방법을 보여 줍니다.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 <xref:System.Windows.Input.RoutedCommand>의 <xref:System.Windows.Input.InputGestureCollection>에 <xref:System.Windows.Input.InputGesture>를 추가하여 <xref:System.Windows.Input.InputGesture>를 <xref:System.Windows.Input.RoutedCommand>에 연결할 수도 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.RoutedCommand>의 <xref:System.Windows.Input.InputGestureCollection>에 <xref:System.Windows.Input.KeyGesture>를 추가하는 방법을 보여 줍니다.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### CommandBinding  
 <xref:System.Windows.Input.CommandBinding>은 명령을 구현하는 이벤트 처리기에 명령을 연결합니다.  
  
 <xref:System.Windows.Input.CommandBinding> 클래스에는 <xref:System.Windows.Input.CommandBinding.Command%2A> 속성과 <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트가 포함됩니다.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A>는 <xref:System.Windows.Input.CommandBinding>을 연결하는 명령이고,  <xref:System.Windows.Input.CommandBinding.PreviewExecuted> 및 <xref:System.Windows.Input.CommandBinding.Executed> 이벤트에 연결된 이벤트 처리기는 명령 논리를 구현합니다.  <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트에 연결된 이벤트 처리기는 현재 명령 대상에 대해 명령을 실행할 수 있는지 여부를 결정합니다.  
  
 다음 예제에서는 응용 프로그램의 루트 <xref:System.Windows.Window>에 <xref:System.Windows.Input.CommandBinding>을 만드는 방법을 보여 줍니다.  <xref:System.Windows.Input.CommandBinding>은 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령을 <xref:System.Windows.Input.CommandManager.Executed> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 처리기와 연결합니다.  
  
 [!code-xml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 그런 다음 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler>를 만듭니다.  <xref:System.Windows.Input.ExecutedRoutedEventHandler>는 명령이 실행되었음을 알리는 문자열을 표시하는 <xref:System.Windows.MessageBox>를 엽니다.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler>는 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 속성을 `true`로 설정합니다.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 <xref:System.Windows.Input.CommandBinding>은 응용 프로그램이나 컨트롤의 루트 <xref:System.Windows.Window>와 같은 특정 개체에 연결됩니다.  <xref:System.Windows.Input.CommandBinding>이 연결된 개체에 따라 바인딩 범위가 정의됩니다.  예를 들어 <xref:System.Windows.Input.CommandBinding.Executed> 이벤트로 명령 대상의 상위 요소에 연결된 <xref:System.Windows.Input.CommandBinding>을 찾을 수 있지만 명령 대상의 하위 요소에 연결된 <xref:System.Windows.Input.CommandBinding>은 찾을 수 없습니다.  이는 이벤트를 발생시킨 개체로부터 <xref:System.Windows.RoutedEvent>가 터널링 및 버블링되는 방법 때문입니다.  
  
 <xref:System.Windows.Controls.TextBox> 클래스와 <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A> 및 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령의 경우처럼 <xref:System.Windows.Input.CommandBinding>이 명령 대상 자체에 연결되기도 합니다.  그러나 대개 <xref:System.Windows.Input.CommandBinding>을 명령 대상의 상위 요소\(예: 주 <xref:System.Windows.Window> 또는 응용 프로그램 개체\)에 연결하면 더 편리하며, 특히 동일한 <xref:System.Windows.Input.CommandBinding>을 여러 명령 대상에 사용할 수 있는 경우에는 이 방법을 사용하는 것이 좋습니다.  이러한 디자인 결정 사항은 명령 인프라를 직접 만들 때 고려하는 것이 좋습니다.  
  
<a name="Commane_Target"></a>   
### 명령 대상  
 명령 대상은 명령이 실행될 요소입니다.  <xref:System.Windows.Input.RoutedCommand>와 관련하여 명령 대상은 <xref:System.Windows.Input.CommandManager.Executed> 및 <xref:System.Windows.Input.CommandManager.CanExecute>의 라우팅이 시작되는 요소입니다.  앞에서 설명했듯이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Input.ICommand>가 <xref:System.Windows.Input.RoutedCommand>인 경우에만 <xref:System.Windows.Input.ICommandSource>에 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 속성을 적용할 수 있습니다.  <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>이 <xref:System.Windows.Input.ICommandSource>에 설정되어 있고 해당 명령이 <xref:System.Windows.Input.RoutedCommand>가 아니면 명령 대상이 무시됩니다.  
  
 명령 소스가 명령 대상을 명시적으로 설정할 수 있습니다.  명령 대상이 정의되어 있지 않으면 키보드 포커스가 있는 요소가 명령 대상으로 사용됩니다.  키보드 포커스가 있는 요소를 명령 대상으로 사용하면 응용 프로그램 개발자가 명령 대상을 따로 관리하지 않고 같은 명령 소스를 사용하여 여러 대상에서 명령을 호출할 수 있다는 장점이 있습니다.  예를 들어 <xref:System.Windows.Controls.TextBox> 컨트롤과 <xref:System.Windows.Controls.PasswordBox> 컨트롤이 있는 응용 프로그램에서 <xref:System.Windows.Controls.MenuItem>이 **붙여넣기** 명령을 호출할 경우, <xref:System.Windows.Controls.TextBox>와 <xref:System.Windows.Controls.PasswordBox> 중 키보드 포커스가 어느 컨트롤에 있는지에 따라 대상이 결정됩니다.  
  
 다음 예제에서는 태그 및 코드 숨김에서 명령 대상을 명시적으로 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### CommandManager  
 <xref:System.Windows.Input.CommandManager>는 명령과 관련된 여러 가지 기능을 수행합니다.  예를 들어 특정 요소에서 <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute> 및 <xref:System.Windows.Input.CommandManager.CanExecute> 이벤트 처리기를 추가하고 제거하는 정적 메서드 집합을 제공하며,  특정 클래스에 <xref:System.Windows.Input.CommandBinding> 및 <xref:System.Windows.Input.InputBinding> 개체를 등록하는 데 사용되기도 합니다.  <xref:System.Windows.Input.CommandManager>는 또한 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트를 발생시켜야 하는 시점을 <xref:System.Windows.Input.CommandManager.RequerySuggested> 이벤트를 통해 명령에 알립니다.  
  
 <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> 메서드는 <xref:System.Windows.Input.CommandManager>에서 <xref:System.Windows.Input.CommandManager.RequerySuggested> 이벤트를 발생시키도록 합니다.  이 기능은 명령을 비활성화\/활성화해야 하지만 <xref:System.Windows.Input.CommandManager>에서 이를 인식할 수 없는 경우에 유용합니다.  
  
<a name="Command_Library"></a>   
## 명령 라이브러리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 미리 정의된 명령 집합을 제공합니다.  명령 라이브러리는 <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands> 및 <xref:System.Windows.Input.ComponentCommands> 클래스로 구성됩니다.  이러한 클래스는 <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A> 및 <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A>, <xref:System.Windows.Input.MediaCommands.Pause%2A> 같은 명령을 제공합니다.  
  
 이러한 명령 대부분에는 기본 입력 바인딩 집합이 있습니다.  예를 들어 응용 프로그램에서 복사 명령을 처리하도록 지정하면 "Ctrl\+C" 키보드 바인딩이 자동으로 설정됩니다. 그 외에 [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)] 펜 제스처 및 음성 정보와 같이 다른 입력 장치에 대한 바인딩도 기본적으로 사용할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 다양한 명령 라이브러리에서 명령을 참조하는 경우에는 정적 명령 속성을 노출하는 라이브러리의 클래스 이름을 생략할 수 있습니다.  일반적으로 명령 이름은 문자열같이 명확하며 소유 형식을 통해 명령이 논리적으로 그룹화되어 있지만 이러한 소유 형식은 명령을 명확하게 구분하는 데 반드시 필요한 것은 아닙니다.  예를 들어 `Command="ApplicationCommands.Cut"` 대신 `Command="Cut"`와 같이 간단하게 명령을 지정할 수 있습니다.  이 편리한 메커니즘은 명령에 사용할 수 있도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 기본적으로 구현됩니다. 엄밀하게 말하자면 이 메커니즘은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세스가 로드 시 참조하는 <xref:System.Windows.Input.ICommand>의 형식 변환기 동작입니다.  
  
<a name="creating_commands"></a>   
## 사용자 지정 명령 만들기  
 명령 라이브러리 클래스의 명령으로 필요한 기능을 구현할 수 없는 경우에는 사용자 지정 명령을 만들 수 있습니다.  사용자 지정 명령은 두 가지 방법으로 만들 수 있습니다.  하나는 <xref:System.Windows.Input.ICommand> 인터페이스를 처음부터 만들어 구현하는 것이고,  다른 하나는 <xref:System.Windows.Input.RoutedCommand> 또는 <xref:System.Windows.Input.RoutedUICommand>를 만드는 방법으로, 이 방법이 더 일반적으로 사용됩니다.  
  
 사용자 지정 <xref:System.Windows.Input.RoutedCommand>를 만드는 예제를 보려면 [Create a Custom RoutedCommand 샘플](http://go.microsoft.com/fwlink/?LinkID=159980)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Input.RoutedCommand>   
 <xref:System.Windows.Input.CommandBinding>   
 <xref:System.Windows.Input.InputBinding>   
 <xref:System.Windows.Input.CommandManager>   
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [ICommandSource 구현](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)   
 [How to: Add a Command to a MenuItem](http://msdn.microsoft.com/ko-kr/013d68a0-5373-4a68-bd91-5de574307370)   
 [Create a Custom RoutedCommand 샘플](http://go.microsoft.com/fwlink/?LinkID=159980)