---
title: "연습: ElementHost 컨트롤을 사용하여 속성 매핑"
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
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0db7b9677b5c8c415b6d0b3f49bd149c06843a33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="4a760-102">연습: ElementHost 컨트롤을 사용하여 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="4a760-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>
<span data-ttu-id="4a760-103">이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> 매핑할 속성 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 해당 속성에 호스팅 속성 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>  
  
 <span data-ttu-id="4a760-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="4a760-105">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="4a760-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="4a760-106">새 속성 매핑 정의.</span><span class="sxs-lookup"><span data-stu-id="4a760-106">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="4a760-107">기본 속성 매핑 제거.</span><span class="sxs-lookup"><span data-stu-id="4a760-107">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="4a760-108">기본 속성 매핑 확장.</span><span class="sxs-lookup"><span data-stu-id="4a760-108">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="4a760-109">이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [ElementHost 컨트롤 샘플을 사용 하 여 속성 매핑](http://go.microsoft.com/fwlink/?LinkID=160018)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](http://go.microsoft.com/fwlink/?LinkID=160018).</span></span>  
  
 <span data-ttu-id="4a760-110">완료 했으면 매핑할 할 수 있습니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 해당 속성 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호스팅된 요소에는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4a760-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4a760-111">Prerequisites</span></span>  
 <span data-ttu-id="4a760-112">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="4a760-113">.</span><span class="sxs-lookup"><span data-stu-id="4a760-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4a760-114">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4a760-114">Creating the Project</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="4a760-115">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4a760-115">To create the project</span></span>  
  
1.  <span data-ttu-id="4a760-116">만들기는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 라는 응용 프로그램 프로젝트 `PropertyMappingWithElementHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-116">Create a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project named `PropertyMappingWithElementHost`.</span></span> <span data-ttu-id="4a760-117">자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a760-117">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="4a760-118">솔루션 탐색기에서 다음에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-118">In Solution Explorer, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>  
  
    -   <span data-ttu-id="4a760-119">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="4a760-119">PresentationCore</span></span>  
  
    -   <span data-ttu-id="4a760-120">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="4a760-120">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="4a760-121">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="4a760-121">WindowsBase</span></span>  
  
    -   <span data-ttu-id="4a760-122">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="4a760-122">WindowsFormsIntegration</span></span>  
  
3.  <span data-ttu-id="4a760-123">맨 위에 다음 코드를 복사는 `Form1` 코드 파일.</span><span class="sxs-lookup"><span data-stu-id="4a760-123">Copy the following code into the top of the `Form1` code file.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="4a760-124">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-124">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="4a760-125">에 대 한 이벤트 처리기를 추가 하려면 폼을 두 번 클릭은 <xref:System.Windows.Forms.Form.Load> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-125">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
5.  <span data-ttu-id="4a760-126">폼의에 대 한 이벤트 처리기를 추가 하 고 Windows Forms 디자이너로 돌아갑니다 <xref:System.Windows.Forms.Control.Resize> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-126">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="4a760-127">자세한 내용은 참조 [하는 방법: 디자이너를 사용 이벤트 처리기 만들기](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2)합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-127">For more information, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/en-us/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
6.  <span data-ttu-id="4a760-128">선언 된 <xref:System.Windows.Forms.Integration.ElementHost> 필드에 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-128">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a><span data-ttu-id="4a760-129">새 속성 매핑 정의</span><span class="sxs-lookup"><span data-stu-id="4a760-129">Defining New Property Mappings</span></span>  
 <span data-ttu-id="4a760-130"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 몇 가지 기본 속성 매핑을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-130">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="4a760-131">호출 하 여 새 속성 매핑을 추가 <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> 에서 메서드는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-131">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-new-property-mappings"></a><span data-ttu-id="4a760-132">새 속성 매핑을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="4a760-132">To define new property mappings</span></span>  
  
1.  <span data-ttu-id="4a760-133">에 대 한 정의에 다음 코드를 복사는 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-133">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     <span data-ttu-id="4a760-134">`AddMarginMapping` 에 대 한 새 매핑을 추가 하는 메서드는 <xref:System.Windows.Forms.Control.Margin%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-134">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>  
  
     <span data-ttu-id="4a760-135">`OnMarginChange` 메서드 변환 하는 <xref:System.Windows.Forms.Control.Margin%2A> 속성을는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-135">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>  
  
2.  <span data-ttu-id="4a760-136">에 대 한 정의에 다음 코드를 복사는 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-136">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     <span data-ttu-id="4a760-137">`AddRegionMapping` 에 대 한 새 매핑을 추가 하는 메서드는 <xref:System.Windows.Forms.Control.Region%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-137">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="4a760-138">`OnRegionChange` 메서드 변환 하는 <xref:System.Windows.Forms.Control.Region%2A> 속성을는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-138">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="4a760-139">`Form1_Resize` 양식의 처리 <xref:System.Windows.Forms.Control.Resize> 이벤트 고 호스팅된 요소에 맞게 클리핑 영역 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-139">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="4a760-140">기본 속성 매핑 제거</span><span class="sxs-lookup"><span data-stu-id="4a760-140">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="4a760-141">호출 하 여 기본 속성 매핑을 제거는 <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> 에서 메서드는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-141">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="4a760-142">기본 속성 매핑을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="4a760-142">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="4a760-143">에 대 한 정의에 다음 코드를 복사는 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-143">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     <span data-ttu-id="4a760-144">`RemoveCursorMapping` 메서드에 대 한 기본 매핑을 삭제 하는 <xref:System.Windows.Forms.Control.Cursor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-144">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="4a760-145">기본 속성 매핑 확장</span><span class="sxs-lookup"><span data-stu-id="4a760-145">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="4a760-146">기본 속성 매핑을 사용하고 고유 매핑으로 확장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-146">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="4a760-147">기본 속성 매핑을 확장하려면</span><span class="sxs-lookup"><span data-stu-id="4a760-147">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="4a760-148">에 대 한 정의에 다음 코드를 복사는 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-148">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     <span data-ttu-id="4a760-149">`ExtendBackColorMapping` 메서드를 기존 사용자 지정 속성 변환기를 추가 <xref:System.Windows.Forms.Control.BackColor%2A> 속성 매핑.</span><span class="sxs-lookup"><span data-stu-id="4a760-149">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>  
  
     <span data-ttu-id="4a760-150">`OnBackColorChange` 메서드를 호스팅된 컨트롤의 특정 이미지를 할당 <xref:System.Windows.Controls.Control.Background%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-150">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="4a760-151">`OnBackColorChange` 기본 속성 매핑을 적용 된 후 메서드가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-151">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="4a760-152">속성 매핑 초기화</span><span class="sxs-lookup"><span data-stu-id="4a760-152">Initializing Your Property Mappings</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="4a760-153">속성 매핑을 초기화하려면</span><span class="sxs-lookup"><span data-stu-id="4a760-153">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="4a760-154">에 대 한 정의에 다음 코드를 복사는 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-154">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     <span data-ttu-id="4a760-155">`Form1_Load` 메서드 핸들은 <xref:System.Windows.Forms.Form.Load> 이벤트 하 고 초기화 하는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-155">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="4a760-156">만듭니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-156">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>  
  
    -   <span data-ttu-id="4a760-157">연습에서 이전에 정의한 메서드를 호출하여 속성 매핑을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-157">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="4a760-158">매핑된 속성에 초기 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-158">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="4a760-159">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4a760-159">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a760-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a760-160">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="4a760-161">Windows Forms 및 WPF 속성 매핑</span><span class="sxs-lookup"><span data-stu-id="4a760-161">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="4a760-162">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="4a760-162">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="4a760-163">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="4a760-163">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
