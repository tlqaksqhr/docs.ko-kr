---
title: "액세스 가능성에 대한 유용한 정보"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices for accessibility
- accessibility, best practices for
ms.assetid: e6d5cd98-21a3-4b01-999c-fb953556d0e6
caps.latest.revision: "16"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: d8714bb211c649d783cb1cfc46058e3b097def26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="accessibility-best-practices"></a><span data-ttu-id="cbc21-102">액세스 가능성에 대한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="cbc21-102">Accessibility Best Practices</span></span>
> [!NOTE]
>  <span data-ttu-id="cbc21-103">이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cbc21-104">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbc21-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="cbc21-105">컨트롤이나 응용 프로그램에서 다음 모범 사례를 구현하면 [!INCLUDE[TLA#tla_at](../../../includes/tlasharptla-at-md.md)] 장치 사용자에 대한 액세스 가능성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-105">Implementing the following best practices in controls or applications will improve their accessibility for people who use [!INCLUDE[TLA#tla_at](../../../includes/tlasharptla-at-md.md)] devices.</span></span> <span data-ttu-id="cbc21-106">이들 모범 사례는 대부분 효율적인 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 디자인에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-106">Many of these best practices focus on good [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] design.</span></span> <span data-ttu-id="cbc21-107">각 모범 사례에는 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 컨트롤 또는 응용 프로그램에 대한 구현 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-107">Each best practice includes implementation information for [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] controls or applications.</span></span> <span data-ttu-id="cbc21-108">대부분 경우에 이들 모범 사례에 맞는 작업이 이미 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-108">In many cases, the work to meet these best practices is already included in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>  
  
<a name="Programmatic_Access"></a>   
## <a name="programmatic-access"></a><span data-ttu-id="cbc21-109">프로그래밍 방식 액세스</span><span class="sxs-lookup"><span data-stu-id="cbc21-109">Programmatic Access</span></span>  
 <span data-ttu-id="cbc21-110">프로그래밍 방식 액세스에서는 모든 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소에 레이블이 지정되고, 속성 값이 노출되고, 적절한 이벤트가 발생하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-110">Programmatic access involves ensuring that all [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements are labeled, property values are exposed, and appropriate events are raised.</span></span> <span data-ttu-id="cbc21-111">표준 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 경우 이 작업 대부분이 <xref:System.Windows.Automation.Peers.AutomationPeer>를 통해 이미 수행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-111">For standard [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] controls, most of this work is already done through <xref:System.Windows.Automation.Peers.AutomationPeer>.</span></span> <span data-ttu-id="cbc21-112">사용자 지정 컨트롤에는 프로그래밍 방식 액세스가 제대로 구현되었는지 확인하는 작업이 추가로 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-112">Custom controls require additional work to ensure that programmatic access is correctly implemented.</span></span>  
  
<a name="Enable_Programmatic_Access_to_all_UI_Elements_and_Text"></a>   
### <a name="enable-programmatic-access-to-all-ui-elements-and-text"></a><span data-ttu-id="cbc21-113">모든 UI 요소 및 텍스트에 대해 프로그래밍 방식 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="cbc21-113">Enable Programmatic Access to all UI Elements and Text</span></span>  
 [!INCLUDE[TLA#tla_ui#initcap](../../../includes/tlasharptla-uisharpinitcap-md.md)]<span data-ttu-id="cbc21-114"> 요소는 프로그래밍 방식 액세스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-114"> elements should enable programmatic access.</span></span> <span data-ttu-id="cbc21-115">[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 가 표준 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이면 프로그래밍 방식 액세스 지원이 컨트롤에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-115">If the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] is a standard [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control, support for programmatic access is included in the control.</span></span> <span data-ttu-id="cbc21-116">공용 컨트롤에서 서브클래싱된 컨트롤이나 컨트롤에서 서브클래싱된 컨트롤과 같은 사용자 지정 컨트롤이면 <xref:System.Windows.Automation.Peers.AutomationPeer> 구현에서 수정해야 할 수 있는 영역이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-116">If the control is a custom control – a control that has been subclassed from a common control or a control that has been subclassed from Control – then you must check the <xref:System.Windows.Automation.Peers.AutomationPeer> implementation for areas that may need modification.</span></span>  
  
 <span data-ttu-id="cbc21-117">이 모범 사례를 따르면 [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)] 공급업체에서 제품 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]의 요소를 식별 및 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-117">Following this best practice allows [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)] vendors to identify and manipulate elements of your product's [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
<a name="Place_Names__Titles_and_Descriptions_on_UI_Objects_"></a>   
### <a name="place-names-titles-and-descriptions-on-ui-objects-frames-and-pages"></a><span data-ttu-id="cbc21-118">UI 개체, 프레임 및 페이지에 대한 위치 이름, 제목 및 설명</span><span class="sxs-lookup"><span data-stu-id="cbc21-118">Place Names, Titles, and Descriptions on UI Objects, Frames, and Pages</span></span>  
 <span data-ttu-id="cbc21-119">보조 기술, 특히 화면 읽기 프로그램에서는 제목을 사용하여 탐색 체계에서 프레임, 개체 또는 페이지의 위치를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-119">Assistive technologies, especially screen readers, use the title to understand the location of the frame, object, or page in the navigation scheme.</span></span> <span data-ttu-id="cbc21-120">따라서 제목은 구체적인 설명을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-120">Therefore, the title must be very descriptive.</span></span> <span data-ttu-id="cbc21-121">예를 들어 사용자가 특정 영역을 자세히 탐색한 경우에는 웹 페이지 제목이 "Microsoft 웹 페이지"인 것은 도움이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-121">For example, a Web page title of "Microsoft Web Page" is useless if the user has navigated deeply into some particular area.</span></span> <span data-ttu-id="cbc21-122">시각 장애가 있고 화면 읽기 프로그램에 의존하는 사용자에게는 구체적인 설명이 포함된 제목이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-122">A descriptive title is critical for users who are blind and depend on screen readers.</span></span> <span data-ttu-id="cbc21-123">마찬가지로 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 컨트롤의 경우 <xref:System.Windows.Automation.AutomationProperties.NameProperty> 장치에 대한 <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> 및 [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)] 가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-123">Similarly, for [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] controls, <xref:System.Windows.Automation.AutomationProperties.NameProperty> and <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> are important for [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)] devices.</span></span>  
  
 <span data-ttu-id="cbc21-124">이 모범 사례를 따르면 [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)]가 샘플 컨트롤 및 응용 프로그램에서 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 를 식별 및 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-124">Following this best practice allows [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)]s to identify and manipulate [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] in sample controls and applications.</span></span>  
  
