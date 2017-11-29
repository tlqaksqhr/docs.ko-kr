---
title: "명령 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interfaces [WPF], ICommandSource
- command library [WPF]
- commands [WPF], definition of
- CommandBindings [WPF]
- ICommandSource interfaces [WPF]
- commanding [WPF]
- CommandManager [WPF]
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9b75319b5a07ac2ee1601f30394da641eb2b781c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="commanding-overview"></a>명령 개요
<a name="introduction"></a> 명령은 장치 입력보다 더 의미 있는 수준의 입력 처리를 제공하는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 입력 메커니즘입니다. 이러한 명령의 예로는 많은 응용 프로그램의 **복사**, **잘라내기** 및 **붙여넣기** 작업을 들 수 있습니다.  
  
 이 개요에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 명령, 명령 모델의 일부인 클래스 및 응용 프로그램에서 명령을 사용하고 만드는 방법을 정의합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [명령이란?](#commands_at_10000_feet)  
  
-   [WPF의 간단한 명령 예제](#simple_command)  
  
-   [WPF 명령의 네 가지 주요 개념](#Four_main_Concepts)  
  
-   [명령 라이브러리](#Command_Library)  
  
-   [사용자 지정 명령 만들기](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## <a name="what-are-commands"></a>명령이란?  
 명령의 목적에는 몇 가지가 있습니다. 첫 번째 목적은 명령을 실행하는 논리에서 명령을 호출하는 개체와 의미 체계를 분리하는 것입니다. 이렇게 하면 여러 소스에서 동일한 명령 논리를 호출할 수 있고 명령 논리가 여러 대상에 대해 사용자 지정될 수 있습니다. 예를 들어 다양한 사용자 작업이 명령을 사용하여 구현된 경우 이러한 작업을 사용하여 많은 응용 프로그램에 사용되는 편집 작업인 **복사**, **잘라내기** 및 **붙여넣기**를 호출할 수 있습니다. 응용 프로그램에서 단추를 클릭하거나, 메뉴에서 항목을 선택하거나, Ctrl+X 등의 키 조합을 사용하여 사용자가 선택한 개체 또는 텍스트를 잘라낼 수 있습니다. 명령을 사용하여 각 사용자 작업 형식을 동일한 논리에 바인딩할 수 있습니다.  
  
 명령의 또 다른 목적은 작업을 사용할 수 있는지 여부를 나타내는 것입니다. 개체 또는 텍스트 잘라내기의 경우 항목을 선택했을 때만 의미를 갖습니다. 사용자가 아무것도 선택하지 않고 개체 또는 텍스트를 잘라내려고 하면 작업이 수행되지 않습니다. 많은 응용 프로그램에서는 사용자가 작업 수행 가능 여부를 알 수 있도록 단추 및 메뉴 항목을 사용하지 않도록 설정합니다. 명령을 구현 하 여 동작 가능한 지 여부를 나타낼 수는 <xref:System.Windows.Input.ICommand.CanExecute%2A> 메서드. 단추에 가입할 수는 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트 경우 비활성화 되 고 <xref:System.Windows.Input.ICommand.CanExecute%2A> 반환 `false` 경우 활성화 될 <xref:System.Windows.Input.ICommand.CanExecute%2A> 반환 `true`합니다.  
  
 명령의 의미 체계는 모든 응용 프로그램 및 클래스에서 일관적일 수 있지만 작업의 논리는 수행된 특정 개체에 따라 다릅니다. 텍스트 클래스, 이미지 클래스 및 웹 브라우저에서 Ctrl+X 키 조합을 사용하면 **Cut** 명령이 호출되지만 **잘라내기** 작업을 수행하는 실제 논리는 잘라내기를 수행하는 응용 프로그램에 의해 정의됩니다. A <xref:System.Windows.Input.RoutedCommand> 논리를 구현 하는 클라이언트 수 있습니다. 텍스트 개체는 선택한 텍스트를 클립보드로 잘라낼 수 있지만 이미지 개체는 선택한 이미지를 잘라낼 수 있습니다. 응용 프로그램에서 처리 하는 경우는 <xref:System.Windows.Input.CommandManager.Executed> 이벤트 명령 대상에 액세스할 수 있으며 대상의 유형에 따라 적절 한 작업을 수행할 수 있습니다.  
  
<a name="simple_command"></a>   
## <a name="simple-command-example-in-wpf"></a>WPF의 간단한 명령 예제  
 명령을 사용 하는 가장 간단한 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 미리 정의 된 사용 하 여 <xref:System.Windows.Input.RoutedCommand> 명령 라이브러리 클래스; 중 하나에서 한 명령을 처리 하는;에 대 한 기본 지원을 있는 컨트롤을 사용 하 고 명령을 호출 하는 데 기본적으로 지 원하는 컨트롤을 사용 합니다.  <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령에서 미리 정의 된 명령 중 하나는 <xref:System.Windows.Input.ApplicationCommands> 클래스입니다.  <xref:System.Windows.Controls.TextBox> 컨트롤의 기본 제공 처리에 대 한 논리는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령입니다.  및 <xref:System.Windows.Controls.MenuItem> 클래스에는 기본적으로 지 원하는 명령을 호출 합니다.  
  
 설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.MenuItem> 를 클릭 하면 호출 됩니다는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령을 <xref:System.Windows.Controls.TextBox>되었다고 가정 하 고는 <xref:System.Windows.Controls.TextBox> 키보드 포커스가 합니다.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## <a name="four-main-concepts-in-wpf-commanding"></a>WPF 명령의 네 가지 주요 개념  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 라우트된 명령 모델은 명령, 명령 소스, 명령 대상 및 명령 바인딩 네 가지 주요 개념으로 나눌 수 있습니다.  
  
-   *명령*은 실행할 작업입니다.  
  
-   *명령 소스*는 명령을 호출하는 개체입니다.  
  
-   *명령 대상*은 명령이 실행되는 개체입니다.  
  
-   *명령 바인딩*은 명령 논리를 명령에 매핑하는 개체입니다.  
  
 이전 예에서 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 는 명령, 명령은 <xref:System.Windows.Controls.MenuItem> 명령 원본인는 <xref:System.Windows.Controls.TextBox> 명령 대상 이며 명령 바인딩을 제공는 <xref:System.Windows.Controls.TextBox> 컨트롤입니다.  아닌지 항상 대/소문자 주목할 하는 <xref:System.Windows.Input.CommandBinding> 명령 대상 클래스에 해당 하는 컨트롤에서 제공 됩니다.  경우가 매우 자주는 <xref:System.Windows.Input.CommandBinding> 응용 프로그램 개발자가 만들어야 합니다 또는 <xref:System.Windows.Input.CommandBinding> 명령 대상의 상위 항목에 연결할 수 있습니다.  
  
<a name="Commands"></a>   
### <a name="commands"></a>명령  
 명령은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현 하 여 만듭니다는 <xref:System.Windows.Input.ICommand> 인터페이스입니다.  <xref:System.Windows.Input.ICommand>두 개의 메서드를 노출 <xref:System.Windows.Input.ICommand.Execute%2A>, 및 <xref:System.Windows.Input.ICommand.CanExecute%2A>, 이벤트를 <xref:System.Windows.Input.ICommand.CanExecuteChanged>합니다. <xref:System.Windows.Input.ICommand.Execute%2A>명령과 사용 하 여 연결 된 작업을 수행 합니다. <xref:System.Windows.Input.ICommand.CanExecute%2A>현재 명령 대상에서 명령을 실행할 수 있는지 여부를 결정 합니다. <xref:System.Windows.Input.ICommand.CanExecuteChanged>명령 작업을 중앙 관리 하는 명령 관리자에서 발생 하는 되었지만 아직 실행 되지 않은 명령 바인딩에서 명령을 무효화할 수 있는 명령 원본에서 변경 내용을 검색 하는 경우 발생 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현의 <xref:System.Windows.Input.ICommand> 는 <xref:System.Windows.Input.RoutedCommand> 클래스 및이 개요의 중심은 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 주 입력 소스는 마우스, 키보드, 잉크 및 라우트된 명령입니다.  장치 지향 입력을 사용 하 여는 <xref:System.Windows.RoutedEvent> 입력된 이벤트가 발생 했음을 응용 프로그램 페이지에 있는 개체를 알릴 수 있습니다.  A <xref:System.Windows.Input.RoutedCommand> 도 마찬가지입니다.  <xref:System.Windows.Input.RoutedCommand.Execute%2A> 및 <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> 의 메서드는 <xref:System.Windows.Input.RoutedCommand> 명령에 대 한 응용 프로그램 논리를 포함 하지 않습니다 있지만 터널 라우트된 이벤트를 발생 하며을 가진 개체를 찾을 때까지 요소 트리를 통해 거품형 아니라는 <xref:System.Windows.Input.CommandBinding>합니다.  <xref:System.Windows.Input.CommandBinding> 이러한 이벤트에 대 한 처리기가 포함 되어 있고 그것이 명령을 수행 하는 처리기.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 이벤트 라우팅에 대한 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하세요.  
  
 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드를 한 <xref:System.Windows.Input.RoutedCommand> 발생는 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 및 <xref:System.Windows.Input.CommandManager.Executed> 명령 대상에서 이벤트입니다.  <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> 메서드를 한 <xref:System.Windows.Input.RoutedCommand> 발생는 <xref:System.Windows.Input.CommandManager.CanExecute> 및 <xref:System.Windows.Input.CommandManager.PreviewCanExecute> 명령 대상에서 이벤트입니다.  이러한 이벤트 터널을 가진 요소에 도달할 때까지 요소 트리를 통해 거품형은 <xref:System.Windows.Input.CommandBinding> 는 해당 명령에 대 한 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]여러 클래스에는 일반적인 라우트된 명령 집합을 분산 하는 공급: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands>, 및 <xref:System.Windows.Documents.EditingCommands>합니다.  이러한 클래스만 이루어진는 <xref:System.Windows.Input.RoutedCommand> 개체 및 명령에 대 한 구현 논리 하지 않습니다.  구현 논리는 명령이 실행 중인 개체에서 제공해야 합니다.  
  
<a name="Command_Sources"></a>   
### <a name="command-sources"></a>명령 소스  
 명령 소스는 명령을 호출하는 개체입니다.  명령 원본의 예로 <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button>, 및 <xref:System.Windows.Input.KeyGesture>합니다.  
  
 명령에 소스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 일반적으로 구현 된 <xref:System.Windows.Input.ICommandSource> 인터페이스입니다.  
  
 <xref:System.Windows.Input.ICommandSource>세 가지 속성을 노출: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>, 및 <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A>명령 소스가 호출 될 때 실행할 명령이입니다.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>명령을 실행할 대상 개체가입니다.  에 주목할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 속성 <xref:System.Windows.Input.ICommandSource> 인 적용 가능한 경우에는 <xref:System.Windows.Input.ICommand> 는 <xref:System.Windows.Input.RoutedCommand>합니다.  경우는 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 에 설정 되어는 <xref:System.Windows.Input.ICommandSource> 해당 명령이 아니며는 <xref:System.Windows.Input.RoutedCommand>, 명령 대상이 무시 됩니다. 경우는 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 키보드 포커스가 있는 요소에 명령 대상이 될를 설정 하지 않으면 합니다.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>정보를 전달 하는 처리기에 사용 되는 사용자 정의 데이터 형식은 명령을 구현 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현 하는 클래스 <xref:System.Windows.Input.ICommandSource> 는 <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink>, 및 <xref:System.Windows.Input.InputBinding>합니다.  <xref:System.Windows.Controls.Primitives.ButtonBase><xref:System.Windows.Controls.MenuItem>, 및 <xref:System.Windows.Documents.Hyperlink> 를 클릭할 때와 명령을 호출 <xref:System.Windows.Input.InputBinding> 명령을 호출 때는 <xref:System.Windows.Input.InputGesture> 관련으로 수행 됩니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.MenuItem> 에 <xref:System.Windows.Controls.ContextMenu> 명령 원본으로는 <xref:System.Windows.Input.ApplicationCommands.Properties%2A> 명령입니다.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 명령 소스를 수신 하는 일반적으로 <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged> 이벤트입니다.  이 이벤트는 현재 명령 대상에서 명령을 실행할 수 있는 기능이 변경되었을 수 있음을 명령 소스에 알립니다.  명령 소스가의 현재 상태를 쿼리할 수는 <xref:System.Windows.Input.RoutedCommand> 를 사용 하 여는 <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> 메서드.  명령을 실행할 수 없는 경우 명령 소스는 자체적으로 사용하지 않도록 설정될 수 있습니다.  이 예제는 <xref:System.Windows.Controls.MenuItem> 는 명령을 실행할 수 없는 경우 회색으로 합니다.  
  
 <xref:System.Windows.Input.InputGesture> 명령 원본으로 사용할 수 있습니다.  두 가지 유형의 입력된 제스처 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 됩니다는 <xref:System.Windows.Input.KeyGesture> 및 <xref:System.Windows.Input.MouseGesture>합니다.  생각할 수 있습니다는 <xref:System.Windows.Input.KeyGesture> 바로 가기 키 CTRL + C와 같은 합니다.  A <xref:System.Windows.Input.KeyGesture> 로 이루어진는 <xref:System.Windows.Input.Key> 및 집합이 <xref:System.Windows.Input.ModifierKeys>합니다.  A <xref:System.Windows.Input.MouseGesture> 로 이루어진는 <xref:System.Windows.Input.MouseAction> 및 선택적 집합 <xref:System.Windows.Input.ModifierKeys>합니다.  
  
 에 대 한 순서 대로 한 <xref:System.Windows.Input.InputGesture> 명령 소스 역할을 하는 명령과 사용 하 여 연결 되어야 합니다. 이 작업을 수행하는 방법은 몇 가지가 있습니다.  한 가지 방법은 사용 하는 <xref:System.Windows.Input.InputBinding>합니다.  
  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Input.KeyBinding> 간에 <xref:System.Windows.Input.KeyGesture> 및 <xref:System.Windows.Input.RoutedCommand>합니다.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 연결 하는 다른 방법은 <xref:System.Windows.Input.InputGesture> 에 <xref:System.Windows.Input.RoutedCommand> 추가 하는 것의 <xref:System.Windows.Input.InputGesture> 에 <xref:System.Windows.Input.InputGestureCollection> 에 <xref:System.Windows.Input.RoutedCommand>합니다.  
  
 추가 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Input.KeyGesture> 에 <xref:System.Windows.Input.InputGestureCollection> 의 <xref:System.Windows.Input.RoutedCommand>합니다.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### <a name="commandbinding"></a>CommandBinding  
 A <xref:System.Windows.Input.CommandBinding> 명령의 명령을 구현 하는 이벤트 처리기와 연결 합니다.  
  
 <xref:System.Windows.Input.CommandBinding> 클래스를 포함 한 <xref:System.Windows.Input.CommandBinding.Command%2A> 속성 및 <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute>, 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A>명령 하는 <xref:System.Windows.Input.CommandBinding> 와 연결 하는 중입니다.  에 연결 된 이벤트 처리기는 <xref:System.Windows.Input.CommandBinding.PreviewExecuted> 및 <xref:System.Windows.Input.CommandBinding.Executed> 명령 논리를 구현 하는 이벤트입니다.  에 연결 된 이벤트 처리기는 <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트 현재 명령 대상에서 명령을 실행할 수는 경우를 결정 합니다.  
  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Input.CommandBinding> 루트에 <xref:System.Windows.Window> 응용 프로그램의 합니다.  <xref:System.Windows.Input.CommandBinding> 연결는 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령을 <xref:System.Windows.Input.CommandManager.Executed> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 처리기입니다.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 다음으로 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 만들어집니다.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> 열립니다는 <xref:System.Windows.MessageBox> 알리는 명령이 실행 된 문자열을 표시 하는 합니다.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 설정는 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 속성을 `true`합니다.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 A <xref:System.Windows.Input.CommandBinding> 루트와 같은 특정 개체에 연결 된 <xref:System.Windows.Window> 응용 프로그램 또는 컨트롤의 합니다.  개체는는 <xref:System.Windows.Input.CommandBinding> 바인딩의 범위를 정의 하는 연결 합니다.  예를 들어 한 <xref:System.Windows.Input.CommandBinding> 연결 된 명령 상위 항목에 대상을 통해 연결할 수는 <xref:System.Windows.Input.CommandBinding.Executed> 이벤트, 하지만 <xref:System.Windows.Input.CommandBinding> 연결 된 하위 명령에 대상을 연결할 수 없습니다.  이 직접 방식의 <xref:System.Windows.RoutedEvent> 터널 및 이벤트를 발생 하는 개체에서 거품 합니다.  
  
 일부 경우에는 <xref:System.Windows.Input.CommandBinding> 와 같은 자체 명령 대상에 연결 되어는 <xref:System.Windows.Controls.TextBox> 클래스 및 <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, 및 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령입니다. 경우가 매우 자주,이 기능은 연결 하는 편리한 방법을 <xref:System.Windows.Input.CommandBinding> 예: 주 명령 대상에서의 부모에 <xref:System.Windows.Window> 또는 응용 프로그램 개체 경우에 특히 동일한 <xref:System.Windows.Input.CommandBinding> 여러 명령 대상에 사용할 수 있습니다.  명령 인프라를 만들 때 이러한 디자인 사항을 결정해야 합니다.  
  
<a name="Commane_Target"></a>   
### <a name="command-target"></a>명령 대상  
 명령 대상은 명령이 실행되는 요소입니다.  와 관련 하는 <xref:System.Windows.Input.RoutedCommand>, 명령 대상이 있는 라우팅에 있는 요소는 <xref:System.Windows.Input.CommandManager.Executed> 및 <xref:System.Windows.Input.CommandManager.CanExecute> 시작 합니다.  이전에 듯이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 속성을 <xref:System.Windows.Input.ICommandSource> 인 적용 가능한 경우에는 <xref:System.Windows.Input.ICommand> 는 <xref:System.Windows.Input.RoutedCommand>합니다.  경우는 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 에 설정 되어는 <xref:System.Windows.Input.ICommandSource> 해당 명령이 아니며는 <xref:System.Windows.Input.RoutedCommand>, 명령 대상이 무시 됩니다.  
  
 명령 소스는 명령 대상을 명시적으로 설정할 수 있습니다.  명령 대상이 정의되지 않은 경우 키보드 포커스가 있는 요소가 명령 대상으로 사용됩니다.  키보드 포커스가 있는 요소를 명령 대상으로 사용하면 응용 프로그램 개발자가 명령 대상을 추적하지 않고도 동일한 명령 소스를 사용하여 여러 대상에서 명령을 호출할 수 있다는 장점이 있습니다.  예를 들어 경우는 <xref:System.Windows.Controls.MenuItem> 호출는 **붙여넣기** 명령에 응용 프로그램을 한 <xref:System.Windows.Controls.TextBox> 제어 및 <xref:System.Windows.Controls.PasswordBox> 컨트롤이, 대상 하거나 될 수는 <xref:System.Windows.Controls.TextBox> 또는 <xref:System.Windows.Controls.PasswordBox> 에 따라 컨트롤에 키보드 포커스가 있습니다.  
  
 다음 예제에서는 태그 및 코드 숨김에서 명령 대상을 명시적으로 설정하는 방법을 보여 줍니다.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### <a name="the-commandmanager"></a>CommandManager  
 <xref:System.Windows.Input.CommandManager> 관련 함수를 여러 명령 하는 데 사용 합니다.  추가 및 제거 하기 위한 정적 메서드 집합을 제공 <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute>, 및 <xref:System.Windows.Input.CommandManager.CanExecute> 특정 요소와 이벤트 처리기입니다.  등록 하는 데 제공 <xref:System.Windows.Input.CommandBinding> 및 <xref:System.Windows.Input.InputBinding> 특정 클래스에는 개체입니다.  <xref:System.Windows.Input.CommandManager> 통해는 수단을 제공 된 <xref:System.Windows.Input.CommandManager.RequerySuggested> 이벤트를 발생 시켜야 하는 경우 명령에 알리기 위해는 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트입니다.  
  
 <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> 메서드는 <xref:System.Windows.Input.CommandManager> 시키려면는 <xref:System.Windows.Input.CommandManager.RequerySuggested> 이벤트입니다.  해야 하는 조건이 유용 명령을 하지는 않지만 사용 되는 조건은 <xref:System.Windows.Input.CommandManager> 를 인식 합니다.  
  
<a name="Command_Library"></a>   
## <a name="command-library"></a>명령 라이브러리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 미리 정의된 명령 집합을 제공합니다.  다음 클래스로 구성 됩니다 명령 라이브러리: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands>, 및 <xref:System.Windows.Input.ComponentCommands>합니다.  이러한 클래스는 같은 명령을 제공 <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> 및 <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A>, 및 <xref:System.Windows.Input.MediaCommands.Pause%2A>합니다.  
  
 이 중 많은 명령이 기본 입력 바인딩 집합을 포함합니다.  예를 들어 응용 프로그램에서 복사 명령을 처리하도록 지정하면 키보드 바인딩 "Ctrl+C"가 자동으로 지정됩니다. [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)] 펜 제스처 및 음성 정보 등 다른 입력 장치에 대한 바인딩도 사용할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 다양한 명령 라이브러리에서 명령을 참조할 때 일반적으로 정적 명령 특성을 노출하는 라이브러리 클래스의 클래스 이름을 생략할 수 있습니다. 일반적으로 명령 이름은 문자열처럼 명확하지 않으며 명령의 논리적 그룹화를 제공하기 위한 소유 유형이 존재하지만 명확성을 위해 반드시 필요하지는 않습니다. 예를 들어 더 자세한 `Command="ApplicationCommands.Cut"` 대신 `Command="Cut"`을 지정할 수 있습니다. 에 기본 제공 하는 편리한 메커니즘은이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 명령에 대 한 프로세서 (보다 정확 하 게 형식 변환기의 동작을은 <xref:System.Windows.Input.ICommand>, 어떤는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 로드 시 프로세서 참조).  
  
<a name="creating_commands"></a>   
## <a name="creating-custom-commands"></a>사용자 지정 명령 만들기  
 명령 라이브러리 클래스의 명령이 사용자 요구 사항을 충족시키지 못하면 사용자가 직접 명령을 만들 수 있습니다.  두 가지 방법으로 사용자 지정 명령을 만들 수 있습니다.  첫 번째는 처음부터 다시 시작 하 고 구현 하는 <xref:System.Windows.Input.ICommand> 인터페이스입니다.  일반적인 접근 방식 및 다른 방법으로 만드는 것을 <xref:System.Windows.Input.RoutedCommand> 또는 <xref:System.Windows.Input.RoutedUICommand>합니다.  
  
 사용자 지정 만들기에 대 한 예제 <xref:System.Windows.Input.RoutedCommand>, 참조 [사용자 지정 RoutedCommand 예제 만들기](http://go.microsoft.com/fwlink/?LinkID=159980)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Input.RoutedCommand>  
 <xref:System.Windows.Input.CommandBinding>  
 <xref:System.Windows.Input.InputBinding>  
 <xref:System.Windows.Input.CommandManager>  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [ICommandSource 구현](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)  
 [방법: MenuItem에 명령 추가](http://msdn.microsoft.com/en-us/013d68a0-5373-4a68-bd91-5de574307370)  
 [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980)(사용자 지정 RoutedCommand 샘플 만들기)
