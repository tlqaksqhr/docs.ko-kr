---
title: "연습: WindowsFormsHost 요소를 사용하여 속성 매핑"
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
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eaab6b7724a1e6145dfce3998ccf75904df01802
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="80b9f-102">연습: WindowsFormsHost 요소를 사용하여 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="80b9f-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>
<span data-ttu-id="80b9f-103">이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> 매핑할 속성 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 해당 속성에 호스팅 속성 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="80b9f-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="80b9f-105">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="80b9f-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="80b9f-106">응용 프로그램 레이아웃 정의.</span><span class="sxs-lookup"><span data-stu-id="80b9f-106">Defining the application layout.</span></span>  
  
-   <span data-ttu-id="80b9f-107">새 속성 매핑 정의.</span><span class="sxs-lookup"><span data-stu-id="80b9f-107">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="80b9f-108">기본 속성 매핑 제거.</span><span class="sxs-lookup"><span data-stu-id="80b9f-108">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="80b9f-109">기본 속성 매핑 바꾸기.</span><span class="sxs-lookup"><span data-stu-id="80b9f-109">Replacing a default property mapping.</span></span>  
  
-   <span data-ttu-id="80b9f-110">기본 속성 매핑 확장.</span><span class="sxs-lookup"><span data-stu-id="80b9f-110">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="80b9f-111">이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [WindowsFormsHost 요소 예제를 사용 하 여 매핑 속성](http://go.microsoft.com/fwlink/?LinkID=160019)합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](http://go.microsoft.com/fwlink/?LinkID=160019).</span></span>  
  
 <span data-ttu-id="80b9f-112">완료 했으면 매핑할 할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 해당 속성에 호스팅 속성 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="80b9f-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="80b9f-113">Prerequisites</span></span>  
 <span data-ttu-id="80b9f-114">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="80b9f-115">.</span><span class="sxs-lookup"><span data-stu-id="80b9f-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="80b9f-116">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="80b9f-116">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="80b9f-117">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="80b9f-117">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="80b9f-118">이라는 WPF 응용 프로그램 프로젝트 만들기 `PropertyMappingWithWfhSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-118">Create a WPF Application project named `PropertyMappingWithWfhSample`.</span></span>  
  
2.  <span data-ttu-id="80b9f-119">솔루션 탐색기에서 WindowsFormsIntegration.dll 라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-119">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="80b9f-120">솔루션 탐색기에서 System.Drawing 및 System.Windows.Forms 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-120">In Solution Explorer, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="defining-the-application-layout"></a><span data-ttu-id="80b9f-121">응용 프로그램 레이아웃 정의</span><span class="sxs-lookup"><span data-stu-id="80b9f-121">Defining the Application Layout</span></span>  
 <span data-ttu-id="80b9f-122">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스트에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-122">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-define-the-application-layout"></a><span data-ttu-id="80b9f-123">응용 프로그램 레이아웃을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="80b9f-123">To define the application layout</span></span>  
  
1.  <span data-ttu-id="80b9f-124">Window1.xaml에서 열고는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-124">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="80b9f-125">기존 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-125">Replace the existing code with the following code.</span></span>  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  <span data-ttu-id="80b9f-126">코드 편집기에서 Window1.xaml.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-126">Open Window1.xaml.cs in the Code Editor.</span></span>  
  
4.  <span data-ttu-id="80b9f-127">파일의 맨 위에서 다음 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-127">At the top of the file, import the following namespaces.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="80b9f-128">새 속성 매핑 정의</span><span class="sxs-lookup"><span data-stu-id="80b9f-128">Defining a New Property Mapping</span></span>  
 <span data-ttu-id="80b9f-129"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 여러 기본 속성 매핑을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-129">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="80b9f-130">호출 하 여 새 속성 매핑을 추가 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 에서 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="80b9f-131">새 속성 매핑을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="80b9f-131">To define a new property mapping</span></span>  
  
-   <span data-ttu-id="80b9f-132">에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-132">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     <span data-ttu-id="80b9f-133">`AddClipMapping` 에 대 한 새 매핑을 추가 하는 메서드는 <xref:System.Windows.UIElement.Clip%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-133">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="80b9f-134">`OnClipChange` 메서드 변환 하는 <xref:System.Windows.UIElement.Clip%2A> 속성을는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-134">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="80b9f-135">`Window1_SizeChanged` 창의 처리 <xref:System.Windows.FrameworkElement.SizeChanged> 이벤트 고 응용 프로그램 창에 맞게 클리핑 영역 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-135">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="80b9f-136">기본 속성 매핑 제거</span><span class="sxs-lookup"><span data-stu-id="80b9f-136">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="80b9f-137">호출 하 여 기본 속성 매핑을 제거는 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 에서 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-137">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="80b9f-138">기본 속성 매핑을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="80b9f-138">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="80b9f-139">에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-139">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     <span data-ttu-id="80b9f-140">`RemoveCursorMapping` 메서드에 대 한 기본 매핑을 삭제 하는 <xref:System.Windows.FrameworkElement.Cursor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-140">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>  
  
## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="80b9f-141">기본 속성 매핑 바꾸기</span><span class="sxs-lookup"><span data-stu-id="80b9f-141">Replacing a Default Property Mapping</span></span>  
 <span data-ttu-id="80b9f-142">기본 매핑 및 호출을 제거 하 여 기본 속성 매핑을 바꾸기는 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 에서 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-142">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="80b9f-143">기본 속성 매핑을 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="80b9f-143">To replace a default property mapping</span></span>  
  
-   <span data-ttu-id="80b9f-144">에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-144">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     <span data-ttu-id="80b9f-145">`ReplaceFlowDirectionMapping` 메서드 대체에 대 한 기본 매핑을 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-145">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>  
  
     <span data-ttu-id="80b9f-146">`OnFlowDirectionChange` 메서드 변환 하는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-146">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>  
  
     <span data-ttu-id="80b9f-147">`cb_CheckedChanged` 메서드 핸들의 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 이벤트에는 <xref:System.Windows.Forms.CheckBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-147">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="80b9f-148">할당 된 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성의 값에 따라는 <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="80b9f-148">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="80b9f-149">기본 속성 매핑 확장</span><span class="sxs-lookup"><span data-stu-id="80b9f-149">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="80b9f-150">기본 속성 매핑을 사용하고 고유 매핑으로 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-150">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="80b9f-151">기본 속성 매핑을 확장하려면</span><span class="sxs-lookup"><span data-stu-id="80b9f-151">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="80b9f-152">에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-152">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     <span data-ttu-id="80b9f-153">`ExtendBackgroundMapping` 메서드를 기존 사용자 지정 속성 변환기를 추가 <xref:System.Windows.Controls.Control.Background%2A> 속성 매핑.</span><span class="sxs-lookup"><span data-stu-id="80b9f-153">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>  
  
     <span data-ttu-id="80b9f-154">`OnBackgroundChange` 메서드를 호스팅된 컨트롤의 특정 이미지를 할당 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-154">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="80b9f-155">`OnBackgroundChange` 기본 속성 매핑을 적용 된 후 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-155">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="80b9f-156">속성 매핑 초기화</span><span class="sxs-lookup"><span data-stu-id="80b9f-156">Initializing Your Property Mappings</span></span>  
 <span data-ttu-id="80b9f-157">앞에서 설명한 메서드를 호출 하면 속성 매핑을 설정의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-157">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="80b9f-158">속성 매핑을 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="80b9f-158">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="80b9f-159">에 대 한 정의에 다음 코드를 복사는 `Window1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-159">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     <span data-ttu-id="80b9f-160">`WindowLoaded` 메서드 핸들은 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 하 고 초기화 하는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-160">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="80b9f-161">만듭니다는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-161">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>  
  
    -   <span data-ttu-id="80b9f-162">연습에서 이전에 정의한 메서드를 호출하여 속성 매핑을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-162">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="80b9f-163">매핑된 속성에 초기 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-163">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="80b9f-164">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-164">Press F5 to build and run the application.</span></span> <span data-ttu-id="80b9f-165">효과 확인 하려면이 확인란을 클릭는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 매핑.</span><span class="sxs-lookup"><span data-stu-id="80b9f-165">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="80b9f-166">확인란을 클릭하면 레이아웃이 왼쪽에서 오른쪽으로의 방향을 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="80b9f-166">When you click the check box, the layout reverses its left-right orientation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b9f-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80b9f-167">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="80b9f-168">Windows Forms 및 WPF 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="80b9f-168">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="80b9f-169">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="80b9f-169">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="80b9f-170">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="80b9f-170">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