<a name="Ensure_Programmatic_Events_are_Triggered_by_all_UI"></a>   
### <a name="ensure-programmatic-events-are-triggered-by-all-ui-activities"></a><span data-ttu-id="cbc21-125">프로그래밍 방식 이벤트가 모든 UI 작업에서 트리거되는지 확인</span><span class="sxs-lookup"><span data-stu-id="cbc21-125">Ensure Programmatic Events Are Triggered by All UI Activities</span></span>  
 <span data-ttu-id="cbc21-126">이 모범 사례를 따르면 [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)]가 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 에서 변경 내용을 수신 대기하고 이들 변경 내용을 사용자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-126">Following this best practice allows [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)]s to listen for changes in the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] and notify the user about these changes.</span></span>  
  
<a name="User_Settings"></a>   
## <a name="user-settings"></a><span data-ttu-id="cbc21-127">사용자 설정</span><span class="sxs-lookup"><span data-stu-id="cbc21-127">User Settings</span></span>  
 <span data-ttu-id="cbc21-128">이 섹션의 모범 사례에서는 컨트롤이나 응용 프로그램이 사용자 설정을 재정의하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-128">The best practice in this section ensures that controls or applications do not override user settings.</span></span>  
  
<a name="Respect_all_System_Wide_Settings_and_do_not_Interfere"></a>   
### <a name="respect-all-system-wide-settings-and-do-not-interfere-with-accessibility-functions"></a><span data-ttu-id="cbc21-129">모든 시스템 수준 설정 유지 및 액세스 가능성 기능 방해 안 함</span><span class="sxs-lookup"><span data-stu-id="cbc21-129">Respect All System-Wide Settings and Do Not Interfere with Accessibility Functions</span></span>  
 <span data-ttu-id="cbc21-130">사용자는 제어판을 사용하여 일부 시스템 수준 플래그를 설정할 수 있습니다. 다른 플래그는 프로그래밍 방식으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-130">Users can use the Control Panel to set some system-wide flags; other flags can be set programmatically.</span></span> <span data-ttu-id="cbc21-131">이들 설정은 컨트롤이나 응용 프로그램에 의해 변경되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-131">These settings should not be changed by controls or applications.</span></span> <span data-ttu-id="cbc21-132">또한 응용 프로그램에서는 호스트 운영 체제의 액세스 가능성 설정을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-132">Also, applications must support the accessibility settings of their host operating system.</span></span>  
  
 <span data-ttu-id="cbc21-133">이 모범 사례를 따르면 사용자가 액세스 가능성 설정을 지정하고 해당 설정이 응용 프로그램에 의해 변경되지 않는다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-133">Following this best practice allows users to set accessibility settings and know that those settings will not be changed by applications.</span></span>  
  
