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
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a><span data-ttu-id="0a2b7-102">방법: 명령을 지원하지 않는 컨트롤에 명령 후크</span><span class="sxs-lookup"><span data-stu-id="0a2b7-102">How to: Hook Up a Command to a Control with No Command Support</span></span>
<span data-ttu-id="0a2b7-103">후크 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Input.RoutedCommand> 에 <xref:System.Windows.Controls.Control> 는 않는 하지 기본적으로 명령에 대 한 지원.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-103">The following example shows how to hook up a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Control> which does not have built in support for the command.</span></span>  <span data-ttu-id="0a2b7-104">여러 소스에 명령을 후크하는 전체 샘플은 [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980)(사용자 지정 RoutedCommand 만들기 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-104">For a complete sample which hooks up commands to multiple sources, see the [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980) sample.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a2b7-105">예</span><span class="sxs-lookup"><span data-stu-id="0a2b7-105">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="0a2b7-106">는 응용 프로그램 프로그래머가 자주 접하게 되는 공용 명령의 라이브러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-106"> provides a library of common commands which application programmers encounter regularly.</span></span>  <span data-ttu-id="0a2b7-107">클래스는 명령 라이브러리를 구성 하는: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, 및 <xref:System.Windows.Documents.EditingCommands>합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-107">The classes which comprise the command library are: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, and <xref:System.Windows.Documents.EditingCommands>.</span></span>  
  
 <span data-ttu-id="0a2b7-108">정적 <xref:System.Windows.Input.RoutedCommand> 이러한 클래스를 구성 하는 개체 명령 논리를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-108">The static <xref:System.Windows.Input.RoutedCommand> objects which make up these classes do not supply command logic.</span></span>  <span data-ttu-id="0a2b7-109">사용 하 여 명령과와 연결 된 명령에 대 한 논리는 <xref:System.Windows.Input.CommandBinding>합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-109">The logic for the command is associated with the command with a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="0a2b7-110">많은 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기본적으로 명령은 라이브러리에서 명령 중 일부에 대 한 지원.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-110">Many controls in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] have built in support for some of the commands in the command library.</span></span>  <span data-ttu-id="0a2b7-111"><xref:System.Windows.Controls.TextBox>예를 들어와 같은 다양 한 응용 프로그램 편집 명령을 지원 <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, 및 <xref:System.Windows.Input.ApplicationCommands.Undo%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-111"><xref:System.Windows.Controls.TextBox>, for example, supports many of the application edit commands such as <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, and <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.</span></span>  <span data-ttu-id="0a2b7-112">응용 프로그램 개발자는 이러한 명령을 컨트롤과 함께 사용하기 위해 별도로 해야 하는 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-112">The application developer does not have to do anything special to get these commands to work with these controls.</span></span>  <span data-ttu-id="0a2b7-113">경우는 <xref:System.Windows.Controls.TextBox> 가 명령 대상 명령이 실행 될 때 사용 하 여 명령을 처리할 수 있으므로 <xref:System.Windows.Input.CommandBinding> 컨트롤에 내장 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-113">If the <xref:System.Windows.Controls.TextBox> is the command target when the command is executed, it will handle the command using the <xref:System.Windows.Input.CommandBinding> that is built into the control.</span></span>  
  
 <span data-ttu-id="0a2b7-114">다음을 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Button> 에 대 한 명령 소스로 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-114">The following shows how to use a <xref:System.Windows.Controls.Button> as the command source for the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  <span data-ttu-id="0a2b7-115">A <xref:System.Windows.Input.CommandBinding> 지정된 된 연결 하 만들어집니다 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 와 <xref:System.Windows.Input.RoutedCommand>합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-115">A <xref:System.Windows.Input.CommandBinding> is created that associates the specified <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="0a2b7-116">첫째, 명령 소스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-116">First, the command source is created.</span></span>  <span data-ttu-id="0a2b7-117">A <xref:System.Windows.Controls.Button> 명령 원본으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-117">A <xref:System.Windows.Controls.Button> is used as the command source.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 <span data-ttu-id="0a2b7-118">다음으로 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-118">Next, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> are created.</span></span>  <span data-ttu-id="0a2b7-119"><xref:System.Windows.Input.ExecutedRoutedEventHandler> 열면는 <xref:System.Windows.MessageBox> 명령이 실행 되었음을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-119">The <xref:System.Windows.Input.ExecutedRoutedEventHandler> simply opens a <xref:System.Windows.MessageBox> to signify that the command executed.</span></span>  <span data-ttu-id="0a2b7-120"><xref:System.Windows.Input.CanExecuteRoutedEventHandler> 설정는 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-120">The <xref:System.Windows.Input.CanExecuteRoutedEventHandler> sets the <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> property to `true`.</span></span>  <span data-ttu-id="0a2b7-121">일반적으로 수 있는 실행 처리기를 현재 명령 대상에서 명령을 실행할 수 있습니다 하는 경우 보다 강력한 확인을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-121">Normally, the can execute handler would perform more robust checks to see if the command could execute on the current command target.</span></span>  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 <span data-ttu-id="0a2b7-122">마지막으로, 한 <xref:System.Windows.Input.CommandBinding> 루트에 만들어집니다 <xref:System.Windows.Window> 라우트된 이벤트 처리기를 연결 하는 응용 프로그램의는 <xref:System.Windows.Input.ApplicationCommands.Open%2A> 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="0a2b7-122">Finally, a <xref:System.Windows.Input.CommandBinding> is created on the root <xref:System.Windows.Window> of the application that associates the routed events handlers to the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a><span data-ttu-id="0a2b7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a2b7-123">See Also</span></span>  
 [<span data-ttu-id="0a2b7-124">명령 개요</span><span class="sxs-lookup"><span data-stu-id="0a2b7-124">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [<span data-ttu-id="0a2b7-125">명령을 지원하는 컨트롤에 명령 후크</span><span class="sxs-lookup"><span data-stu-id="0a2b7-125">Hook Up a Command to a Control with Command Support</span></span>](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
