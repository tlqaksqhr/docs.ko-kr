---
title: 소유자가 그린 기본 제공 컨트롤 지원
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: a5cbdc733a2f1cda3e708ceaae8604297f8da58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529249"
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="ead65-102">소유자가 그린 기본 제공 컨트롤 지원</span><span class="sxs-lookup"><span data-stu-id="ead65-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="ead65-103">사용자 지정 그리기라고도 하는 Windows Forms의 소유자 그리기는 특정 컨트롤을 시각적 모양으로 변경하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ead65-104">이 항목의 "제어"에서 파생 되는 클래스를 의미 하는 데 사용은 <xref:System.Windows.Forms.Control> 또는 <xref:System.ComponentModel.Component>합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="ead65-105">일반적으로 Windows 그리기 자동으로 사용 하 여 처리와 같은 속성 설정 <xref:System.Windows.Forms.Control.BackColor%2A> 컨트롤의 모양을 결정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="ead65-106">소유자 그리기를 통해 속성을 사용하여 사용할 수 없는 모양의 요소를 변경하며 그리기 프로세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="ead65-107">예를 들어 많은 컨트롤을 사용하여 표시되는 텍스트의 색을 설정할 수 있지만 단색으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="ead65-108">소유자 그리기를 사용하면 검정과 빨강 부분에 있는 텍스트의 일부를 표시하는 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="ead65-109">실제로 소유자 그리기는 양식에 그래픽을 그리는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="ead65-110">폼의에 대 한 처리기에서 그래픽 메서드를 사용할 수는 예를 들어 <xref:System.Windows.Forms.Control.Paint> 에뮬레이션 하는 이벤트는 `ListBox` 컨트롤 있지만 모든 사용자 상호 작용을 처리 하는 사용자 고유의 코드를 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="ead65-111">소유자 그리기를 통해 컨트롤은 사용자 코드를 사용하여 해당 콘텐츠를 그리지만 그렇지 않은 경우 해당 내장 기능을 모두 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="ead65-112">각 항목의 다른 측면에 대한 기본 모양을 사용하는 동안 각 항목의 일부 측면을 사용자 지정하거나 컨트롤의 각 항목을 그릴 수 있는 그래픽 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="ead65-113">Windows Forms 컨트롤의 소유자 그리기</span><span class="sxs-lookup"><span data-stu-id="ead65-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="ead65-114">소유자 그리기를 지원하는 컨트롤에서 소유자 그리기를 수행하려면 일반적으로 하나의 속성을 설정하고 하나 이상의 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="ead65-115">소유자 그리기를 지원하는 대부분의 컨트롤에는 컨트롤 자체가 그려질 때 해당 그리기 관련 이벤트가 발생할 지 여부를 나타내는 `OwnerDraw` 또는 `DrawMode` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="ead65-116">`OwnerDraw` 또는 `DrawMode` 속성이 없는 컨트롤에는 자동으로 발생하는 그리기 이벤트를 제공하는 `DataGridView` 컨트롤이 포함되고 자체 그리기 관련 이벤트가 있는 외부 렌더링 클래스를 사용하여 그려지는 `ToolStrip` 컨트롤이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="ead65-117">다양한 종류의 그리기 이벤트가 있지만 컨트롤 내에서 단일 항목을 그릴 수 있도록 일반적인 그리기 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="ead65-118">이벤트 처리기는 그려지고 있는 항목 및 그리는 데 사용할 수 있는 도구에 대한 정보를 포함하는 `EventArgs` 개체를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="ead65-119">예를 들어,이 개체는 부모 컬렉션에서 항목의 인덱스 번호를 일반적으로 포함 한 <xref:System.Drawing.Rectangle> 나타내는 항목의 경계를 표시 및 <xref:System.Drawing.Graphics> 그리기 메서드를 호출 하기 위한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="ead65-120">일부 이벤트에서 `EventArgs` 개체는 기본적으로 배경이나 포커스 영역과 같은 항목의 일부 측면을 그리도록 호출할 수 있는 메서드와 항목에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="ead65-121">소유자가 그린 사용자 지정 항목을 포함하는 재사용 가능한 컨트롤을 만들려면, 소유자 그리기를 지원하는 컨트롤 클래스에서 파생되는 새 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="ead65-122">그리기 이벤트를 처리하는 대신 적절한 `On`*EventName* 메서드 또는 새 클래스의 메소드에 대한 재정의에 소유자 그리기 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="ead65-123">이 경우 컨트롤 사용자가 소유자 그리기 이벤트를 처리하고 추가 사용자 지정을 제공할 수 있도록 기본 클래스 `On`*EventName* 메서드를 호출하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="ead65-124">다음 Windows Forms 컨트롤은 모든 버전의 .NET Framework에서 소유자 그리기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <span data-ttu-id="ead65-125"><xref:System.Windows.Forms.MenuItem> (사용 하 여 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="ead65-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="ead65-126">다음 컨트롤은 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서만 소유자 그리기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-126">The following controls support owner drawing only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="ead65-127">다음 컨트롤은 소유자 그리기를 지원하며 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서는 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-127">The following controls support owner drawing and are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="ead65-128">다음 섹션에서는 이 컨트롤에 대한 각각의 추가 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="ead65-129">ListBox 및 ComboBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ead65-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="ead65-130"><xref:System.Windows.Forms.ListBox> 및 <xref:System.Windows.Forms.ComboBox> 컨트롤을 모두 하나의 크기, 또는 다양 한 크기에서 컨트롤의 개별 항목을 그리는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ead65-131">하지만 <xref:System.Windows.Forms.CheckedListBox> 컨트롤에서 파생 되는 <xref:System.Windows.Forms.ListBox> 컨트롤을 지원 하지 않습니다 소유자 그리기 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="ead65-132">그리려면 각 항목을 같은 크기로 설정 합니다는 `DrawMode` 속성을 <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> 처리는 `DrawItem` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="ead65-133">다른 크기를 사용 하 여 각 항목을 그리려면 설정는 `DrawMode` 속성을 <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> 모두 처리는 `MeasureItem` 및 `DrawItem` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="ead65-134">`MeasureItem` 이벤트를 사용하여 `DrawItem` 이벤트가 해당 항목에 대해 발생하기 전에 항목의 크기를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="ead65-135">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-135">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [<span data-ttu-id="ead65-136">방법: ComboBox 컨트롤에서 가변 크기 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="ead65-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="ead65-137">MenuItem 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ead65-137">MenuItem Component</span></span>  
 <span data-ttu-id="ead65-138"><xref:System.Windows.Forms.MenuItem> 구성 요소에서 단일 메뉴 항목을 나타내는 한 <xref:System.Windows.Forms.MainMenu> 또는 <xref:System.Windows.Forms.ContextMenu> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="ead65-139">그릴는 <xref:System.Windows.Forms.MenuItem>설정, 해당 `OwnerDraw` 속성을 `true` 처리 및 해당 `DrawItem` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="ead65-140">`DrawItem` 이벤트가 발생하기 전에 메뉴 항목의 크기를 사용자 지정하려면, 항목의 `MeasureItem` 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="ead65-141">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-141">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="ead65-142">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ead65-142">TabControl Control</span></span>  
 <span data-ttu-id="ead65-143"><xref:System.Windows.Forms.TabControl> 컨트롤을 사용 하면 개별 탭 컨트롤에 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="ead65-144">소유자 그리기 탭을;만 영향을 줍니다. <xref:System.Windows.Forms.TabPage> 내용이 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="ead65-145">각 탭에 그릴는 <xref:System.Windows.Forms.TabControl>설정는 `DrawMode` 속성을 <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> 처리는 `DrawItem` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="ead65-146">이 이벤트는 탭이 컨트롤에 표시되는 경우에만 각 탭에 대해 한 번 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="ead65-147">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-147">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="ead65-148">ToolTip 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ead65-148">ToolTip Component</span></span>  
 <span data-ttu-id="ead65-149"><xref:System.Windows.Forms.ToolTip> 구성 요소를 사용 하면 표시 되는 도구 설명 전체를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="ead65-150">그릴는 <xref:System.Windows.Forms.ToolTip>설정, 해당 `OwnerDraw` 속성을 `true` 처리 및 해당 `Draw` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="ead65-151">크기를 사용자 지정 하는 <xref:System.Windows.Forms.ToolTip> 하기 전에 `Draw` 처리 이벤트가 발생 하면는 `Popup` 이벤트 집합과 <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> 이벤트 처리기에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="ead65-152">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-152">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="ead65-153">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ead65-153">ListView Control</span></span>  
 <span data-ttu-id="ead65-154"><xref:System.Windows.Forms.ListView> 컨트롤을 사용 하면 컨트롤의 개별 항목, 하위 항목 및 열 머리글을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="ead65-155">소유자 그리기를 컨트롤에서 사용하려면 `OwnerDraw` 속성을 `true`(으)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="ead65-156">컨트롤의 각 항목을 그리려면 `DrawItem` 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="ead65-157">컨트롤의 각 하위 항목 또는 열 머리글을 그릴 때는 <xref:System.Windows.Forms.ListView.View%2A> 속성이 <xref:System.Windows.Forms.View.Details>, 처리는 `DrawSubItem` 및 `DrawColumnHeader` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="ead65-158">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-158">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="ead65-159">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ead65-159">TreeView Control</span></span>  
 <span data-ttu-id="ead65-160"><xref:System.Windows.Forms.TreeView> 컨트롤을 사용 하면 컨트롤의 개별 노드를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="ead65-161">각 노드에 표시 되는 텍스트에만 그리려면 설정는 `DrawMode` 속성을 <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> 하 고 처리는 `DrawNode` 이벤트 텍스트를 그릴 합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="ead65-162">각 노드의 모든 요소를 그리려면 설정는 `DrawMode` 속성을 <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> 처리는 `DrawNode` 텍스트, 아이콘, 확인란, 더하기 및 빼기 기호 같이 및 노드를 연결 하는 선 필요한 모든 요소를 그리는 데 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="ead65-163">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-163">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="ead65-164">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ead65-164">DataGridView Control</span></span>  
 <span data-ttu-id="ead65-165"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하면 컨트롤의 개별 셀 및 행을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="ead65-166">개별 셀을 그리려면 `CellPainting` 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="ead65-167">개별 행이나 행의 요소를 그리려면 `RowPrePaint` 및 `RowPostPaint` 이벤트 중 하나 또는 모두를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="ead65-168">`RowPrePaint` 이벤트는 행의 셀이 그려지기 전에 발생하며 `RowPostPaint` 이벤트는 셀이 그려진 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="ead65-169">두 이벤트 및 `CellPainting` 이벤트 모두를 처리하여 별도로 행 배경, 개별 셀 및 행 전경을 그리거나, 필요한 곳에 특정 사용자 지정을 제공하고 행의 다른 요소에 대한 기본 표시를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="ead65-170">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-170">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [<span data-ttu-id="ead65-171">방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ead65-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [<span data-ttu-id="ead65-172">방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ead65-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="ead65-173">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ead65-173">ToolStrip Control</span></span>  
 <span data-ttu-id="ead65-174"><xref:System.Windows.Forms.ToolStrip> 및 파생 된 컨트롤을 사용 하면 표시 되는 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="ead65-175">에 대 한 사용자 지정 렌더링을 제공 하기 <xref:System.Windows.Forms.ToolStrip> 컨트롤 설정는 `Renderer` 속성은 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, 또는 <xref:System.Windows.Forms.ToolStripContentPanel> 에 `ToolStripRenderer` 개체를 하나 이상에서 제공 하는 여러 그리기 이벤트 처리는 `ToolStripRenderer` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ead65-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="ead65-176">또는 설정는 `Renderer` 사용자 지정 클래스의 인스턴스에 대 한 속성에서 파생 된 `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, 또는 <xref:System.Windows.Forms.ToolStripSystemRenderer> 구현 하거나 특정 재정의 `On` *EventName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="ead65-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="ead65-177">코드 예제를 포함한 자세한 내용은 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ead65-177">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [<span data-ttu-id="ead65-178">방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러를 설정하고 만들기</span><span class="sxs-lookup"><span data-stu-id="ead65-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [<span data-ttu-id="ead65-179">방법: ToolStrip 컨트롤 그리기 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ead65-179">How to: Custom Draw a ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="ead65-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ead65-180">See Also</span></span>  
 [<span data-ttu-id="ead65-181">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ead65-181">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
