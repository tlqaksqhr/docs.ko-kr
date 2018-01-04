---
title: "방법: 명령을 지원하지 않는 컨트롤에 명령 후크"
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
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 804c4ffd54a0f8cc94e8849a223b1af8b27a58b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>방법: 명령을 지원하지 않는 컨트롤에 명령 후크
후크 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Input.RoutedCommand> 에 <xref:System.Windows.Controls.Control> 는 않는 하지 기본적으로 명령에 대 한 지원.  여러 소스에 명령을 후크하는 전체 샘플은 [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980)(사용자 지정 RoutedCommand 만들기 샘플)을 참조하세요.  
  
## <a name="example"></a>예  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 응용 프로그램 프로그래머가 자주 접하게 되는 공용 명령의 라이브러리를 제공합니다.  클래스는 명령 라이브러리를 구성 하는: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, 및 <xref:System.Windows.Documents.EditingCommands>합니다.  
  
 정적 <xref:System.Windows.Input.RoutedCommand> 이러한 클래스를 구성 하는 개체 명령 논리를 제공 하지 않습니다.  사용 하 여 명령과와 연결 된 명령에 대 한 논리는 <xref:System.Windows.Input.CommandBinding>합니다.  많은 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기본적으로 명령은 라이브러리에서 명령 중 일부에 대 한 지원.  <xref:System.Windows.Controls.TextBox>예를 들어와 같은 다양 한 응용 프로그램 편집 명령을 지원 <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, 및 <xref:System.Windows.Input.ApplicationCommands.Undo%2A>합니다.  응용 프로그램 개발자는 이러한 명령을 컨트롤과 함께 사용하기 위해 별도로 해야 하는 작업은 없습니다.  경우는 <xref:System.Windows.Controls.TextBox> 가 명령 대상 명령이 실행 될 때 사용 하 여 명령을 처리할 수 있으므로 <xref:System.Windows.Input.CommandBinding> 컨트롤에 내장 되어 있습니다.  
  
 다음을 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Button> 에 대 한 명령 소스로 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령입니다.  A <xref:System.Windows.Input.CommandBinding> 지정된 된 연결 하 만들어집니다 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 와 <xref:System.Windows.Input.RoutedCommand>합니다.  
  
 첫째, 명령 소스가 만들어집니다.  A <xref:System.Windows.Controls.Button> 명령 원본으로 사용 됩니다.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 다음으로 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 만들어집니다.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> 열면는 <xref:System.Windows.MessageBox> 명령이 실행 되었음을 나타내는입니다.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 설정는 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 속성을 `true`합니다.  일반적으로 수 있는 실행 처리기를 현재 명령 대상에서 명령을 실행할 수 있습니다 하는 경우 보다 강력한 확인을 수행 합니다.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 마지막으로, 한 <xref:System.Windows.Input.CommandBinding> 루트에 만들어집니다 <xref:System.Windows.Window> 라우트된 이벤트 처리기를 연결 하는 응용 프로그램의는 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령입니다.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>참고 항목  
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [명령을 지원하는 컨트롤에 명령 후크](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
