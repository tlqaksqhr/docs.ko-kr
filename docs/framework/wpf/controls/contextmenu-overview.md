---
title: "ContextMenu 개요"
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
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f3061b7fed225f00bf6bb91efe529de35a5a036a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="contextmenu-overview"></a><span data-ttu-id="9fa0d-102">ContextMenu 개요</span><span class="sxs-lookup"><span data-stu-id="9fa0d-102">ContextMenu Overview</span></span>
<span data-ttu-id="9fa0d-103"><xref:System.Windows.Controls.ContextMenu> 클래스 관련 컨텍스트를 사용 하 여 기능을 노출 하는 요소를 나타냅니다. <xref:System.Windows.Controls.Menu>합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="9fa0d-104">일반적으로 사용자 표시의 <xref:System.Windows.Controls.ContextMenu> 에 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 마우스 단추를 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="9fa0d-105">이 항목에서는 소개는 <xref:System.Windows.Controls.ContextMenu> 요소에서 사용 하는 방법의 예제를 제공 하 고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  
  
  
  
<a name="contextmenu_control"></a>   
## <a name="contextmenu-control"></a><span data-ttu-id="9fa0d-106">ContextMenu 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9fa0d-106">ContextMenu Control</span></span>  
 <span data-ttu-id="9fa0d-107">A <xref:System.Windows.Controls.ContextMenu> 특정 컨트롤에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="9fa0d-108"><xref:System.Windows.Controls.ContextMenu> 요소를 사용 하면 명령이 나 예를 들어 특정 컨트롤과 관련 된 옵션을 지정 하는 항목의 목록으로 표시 하는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="9fa0d-109">사용자가 컨트롤을 마우스 오른쪽 단추로 클릭하면 메뉴가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="9fa0d-110">클릭 하면 일반적으로 <xref:System.Windows.Controls.MenuItem> 명령을 실행 하도록 응용 프로그램 또는 하위 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>   
## <a name="creating-contextmenus"></a><span data-ttu-id="9fa0d-111">ContextMenu 만들기</span><span class="sxs-lookup"><span data-stu-id="9fa0d-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="9fa0d-112">다음 예제를 만드는 방법을 보여는 <xref:System.Windows.Controls.ContextMenu> 하위 메뉴가 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="9fa0d-113"><xref:System.Windows.Controls.ContextMenu> 컨트롤 단추 컨트롤에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>   
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="9fa0d-114">ContextMenu에 스타일 적용</span><span class="sxs-lookup"><span data-stu-id="9fa0d-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="9fa0d-115">컨트롤을 사용 하 여 <xref:System.Windows.Style>, 모양 및 동작을 크게 변경할 수 있습니다는 <xref:System.Windows.Controls.ContextMenu> 사용자 지정 컨트롤을 작성 하지 않고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="9fa0d-116">시각적 속성을 설정하는 것 외에 컨트롤의 파트에 스타일을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="9fa0d-117">예를 들어 속성을 사용 하 여 컨트롤의 부분 동작을 변경할 수 있습니다 또는 일부를 추가 하거나 레이아웃을 변경할 수 있습니다는 <xref:System.Windows.Controls.ContextMenu>합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="9fa0d-118">다음 예에서는 표시 스타일을 추가 하는 여러 방법을 <xref:System.Windows.Controls.ContextMenu> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="9fa0d-119">첫 번째 예제는 스타일에서 현재 시스템 설정을 사용하는 방법을 보여 주는 `SimpleSysResources`라는 스타일을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="9fa0d-120">이 예에서는 할당 <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> 로 <xref:System.Windows.Controls.Control.Background%2A> 색 및 <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> 로 <xref:System.Windows.Controls.Control.Foreground%2A> 의 색은 <xref:System.Windows.Controls.ContextMenu>합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=   
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=   
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="9fa0d-121">다음 예제에서는 <xref:System.Windows.Trigger> 의 모양을 변경 하는 요소는 <xref:System.Windows.Controls.Menu> 에서 발생 하는 이벤트에 대 한 응답에는 <xref:System.Windows.Controls.ContextMenu>합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="9fa0d-122">사용자의 모양 메뉴 위로 마우스를 이동 하는 경우는 <xref:System.Windows.Controls.ContextMenu> 항목을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa0d-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fa0d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fa0d-123">See Also</span></span>  
 <xref:System.Windows.Controls.ContextMenu>  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.Menu>  
 <xref:System.Windows.Controls.MenuItem>  
 [<span data-ttu-id="9fa0d-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="9fa0d-124">ContextMenu</span></span>](../../../../docs/framework/wpf/controls/contextmenu.md)  
 [<span data-ttu-id="9fa0d-125">ContextMenu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="9fa0d-125">ContextMenu Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md)  
 <span data-ttu-id="9fa0d-126">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)(WPF 컨트롤 갤러리 샘플)</span><span class="sxs-lookup"><span data-stu-id="9fa0d-126">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)</span></span>
