---
title: "방법: 명령 사용"
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
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b27f8544a44a252eb1a1afd6e096f303360c14e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-a-command"></a><span data-ttu-id="2eaa2-102">방법: 명령 사용</span><span class="sxs-lookup"><span data-stu-id="2eaa2-102">How to: Enable a Command</span></span>
<span data-ttu-id="2eaa2-103">다음 예제에서 명령을 사용 하는 방법을 보여 줍니다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-103">The following example demonstrates how to use commanding in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  <span data-ttu-id="2eaa2-104">이 예제에서는 연결 하는 방법을 보여 줍니다는 <xref:System.Windows.Input.RoutedCommand> 에 <xref:System.Windows.Controls.Button>, 만들는 <xref:System.Windows.Input.CommandBinding>, 구현 하는 이벤트 처리기를 만들는 <xref:System.Windows.Input.RoutedCommand>합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-104">The example shows how to associate a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Button>, create a <xref:System.Windows.Input.CommandBinding>, and create the event handlers which implement the <xref:System.Windows.Input.RoutedCommand>.</span></span>  <span data-ttu-id="2eaa2-105">명령에 대 한 자세한 내용은 참조는 [명령 실행 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-105">For more information on commanding, see the [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2eaa2-106">예</span><span class="sxs-lookup"><span data-stu-id="2eaa2-106">Example</span></span>  
 <span data-ttu-id="2eaa2-107">코드의 첫 번째 섹션을 만듭니다는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)],으로 구성 되는 <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.StackPanel>, 만듭니다는 <xref:System.Windows.Input.CommandBinding> 명령 처리기와 연결 하는 <xref:System.Windows.Input.RoutedCommand>합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-107">The first section of code creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], which consists of a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.StackPanel>, and creates a <xref:System.Windows.Input.CommandBinding> that associates the command handlers with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="2eaa2-108"><xref:System.Windows.Input.ICommandSource.Command%2A> 의 속성은 <xref:System.Windows.Controls.Button> 연결 된는 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-108">The <xref:System.Windows.Input.ICommandSource.Command%2A> property of the <xref:System.Windows.Controls.Button> is associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="2eaa2-109"><xref:System.Windows.Input.CommandBinding> 에 추가 되 고 <xref:System.Windows.Input.CommandBindingCollection> 루트의 <xref:System.Windows.Window>합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-109">The <xref:System.Windows.Input.CommandBinding> is added to the <xref:System.Windows.Input.CommandBindingCollection> of the root <xref:System.Windows.Window>.</span></span> <span data-ttu-id="2eaa2-110"><xref:System.Windows.Input.CommandBinding.Executed> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트 처리기는이 바인딩에 연결 및 연결 된는 <xref:System.Windows.Input.ApplicationCommands.Close%2A> 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-110">The <xref:System.Windows.Input.CommandBinding.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers are attached to this binding and associated with the <xref:System.Windows.Input.ApplicationCommands.Close%2A> command.</span></span>  
  
 <span data-ttu-id="2eaa2-111">없이 <xref:System.Windows.Input.CommandBinding> 명령 논리가만 명령을 호출 하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-111">Without the <xref:System.Windows.Input.CommandBinding> there is no command logic, only a mechanism to invoke the command.</span></span>  <span data-ttu-id="2eaa2-112">경우는 <xref:System.Windows.Controls.Button> 를 클릭 하면는 <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> 이어서 명령 대상에서 발생 합니다.는 <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-112">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> is raised on the command target followed by the <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.</span></span>  <span data-ttu-id="2eaa2-113">이러한 이벤트에 대 한 찾는 요소 트리를 탐색 한 <xref:System.Windows.Input.CommandBinding> 는 해당 명령에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-113">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for that particular command.</span></span>  <span data-ttu-id="2eaa2-114">때문에 주목할 <xref:System.Windows.RoutedEvent> 터널을 요소 트리를 통해 거품형 주의 해야 where에서는 <xref:System.Windows.Input.CommandBinding> 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-114">It is worth noting that because <xref:System.Windows.RoutedEvent> tunnel and bubble through the element tree, care must be taken in where the <xref:System.Windows.Input.CommandBinding> is put.</span></span>   <span data-ttu-id="2eaa2-115">경우는 <xref:System.Windows.Input.CommandBinding> 명령 대상 또는의 경로에 있지 않은 다른 노드로의 형제 자격에는 <xref:System.Windows.RoutedEvent>, <xref:System.Windows.Input.CommandBinding> 에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-115">If the <xref:System.Windows.Input.CommandBinding> is on a sibling of the command target or another node that is not on the route of the <xref:System.Windows.RoutedEvent>, the <xref:System.Windows.Input.CommandBinding> will not be accessed.</span></span>  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 <span data-ttu-id="2eaa2-116">구현 코드의 다음 섹션의 <xref:System.Windows.Input.CommandManager.Executed> 및 <xref:System.Windows.Input.CommandBinding.CanExecute> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-116">The next section of code implements the <xref:System.Windows.Input.CommandManager.Executed> and <xref:System.Windows.Input.CommandBinding.CanExecute> event handlers.</span></span>  
  
 <span data-ttu-id="2eaa2-117"><xref:System.Windows.Input.CommandManager.Executed> 열려 파일을 닫는 메서드를 호출 하는 처리기.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-117">The <xref:System.Windows.Input.CommandManager.Executed> handler calls a method to close the open file.</span></span>  <span data-ttu-id="2eaa2-118"><xref:System.Windows.Input.CommandBinding.CanExecute> 파일이 열려 있는지 여부를 결정 하는 메서드를 호출 하는 처리기.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-118">The <xref:System.Windows.Input.CommandBinding.CanExecute> handler calls a method to determine whether a file is open.</span></span>  <span data-ttu-id="2eaa2-119">파일이 열려 있으면 <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> 로 설정 된 `true`, 그렇지 않으면로 설정 된 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa2-119">If a file is open, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> is set to `true`; otherwise, it is set to `false`.</span></span>  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a><span data-ttu-id="2eaa2-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2eaa2-120">See Also</span></span>  
 [<span data-ttu-id="2eaa2-121">명령 개요</span><span class="sxs-lookup"><span data-stu-id="2eaa2-121">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)