<a name="Visual_UI_Design"></a>   
## <a name="visual-ui-design"></a><span data-ttu-id="cbc21-134">시각적 UI 디자인</span><span class="sxs-lookup"><span data-stu-id="cbc21-134">Visual UI Design</span></span>  
 <span data-ttu-id="cbc21-135">이 섹션의 모범 사례에서는 컨트롤이나 응용 프로그램에서 색 및 이미지를 효과적으로 사용하고 [!INCLUDE[TLA2#tla_at#plural](../../../includes/tla2sharptla-atsharpplural-md.md)]에서 사용될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-135">Best Practices in this section ensure that controls or applications use color and images effectively and are able to be used by [!INCLUDE[TLA2#tla_at#plural](../../../includes/tla2sharptla-atsharpplural-md.md)].</span></span>  
  
<a name="Don_t_Hard_Code_Colors"></a>   
### <a name="dont-hard-code-colors"></a><span data-ttu-id="cbc21-136">색 하드 코드 안 함</span><span class="sxs-lookup"><span data-stu-id="cbc21-136">Don't Hard-Code Colors</span></span>  
 <span data-ttu-id="cbc21-137">색맹이거나 시력이 낮거나 흑백 화면을 사용하는 사용자는 하드 코드된 색으로 응용 프로그램을 사용하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-137">People who are color blind, have low vision, or are using a black and white screen might not be able to use applications with hard-coded colors.</span></span>  
  
 <span data-ttu-id="cbc21-138">이 모범 사례를 따르면 사용자가 개별 요구 사항에 따라 색 조합을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-138">Following this best practice allows users to adjust color combinations based on individual needs.</span></span>  
  
<a name="Support_High_Contrast_and_all_System_Display_Attributes"></a>   
### <a name="support-high-contrast-and-all-system-display-attributes"></a><span data-ttu-id="cbc21-139">고대비 및 모든 시스템 표시 특성 지원</span><span class="sxs-lookup"><span data-stu-id="cbc21-139">Support High Contrast and all System Display Attributes</span></span>  
 <span data-ttu-id="cbc21-140">응용 프로그램은 사용자가 선택한 시스템 수준 대비 설정, 색 선택 또는 기타 시스템 수준 표시 설정과 특성을 방해하거나 비활성화하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-140">Applications should not disrupt or disable user-selected, system-wide contrast settings, color selections, or other system-wide display settings and attributes.</span></span> <span data-ttu-id="cbc21-141">사용자가 선택한 시스템 수준 설정은 응용 프로그램의 액세스 가능성을 개선하므로 응용 프로그램에 의해 비활성화되거나 무시되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-141">System-wide settings adopted by a user enhance the accessibility of applications, so they should not be disabled or disregarded by applications.</span></span> <span data-ttu-id="cbc21-142">적절한 대비를 제공하려면 올바른 배경 기반 전경 조합으로 색을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-142">Color should be used in their correct foreground-on-background combination to provide proper contrast.</span></span> <span data-ttu-id="cbc21-143">관련되지 않은 색을 혼합하지 않아야 하고 색을 반전하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-143">Unrelated colors should not be mixed, and colors should not be reversed.</span></span>  
  
 <span data-ttu-id="cbc21-144">대부분 사용자에게는 검은색 배경 기반 흰색 텍스트와 같은 특수 고대비 조합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-144">Many users require specific high-contrast combinations, such as white text on a black background.</span></span> <span data-ttu-id="cbc21-145">흰색 배경 기반 검은색 텍스트처럼 이들 색을 반전해서 그리면 배경이 전경 위로 번지므로 몇몇 사용자는 텍스트를 읽기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-145">Drawing these reversed, as black text on a white background causes the background to bleed over the foreground and can make reading difficult for some users.</span></span>  
  
<a name="Ensure_all_UI_Correctly_Scales_by_any_DPI_Setting"></a>   
### <a name="ensure-all-ui-correctly-scales-by-any-dpi-setting"></a><span data-ttu-id="cbc21-146">DPI 설정으로 모든 UI가 올바르게 크기 조정되는지 확인</span><span class="sxs-lookup"><span data-stu-id="cbc21-146">Ensure All UI Correctly Scales by Any DPI Setting</span></span>  
 <span data-ttu-id="cbc21-147">모든 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 가 [!INCLUDE[TLA#tla_dpi](../../../includes/tlasharptla-dpi-md.md)] 설정으로 올바르게 크기 조정될 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-147">Ensure that all [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] can correctly scale by any [!INCLUDE[TLA#tla_dpi](../../../includes/tlasharptla-dpi-md.md)] setting.</span></span> <span data-ttu-id="cbc21-148">또한 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소가 1024 x 768 화면에 120 [!INCLUDE[TLA#tla_dpi](../../../includes/tlasharptla-dpi-md.md)]로 맞춰지는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-148">Also, ensure that [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements fit in a screen of 1024 x 768 with 120 [!INCLUDE[TLA#tla_dpi](../../../includes/tlasharptla-dpi-md.md)].</span></span>  
  
<a name="Navigation"></a>   
## <a name="navigation"></a><span data-ttu-id="cbc21-149">탐색</span><span class="sxs-lookup"><span data-stu-id="cbc21-149">Navigation</span></span>  
 <span data-ttu-id="cbc21-150">이 섹션의 모범 사례에서는 컨트롤 및 응용 프로그램에 대한 탐색이 처리되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-150">Best Practices in this section ensure that navigation has been addressed for controls and applications.</span></span>  
  
<a name="Provide_Keyboard_Interface_for_all_UI_Elements"></a>   
### <a name="provide-keyboard-interface-for-all-ui-elements"></a><span data-ttu-id="cbc21-151">모든 UI 요소에 대한 키보드 인터페이스 제공</span><span class="sxs-lookup"><span data-stu-id="cbc21-151">Provide Keyboard Interface for All UI Elements</span></span>  
 <span data-ttu-id="cbc21-152">특히 신중하게 계획된 탭 정지는 사용자에게 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]를 탐색하는 또 다른 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-152">Tab stops, especially when carefully planned, give users another way to navigate the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="cbc21-153">응용 프로그램에서는 다음 키보드 인터페이스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-153">Applications should provide the following keyboard interfaces:</span></span>  
  
-   <span data-ttu-id="cbc21-154">단추, 링크 또는 목록 상자와 같이 사용자가 조작할 수 있는 모든 컨트롤에 대한 탭 정지</span><span class="sxs-lookup"><span data-stu-id="cbc21-154">tab stops for all controls that the user can interact with, such as buttons, links, or list boxes</span></span>  
  
-   <span data-ttu-id="cbc21-155">논리적 탭 순서</span><span class="sxs-lookup"><span data-stu-id="cbc21-155">logical tab order</span></span>  
  
<a name="Show_the_Keyboard_Focus"></a>   
### <a name="show-the-keyboard-focus"></a><span data-ttu-id="cbc21-156">키보드 포커스 표시</span><span class="sxs-lookup"><span data-stu-id="cbc21-156">Show the Keyboard Focus</span></span>  
 <span data-ttu-id="cbc21-157">사용자는 키 입력의 효과를 예상할 수 있도록 키보드 포커스가 있는 개체를 사용자가 알 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-157">Users need to know which object has the keyboard focus so that they can anticipate the effect of their keystrokes.</span></span> <span data-ttu-id="cbc21-158">키보드 포커스를 강조 표시하려면 색, 글꼴 또는 그래픽(예: 사각형 또는 확대)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-158">To highlight the keyboard focus, use colors, fonts, or graphics such as rectangles or magnification.</span></span> <span data-ttu-id="cbc21-159">키보드 포커스를 청각적으로 강조하려면 볼륨, 피치 또는 음조 품질을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-159">To audibly highlight the keyboard focus, change the volume, pitch or tonal quality.</span></span>  
  
 <span data-ttu-id="cbc21-160">혼동을 방지하려면 응용 프로그램이 모든 시각적 포커스 표시기를 숨기고 비활성 창에 있는 선택 항목을 흐리게 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-160">To avoid confusion, applications should hide all visual focus indicators and dim selections that are located in inactive windows (or panes).</span></span>  
  
 <span data-ttu-id="cbc21-161">응용프로그램에서는 키보드 포커스를 통해 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-161">Applications should do the following with keyboard focus:</span></span>  
  
-   <span data-ttu-id="cbc21-162">키보드 포커스가 항상 한 항목에 있어야 함</span><span class="sxs-lookup"><span data-stu-id="cbc21-162">one item should always have keyboard focus</span></span>  
  
-   <span data-ttu-id="cbc21-163">키보드 포커스가 표시되고 분명해야 함</span><span class="sxs-lookup"><span data-stu-id="cbc21-163">keyboard focus should be visible and obvious</span></span>  
  
-   <span data-ttu-id="cbc21-164">선택 항목 및/또는 포커스가 있는 항목이 시각적으로 강조되어야 함</span><span class="sxs-lookup"><span data-stu-id="cbc21-164">selections and/or focused items should be visually highlighted</span></span>  
  
<a name="Support_Navigation_Standards_and_Powerful_Navigation"></a>   
### <a name="support-navigation-standards-and-powerful-navigation-schemes"></a><span data-ttu-id="cbc21-165">탐색 표준 및 강력한 탐색 체계 지원</span><span class="sxs-lookup"><span data-stu-id="cbc21-165">Support Navigation Standards and Powerful Navigation Schemes</span></span>  
 <span data-ttu-id="cbc21-166">키보드 탐색의 다양한 측면을 통해 사용자가 다양한 방법으로 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]을(를) 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-166">Different aspects of keyboard navigation provide different ways for users to navigate the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="cbc21-167">응용 프로그램에서는 다음 키보드 인터페이스를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-167">Applications should provide the following keyboard interfaces:</span></span>  
  
-   <span data-ttu-id="cbc21-168">모든 명령, 메뉴 및 컨트롤에 대한 바로 가기 키 및 밑줄이 표시된 액세스 키</span><span class="sxs-lookup"><span data-stu-id="cbc21-168">shortcut keys and underlined access keys for all commands, menus and controls</span></span>  
  
-   <span data-ttu-id="cbc21-169">중요 링크에 대한 키보드 바로 가기</span><span class="sxs-lookup"><span data-stu-id="cbc21-169">keyboard shortcuts to important links</span></span>  
  
-   <span data-ttu-id="cbc21-170">모든 메뉴 항목에는 액세스 키가 있고 모든 단추와 모든 명령에는 액셀러레이터 키가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-170">all menu items have an access key; all buttons have accelerator keys, all commands have an accelerator key.</span></span>  
  
<a name="Do_not_let_Mouse_Location_Interfere_with_Keyboard"></a>   
### <a name="do-not-let-mouse-location-interfere-with-keyboard-navigation"></a><span data-ttu-id="cbc21-171">마우스 위치가 키보드 탐색을 방해하면 안 됨</span><span class="sxs-lookup"><span data-stu-id="cbc21-171">Do Not Let Mouse Location Interfere with Keyboard Navigation</span></span>  
 <span data-ttu-id="cbc21-172">마우스 위치가 키보드 탐색을 방해하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-172">Mouse location should not interfere with keyboard navigation.</span></span> <span data-ttu-id="cbc21-173">예를 들어 마우스가 임의 위치에 있고 사용자가 키보드로 탐색할 경우 사용자가 시작하지 않은 마우스 클릭이 발생하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-173">For example, if the mouse is positioned someplace and the user is navigating with the keyboard, a mouse click should not happen unless initiated by the user.</span></span>  
  
<a name="Multimodal_Interface"></a>   
## <a name="multimodal-interface"></a><span data-ttu-id="cbc21-174">다중 모달 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cbc21-174">Multimodal Interface</span></span>  
 <span data-ttu-id="cbc21-175">이 섹션의 모범 사례에서는 응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 에 시각적 요소에 대한 대안이 포함되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-175">Best Practices in this section ensure that application [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] includes alternatives for visual elements.</span></span>  
  
<a name="Provide_User_Selectable_Equivalents_for_Non_Text"></a>   
### <a name="provide-user-selectable-equivalents-for-non-text-elements"></a><span data-ttu-id="cbc21-176">텍스트가 아닌 요소에 대한 사용자가 선택할 수 있는 요소 제공</span><span class="sxs-lookup"><span data-stu-id="cbc21-176">Provide User-Selectable Equivalents for Non-Text Elements</span></span>  
 <span data-ttu-id="cbc21-177">각 텍스트가 아닌 요소의 경우 텍스트, 기록 또는 오디오 설명(예: 대체 텍스트, 캡션 또는 시각적 피드백)에 대한 사용자가 선택할 수 있는 요소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-177">For each non-text element, provide a user-selectable equivalent for text, transcripts, or audio descriptions, such as alt text, captions, or visual feedback.</span></span>  
  
 <span data-ttu-id="cbc21-178">텍스트가 아닌 요소는 이미지, 이미지 맵 영역, 애니메이션, 애플릿, 프레임, 스크립트, 그래픽 단추, 소리, 독립 실행형 오디오 파일 및 비디오를 포함한 광범위한 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-178">Non-text elements cover a wide range of [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements including: images, image map regions, animations, applets, frames, scripts, graphical buttons, sounds, stand-alone audio files and video.</span></span> <span data-ttu-id="cbc21-179">텍스트가 아닌 요소는 사용자가 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]의 콘텐츠를 이해하기 위해 액세스해야 하는 시각적 정보, 음성 또는 일반 오디오 정보를 포함할 때 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-179">Non-text elements are important when they contain visual information, speech, or general audio information that the user needs access to in order to understand the content of the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
<a name="Use_Color_but_also_Provide_Alternatives_to_Color"></a>   
### <a name="use-color-but-also-provide-alternatives-to-color"></a><span data-ttu-id="cbc21-180">색을 사용하지만 색의 대안 제공</span><span class="sxs-lookup"><span data-stu-id="cbc21-180">Use Color but Also Provide Alternatives to Color</span></span>  
 <span data-ttu-id="cbc21-181">색을 사용하여 다른 수단으로 표시된 정보를 개선, 강조 또는 반복하지만 색만 사용해서 정보를 전달하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-181">Use color to enhance, emphasize, or reiterate information shown by other means, but do not communicate information by using color alone.</span></span> <span data-ttu-id="cbc21-182">색맹이거나 단색 디스플레이를 사용하는 사용자는 색의 대안이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-182">Users who are color blind or have a monochrome display need alternatives to color.</span></span>  
  
<a name="Use_Standard_Input_APIs_with_Devices_Independent"></a>   
### <a name="use-standard-input-apis-with-device-independent-calls"></a><span data-ttu-id="cbc21-183">장치 독립적 호출을 통해 표준 입력 API 사용</span><span class="sxs-lookup"><span data-stu-id="cbc21-183">Use Standard Input APIs with Device-Independent Calls</span></span>  
 <span data-ttu-id="cbc21-184">장치 독립적 호출을 사용하면 키보드 기능과 마우스 기능이 동일해지고 [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)] 에 대한 필요한 정보와 함께 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]을(를) 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc21-184">Device-independent calls ensure keyboard and mouse feature equality, while providing [!INCLUDE[TLA2#tla_at](../../../includes/tla2sharptla-at-md.md)] with needed information about the [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc21-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbc21-185">See Also</span></span>  
 <xref:System.Windows.Automation.Peers>  
 [<span data-ttu-id="cbc21-186">테마와 UI 자동화 지원 샘플이 있는 NumericUpDown 사용자 지정 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cbc21-186">NumericUpDown Custom Control with Theme and UI Automation Support Sample</span></span>](http://msdn.microsoft.com/en-us/9aed3c10-68eb-419e-a57f-1d2af15a8253)  
 [<span data-ttu-id="cbc21-187">키보드 사용자 인터페이스 디자인에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="cbc21-187">Guidelines for Keyboard User Interface Design</span></span>](http://msdn2.microsoft.com/library/ms971323.aspx)
