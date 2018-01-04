---
title: "연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08cb39215ea1d9aff1cd7ecc125bd731f14a4d7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="46686-102">연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기</span><span class="sxs-lookup"><span data-stu-id="46686-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="46686-103">사용 중인 구성 요소는 현재 열려 있는 솔루션의 프로젝트에서 정의 된 경우 자동으로에 표시 됩니다는 **도구 상자**, 작업이 사용자가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46686-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="46686-104">수동으로 채울 수 있습니다는 **도구 상자** 를 사용 하 여 사용자 지정 구성 요소와는 [선택 도구 상자 항목 대화 상자 (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb), 하지만 **도구 상자** 고려 솔루션에 있는 항목의 다음 특성을 모두의 출력을 빌드:</span><span class="sxs-lookup"><span data-stu-id="46686-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="46686-105">구현 <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="46686-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="46686-106">없는 <xref:System.ComponentModel.ToolboxItemAttribute> 로 설정 `false`;</span><span class="sxs-lookup"><span data-stu-id="46686-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="46686-107">없는 <xref:System.ComponentModel.DesignTimeVisibleAttribute> 로 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46686-108">**도구 상자** 때문에 프로젝트 솔루션에 의해 빌드되지 않은 항목을 표시 하지 것입니다 참조 체인을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46686-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="46686-109">이 연습에서는 사용자 지정 구성 요소에 자동으로 표시 방법을 **도구 상자** 빌드될 때 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="46686-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="46686-110">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46686-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="46686-111">Windows Forms 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="46686-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="46686-112">사용자 지정 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46686-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="46686-113">사용자 지정 구성 요소의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46686-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="46686-114">언로드 및 사용자 지정 구성 요소를 다시 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="46686-115">완료 했으면 확인 하 게는 **도구 상자** 사용자가 만든 구성 요소와 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="46686-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46686-116">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46686-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="46686-117">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="46686-118">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46686-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="46686-119">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="46686-119">Creating the Project</span></span>  
 <span data-ttu-id="46686-120">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46686-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="46686-121">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="46686-121">To create the project</span></span>  
  
1.  <span data-ttu-id="46686-122">`ToolboxExample`이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46686-122">Create a Windows-based application project called `ToolboxExample`.</span></span>  
  
     <span data-ttu-id="46686-123">자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46686-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="46686-124">프로젝트에 새 구성 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-124">Add a new component to the project.</span></span> <span data-ttu-id="46686-125">호출 `DemoComponent`합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-125">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="46686-126">자세한 내용은 참조 [NIB: 방법: 새 프로젝트 항목 추가](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-126">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="46686-127">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-127">Build the project.</span></span>  
  
4.  <span data-ttu-id="46686-128">**도구** 메뉴를 클릭 하 여는 **옵션** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="46686-128">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="46686-129">클릭 **일반** 아래는 **Windows Forms 디자이너** 항목을 확인 하는 **AutoToolboxPopulate** 옵션이로 설정 되어 **True**합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-129">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="46686-130">사용자 지정 구성 요소 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="46686-130">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="46686-131">다음 단계는 양식에서 사용자 지정 구성 요소의 인스턴스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46686-131">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="46686-132">때문에 **도구 상자** 자동으로 새 구성 요소에 대 한 계정을,이 다른 구성 요소 또는 컨트롤을 만드는 것도 그만큼 용이 합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-132">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="46686-133">사용자 지정 구성 요소의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="46686-133">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="46686-134">프로젝트의 폼에서 열고는 **Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-134">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="46686-135">에 **도구 상자**, 새 탭을 누릅니다 **ToolboxExample 구성 요소**합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-135">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="46686-136">이 탭을 클릭 하면 표시 됩니다 **DemoComponent**합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-136">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46686-137">성능상의 이유로 구성 요소 자동으로 채워진 영역에는 **도구 상자** 사용자 지정 비트맵을 표시 하지 않습니다 및 <xref:System.Drawing.ToolboxBitmapAttribute> 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46686-137">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="46686-138">사용자 지정 구성 요소에 대 한 아이콘을 표시 하려면는 **도구 상자**를 사용 하 여는 **도구 상자 항목 선택** 요소를 로드 하려면 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="46686-138">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="46686-139">구성 요소를 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="46686-139">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="46686-140">구성 요소의 인스턴스 만들어지고에 추가 된 **구성 요소 트레이**합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-140">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="46686-141">언로드 및 사용자 지정 구성 요소를 다시 로드</span><span class="sxs-lookup"><span data-stu-id="46686-141">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="46686-142">**도구 상자** 고려 각 구성 요소 프로젝트를 로드 하 고 프로젝트를 로드할 프로젝트의 구성 요소에 대 한 참조를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-142">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="46686-143">언로드 및 구성 요소를 다시 로드의 도구 상자에 영향을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="46686-143">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="46686-144">솔루션에서 프로젝트를 언로드하십시오.</span><span class="sxs-lookup"><span data-stu-id="46686-144">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="46686-145">프로젝트를 언로드하여에 대 한 자세한 내용은 참조 [NIB: 방법: 프로젝트 다시 로드 및 언로드](http://msdn.microsoft.com/en-us/abc0155b-8fcb-4ffc-95b6-698518a7100b)합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-145">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/en-us/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="46686-146">저장 하는 메시지가 선택 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-146">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="46686-147">새로 추가 **Windows 응용 프로그램** 프로젝트를 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="46686-147">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="46686-148">양식을 엽니다는 **디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-148">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="46686-149">**ToolboxExample 구성 요소** 탭에서 이전 프로젝트는 이제 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="46686-149">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="46686-150">다시 로드는 `ToolboxExample` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="46686-150">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="46686-151">**ToolboxExample 구성 요소** 탭 이제 다시 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="46686-151">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="46686-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="46686-152">Next Steps</span></span>  
 <span data-ttu-id="46686-153">이 연습에서는 하는 **도구 상자** 프로젝트의 구성 요소를 고려 되지만 **도구 상자** 컨트롤의 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-153">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="46686-154">추가 하 고 솔루션에서 제어 프로젝트를 제거 하 여 사용자 지정 컨트롤을 시험해 합니다.</span><span class="sxs-lookup"><span data-stu-id="46686-154">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46686-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46686-155">See Also</span></span>  
 [<span data-ttu-id="46686-156">옵션 대화 상자, Windows Forms 디자이너, 일반</span><span class="sxs-lookup"><span data-stu-id="46686-156">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="46686-157">방법: 도구 상자 탭 조작</span><span class="sxs-lookup"><span data-stu-id="46686-157">How to: Manipulate Toolbox Tabs</span></span>](http://msdn.microsoft.com/en-us/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [<span data-ttu-id="46686-158">도구 상자 항목 선택 대화 상자(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="46686-158">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="46686-159">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="46686-159">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
