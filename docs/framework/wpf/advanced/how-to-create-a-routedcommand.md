---
title: "방법: RoutedCommand 만들기"
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
helpviewer_keywords: RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 449b55d07aa0119ff23c8642ca83b0989f5b1d4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="03aeb-102">방법: RoutedCommand 만들기</span><span class="sxs-lookup"><span data-stu-id="03aeb-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="03aeb-103">이 예제에는 사용자 지정을 만드는 방법을 보여 줍니다 <xref:System.Windows.Input.RoutedCommand> 를 만들어서 사용자 지정 명령을 구현 하는 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 및 <xref:System.Windows.Input.CanExecuteRoutedEventHandler> 에 연결 하는 <xref:System.Windows.Input.CommandBinding>합니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="03aeb-104">명령에 대 한 자세한 내용은 참조는 [명령 실행 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-104">For more information on commanding, see the [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03aeb-105">예</span><span class="sxs-lookup"><span data-stu-id="03aeb-105">Example</span></span>  
 <span data-ttu-id="03aeb-106">만들 때 첫 번째 단계는 <xref:System.Windows.Input.RoutedCommand> 는 명령을 정의 하 고 인스턴스화하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="03aeb-107">명령에 대해 정의 하는 이벤트 처리기를 만들 해야 응용 프로그램에서 명령을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="03aeb-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="03aeb-108">다음으로 <xref:System.Windows.Input.CommandBinding> 명령을 이벤트 처리기와 연결 하 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="03aeb-109"><xref:System.Windows.Input.CommandBinding> 특정 개체에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="03aeb-110">이 개체의 범위를 정의 고 <xref:System.Windows.Input.CommandBinding> 요소 트리에 있는</span><span class="sxs-lookup"><span data-stu-id="03aeb-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="03aeb-111">마지막 단계에서는 명령을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-111">The final step is invoking the command.</span></span>  <span data-ttu-id="03aeb-112">와 연결 하는 명령을 호출 하는 한 가지 방법은 <xref:System.Windows.Input.ICommandSource>와 같은 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="03aeb-113">단추를 클릭할 때는 <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드를 사용자 지정 <xref:System.Windows.Input.RoutedCommand> 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="03aeb-114"><xref:System.Windows.Input.RoutedCommand> 발생는 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 및 <xref:System.Windows.Input.CommandManager.Executed> 라우트된 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="03aeb-115">이러한 이벤트에 대 한 찾는 요소 트리를 탐색 한 <xref:System.Windows.Input.CommandBinding> 이 특정 명령에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="03aeb-116">경우는 <xref:System.Windows.Input.CommandBinding> 발견 되는 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 연관 <xref:System.Windows.Input.CommandBinding> 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03aeb-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03aeb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03aeb-117">See Also</span></span>  
 <xref:System.Windows.Input.RoutedCommand>  
 [<span data-ttu-id="03aeb-118">명령 개요</span><span class="sxs-lookup"><span data-stu-id="03aeb-118">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)
