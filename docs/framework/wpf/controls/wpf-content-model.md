---
title: WPF 콘텐츠 모델
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: 48e96b04a3459aa18a52624758d5fa2347570fcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558202"
---
# <a name="wpf-content-model"></a><span data-ttu-id="f9b60-102">WPF 콘텐츠 모델</span><span class="sxs-lookup"><span data-stu-id="f9b60-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="f9b60-103">는 다양한 형식의 콘텐츠를 표시하는 것을 기본 용도로 하는 많은 컨트롤 형식 및 컨트롤과 유사한 형식을 제공하는 프레젠테이션 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-103"> is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="f9b60-104">사용할 컨트롤이나 파생시킬 컨트롤을 결정하려면 특정 컨트롤이 가장 잘 표시할 수 있는 개체 유형을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="f9b60-105">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 형식 및 컨트롤과 비슷한 형식에 대한 콘텐츠 모델을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="f9b60-106">콘텐츠 모델은 컨트롤에 사용될 수 있는 컨트롤에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="f9b60-107">또한 이 항목에서는 각 컨트롤 모델에 대한 콘텐츠 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="f9b60-108">콘텐츠 속성은 개체의 콘텐츠를 저장하는 데 사용되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="f9b60-109">임의의 콘텐츠가 들어 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="f9b60-110">일부 컨트롤 문자열과 같은 모든 형식의 개체를 포함할 수 있습니다는 <xref:System.DateTime> 개체 또는 <xref:System.Windows.UIElement> 추가 항목에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="f9b60-111">예를 들어 한 <xref:System.Windows.Controls.Button> 이미지 및 일부 텍스트, 포함할 수 있습니다 또는 <xref:System.Windows.Controls.CheckBox> 의 값을 포함할 수도 <xref:System.DateTime.Now%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="f9b60-112">에는 임의의 콘텐츠가 들어 있는 네 개의 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-112"> has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="f9b60-113">다음 표에서에서 상속 되는 클래스를 보여 줍니다. <xref:System.Windows.Controls.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="f9b60-114">임의의 콘텐츠가 들어 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="f9b60-115">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f9b60-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="f9b60-116">임의의 단일 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="f9b60-117">헤더 및 단일 항목이며 둘 모두 임의의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="f9b60-118">임의 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="f9b60-119">헤더와 항목 컬렉션이며 모두 임의의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="f9b60-120">이러한 클래스에서 상속하는 컨트롤은 동일한 형식의 콘텐츠를 포함하며 콘텐츠를 동일한 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="f9b60-121">다음 그림에서는 이미지와 일부 텍스트를 포함하는 각 콘텐츠 모델의 컨트롤을 하나씩 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="f9b60-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="f9b60-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="f9b60-123">임의의 단일 개체가 들어 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f9b60-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="f9b60-124"><xref:System.Windows.Controls.ContentControl> 클래스 임의의 콘텐츠가의 한 부분을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="f9b60-125">해당 콘텐츠 속성은 <xref:System.Windows.Controls.ContentControl.Content%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="f9b60-126">다음 컨트롤에서 상속 <xref:System.Windows.Controls.ContentControl> 및 해당 콘텐츠 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 <span data-ttu-id="f9b60-127">단추를 다음 그림에서는 4 개의 <xref:System.Windows.Controls.ContentControl.Content%2A> 는 문자열로 설정 됩니다는 <xref:System.DateTime> 개체는 <xref:System.Windows.Shapes.Rectangle>, 및 <xref:System.Windows.Controls.Panel> 를 포함 하는 <xref:System.Windows.Shapes.Ellipse> 및 <xref:System.Windows.Controls.TextBlock>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="f9b60-128">![단추가 네 개](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="f9b60-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="f9b60-129">다양한 형식의 내용을 가진 네 개의 단추</span><span class="sxs-lookup"><span data-stu-id="f9b60-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="f9b60-130">설정 하는 방법의 예는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성 참조 <xref:System.Windows.Controls.ContentControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="f9b60-131">헤더와 임의의 단일 개체가 들어 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f9b60-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="f9b60-132"><xref:System.Windows.Controls.HeaderedContentControl> 클래스에서 상속 <xref:System.Windows.Controls.ContentControl> 헤더와 콘텐츠를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="f9b60-133">콘텐츠 속성을 상속 <xref:System.Windows.Controls.ContentControl.Content%2A>에서 <xref:System.Windows.Controls.ContentControl> 정의 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 형식을 가진 속성 <xref:System.Object>; 따라서 임의의 개체를 모두 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="f9b60-134">다음 컨트롤에서 상속 <xref:System.Windows.Controls.HeaderedContentControl> 및 해당 콘텐츠 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="f9b60-135">다음 그림에 나와 두 <xref:System.Windows.Controls.TabItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="f9b60-136">첫 번째 <xref:System.Windows.Controls.TabItem> 가 <xref:System.Windows.UIElement> 개체로 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 및 <xref:System.Windows.Controls.ContentControl.Content%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="f9b60-137"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 로 설정 되는 <xref:System.Windows.Controls.StackPanel> 를 포함 하는 <xref:System.Windows.Shapes.Ellipse> 및 <xref:System.Windows.Controls.TextBlock>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="f9b60-138"><xref:System.Windows.Controls.ContentControl.Content%2A> 로 설정 되는 <xref:System.Windows.Controls.StackPanel> 를 포함 하는 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Controls.Label>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="f9b60-139">두 번째 <xref:System.Windows.Controls.TabItem> 에 문자열이 있는 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 및 <xref:System.Windows.Controls.TextBlock> 에 <xref:System.Windows.Controls.ContentControl.Content%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="f9b60-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="f9b60-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="f9b60-141">헤더 속성에서 다양한 형식을 사용하는 TabControl</span><span class="sxs-lookup"><span data-stu-id="f9b60-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="f9b60-142">만드는 방법의 예제를 보려면 <xref:System.Windows.Controls.TabItem> 개체 참조 <xref:System.Windows.Controls.HeaderedContentControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="f9b60-143">임의 개체의 컬렉션을 포함하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f9b60-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="f9b60-144"><xref:System.Windows.Controls.ItemsControl> 클래스에서 상속 <xref:System.Windows.Controls.Control> 하며 문자열, 개체 또는 기타 요소와 같은 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="f9b60-145">콘텐츠 속성은 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 및 <xref:System.Windows.Controls.ItemsControl.Items%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="f9b60-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 일반적으로 채우는 데 사용 되는 <xref:System.Windows.Controls.ItemsControl> 데이터 컬렉션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="f9b60-147">경우 원하지 않는 컬렉션을 채우는 데 사용 하는 <xref:System.Windows.Controls.ItemsControl>를 사용 하 여 항목을 추가할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="f9b60-148">다음 컨트롤에서 상속 <xref:System.Windows.Controls.ItemsControl> 및 해당 콘텐츠 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="f9b60-149">다음 그림에서는 한 <xref:System.Windows.Controls.ListBox> 이러한 유형의 항목을 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="f9b60-150">문자열</span><span class="sxs-lookup"><span data-stu-id="f9b60-150">A string.</span></span>  
  
