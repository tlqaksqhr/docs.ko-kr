---
title: "Menu 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ab5092b1bc9db22390a18b2c1cb1ad5725a2037
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="menu-overview"></a><span data-ttu-id="601ef-102">Menu 개요</span><span class="sxs-lookup"><span data-stu-id="601ef-102">Menu Overview</span></span>
<span data-ttu-id="601ef-103"><xref:System.Windows.Controls.Menu> 클래스를 사용 하면 명령 및 이벤트 처리기를 계층적 순서로 관련 된 요소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-103">The <xref:System.Windows.Controls.Menu> class enables you to organize elements associated with commands and event handlers in a hierarchical order.</span></span> <span data-ttu-id="601ef-104">각 <xref:System.Windows.Controls.Menu> 의 컬렉션을 포함 하는 요소 <xref:System.Windows.Controls.MenuItem> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-104">Each <xref:System.Windows.Controls.Menu> element contains a collection of <xref:System.Windows.Controls.MenuItem> elements.</span></span>  
  
  
<a name="menu_control"></a>   
## <a name="menu-control"></a><span data-ttu-id="601ef-105">Menu 컨트롤</span><span class="sxs-lookup"><span data-stu-id="601ef-105">Menu Control</span></span>  
 <span data-ttu-id="601ef-106"><xref:System.Windows.Controls.Menu> 컨트롤에 명령 또는 응용 프로그램에 대 한 옵션을 지정 하는 항목의 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-106">The <xref:System.Windows.Controls.Menu> control presents a list of items that specify commands or options for an application.</span></span> <span data-ttu-id="601ef-107">클릭 하면 일반적으로 <xref:System.Windows.Controls.MenuItem> 명령을 실행 하도록 응용 프로그램 또는 하위 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-107">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a><span data-ttu-id="601ef-108">메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="601ef-108">Creating Menus</span></span>  
 <span data-ttu-id="601ef-109">다음 예제에서는 한 <xref:System.Windows.Controls.Menu> 텍스트를 조작 하는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-109">The following example creates a <xref:System.Windows.Controls.Menu> to manipulate text in a <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="601ef-110"><xref:System.Windows.Controls.Menu> 포함 <xref:System.Windows.Controls.MenuItem> 사용 하는 개체는 <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, 및 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성 및 <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, 및 <xref:System.Windows.Controls.MenuItem.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-110">The <xref:System.Windows.Controls.Menu> contains <xref:System.Windows.Controls.MenuItem> objects that use the <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, and <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> properties and the <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, and <xref:System.Windows.Controls.MenuItem.Click> events.</span></span>  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a><span data-ttu-id="601ef-111">바로 가기 키가 있는 MenuItem</span><span class="sxs-lookup"><span data-stu-id="601ef-111">MenuItems with Keyboard Shortcuts</span></span>  
 <span data-ttu-id="601ef-112">바로 가기 키를 호출 하는 키보드로 입력할 수 있는 문자 조합을 <xref:System.Windows.Controls.Menu> 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-112">Keyboard shortcuts are character combinations that can be entered with the keyboard to invoke <xref:System.Windows.Controls.Menu> commands.</span></span> <span data-ttu-id="601ef-113">예를 들어 **복사**의 바로 가기는 Ctrl+C입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-113">For example, the shortcut for **Copy** is CTRL+C.</span></span> <span data-ttu-id="601ef-114">두 가지 속성 메뉴 항목 및 바로 가기 키와 함께 사용할-<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 또는 <xref:System.Windows.Controls.MenuItem.Command%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-114">There are two properties to use with keyboard shortcuts and menu items —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> or <xref:System.Windows.Controls.MenuItem.Command%2A>.</span></span>  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a><span data-ttu-id="601ef-115">InputGestureText</span><span class="sxs-lookup"><span data-stu-id="601ef-115">InputGestureText</span></span>  
 <span data-ttu-id="601ef-116">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> 키보드 바로 가기 텍스트를 할당 하는 속성 <xref:System.Windows.Controls.MenuItem> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-116">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> property to assign keyboard shortcut text to <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="601ef-117">이렇게 해야만 메뉴 항목에 바로 가기 키가 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-117">This only places the keyboard shortcut in the menu item.</span></span>  <span data-ttu-id="601ef-118">사용 하 여 명령을 연결 하지는 않습니다는 <xref:System.Windows.Controls.MenuItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-118">It does not associate the command with the <xref:System.Windows.Controls.MenuItem>.</span></span> <span data-ttu-id="601ef-119">응용 프로그램은 사용자 입력을 처리하여 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-119">The application must handle the user's input to carry out the action.</span></span>  
  
 [!code-xaml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a><span data-ttu-id="601ef-120">명령</span><span class="sxs-lookup"><span data-stu-id="601ef-120">Command</span></span>  
 <span data-ttu-id="601ef-121">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.MenuItem.Command%2A> 연결할 속성은 **열려** 및 **저장** 로 명령을 <xref:System.Windows.Controls.MenuItem> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-121">The following example shows how to use the <xref:System.Windows.Controls.MenuItem.Command%2A> property to associate the **Open** and **Save** commands with <xref:System.Windows.Controls.MenuItem> controls.</span></span> <span data-ttu-id="601ef-122">Command 속성에서 사용 하는 명령은 연결 뿐만 아니라는 <xref:System.Windows.Controls.MenuItem>, 바로 가기도 사용할 입력된 제스처 텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-122">Not only does the command property associate a command with a <xref:System.Windows.Controls.MenuItem>, but it also supplies the input gesture text to use as a shortcut.</span></span>  
  
 [!code-xaml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <span data-ttu-id="601ef-123"><xref:System.Windows.Controls.MenuItem> 클래스에는 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 은 명령이 발생 하는 요소를 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-123">The <xref:System.Windows.Controls.MenuItem> class also has a <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> property, which specifies the element where the command occurs.</span></span> <span data-ttu-id="601ef-124">경우 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 키보드 포커스가 있는 요소는 명령을 받은 설정 하지 않으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-124">If <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> is not set, the element that has keyboard focus receives the command.</span></span> <span data-ttu-id="601ef-125">명령에 대한 자세한 내용은 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="601ef-125">For more information about commands, see [Commanding Overview](../../../../docs/framework/wpf/advanced/commanding-overview.md).</span></span>  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a><span data-ttu-id="601ef-126">메뉴 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="601ef-126">Menu Styling</span></span>  
 <span data-ttu-id="601ef-127">컨트롤 스타일 지정을 변경할 수 있습니다 획기적으로 모양 및 동작의 <xref:System.Windows.Controls.Menu> 사용자 지정 컨트롤을 작성 하지 않고도 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-127">With control styling, you can dramatically change the appearance and behavior of <xref:System.Windows.Controls.Menu> controls without having to write a custom control.</span></span> <span data-ttu-id="601ef-128">시각적 속성을 설정 하는 것 외에도 적용할 수 있습니다는 <xref:System.Windows.Style> 을 컨트롤의 개별 부분에 속성을 통해 해당 컨트롤의 부분 동작을 변경 또는 추가 부분을 추가 하거나 컨트롤의 레이아웃을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-128">In addition to setting visual properties, you can also apply a <xref:System.Windows.Style> to individual parts of a control, change the behavior of parts of the control through properties, or add additional parts or change the layout of a control.</span></span> <span data-ttu-id="601ef-129">다음 예에서는 여러 가지 방법으로 추가할 수를 보여 줍니다.는 <xref:System.Windows.Style> 에 <xref:System.Windows.Controls.Menu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-129">The following examples demonstrate several ways to add a <xref:System.Windows.Style> to a <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 <span data-ttu-id="601ef-130">첫 번째 코드 예제에서는 정의 <xref:System.Windows.Style> 호출 `Simple` 스타일에는 현재 시스템 설정을 사용 하는 방법을 보여 주는 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-130">The first code example defines a <xref:System.Windows.Style> called `Simple` that shows how to use the current system settings in your style.</span></span> <span data-ttu-id="601ef-131">코드에서는 `MenuHighlightBrush`의 색을 메뉴의 배경색으로 할당하고 `MenuTextBrush`를 메뉴의 전경색으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-131">The code assigns the color of the `MenuHighlightBrush` as the menu's background color and the `MenuTextBrush` as the menu's foreground color.</span></span> <span data-ttu-id="601ef-132">리소스 키를 사용하여 브러시를 할당하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-132">Notice that you use resource keys to assign the brushes.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 <span data-ttu-id="601ef-133">다음 샘플에서는 <xref:System.Windows.Trigger> 의 모양을 변경할 수 있도록 하는 요소는 <xref:System.Windows.Controls.MenuItem> 에서 발생 하는 이벤트에 대 한 응답에는 <xref:System.Windows.Controls.Menu>합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-133">The following sample uses <xref:System.Windows.Trigger> elements that enable you to change the appearance of a <xref:System.Windows.Controls.MenuItem> in response to events that occur on the <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="601ef-134">위로 마우스를 이동 하면는 <xref:System.Windows.Controls.Menu>, 전경색 및 메뉴 항목의 글꼴 특성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="601ef-134">When you move the mouse over the <xref:System.Windows.Controls.Menu>, the foreground color and the font characteristics of the menu items change.</span></span>  
  
 [!code-xaml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="601ef-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="601ef-135">See Also</span></span>  
 <span data-ttu-id="601ef-136">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)(WPF 컨트롤 갤러리 샘플)</span><span class="sxs-lookup"><span data-stu-id="601ef-136">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)</span></span>
