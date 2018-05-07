---
title: '방법: RoutedCommand 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: 75e6c435516fe2a174cf991bd41f24e1b30a212a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-routedcommand"></a>방법: RoutedCommand 만들기
이 예제에는 사용자 지정을 만드는 방법을 보여 줍니다 <xref:System.Windows.Input.RoutedCommand> 를 만들어서 사용자 지정 명령을 구현 하는 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 에 연결 하는 <xref:System.Windows.Input.CommandBinding>합니다.  명령에 대 한 자세한 내용은 참조는 [명령 실행 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)합니다.  
  
## <a name="example"></a>예제  
 만들 때 첫 번째 단계는 <xref:System.Windows.Input.RoutedCommand> 는 명령을 정의 하 고 인스턴스화하는 합니다.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 명령에 대해 정의 하는 이벤트 처리기를 만들 해야 응용 프로그램에서 명령을 사용 하려면  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 다음으로 <xref:System.Windows.Input.CommandBinding> 명령을 이벤트 처리기와 연결 하 만들어집니다. <xref:System.Windows.Input.CommandBinding> 특정 개체에 만들어집니다.  이 개체의 범위를 정의 고 <xref:System.Windows.Input.CommandBinding> 요소 트리에 있는  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 마지막 단계에서는 명령을 호출 합니다.  와 연결 하는 명령을 호출 하는 한 가지 방법은 <xref:System.Windows.Input.ICommandSource>와 같은 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 단추를 클릭할 때는 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드를 사용자 지정 <xref:System.Windows.Input.RoutedCommand> 호출 됩니다.  <xref:System.Windows.Input.RoutedCommand> 발생는 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 및 <xref:System.Windows.Input.CommandManager.Executed> 라우트된 이벤트입니다.  이러한 이벤트에 대 한 찾는 요소 트리를 탐색 한 <xref:System.Windows.Input.CommandBinding> 이 특정 명령에 대 한 합니다.  경우는 <xref:System.Windows.Input.CommandBinding> 발견 되는 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 연관 <xref:System.Windows.Input.CommandBinding> 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Input.RoutedCommand>  
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)