-   <span data-ttu-id="f9b60-151"><xref:System.DateTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="f9b60-152"><xref:System.Windows.UIElement></span><span class="sxs-lookup"><span data-stu-id="f9b60-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="f9b60-153">A <xref:System.Windows.Controls.Panel> 를 포함 하는 <xref:System.Windows.Shapes.Ellipse> 및 <xref:System.Windows.Controls.TextBlock>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="f9b60-154">![네 형식의 콘텐츠가 있는 ListBox](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="f9b60-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="f9b60-155">여러 개체 형식이 들어 있는 ListBox</span><span class="sxs-lookup"><span data-stu-id="f9b60-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="f9b60-156">헤더와 임의 개체의 컬렉션을 포함하는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f9b60-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="f9b60-157"><xref:System.Windows.Controls.HeaderedItemsControl> 클래스에서 상속 <xref:System.Windows.Controls.ItemsControl> 하며 문자열, 개체, 또는 기타 요소는 헤더와 같은 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="f9b60-158">상속에서 <xref:System.Windows.Controls.ItemsControl> 콘텐츠 속성을 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, 및 <xref:System.Windows.Controls.ItemsControl.Items%2A>, 정의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 임의의 개체가 될 수 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="f9b60-159">다음 컨트롤에서 상속 <xref:System.Windows.Controls.HeaderedItemsControl> 및 해당 콘텐츠 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="f9b60-160">UIElement 개체 컬렉션을 포함하는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="f9b60-161"><xref:System.Windows.Controls.Panel> 배치 하 고 자식 정렬 하는 클래스 <xref:System.Windows.UIElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="f9b60-162">해당 콘텐츠 속성은 <xref:System.Windows.Controls.Panel.Children%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="f9b60-163">다음 클래스에서 상속 된 <xref:System.Windows.Controls.Panel> 클래스 및 해당 콘텐츠 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="f9b60-164">자세한 내용은 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9b60-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="f9b60-165">UIElement의 모양에 영향을 주는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="f9b60-166"><xref:System.Windows.Controls.Decorator> 또는 그 자식 주위에 시각적 효과 적용 하는 클래스 <xref:System.Windows.UIElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="f9b60-167">해당 콘텐츠 속성은 <xref:System.Windows.Controls.Decorator.Child%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="f9b60-168">다음 클래스에서 상속 <xref:System.Windows.Controls.Decorator> 및 해당 콘텐츠 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="f9b60-169">다음 그림에서는 한 <xref:System.Windows.Controls.TextBox> 올려진 (으로 데코레이팅되 어)는 <xref:System.Windows.Controls.Border> 주위 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="f9b60-170">![검은색 테두리가 있는 TextBox](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="f9b60-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="f9b60-171">테두리가 있는 TextBlock</span><span class="sxs-lookup"><span data-stu-id="f9b60-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="f9b60-172">UIElement에 대한 시각적 피드백을 제공하는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="f9b60-173"><xref:System.Windows.Documents.Adorner> 클래스는 사용자에 게 시각적 표시를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="f9b60-174">사용 예를 들어 한 <xref:System.Windows.Documents.Adorner> 함수 핸들에 요소를 추가 하거나 컨트롤에 대 한 상태 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="f9b60-175"><xref:System.Windows.Documents.Adorner> 클래스 프레임 워크를 제공 하 여 사용자 고유의 표시기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="f9b60-176">는 구현된 표시기를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-176"> does not provide any implemented adorners.</span></span> <span data-ttu-id="f9b60-177">자세한 내용은 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9b60-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="f9b60-178">사용자가 텍스트를 입력할 수 있는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="f9b60-179">WPF는 사용자가 텍스트를 입력할 수 있는 세 개의 기본 컨트롤을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="f9b60-180">각 컨트롤에는 텍스트가 다르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-180">Each control displays the text differently.</span></span> <span data-ttu-id="f9b60-181">다음 표에서는 이 세 가지 텍스트 관련 컨트롤과 텍스트를 표시할 때의 기능 및 컨트롤 텍스트를 포함하는 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="f9b60-182">Control</span><span class="sxs-lookup"><span data-stu-id="f9b60-182">Control</span></span>|<span data-ttu-id="f9b60-183">텍스트 표시</span><span class="sxs-lookup"><span data-stu-id="f9b60-183">Text is displayed as</span></span>|<span data-ttu-id="f9b60-184">콘텐츠 속성</span><span class="sxs-lookup"><span data-stu-id="f9b60-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="f9b60-185">일반 텍스트</span><span class="sxs-lookup"><span data-stu-id="f9b60-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="f9b60-186">서식 있는 텍스트</span><span class="sxs-lookup"><span data-stu-id="f9b60-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="f9b60-187">숨겨진 텍스트(문자가 마스킹됨)</span><span class="sxs-lookup"><span data-stu-id="f9b60-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="f9b60-188">텍스트를 표시하는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="f9b60-189">여러 클래스를 사용하여 일반 텍스트나 서식이 지정된 텍스트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="f9b60-190">사용할 수 있습니다 <xref:System.Windows.Controls.TextBlock> 적은 양의 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="f9b60-191">많은 양의 텍스트를 표시 하려는 경우 사용 하 여는 <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, 또는 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="f9b60-192"><xref:System.Windows.Controls.TextBlock> 두 콘텐츠 속성이: <xref:System.Windows.Controls.TextBlock.Text%2A> 및 <xref:System.Windows.Controls.TextBlock.Inlines%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="f9b60-193">일관 된 서식을 사용 하는 텍스트를 표시 하려는 경우는 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성은 가장 좋은 방법은 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="f9b60-194">전체 텍스트에서 서로 다른 서식을 사용 하려는 경우 사용 하 여는 <xref:System.Windows.Controls.TextBlock.Inlines%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="f9b60-195"><xref:System.Windows.Controls.TextBlock.Inlines%2A> 속성의 컬렉션은 <xref:System.Windows.Documents.Inline> 텍스트 서식을 지정 하는 방법을 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="f9b60-196">다음 표에서에 대 한 콘텐츠 속성 <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="f9b60-197">Control</span><span class="sxs-lookup"><span data-stu-id="f9b60-197">Control</span></span>|<span data-ttu-id="f9b60-198">콘텐츠 속성</span><span class="sxs-lookup"><span data-stu-id="f9b60-198">Content property</span></span>|<span data-ttu-id="f9b60-199">콘텐츠 속성 형식</span><span class="sxs-lookup"><span data-stu-id="f9b60-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="f9b60-200">문서</span><span class="sxs-lookup"><span data-stu-id="f9b60-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="f9b60-201">문서</span><span class="sxs-lookup"><span data-stu-id="f9b60-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="f9b60-202">문서</span><span class="sxs-lookup"><span data-stu-id="f9b60-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="f9b60-203"><xref:System.Windows.Documents.FlowDocument> 구현 하는 <xref:System.Windows.Documents.IDocumentPaginatorSource> 인터페이스; 따라서, 세 클래스 모두 수행할 수 있습니다는 <xref:System.Windows.Documents.FlowDocument> 콘텐츠로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="f9b60-204">텍스트 서식을 지정하는 클래스</span><span class="sxs-lookup"><span data-stu-id="f9b60-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="f9b60-205"><xref:System.Windows.Documents.TextElement> 및 관련된 클래스를 사용 하면 텍스트 서식을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="f9b60-206"><xref:System.Windows.Documents.TextElement> 개체를 포함 하 고 텍스트 서식 지정 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="f9b60-207">두 가지 기본 유형이 <xref:System.Windows.Documents.TextElement> 개체는 <xref:System.Windows.Documents.Block> 요소 및 <xref:System.Windows.Documents.Inline> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="f9b60-208">A <xref:System.Windows.Documents.Block> 요소는 단락 또는 목록 등의 텍스트 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="f9b60-209"><xref:System.Windows.Documents.Inline> 요소 블록에는 텍스트의 일부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="f9b60-210">많은 <xref:System.Windows.Documents.Inline> 클래스 적용 되는 텍스트에 대 한 서식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="f9b60-211">각 <xref:System.Windows.Documents.TextElement> 자체 콘텐츠 모델을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9b60-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="f9b60-212">자세한 내용은 [TextElement 콘텐츠 모델 개요](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9b60-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b60-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9b60-213">See Also</span></span>  
 [<span data-ttu-id="f9b60-214">고급</span><span class="sxs-lookup"><span data-stu-id="f9b60-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)
