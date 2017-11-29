---
title: "방법: ICommandSource 구현"
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
helpviewer_keywords: ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdff5ebeb51daff4e8848e9a7c8282c2eee6f208
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="50cfd-102">방법: ICommandSource 구현</span><span class="sxs-lookup"><span data-stu-id="50cfd-102">How to: Implement ICommandSource</span></span>
<span data-ttu-id="50cfd-103">구현 하 여 명령 소스를 만드는 방법을 보여 주는이 예제 <xref:System.Windows.Input.ICommandSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span>  <span data-ttu-id="50cfd-104">명령 소스는 명령을 호출 하는 방법을 알고 있는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-104">A command source is an object that knows how to invoke a command.</span></span>  <span data-ttu-id="50cfd-105"><xref:System.Windows.Input.ICommandSource> 세 멤버를 노출 하는 인터페이스: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, 및 <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, and <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.</span></span>  <span data-ttu-id="50cfd-106"><xref:System.Windows.Input.ICommandSource.Command%2A>호출 되는 명령이입니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-106"><xref:System.Windows.Input.ICommandSource.Command%2A> is the command which will be invoked.</span></span> <span data-ttu-id="50cfd-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A> 명령 소스 명령을 처리 하는 메서드에 전달 되는 사용자 정의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-107">The <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> is a user-defined data type which is passed from the command source to the method which handles the command.</span></span> <span data-ttu-id="50cfd-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A> 명령이 실행 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-108">The <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> is the object that the command is being executed on.</span></span>  
  
 <span data-ttu-id="50cfd-109">이 예제에서는 클래스가 만들어질 서브클래싱하는 <xref:System.Windows.Controls.Slider> 컨트롤과 구현 <xref:System.Windows.Input.ICommandSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-109">In this example, a class is created which subclasses the <xref:System.Windows.Controls.Slider> control and implements <xref:System.Windows.Input.ICommandSource>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50cfd-110">예제</span><span class="sxs-lookup"><span data-stu-id="50cfd-110">Example</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="50cfd-111">다양 한 구현 하는 클래스를 제공 <xref:System.Windows.Input.ICommandSource>와 같은 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, 및 <xref:System.Windows.Controls.ListBoxItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-111"> provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Controls.ListBoxItem>.</span></span>  <span data-ttu-id="50cfd-112">명령 소스가 명령을 호출 하는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-112">A command source defines how it invokes a command.</span></span>   <span data-ttu-id="50cfd-113"><xref:System.Windows.Controls.Button>및 <xref:System.Windows.Controls.MenuItem> 명령을 클릭할 때 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-113"><xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.MenuItem> invoke a command when they are clicked.</span></span>  <span data-ttu-id="50cfd-114">A <xref:System.Windows.Controls.ListBoxItem> 명령을 두 번 클릭할 때 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-114">A <xref:System.Windows.Controls.ListBoxItem> invokes a command when it is double clicked.</span></span> <span data-ttu-id="50cfd-115">이러한 클래스에만 명령이 될 때 원본 자신의 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-115">These classes only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>  
  
 <span data-ttu-id="50cfd-116">슬라이더를 이동 하면 명령을 호출이 예제에 대 한 더 정확 하 게 때는 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-116">For this example we will invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>  
  
 <span data-ttu-id="50cfd-117">다음은 클래스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-117">The following is the class definition.</span></span>  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 <span data-ttu-id="50cfd-118">다음 단계를 구현 하는 것은 <xref:System.Windows.Input.ICommandSource> 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-118">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span>  <span data-ttu-id="50cfd-119">이 예제에서는 속성으로 구현 됩니다 <xref:System.Windows.DependencyProperty> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-119">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span>  <span data-ttu-id="50cfd-120">이렇게 하면 데이터 바인딩을 사용 하 여 속성.</span><span class="sxs-lookup"><span data-stu-id="50cfd-120">This enables the properties to use data binding.</span></span>  <span data-ttu-id="50cfd-121">에 대 한 자세한 내용은 <xref:System.Windows.DependencyProperty> 클래스를 참조 하십시오.는 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-121">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  <span data-ttu-id="50cfd-122">데이터 바인딩에 대 한 자세한 내용은 참조는 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-122">For more information about data binding, see the [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="50cfd-123">만 <xref:System.Windows.Input.ICommandSource.Command%2A> 속성은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-123">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 <span data-ttu-id="50cfd-124">다음은는 <xref:System.Windows.DependencyProperty> 콜백 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-124">The following is the <xref:System.Windows.DependencyProperty> change callback.</span></span>  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 <span data-ttu-id="50cfd-125">다음 단계를 추가 및 제거 명령 소스와 연결 되는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-125">The next step is to add and remove the command which is associated with the command source.</span></span>  <span data-ttu-id="50cfd-126"><xref:System.Windows.Input.ICommandSource.Command%2A> 속성 단순히 덮어쓸 수 없는 새 명령을 추가 되 면 이전 명령과 사용 하 여 이벤트 처리기 연결 되었기 때문에 하나만 있는 경우, 먼저 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-126">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 <span data-ttu-id="50cfd-127">마지막 단계에 대 한 논리를 만드는 것은 <xref:System.Windows.Input.ICommand.CanExecuteChanged> 처리기 및 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="50cfd-127">The last step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler and the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span>  
  
 <span data-ttu-id="50cfd-128"><xref:System.Windows.Input.ICommand.CanExecuteChanged> 이벤트의 현재 명령 대상에서 실행할 명령 기능이 변경 될 수 있습니다 명령 소스를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-128">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span>  <span data-ttu-id="50cfd-129">일반적으로 호출 명령 소스가이 이벤트를 받을 경우는 <xref:System.Windows.Input.ICommand.CanExecute%2A> 명령에는 메서드.</span><span class="sxs-lookup"><span data-stu-id="50cfd-129">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span>  <span data-ttu-id="50cfd-130">현재 명령 대상에서 명령을 실행할 수 없습니다, 명령 소스가 일반적으로 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-130">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span>  <span data-ttu-id="50cfd-131">현재 명령 대상에서 명령을 실행할 수, 하는 경우 명령 소스는 일반적으로 자체으로 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-131">If the command can execute on the current command target, the command source will typically enable itself.</span></span>  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 <span data-ttu-id="50cfd-132">마지막 단계는 <xref:System.Windows.Input.ICommand.Execute%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="50cfd-132">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span>  <span data-ttu-id="50cfd-133">명령이 있는 경우는 <xref:System.Windows.Input.RoutedCommand>, <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> 메서드 호출, 되지 않았으면는 <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="50cfd-133">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a><span data-ttu-id="50cfd-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50cfd-134">See Also</span></span>  
 <xref:System.Windows.Input.ICommandSource>  
 <xref:System.Windows.Input.ICommand>  
 <xref:System.Windows.Input.RoutedCommand>  
 [<span data-ttu-id="50cfd-135">명령 개요</span><span class="sxs-lookup"><span data-stu-id="50cfd-135">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)
