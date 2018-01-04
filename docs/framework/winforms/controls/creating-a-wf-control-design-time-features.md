---
title: "연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms controls, creating
- design-time functionality [Windows Forms], Windows Forms
- DocumentDesigner class [Windows Forms]
- walkthroughs [Windows Forms], controls
ms.assetid: 6f487c59-cb38-4afa-ad2e-95edacb1d626
caps.latest.revision: "46"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7c875721436f0d6fe3f0cc57140a275e8d218f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-windows-forms-control-that-takes-advantage-of-visual-studio-design-time-features"></a><span data-ttu-id="cf0ff-102">연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-102">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>
<span data-ttu-id="cf0ff-103">연결 된 사용자 지정 디자이너를 제작 하 여 사용자 지정 컨트롤에 대 한 디자인 타임 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-103">The design-time experience for a custom control can be enhanced by authoring an associated custom designer.</span></span>  
  
 <span data-ttu-id="cf0ff-104">이 연습에서는 사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-104">This walkthrough illustrates how to create a custom designer for a custom control.</span></span> <span data-ttu-id="cf0ff-105">구현 합니다는 `MarqueeControl` 유형과 라는 연결된 된 디자이너 클래스 `MarqueeControlRootDesigner`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-105">You will implement a `MarqueeControl` type and an associated designer class, called `MarqueeControlRootDesigner`.</span></span>  
  
 <span data-ttu-id="cf0ff-106">`MarqueeControl` 형식이 극장식 움직이는 텍스트 애니메이션된 조명 깜박이 텍스트와 같은 화면 표시를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-106">The `MarqueeControl` type implements a display similar to a theater marquee, with animated lights and flashing text.</span></span>  
  
 <span data-ttu-id="cf0ff-107">이 컨트롤에 대 한 디자이너 디자인 환경 사용자 지정 디자인 타임 환경을 제공 하기 위해 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-107">The designer for this control interacts with the design environment to provide a custom design-time experience.</span></span> <span data-ttu-id="cf0ff-108">사용자 지정 디자이너를 사용 하면 사용자 지정을 어셈블할 수 `MarqueeControl` 애니메이션된 조명 및 여러 가지 조합으로 깜박이 텍스트를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-108">With the custom designer, you can assemble a custom `MarqueeControl` implementation with animated lights and flashing text in many combinations.</span></span> <span data-ttu-id="cf0ff-109">다른 Windows Forms 컨트롤 같이 폼에서 어셈블된 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-109">You can use the assembled control on a form like any other Windows Forms control.</span></span>  
  
 <span data-ttu-id="cf0ff-110">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="cf0ff-111">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-111">Creating the Project</span></span>  
  
-   <span data-ttu-id="cf0ff-112">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-112">Creating a Control Library Project</span></span>  
  
-   <span data-ttu-id="cf0ff-113">사용자 지정 컨트롤 프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="cf0ff-113">Referencing the Custom Control Project</span></span>  
  
-   <span data-ttu-id="cf0ff-114">사용자 지정 컨트롤 및 해당 사용자 지정 디자이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-114">Defining a Custom Control and Its Custom Designer</span></span>  
  
-   <span data-ttu-id="cf0ff-115">사용자 지정 컨트롤의 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-115">Creating an Instance of Your Custom Control</span></span>  
  
-   <span data-ttu-id="cf0ff-116">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-116">Setting Up the Project for Design-Time Debugging</span></span>  
  
-   <span data-ttu-id="cf0ff-117">사용자 지정 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="cf0ff-117">Implementing Your Custom Control</span></span>  
  
-   <span data-ttu-id="cf0ff-118">사용자 지정 컨트롤에 대 한 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-118">Creating a Child Control for Your Custom Control</span></span>  
  
-   <span data-ttu-id="cf0ff-119">통해 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-119">Create the MarqueeBorder Child Control</span></span>  
  
-   <span data-ttu-id="cf0ff-120">그림자 및 필터 속성에 사용자 지정 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-120">Creating a Custom Designer to Shadow and Filter Properties</span></span>  
  
-   <span data-ttu-id="cf0ff-121">구성 요소 변경 내용 처리</span><span class="sxs-lookup"><span data-stu-id="cf0ff-121">Handling Component Changes</span></span>  
  
-   <span data-ttu-id="cf0ff-122">사용자 지정 디자이너를 디자이너 동사를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-122">Adding Designer Verbs to your Custom Designer</span></span>  
  
-   <span data-ttu-id="cf0ff-123">사용자 지정 UITypeEditor 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-123">Creating a Custom UITypeEditor</span></span>  
  
-   <span data-ttu-id="cf0ff-124">디자이너에서 사용자 지정 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="cf0ff-124">Testing your Custom Control in the Designer</span></span>  
  
 <span data-ttu-id="cf0ff-125">완료 되 면 다음과 같은 사용자 지정 컨트롤 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-125">When you are finished, your custom control will look something like the following:</span></span>  
  
 <span data-ttu-id="cf0ff-126">![가능한 MarqueeControl 배치](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "항목")</span><span class="sxs-lookup"><span data-stu-id="cf0ff-126">![A possible MarqueeControl arrangement](../../../../docs/framework/winforms/controls/media/demomarqueecontrol.gif "DemoMarqueeControl")</span></span>  
  
 <span data-ttu-id="cf0ff-127">전체 코드 목록을 보려면 [하는 방법: Windows Forms 제어 하는 이점은의 디자인 타임 기능을 만드는](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-127">For the complete code listing, see [How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf0ff-128">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-128">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cf0ff-129">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-129">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cf0ff-130">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-130">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf0ff-131">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cf0ff-131">Prerequisites</span></span>  
 <span data-ttu-id="cf0ff-132">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-132">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="cf0ff-133">충분 한 권한이을 만들고 Visual Studio가 설치 된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-133">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="cf0ff-134">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-134">Creating the Project</span></span>  
 <span data-ttu-id="cf0ff-135">첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-135">The first step is to create the application project.</span></span> <span data-ttu-id="cf0ff-136">사용자 지정 컨트롤을 호스트 하는 응용 프로그램을 빌드하려면이 프로젝트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-136">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="cf0ff-137">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-137">To create the project</span></span>  
  
-   <span data-ttu-id="cf0ff-138">"MarqueeControlTest." 라는 Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-138">Create a Windows Forms Application project called "MarqueeControlTest."</span></span> <span data-ttu-id="cf0ff-139">자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-139">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="cf0ff-140">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-140">Creating a Control Library Project</span></span>  
 <span data-ttu-id="cf0ff-141">다음 단계는 컨트롤 라이브러리 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-141">The next step is to create the control library project.</span></span> <span data-ttu-id="cf0ff-142">새 사용자 지정 컨트롤 및 해당 해당 사용자 지정 디자이너를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-142">You will create a new custom control and its corresponding custom designer.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="cf0ff-143">컨트롤 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-143">To create the control library project</span></span>  
  
1.  <span data-ttu-id="cf0ff-144">Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-144">Add a Windows Forms Control Library project to the solution.</span></span> <span data-ttu-id="cf0ff-145">"MarqueeControlLibrary" 프로젝트 이름을</span><span class="sxs-lookup"><span data-stu-id="cf0ff-145">Name the project "MarqueeControlLibrary."</span></span>  
  
2.  <span data-ttu-id="cf0ff-146">사용 하 여 **솔루션 탐색기**, 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1.vb", 원본 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-146">Using **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span> <span data-ttu-id="cf0ff-147">자세한 내용은 참조 [NIB: 방법: 제거, 삭제 및 항목 제외](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-147">For more information, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
3.  <span data-ttu-id="cf0ff-148">새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-148">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="cf0ff-149">새 소스 파일 "MarqueeControl"의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-149">Give the new source file a base name of "MarqueeControl."</span></span>  
  
4.  <span data-ttu-id="cf0ff-150">사용 하 여 **솔루션 탐색기**에서 새 폴더 만들기는 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-150">Using **Solution Explorer**, create a new folder in the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="cf0ff-151">자세한 내용은 참조 [NIB: 방법: 새 프로젝트 항목 추가](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-151">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="cf0ff-152">새 폴더를 이름을 지정 "" 디자인 중"입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-152">Name the new folder "Design."</span></span>  
  
5.  <span data-ttu-id="cf0ff-153">마우스 오른쪽 단추로 클릭는 **디자인** 폴더는 새 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-153">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="cf0ff-154">소스 파일 "MarqueeControlRootDesigner"의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-154">Give the source file a base name of "MarqueeControlRootDesigner."</span></span>  
  
6.  <span data-ttu-id="cf0ff-155">System.Design 어셈블리에서 유형을 사용 하므로이에 참조를 추가 해야 합니다는 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-155">You will need to use types from the System.Design assembly, so add this reference to the `MarqueeControlLibrary` project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf0ff-156">System.Design 어셈블리를 사용 하려면 프로젝트 정식 버전의.NET Framework 클라이언트 프로필 아님.NET Framework를 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-156">To use the System.Design assembly, your project must target the full version of the .NET Framework, not the .NET Framework Client Profile.</span></span> <span data-ttu-id="cf0ff-157">대상 프레임 워크를 변경 하려면 참조 [하는 방법:.NET Framework의 버전을 대상](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-157">To change the target framework, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>  
  
## <a name="referencing-the-custom-control-project"></a><span data-ttu-id="cf0ff-158">사용자 지정 컨트롤 프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="cf0ff-158">Referencing the Custom Control Project</span></span>  
 <span data-ttu-id="cf0ff-159">사용 하 여는 `MarqueeControlTest` 프로젝트 사용자 지정 컨트롤을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-159">You will use the `MarqueeControlTest` project to test the custom control.</span></span> <span data-ttu-id="cf0ff-160">에 대 한 프로젝트 참조를 추가할 때 테스트 프로젝트 사용자 지정 컨트롤을 인식 될는 `MarqueeControlLibrary` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-160">The test project will become aware of the custom control when you add a project reference to the `MarqueeControlLibrary` assembly.</span></span>  
  
#### <a name="to-reference-the-custom-control-project"></a><span data-ttu-id="cf0ff-161">사용자 지정 컨트롤 프로젝트를 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-161">To reference the custom control project</span></span>  
  
-   <span data-ttu-id="cf0ff-162">에 `MarqueeControlTest` 프로젝트를 프로젝트 참조를 추가 `MarqueeControlLibrary` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-162">In the `MarqueeControlTest` project, add a project reference to the `MarqueeControlLibrary` assembly.</span></span> <span data-ttu-id="cf0ff-163">사용 하는 **프로젝트** 탭에 **참조 추가** 참조 하는 대신 대화 상자는 `MarqueeControlLibrary` 어셈블리를 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-163">Be sure to use the **Projects** tab in the **Add Reference** dialog box instead of referencing the `MarqueeControlLibrary` assembly directly.</span></span>  
  
## <a name="defining-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="cf0ff-164">사용자 지정 컨트롤 및 해당 사용자 지정 디자이너를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-164">Defining a Custom Control and Its Custom Designer</span></span>  
 <span data-ttu-id="cf0ff-165">사용자 지정 컨트롤에서 파생 되는 <xref:System.Windows.Forms.UserControl> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-165">Your custom control will derive from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="cf0ff-166">이렇게 하면 컨트롤이 다른 컨트롤을 포함 하 고 컨트롤이 있는 다양 한 기본 기능 제공.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-166">This allows your control to contain other controls, and it gives your control a great deal of default functionality.</span></span>  
  
 <span data-ttu-id="cf0ff-167">사용자 지정 컨트롤에 연결 된 사용자 지정 디자이너를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-167">Your custom control will have an associated custom designer.</span></span> <span data-ttu-id="cf0ff-168">이 옵션을 사용 하면 고유한 디자인 환경을 제공 사용자 지정 컨트롤에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-168">This allows you to create a unique design experience tailored specifically for your custom control.</span></span>  
  
 <span data-ttu-id="cf0ff-169">사용 하 여 컨트롤의 디자이너과 연결 된 <xref:System.ComponentModel.DesignerAttribute> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-169">You associate the control with its designer by using the <xref:System.ComponentModel.DesignerAttribute> class.</span></span> <span data-ttu-id="cf0ff-170">사용자 지정 컨트롤의 전체 디자인 타임 동작을 개발 하는 사용자 지정 디자이너 구현 됩니다는 <xref:System.ComponentModel.Design.IRootDesigner> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-170">Because you are developing the entire design-time behavior of your custom control, the custom designer will implement the <xref:System.ComponentModel.Design.IRootDesigner> interface.</span></span>  
  
#### <a name="to-define-a-custom-control-and-its-custom-designer"></a><span data-ttu-id="cf0ff-171">사용자 지정 컨트롤 및 해당 사용자 지정 디자이너를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-171">To define a custom control and its custom designer</span></span>  
  
1.  <span data-ttu-id="cf0ff-172">열기는 `MarqueeControl` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-172">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-173">파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-173">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#220)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#220)]  
  
2.  <span data-ttu-id="cf0ff-174">추가 <xref:System.ComponentModel.DesignerAttribute> 에 `MarqueeControl` 클래스 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-174">Add the <xref:System.ComponentModel.DesignerAttribute> to the `MarqueeControl` class declaration.</span></span> <span data-ttu-id="cf0ff-175">사용자 지정 컨트롤의 디자이너와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-175">This associates the custom control with its designer.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#240)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#240](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#240)]  
  
3.  <span data-ttu-id="cf0ff-176">열기는 `MarqueeControlRootDesigner` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-176">Open the `MarqueeControlRootDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-177">파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-177">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#520)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#520](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#520)]  
  
4.  <span data-ttu-id="cf0ff-178">선언을 변경 `MarqueeControlRootDesigner` 에서 상속 하는 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-178">Change the declaration of `MarqueeControlRootDesigner` to inherit from the <xref:System.Windows.Forms.Design.DocumentDesigner> class.</span></span> <span data-ttu-id="cf0ff-179">적용 된 <xref:System.ComponentModel.ToolboxItemFilterAttribute> 디자이너의 상호 작용을 지정 하는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-179">Apply the <xref:System.ComponentModel.ToolboxItemFilterAttribute> to specify the designer interaction with the **Toolbox**.</span></span>  
  
     <span data-ttu-id="cf0ff-180">**참고** 에 대 한 정의 `MarqueeControlRootDesigner` "MarqueeControlLibrary.Design." 라는 네임 스페이스에 묶여 있습니다 클래스</span><span class="sxs-lookup"><span data-stu-id="cf0ff-180">**Note** The definition for the `MarqueeControlRootDesigner` class has been enclosed in a namespace called "MarqueeControlLibrary.Design."</span></span> <span data-ttu-id="cf0ff-181">이 선언은 디자이너에에서 배치 특수 특수 네임 스페이스 디자인 관련 형식에 대 한 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-181">This declaration places the designer in a special namespace reserved for design-related types.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#530)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#530](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#530)]  
  
5.  <span data-ttu-id="cf0ff-182">생성자에 대 한 정의 `MarqueeControlRootDesigner` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-182">Define the constructor for the `MarqueeControlRootDesigner` class.</span></span> <span data-ttu-id="cf0ff-183">삽입 한 <xref:System.Diagnostics.Trace.WriteLine%2A> 생성자 본문에 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-183">Insert a <xref:System.Diagnostics.Trace.WriteLine%2A> statement in the constructor body.</span></span> <span data-ttu-id="cf0ff-184">이 디버깅 목적으로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-184">This will be useful for debugging purposes.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#540)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#540](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#540)]  
  
## <a name="creating-an-instance-of-your-custom-control"></a><span data-ttu-id="cf0ff-185">사용자 지정 컨트롤의 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-185">Creating an Instance of Your Custom Control</span></span>  
 <span data-ttu-id="cf0ff-186">폼에서 컨트롤의 인스턴스를 사용자 컨트롤의 사용자 지정 디자인 타임 동작을 관찰 정렬은 `MarqueeControlTest` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-186">To observe the custom design-time behavior of your control, you will place an instance of your control on the form in `MarqueeControlTest` project.</span></span>  
  
#### <a name="to-create-an-instance-of-your-custom-control"></a><span data-ttu-id="cf0ff-187">사용자 지정 컨트롤의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-187">To create an instance of your custom control</span></span>  
  
1.  <span data-ttu-id="cf0ff-188">새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 `MarqueeControlTest` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-188">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlTest` project.</span></span> <span data-ttu-id="cf0ff-189">새 소스 파일 "항목"의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-189">Give the new source file a base name of "DemoMarqueeControl."</span></span>  
  
2.  <span data-ttu-id="cf0ff-190">열기는 `DemoMarqueeControl` 파일에 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-190">Open the `DemoMarqueeControl` file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-191">파일 맨 위에 있는 가져오기는 `MarqueeControlLibrary` 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="cf0ff-191">At the top of the file, import the `MarqueeControlLibrary` namespace:</span></span>  
  
```vb  
Imports MarqueeControlLibrary  
```  
  
```csharp  
using MarqueeControlLibrary;  
```  
  
1.  <span data-ttu-id="cf0ff-192">선언을 변경 `DemoMarqueeControl` 에서 상속 하는 `MarqueeControl` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-192">Change the declaration of `DemoMarqueeControl` to inherit from the `MarqueeControl` class.</span></span>  
  
2.  <span data-ttu-id="cf0ff-193">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-193">Build the project.</span></span>  
  
3.  <span data-ttu-id="cf0ff-194">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-194">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="cf0ff-195">찾을 **MarqueeControlTest 구성 요소** 탭에 **도구 상자** 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-195">Find the **MarqueeControlTest Components** tab in the **Toolbox** and open it.</span></span> <span data-ttu-id="cf0ff-196">끌어서는 `DemoMarqueeControl` 에서 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-196">Drag a `DemoMarqueeControl` from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="cf0ff-197">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-197">Build the project.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="cf0ff-198">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-198">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="cf0ff-199">사용자 지정 디자인 타임 환경을 개발 하는 경우 컨트롤 및 구성 요소를 디버그 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-199">When you are developing a custom design-time experience, it will be necessary to debug your controls and components.</span></span> <span data-ttu-id="cf0ff-200">디자인 타임에 디버깅을 허용 하도록 프로젝트를 설정 하는 간단한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-200">There is a simple way to set up your project to allow debugging at design time.</span></span> <span data-ttu-id="cf0ff-201">자세한 내용은 참조 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-201">For more information, see [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="cf0ff-202">디자인 타임 디버깅을 위해 프로젝트를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-202">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="cf0ff-203">마우스 오른쪽 단추로 클릭는 `MarqueeControlLibrary` 프로젝트를 마우스 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-203">Right-click the `MarqueeControlLibrary` project and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="cf0ff-204">"MarqueeControlLibrary 속성 페이지" 대화 상자에서 선택 된 **디버그** 페이지.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-204">In the "MarqueeControlLibrary Property Pages" dialog box, select the **Debug** page.</span></span>  
  
3.  <span data-ttu-id="cf0ff-205">에 **시작 작업** 섹션에서 **시작 외부 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-205">In the **Start Action** section, select **Start External Program**.</span></span> <span data-ttu-id="cf0ff-206">됩니다. Visual Studio의 개별 인스턴스 디버깅 이므로 줄임표를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))를 Visual Studio IDE에 대 한 찾아보기 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-206">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="cf0ff-207">실행 파일의 이름이 devenv.exe를 하 고 경로 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe 기본 위치에 설치한 경우.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-207">The name of the executable file is devenv.exe, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
4.  <span data-ttu-id="cf0ff-208">대화 상자를 닫으려면 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-208">Click OK to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="cf0ff-209">마우스 오른쪽 단추로 클릭는 `MarqueeControlLibrary` 프로젝트 및 "시작 프로젝트로 설정"이 디버깅 구성을 사용 하도록 설정 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-209">Right-click the `MarqueeControlLibrary` project and select "Set as StartUp Project" to enable this debugging configuration.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="cf0ff-210">검사점</span><span class="sxs-lookup"><span data-stu-id="cf0ff-210">Checkpoint</span></span>  
 <span data-ttu-id="cf0ff-211">이제 사용자 지정 컨트롤의 디자인 타임 동작을 디버그 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-211">You are now ready to debug the design-time behavior of your custom control.</span></span> <span data-ttu-id="cf0ff-212">디버깅 환경 올바르게 설정 되어 있는지를 확인 한 후에 사용자 지정 컨트롤 및 사용자 지정 디자이너 간의 연결을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-212">Once you have determined that the debugging environment is set up correctly, you will test the association between the custom control and the custom designer.</span></span>  
  
#### <a name="to-test-the-debugging-environment-and-the-designer-association"></a><span data-ttu-id="cf0ff-213">디버깅 환경 및 디자이너 연결을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-213">To test the debugging environment and the designer association</span></span>  
  
1.  <span data-ttu-id="cf0ff-214">열기는 `MarqueeControlRootDesigner` 소스 파일에는 **코드 편집기** 중단점을 설정 하 고는 <xref:System.Diagnostics.Trace.WriteLine%2A> 문.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-214">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and place a breakpoint on the <xref:System.Diagnostics.Trace.WriteLine%2A> statement.</span></span>  
  
2.  <span data-ttu-id="cf0ff-215">F5 키를 눌러 디버깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-215">Press F5 to start the debugging session.</span></span> <span data-ttu-id="cf0ff-216">Note Visual Studio의 새 인스턴스가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-216">Note that a new instance of Visual Studio is created.</span></span>  
  
3.  <span data-ttu-id="cf0ff-217">Visual Studio의 새 인스턴스를 "MarqueeControlTest" 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-217">In the new instance of Visual Studio, open the "MarqueeControlTest" solution.</span></span> <span data-ttu-id="cf0ff-218">선택 하 여 솔루션을 쉽게 찾을 **최근에 사용한 프로젝트** 에서 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-218">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="cf0ff-219">가장 최근에 사용 된 대로 "MarqueeControlTest.sln" 솔루션 파일을 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-219">The "MarqueeControlTest.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="cf0ff-220">열기는 `DemoMarqueeControl` 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-220">Open the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="cf0ff-221">Visual Studio의 디버깅 인스턴스에 포커스를 획득 하 고 중단점에서 실행이 중지 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-221">Note that the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="cf0ff-222">F5 키를 눌러 디버깅 세션을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-222">Press F5 to continue the debugging session.</span></span>  
  
 <span data-ttu-id="cf0ff-223">이 시점에서 모든 항목은에서 개발 하 고 사용자 지정 컨트롤 및 연결된 된 사용자 지정 디자이너를 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-223">At this point, everything is in place for you to develop and debug your custom control and its associated custom designer.</span></span> <span data-ttu-id="cf0ff-224">이 연습의 나머지 부분에서는의 디자이너 및 컨트롤의 기능을 구현 세부 사항을 중점적으로 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-224">The remainder of this walkthrough will concentrate on the details of implementing features of the control and the designer.</span></span>  
  
## <a name="implementing-your-custom-control"></a><span data-ttu-id="cf0ff-225">사용자 지정 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="cf0ff-225">Implementing Your Custom Control</span></span>  
 <span data-ttu-id="cf0ff-226">`MarqueeControl` 은 한 <xref:System.Windows.Forms.UserControl> 와 약간의 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-226">The `MarqueeControl` is a <xref:System.Windows.Forms.UserControl> with a little bit of customization.</span></span> <span data-ttu-id="cf0ff-227">두 개의 메서드를 노출: `Start`, 움직이는 텍스트 애니메이션을 시작 하 고 `Stop`, 애니메이션을 중지 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-227">It exposes two methods: `Start`, which starts the marquee animation, and `Stop`, which stops the animation.</span></span> <span data-ttu-id="cf0ff-228">때문에 `MarqueeControl` 구현 하는 자식 컨트롤을 포함는 `IMarqueeWidget` 인터페이스를 `Start` 및 `Stop` 각 자식 컨트롤과 호출 열거는 `StartMarquee` 및 `StopMarquee` 메서드, 각 자식 컨트롤에 각각 구현 하는 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-228">Because the `MarqueeControl` contains child controls that implement the `IMarqueeWidget` interface, `Start` and `Stop` enumerate each child control and call the `StartMarquee` and `StopMarquee` methods, respectively, on each child control that implements `IMarqueeWidget`.</span></span>  
  
 <span data-ttu-id="cf0ff-229">모양을 `MarqueeBorder` 및 `MarqueeText` 컨트롤의 레이아웃에 따라 달라 집니다. 하므로 `MarqueeControl` 재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 메서드 및 호출 <xref:System.Windows.Forms.Control.PerformLayout%2A> 이 형식의 자식 컨트롤에 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-229">The appearance of the `MarqueeBorder` and `MarqueeText` controls is dependent on the layout, so `MarqueeControl` overrides the <xref:System.Windows.Forms.Control.OnLayout%2A> method and calls <xref:System.Windows.Forms.Control.PerformLayout%2A> on child controls of this type.</span></span>  
  
 <span data-ttu-id="cf0ff-230">이 범위는 `MarqueeControl` 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-230">This is the extent of the `MarqueeControl` customizations.</span></span> <span data-ttu-id="cf0ff-231">런타임 기능에서 구현 되는 `MarqueeBorder` 및 `MarqueeText` 컨트롤 및 디자인 타임 기능에서 구현 되는 `MarqueeBorderDesigner` 및 `MarqueeControlRootDesigner` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-231">The run-time features are implemented by the `MarqueeBorder` and `MarqueeText` controls, and the design-time features are implemented by the `MarqueeBorderDesigner` and `MarqueeControlRootDesigner` classes.</span></span>  
  
#### <a name="to-implement-your-custom-control"></a><span data-ttu-id="cf0ff-232">사용자 지정 컨트롤을 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-232">To implement your custom control</span></span>  
  
1.  <span data-ttu-id="cf0ff-233">열기는 `MarqueeControl` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-233">Open the `MarqueeControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-234">구현 된 `Start` 및 `Stop` 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-234">Implement the `Start` and `Stop` methods.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#260)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#260](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#260)]  
  
2.  <span data-ttu-id="cf0ff-235"><xref:System.Windows.Forms.Control.OnLayout%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-235">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrol.cs#270)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#270](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrol.vb#270)]  
  
## <a name="creating-a-child-control-for-your-custom-control"></a><span data-ttu-id="cf0ff-236">사용자 지정 컨트롤에 대 한 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-236">Creating a Child Control for Your Custom Control</span></span>  
 <span data-ttu-id="cf0ff-237">`MarqueeControl` 두 종류의 자식 컨트롤을 호스팅할:는 `MarqueeBorder` 제어 및 `MarqueeText` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-237">The `MarqueeControl` will host two kinds of child control: the `MarqueeBorder` control and the `MarqueeText` control.</span></span>  
  
-   <span data-ttu-id="cf0ff-238">`MarqueeBorder`:이 컨트롤의 가장자리 주위 "lights"의 테두리를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-238">`MarqueeBorder`: This control paints a border of "lights" around its edges.</span></span> <span data-ttu-id="cf0ff-239">조명을 없으므로 테두리 이동할 것 표시 순서 대로 플래시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-239">The lights flash in sequence, so they appear to be moving around the border.</span></span> <span data-ttu-id="cf0ff-240">조명을 깜박이 속도 라는 속성에 의해 제어 됩니다 `UpdatePeriod`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-240">The speed at which the lights flash is controlled by a property called `UpdatePeriod`.</span></span> <span data-ttu-id="cf0ff-241">다른 몇 가지 사용자 지정 속성은 컨트롤의 모양의 다른 측면을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-241">Several other custom properties determine other aspects of the control's appearance.</span></span> <span data-ttu-id="cf0ff-242">라는 메서드가 2 개 `StartMarquee` 및 `StopMarquee`, 애니메이션의 시작 및 중지 시기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-242">Two methods, called `StartMarquee` and `StopMarquee`, control when the animation starts and stops.</span></span>  
  
-   <span data-ttu-id="cf0ff-243">`MarqueeText`:이 컨트롤은 깜박이 문자열을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-243">`MarqueeText`: This control paints a flashing string.</span></span> <span data-ttu-id="cf0ff-244">마찬가지로 `MarqueeBorder` 컨트롤, 텍스트 깜박이 속도 의해 제어 됩니다는 `UpdatePeriod` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-244">Like the `MarqueeBorder` control, the speed at which the text flashes is controlled by the `UpdatePeriod` property.</span></span> <span data-ttu-id="cf0ff-245">`MarqueeText` 컨트롤에는 `StartMarquee` 및 `StopMarquee` 공통 된 메서드는 `MarqueeBorder` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-245">The `MarqueeText` control also has the `StartMarquee` and `StopMarquee` methods in common with the `MarqueeBorder` control.</span></span>  
  
 <span data-ttu-id="cf0ff-246">디자인 타임에는 `MarqueeControlRootDesigner` 이러한 두 가지 컨트롤 형식에 추가할 수 있습니다는 `MarqueeControl` 의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-246">At design time, the `MarqueeControlRootDesigner` allows these two control types to be added to a `MarqueeControl` in any combination.</span></span>  
  
 <span data-ttu-id="cf0ff-247">두 컨트롤의 일반적인 기능 이라는 인터페이스로 분석 되어 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-247">Common features of the two controls are factored into an interface called `IMarqueeWidget`.</span></span> <span data-ttu-id="cf0ff-248">이 통해는 `MarqueeControl` 을 움직이는 텍스트와 관련 된 자식 컨트롤을 찾아 특별 한 처리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-248">This allows the `MarqueeControl` to discover any Marquee-related child controls and give them special treatment.</span></span>  
  
 <span data-ttu-id="cf0ff-249">주기적인 애니메이션 기능을 구현 하려면 사용할 <xref:System.ComponentModel.BackgroundWorker> 에서 개체는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-249">To implement the periodic animation feature, you will use <xref:System.ComponentModel.BackgroundWorker> objects from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="cf0ff-250">사용할 수 있습니다 <xref:System.Windows.Forms.Timer> 개체 있지만 많은 `IMarqueeWidget` 개체가 단일 UI 스레드에서 애니메이션을 지속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-250">You could use <xref:System.Windows.Forms.Timer> objects, but when many `IMarqueeWidget` objects are present, the single UI thread may be unable to keep up with the animation.</span></span>  
  
#### <a name="to-create-a-child-control-for-your-custom-control"></a><span data-ttu-id="cf0ff-251">사용자 지정 컨트롤에 대 한 자식 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-251">To create a child control for your custom control</span></span>  
  
1.  <span data-ttu-id="cf0ff-252">새 클래스 항목을 추가 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-252">Add a new class item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="cf0ff-253">새 소스 파일 "IMarqueeWidget"의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-253">Give the new source file a base name of "IMarqueeWidget."</span></span>  
  
2.  <span data-ttu-id="cf0ff-254">열기는 `IMarqueeWidget` 소스 파일에는 **코드 편집기** 에서 선언을 변경 하 고 `class` 를 `interface`:</span><span class="sxs-lookup"><span data-stu-id="cf0ff-254">Open the `IMarqueeWidget` source file in the **Code Editor** and change the declaration from `class` to `interface`:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#2)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#2)]  
  
3.  <span data-ttu-id="cf0ff-255">다음 코드를 추가 하는 `IMarqueeWidget` 조작할 움직이는 텍스트 애니메이션 하는 속성을 두 개의 메서드를 노출 하는 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="cf0ff-255">Add the following code to the `IMarqueeWidget` interface to expose two methods and a property that manipulate the marquee animation:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/imarqueewidget.cs#3)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/imarqueewidget.vb#3)]  
  
4.  <span data-ttu-id="cf0ff-256">새로 추가 **사용자 지정 컨트롤** 항목의 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-256">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="cf0ff-257">새 소스 파일 "통해"의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-257">Give the new source file a base name of "MarqueeText."</span></span>  
  
5.  <span data-ttu-id="cf0ff-258">끌어서는 <xref:System.ComponentModel.BackgroundWorker> 에서 구성 요소는 **도구 상자** 에 프로그램 `MarqueeText` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-258">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeText` control.</span></span> <span data-ttu-id="cf0ff-259">이 구성에서 `MarqueeText` 요소를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-259">This component will allow the `MarqueeText` control to update itself asynchronously.</span></span>  
  
6.  <span data-ttu-id="cf0ff-260">속성 창에서 설정 된 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgess` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-260">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgess` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="cf0ff-261">이러한 설정을 사용 하는 <xref:System.ComponentModel.BackgroundWorker> 주기적으로 발생 하는 구성 요소는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 고 작업을 비동기 업데이트를 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-261">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="cf0ff-262">자세한 내용은 참조 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-262">For more information, see [BackgroundWorker Component](../../../../docs/framework/winforms/controls/backgroundworker-component.md).</span></span>  
  
7.  <span data-ttu-id="cf0ff-263">열기는 `MarqueeText` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-263">Open the `MarqueeText` source file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-264">파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-264">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#120)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#120)]  
  
8.  <span data-ttu-id="cf0ff-265">선언을 변경 `MarqueeText` 상속할 <xref:System.Windows.Forms.Label> 및 구현 하는 `IMarqueeWidget` 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="cf0ff-265">Change the declaration of `MarqueeText` to inherit from <xref:System.Windows.Forms.Label> and to implement the `IMarqueeWidget` interface:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#130)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#130)]  
  
9. <span data-ttu-id="cf0ff-266">노출된 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-266">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span> <span data-ttu-id="cf0ff-267">`isLit` 필드 텍스트에 지정 된 색에 그릴 수 있는지 여부를 결정은 `LightColor` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-267">The `isLit` field determines if the text is to be painted in the color given by the `LightColor` property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#140)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#140)]  
  
10. <span data-ttu-id="cf0ff-268">`IMarqueeWidget` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-268">Implement the `IMarqueeWidget` interface.</span></span>  
  
     <span data-ttu-id="cf0ff-269">`StartMarquee` 및 `StopMarquee` 메서드 호출는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 메서드 시작 하 고 애니메이션을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-269">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>  
  
     <span data-ttu-id="cf0ff-270"><xref:System.ComponentModel.CategoryAttribute.Category%2A> 및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성에 적용 되는 `UpdatePeriod` "움직이는 텍스트입니다." 라는 속성 창의 사용자 지정 섹션에 나타나는 속성</span><span class="sxs-lookup"><span data-stu-id="cf0ff-270">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to the `UpdatePeriod` property so it appears in a custom section of the Properties window called "Marquee."</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#150)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#150)]  
  
11. <span data-ttu-id="cf0ff-271">속성 접근자를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-271">Implement the property accessors.</span></span> <span data-ttu-id="cf0ff-272">클라이언트에 두 개의 속성을 노출 합니다: `LightColor` 및 `DarkColor`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-272">You will expose two properties to clients: `LightColor` and `DarkColor`.</span></span> <span data-ttu-id="cf0ff-273"><xref:System.ComponentModel.CategoryAttribute.Category%2A> 및 <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> 특성이 속성이 속성 창 "움직이는 텍스트입니다." 라는 사용자 지정 섹션에 표시 되므로 이러한 속성에 적용 됩니다</span><span class="sxs-lookup"><span data-stu-id="cf0ff-273">The <xref:System.ComponentModel.CategoryAttribute.Category%2A> and <xref:System.ComponentModel.BrowsableAttribute.Browsable%2A> attributes are applied to these properties, so the properties appear in a custom section of the Properties window called "Marquee."</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#160)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#160)]  
  
12. <span data-ttu-id="cf0ff-274">구현에 대 한 처리기는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-274">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
     <span data-ttu-id="cf0ff-275"><xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에 지정 된 밀리초 수에 대 한 대기 `UpdatePeriod` 발생 하는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 코드를 호출 하 여 애니메이션 중지 될 때까지 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-275">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>  
  
     <span data-ttu-id="cf0ff-276"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기에 밝은 영역과 어두운 상태로 깜박임의 나타내기 위해 텍스트 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-276">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler toggles the text between its light and dark state to give the appearance of flashing.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#180)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#180)]  
  
13. <span data-ttu-id="cf0ff-277">재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 애니메이션을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-277">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method to enable the animation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueetext.cs#170)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueetext.vb#170)]  
  
14. <span data-ttu-id="cf0ff-278">F6 키를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-278">Press F6 to build the solution.</span></span>  
  
## <a name="create-the-marqueeborder-child-control"></a><span data-ttu-id="cf0ff-279">통해 자식 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-279">Create the MarqueeBorder Child Control</span></span>  
 <span data-ttu-id="cf0ff-280">`MarqueeBorder` 컨트롤은 보다 약간 더 복잡는 `MarqueeText` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-280">The `MarqueeBorder` control is slightly more sophisticated than the `MarqueeText` control.</span></span> <span data-ttu-id="cf0ff-281">에 더 많은 속성 및에서 애니메이션의 <xref:System.Windows.Forms.Control.OnPaint%2A> 방법은 조금 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-281">It has more properties and the animation in the <xref:System.Windows.Forms.Control.OnPaint%2A> method is more involved.</span></span> <span data-ttu-id="cf0ff-282">원칙적으로 유사 하지만는 `MarqueeText` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-282">In principle, it is quite similar to the `MarqueeText` control.</span></span>  
  
 <span data-ttu-id="cf0ff-283">때문에 `MarqueeBorder` 컨트롤에 자식 컨트롤이 있을 수 있습니다, 알고 있어야 하는 데 필요한 <xref:System.Windows.Forms.Control.Layout> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-283">Because the `MarqueeBorder` control can have child controls, it needs to be aware of <xref:System.Windows.Forms.Control.Layout> events.</span></span>  
  
#### <a name="to-create-the-marqueeborder-control"></a><span data-ttu-id="cf0ff-284">통해를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-284">To create the MarqueeBorder control</span></span>  
  
1.  <span data-ttu-id="cf0ff-285">새로 추가 **사용자 지정 컨트롤** 항목의 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-285">Add a new **Custom Control** item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="cf0ff-286">새 소스 파일 "통해"의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-286">Give the new source file a base name of "MarqueeBorder."</span></span>  
  
2.  <span data-ttu-id="cf0ff-287">끌어서는 <xref:System.ComponentModel.BackgroundWorker> 에서 구성 요소는 **도구 상자** 에 프로그램 `MarqueeBorder` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-287">Drag a <xref:System.ComponentModel.BackgroundWorker> component from the **Toolbox** onto your `MarqueeBorder` control.</span></span> <span data-ttu-id="cf0ff-288">이 구성에서 `MarqueeBorder` 요소를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-288">This component will allow the `MarqueeBorder` control to update itself asynchronously.</span></span>  
  
3.  <span data-ttu-id="cf0ff-289">속성 창에서 설정 된 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 `WorkerReportsProgess` 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-289">In the Properties window, set the <xref:System.ComponentModel.BackgroundWorker> component's `WorkerReportsProgess` and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span> <span data-ttu-id="cf0ff-290">이러한 설정을 사용 하는 <xref:System.ComponentModel.BackgroundWorker> 주기적으로 발생 하는 구성 요소는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 고 작업을 비동기 업데이트를 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-290">These settings allow the <xref:System.ComponentModel.BackgroundWorker> component to periodically raise the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event and to cancel asynchronous updates.</span></span> <span data-ttu-id="cf0ff-291">자세한 내용은 참조 [BackgroundWorker 구성 요소](../../../../docs/framework/winforms/controls/backgroundworker-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-291">For more information, see [BackgroundWorker Component](../../../../docs/framework/winforms/controls/backgroundworker-component.md).</span></span>  
  
4.  <span data-ttu-id="cf0ff-292">속성 창의 이벤트 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-292">In the Properties window, click the Events button.</span></span> <span data-ttu-id="cf0ff-293">연결에 대 한 처리기는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-293">Attach handlers for the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
5.  <span data-ttu-id="cf0ff-294">열기는 `MarqueeBorder` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-294">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-295">파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-295">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#20)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#20)]  
  
6.  <span data-ttu-id="cf0ff-296">선언을 변경 `MarqueeBorder` 상속할 <xref:System.Windows.Forms.Panel> 및 구현 하는 `IMarqueeWidget` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-296">Change the declaration of `MarqueeBorder` to inherit from <xref:System.Windows.Forms.Panel> and to implement the `IMarqueeWidget` interface.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#30)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#30)]  
  
7.  <span data-ttu-id="cf0ff-297">관리 하기 위한 두 개의 열거형 선언는 `MarqueeBorder` 컨트롤의 상태가: `MarqueeSpinDirection`는 조명 "회전" 테두리는 방향을 결정 하 및 `MarqueeLightShape`, (사각형 또는 순환) 광원의 모양을 결정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-297">Declare two enumerations for managing the `MarqueeBorder` control's state: `MarqueeSpinDirection`, which determines the direction in which the lights "spin" around the border, and `MarqueeLightShape`, which determines the shape of the lights (square or circular).</span></span> <span data-ttu-id="cf0ff-298">이러한 선언을 `MarqueeBorder` 클래스 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-298">Place these declarations before the `MarqueeBorder` class declaration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#97)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#97](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#97)]  
  
8.  <span data-ttu-id="cf0ff-299">노출된 된 속성에 해당 하는 인스턴스 변수를 선언 하 고 생성자에서 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-299">Declare the instance variables that correspond to the exposed properties, and initialize them in the constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#40)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#40)]  
  
9. <span data-ttu-id="cf0ff-300">`IMarqueeWidget` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-300">Implement the `IMarqueeWidget` interface.</span></span>  
  
     <span data-ttu-id="cf0ff-301">`StartMarquee` 및 `StopMarquee` 메서드 호출는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 및 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 메서드 시작 하 고 애니메이션을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-301">The `StartMarquee` and `StopMarquee` methods invoke the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> and <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> methods to start and stop the animation.</span></span>  
  
     <span data-ttu-id="cf0ff-302">때문에 `MarqueeBorder` 컨트롤에는 자식 컨트롤을 포함할 수는 `StartMarquee` 메서드 열거 모든 자식 컨트롤을 호출 `StartMarquee` 에 구현 하는 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-302">Because the `MarqueeBorder` control can contain child controls, the `StartMarquee` method enumerates all child controls and calls `StartMarquee` on those that implement `IMarqueeWidget`.</span></span> <span data-ttu-id="cf0ff-303">`StopMarquee` 메서드에 구현 방법이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-303">The `StopMarquee` method has a similar implementation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#50)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#50)]  
  
10. <span data-ttu-id="cf0ff-304">속성 접근자를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-304">Implement the property accessors.</span></span> <span data-ttu-id="cf0ff-305">`MarqueeBorder` 컨트롤에 모양을 제어 하기 위한 몇 가지 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-305">The `MarqueeBorder` control has several properties for controlling its appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#60)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#60)]  
  
11. <span data-ttu-id="cf0ff-306">구현에 대 한 처리기는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-306">Implement the handlers for the <xref:System.ComponentModel.BackgroundWorker> component's <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> events.</span></span>  
  
     <span data-ttu-id="cf0ff-307"><xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기에 지정 된 밀리초 수에 대 한 대기 `UpdatePeriod` 발생 하는 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 코드를 호출 하 여 애니메이션 중지 될 때까지 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-307">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler sleeps for the number of milliseconds specified by `UpdatePeriod` then raises the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event, until your code stops the animation by calling <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A>.</span></span>  
  
     <span data-ttu-id="cf0ff-308"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기는 다른 조명의 밝기 상태 확인 되 "기본" 밝은 테마와 호출의 위치를 증가 시킵니다.는 <xref:System.Windows.Forms.Control.Refresh%2A> 메서드를 누르면 컨트롤이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-308">The <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler increments the position of the "base" light, from which the light/dark state of the other lights is determined, and calls the <xref:System.Windows.Forms.Control.Refresh%2A> method to cause the control to repaint itself.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#90)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#90](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#90)]  
  
12. <span data-ttu-id="cf0ff-309">도우미 메서드를 구현 `IsLit` 및 `DrawLight`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-309">Implement the helper methods, `IsLit` and `DrawLight`.</span></span>  
  
     <span data-ttu-id="cf0ff-310">`IsLit` 메서드는 지정 된 위치의 광원의 색을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-310">The `IsLit` method determines the color of a light at a given position.</span></span> <span data-ttu-id="cf0ff-311">에 지정 된 색으로 "켜져" lights 그려집니다는 `LightColor` 속성을 "어두운" 되는 것에 지정 된 색에 그려집니다는 `DarkColor` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-311">Lights that are "lit" are drawn in the color given by the `LightColor` property, and those that are "dark" are drawn in the color given by the `DarkColor` property.</span></span>  
  
     <span data-ttu-id="cf0ff-312">`DrawLight` 메서드 적절 한 색, 모양 및 위치를 사용 하 여 빛을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-312">The `DrawLight` method draws a light using the appropriate color, shape, and position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#80)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#80](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#80)]  
  
13. <span data-ttu-id="cf0ff-313">재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 및 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-313">Override the <xref:System.Windows.Forms.Control.OnLayout%2A> and <xref:System.Windows.Forms.Control.OnPaint%2A> methods.</span></span>  
  
     <span data-ttu-id="cf0ff-314"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드의 가장자리를 따라 조명을 `MarqueeBorder` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-314">The <xref:System.Windows.Forms.Control.OnPaint%2A> method draws the lights along the edges of the `MarqueeBorder` control.</span></span>  
  
     <span data-ttu-id="cf0ff-315">때문에 <xref:System.Windows.Forms.Control.OnPaint%2A> 방법은의 크기에 따라 달라 집니다는 `MarqueeBorder` 레이아웃 변경 될 때마다 호출 해야 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-315">Because the <xref:System.Windows.Forms.Control.OnPaint%2A> method depends on the dimensions of the `MarqueeBorder` control, you need to call it whenever the layout changes.</span></span> <span data-ttu-id="cf0ff-316">이를 위해 재정의 <xref:System.Windows.Forms.Control.OnLayout%2A> 호출 <xref:System.Windows.Forms.Control.Refresh%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-316">To achieve this, override <xref:System.Windows.Forms.Control.OnLayout%2A> and call <xref:System.Windows.Forms.Control.Refresh%2A>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#70)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#70)]  
  
## <a name="creating-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="cf0ff-317">그림자 및 필터 속성에 사용자 지정 디자이너 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-317">Creating a Custom Designer to Shadow and Filter Properties</span></span>  
 <span data-ttu-id="cf0ff-318">`MarqueeControlRootDesigner` 루트 디자이너에 대 한 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-318">The `MarqueeControlRootDesigner` class provides the implementation for the root designer.</span></span> <span data-ttu-id="cf0ff-319">작동 하는 외에도이 디자이너는 `MarqueeControl`, 특히 연결 된 사용자 지정 디자이너를 해야 합니다는 `MarqueeBorder` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-319">In addition to this designer, which operates on the `MarqueeControl`, you will need a custom designer that is specifically associated with the `MarqueeBorder` control.</span></span> <span data-ttu-id="cf0ff-320">이 디자이너는 사용자 지정 루트 디자이너의 컨텍스트에서 적절 한 사용자 지정 동작을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-320">This designer provides custom behavior that is appropriate in the context of the custom root designer.</span></span>  
  
 <span data-ttu-id="cf0ff-321">특히,는 `MarqueeBorderDesigner` "그림자" 되며에서 특정 속성을 필터링 하는 `MarqueeBorder` 컨트롤을 디자인 환경와의 상호 작용을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-321">Specifically, the `MarqueeBorderDesigner` will "shadow" and filter certain properties on the `MarqueeBorder` control, changing their interaction with the design environment.</span></span>  
  
 <span data-ttu-id="cf0ff-322">"숨김"으로 알려져 구성 요소의 속성 접근자에 대 한 호출을 가로채</span><span class="sxs-lookup"><span data-stu-id="cf0ff-322">Intercepting calls to a component's property accessor is known as "shadowing."</span></span> <span data-ttu-id="cf0ff-323">하면 디자이너는 사용자가 설정한 값을 추적 하 고 필요에 따라 디자인 하 고 구성 요소에 해당 값을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-323">It allows a designer to track the value set by the user and optionally pass that value to the component being designed.</span></span>  
  
 <span data-ttu-id="cf0ff-324">이 예는 <xref:System.Windows.Forms.Control.Visible%2A> 및 <xref:System.Windows.Forms.Control.Enabled%2A> 속성에 의해 숨겨질 수는 `MarqueeBorderDesigner`, 과정에서 사용자를 방지 하는 `MarqueeBorder` 보이지 않는 또는 디자인 타임 동안 비활성화 된 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-324">For this example, the <xref:System.Windows.Forms.Control.Visible%2A> and <xref:System.Windows.Forms.Control.Enabled%2A> properties will be shadowed by the `MarqueeBorderDesigner`, which prevents the user from making the `MarqueeBorder` control invisible or disabled during design time.</span></span>  
  
 <span data-ttu-id="cf0ff-325">또한 디자이너 추가 하 고 속성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-325">Designers can also add and remove properties.</span></span> <span data-ttu-id="cf0ff-326">이 예는 <xref:System.Windows.Forms.Control.Padding%2A> 디자인 타임에 속성을 제거할 수는 `MarqueeBorder` 로 지정 된 광원의 크기에 따라 있는 안쪽 여백을 프로그래밍 방식으로 설정 하는 컨트롤은 `LightSize` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-326">For this example, the <xref:System.Windows.Forms.Control.Padding%2A> property will be removed at design time, because the `MarqueeBorder` control programmatically sets the padding based on the size of the lights specified by the `LightSize` property.</span></span>  
  
 <span data-ttu-id="cf0ff-327">에 대 한 기본 클래스 `MarqueeBorderDesigner` 은 <xref:System.ComponentModel.Design.ComponentDesigner>, 특성, 속성 및 디자인 타임에 컨트롤에서 노출 하는 이벤트를 변경할 수 있는 메서드가 있는:</span><span class="sxs-lookup"><span data-stu-id="cf0ff-327">The base class for `MarqueeBorderDesigner` is <xref:System.ComponentModel.Design.ComponentDesigner>, which has methods that can change the attributes, properties, and events exposed by a control at design time:</span></span>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterProperties%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterAttributes%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterEvents%2A>  
  
-   <xref:System.ComponentModel.Design.ComponentDesigner.PostFilterEvents%2A>  
  
 <span data-ttu-id="cf0ff-328">이러한 메서드를 사용 하는 구성 요소의 공용 인터페이스를 변경할 때는 이러한 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-328">When changing the public interface of a component using these methods, you must follow these rules:</span></span>  
  
-   <span data-ttu-id="cf0ff-329">에 항목 추가 또는 제거는 `PreFilter` 만 메서드</span><span class="sxs-lookup"><span data-stu-id="cf0ff-329">Add or remove items in the `PreFilter` methods only</span></span>  
  
-   <span data-ttu-id="cf0ff-330">기존 항목을 수정할는 `PostFilter` 만 메서드</span><span class="sxs-lookup"><span data-stu-id="cf0ff-330">Modify existing items in the `PostFilter` methods only</span></span>  
  
-   <span data-ttu-id="cf0ff-331">항상 기본 구현을 먼저 호출는 `PreFilter` 메서드</span><span class="sxs-lookup"><span data-stu-id="cf0ff-331">Always call the base implementation first in the `PreFilter` methods</span></span>  
  
-   <span data-ttu-id="cf0ff-332">항상 기본 구현을 마지막는 `PostFilter` 메서드</span><span class="sxs-lookup"><span data-stu-id="cf0ff-332">Always call the base implementation last in the `PostFilter` methods</span></span>  
  
 <span data-ttu-id="cf0ff-333">이러한 규칙을 따르는에서는 디자인 타임 환경에서 모든 디자이너의 모든 구성 요소를 디자인 하 고 일관 된 보기 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-333">Adhering to these rules ensures that all designers in the design-time environment have a consistent view of all components being designed.</span></span>  
  
 <span data-ttu-id="cf0ff-334"><xref:System.ComponentModel.Design.ComponentDesigner> 클래스 특정 인스턴스 변수를 만들 필요는 섀도 처리 된 속성의 값을 관리 하기 위한 사전을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-334">The <xref:System.ComponentModel.Design.ComponentDesigner> class provides a dictionary for managing the values of shadowed properties, which relieves you of the need to create specific instance variables.</span></span>  
  
#### <a name="to-create-a-custom-designer-to-shadow-and-filter-properties"></a><span data-ttu-id="cf0ff-335">그림자 및 필터 속성을 사용자 지정 디자이너를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-335">To create a custom designer to shadow and filter properties</span></span>  
  
1.  <span data-ttu-id="cf0ff-336">마우스 오른쪽 단추로 클릭는 **디자인** 폴더는 새 클래스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-336">Right-click the **Design** folder and add a new class.</span></span> <span data-ttu-id="cf0ff-337">소스 파일 "MarqueeBorderDesigner"의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-337">Give the source file a base name of "MarqueeBorderDesigner."</span></span>  
  
2.  <span data-ttu-id="cf0ff-338">열기는 `MarqueeBorderDesigner` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-338">Open the `MarqueeBorderDesigner` source file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-339">파일 맨 위에 있는 다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-339">At the top of the file, import the following namespaces:</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#420)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#420](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#420)]  
  
3.  <span data-ttu-id="cf0ff-340">선언을 변경 `MarqueeBorderDesigner` 상속할 <xref:System.Windows.Forms.Design.ParentControlDesigner>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-340">Change the declaration of `MarqueeBorderDesigner` to inherit from <xref:System.Windows.Forms.Design.ParentControlDesigner>.</span></span>  
  
     <span data-ttu-id="cf0ff-341">때문에 `MarqueeBorder` 컨트롤에는 자식 컨트롤을 포함할 수 `MarqueeBorderDesigner` 에서 상속 <xref:System.Windows.Forms.Design.ParentControlDesigner>, 부모-자식 상호 작용을 처리 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-341">Because the `MarqueeBorder` control can contain child controls, `MarqueeBorderDesigner` inherits from <xref:System.Windows.Forms.Design.ParentControlDesigner>, which handles the parent-child interaction.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#430)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#430](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#430)]  
  
4.  <span data-ttu-id="cf0ff-342">기본 구현을 재정의 <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-342">Override the base implementation of <xref:System.ComponentModel.Design.ComponentDesigner.PreFilterProperties%2A>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#450)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#450](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#450)]  
  
5.  <span data-ttu-id="cf0ff-343"><xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A> 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-343">Implement the <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A> properties.</span></span> <span data-ttu-id="cf0ff-344">이러한 구현은 컨트롤의 속성을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-344">These implementations shadow the control's properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborderdesigner.cs#440)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#440](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborderdesigner.vb#440)]  
  
## <a name="handling-component-changes"></a><span data-ttu-id="cf0ff-345">구성 요소 변경 내용 처리</span><span class="sxs-lookup"><span data-stu-id="cf0ff-345">Handling Component Changes</span></span>  
 <span data-ttu-id="cf0ff-346">`MarqueeControlRootDesigner` 클래스에 대 한 사용자 지정 디자인 타임 환경을 제공 프로그램 `MarqueeControl` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-346">The `MarqueeControlRootDesigner` class provides the custom design-time experience for your `MarqueeControl` instances.</span></span> <span data-ttu-id="cf0ff-347">대부분의 디자인 타임 기능이에서 상속 되는 <xref:System.Windows.Forms.Design.DocumentDesigner> 클래스 하므로 두 개의 특정 사용자 지정을 구현 하 여 코드에서: 구성 요소 변경 내용을 처리 하 고 디자이너 동사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-347">Most of the design-time functionality is inherited from the <xref:System.Windows.Forms.Design.DocumentDesigner> class; your code will implement two specific customizations: handling component changes, and adding designer verbs.</span></span>  
  
 <span data-ttu-id="cf0ff-348">사용자가 디자인으로 자신의 `MarqueeControl` 인스턴스, 루트 디자이너의 변경 내용을 추적 하는 `MarqueeControl` 및 해당 자식 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-348">As users design their `MarqueeControl` instances, your root designer will track changes to the `MarqueeControl` and its child controls.</span></span> <span data-ttu-id="cf0ff-349">편리 하 게 서비스를 제공 하는 디자인 타임 환경 <xref:System.ComponentModel.Design.IComponentChangeService>구성 요소의 상태 변경 사항 추적에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-349">The design-time environment offers a convenient service, <xref:System.ComponentModel.Design.IComponentChangeService>, for tracking changes to component state.</span></span>  
  
 <span data-ttu-id="cf0ff-350">이 서비스에 대 한 참조를 사용 하 여 환경에 쿼리하여 획득는 <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-350">You acquire a reference to this service by querying the environment with the <xref:System.ComponentModel.Design.ComponentDesigner.GetService%2A> method.</span></span> <span data-ttu-id="cf0ff-351">쿼리가 성공 하는 경우 디자이너에 대 한 처리기에서 연결할 수는 <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> 이벤트 디자인 타임에 일관 된 상태로 유지 하기 위해 필요한 모든 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-351">If the query is successful, your designer can attach a handler for the <xref:System.ComponentModel.Design.IComponentChangeService.ComponentChanged> event and perform whatever tasks are required to maintain a consistent state at design time.</span></span>  
  
 <span data-ttu-id="cf0ff-352">경우에 `MarqueeControlRootDesigner` 호출 클래스는 <xref:System.Windows.Forms.Control.Refresh%2A> 각 메서드 `IMarqueeWidget` 에 포함 된 개체는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-352">In the case of the `MarqueeControlRootDesigner` class, you will call the <xref:System.Windows.Forms.Control.Refresh%2A> method on each `IMarqueeWidget` object contained by the `MarqueeControl`.</span></span> <span data-ttu-id="cf0ff-353">이렇게 하면는 `IMarqueeWidget` 그려집니다 적절 하 게 같은 부모 항목의 속성 때 개체 <xref:System.Windows.Forms.Control.Size%2A> 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-353">This will cause the `IMarqueeWidget` object to repaint itself appropriately when properties like its parent's <xref:System.Windows.Forms.Control.Size%2A> are changed.</span></span>  
  
#### <a name="to-handle-component-changes"></a><span data-ttu-id="cf0ff-354">구성 요소 변경을 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-354">To handle component changes</span></span>  
  
1.  <span data-ttu-id="cf0ff-355">열기는 `MarqueeControlRootDesigner` 소스 파일에는 **코드 편집기** 재정의 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-355">Open the `MarqueeControlRootDesigner` source file in the **Code Editor** and override the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span> <span data-ttu-id="cf0ff-356">기본 구현을 호출 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 및에 대 한 쿼리는 <xref:System.ComponentModel.Design.IComponentChangeService>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-356">Call the base implementation of <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> and query for the <xref:System.ComponentModel.Design.IComponentChangeService>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#580)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#580](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#580)]  
  
2.  <span data-ttu-id="cf0ff-357">구현 된 <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-357">Implement the <xref:System.ComponentModel.Design.IComponentChangeService.OnComponentChanged%2A> event handler.</span></span> <span data-ttu-id="cf0ff-358">보내는 구성 요소의 형식을 테스트 하 고는 `IMarqueeWidget`, 호출 해당 <xref:System.Windows.Forms.Control.Refresh%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-358">Test the sending component's type, and if it is an `IMarqueeWidget`, call its <xref:System.Windows.Forms.Control.Refresh%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#560)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#560](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#560)]  
  
## <a name="adding-designer-verbs-to-your-custom-designer"></a><span data-ttu-id="cf0ff-359">사용자 지정 디자이너를 디자이너 동사를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-359">Adding Designer Verbs to your Custom Designer</span></span>  
 <span data-ttu-id="cf0ff-360">디자이너 동사는 이벤트 처리기에 연결 된 메뉴 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-360">A designer verb is a menu command linked to an event handler.</span></span> <span data-ttu-id="cf0ff-361">디자이너 동사는 디자인 타임에 구성 요소의 바로 가기 메뉴에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-361">Designer verbs are added to a component's shortcut menu at design time.</span></span> <span data-ttu-id="cf0ff-362">자세한 내용은 <xref:System.ComponentModel.Design.DesignerVerb>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-362">For more information, see <xref:System.ComponentModel.Design.DesignerVerb>.</span></span>  
  
 <span data-ttu-id="cf0ff-363">두 개의 디자이너 동사를 디자이너에 추가 됩니다: **테스트 실행** 및 **테스트 중지**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-363">You will add two designer verbs to your designers: **Run Test** and **Stop Test**.</span></span> <span data-ttu-id="cf0ff-364">이러한 동사를 사용 하면의 런타임 동작을 볼 수 있습니다는 `MarqueeControl` 디자인 타임에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-364">These verbs will allow you to view the run-time behavior of the `MarqueeControl` at design time.</span></span> <span data-ttu-id="cf0ff-365">이러한 동사에 추가 되는 `MarqueeControlRootDesigner`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-365">These verbs will be added to the `MarqueeControlRootDesigner`.</span></span>  
  
 <span data-ttu-id="cf0ff-366">때 **테스트 실행** 은 호출 동사 이벤트 처리기 호출 됩니다는 `StartMarquee` 에서 메서드는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-366">When **Run Test** is invoked, the verb event handler will call the `StartMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="cf0ff-367">때 **테스트 중지** 은 호출 동사 이벤트 처리기 호출 됩니다는 `StopMarquee` 에서 메서드는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-367">When **Stop Test** is invoked, the verb event handler will call the `StopMarquee` method on the `MarqueeControl`.</span></span> <span data-ttu-id="cf0ff-368">구현에서 `StartMarquee` 및 `StopMarquee` 메서드를 구현 하는 포함 된 컨트롤에서 이러한 메서드를 호출 `IMarqueeWidget`하므로 포함 된 모든, `IMarqueeWidget` 컨트롤은 테스트에도 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-368">The implementation of the `StartMarquee` and `StopMarquee` methods call these methods on contained controls that implement `IMarqueeWidget`, so any contained `IMarqueeWidget` controls will also participate in the test.</span></span>  
  
#### <a name="to-add-designer-verbs-to-your-custom-designers"></a><span data-ttu-id="cf0ff-369">사용자 지정 디자이너를 디자이너 동사를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-369">To add designer verbs to your custom designers</span></span>  
  
1.  <span data-ttu-id="cf0ff-370">에 `MarqueeControlRootDesigner` 클래스, 이벤트 처리기 라는 추가 `OnVerbRunTest` 및 `OnVerbStopTest`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-370">In the `MarqueeControlRootDesigner` class, add event handlers named `OnVerbRunTest` and `OnVerbStopTest`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#570)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#570](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#570)]  
  
2.  <span data-ttu-id="cf0ff-371">해당 디자이너 동사에 이러한 이벤트 처리기를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-371">Connect these event handlers to their corresponding designer verbs.</span></span> <span data-ttu-id="cf0ff-372">`MarqueeControlRootDesigner`상속 된 <xref:System.ComponentModel.Design.DesignerVerbCollection> 해당 기본 클래스에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-372">`MarqueeControlRootDesigner` inherits a <xref:System.ComponentModel.Design.DesignerVerbCollection> from its base class.</span></span> <span data-ttu-id="cf0ff-373">만들려는 두 개의 새 <xref:System.ComponentModel.Design.DesignerVerb> 개체에서이 컬렉션에 추가 하는 <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-373">You will create two new <xref:System.ComponentModel.Design.DesignerVerb> objects and add them to this collection in the <xref:System.Windows.Forms.Design.DocumentDesigner.Initialize%2A> method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueecontrolrootdesigner.cs#590)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#590](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueecontrolrootdesigner.vb#590)]  
  
## <a name="creating-a-custom-uitypeeditor"></a><span data-ttu-id="cf0ff-374">사용자 지정 UITypeEditor 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-374">Creating a Custom UITypeEditor</span></span>  
 <span data-ttu-id="cf0ff-375">사용자에 대 한 사용자 지정 디자인 타임 환경을 만들 때을 속성 창에서 사용자 지정 상호 작용을 만들려는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-375">When you create a custom design-time experience for users, it is often desirable to create a custom interaction with the Properties window.</span></span> <span data-ttu-id="cf0ff-376">만들어서이 작업을 수행할 수는 <xref:System.Drawing.Design.UITypeEditor>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-376">You can accomplish this by creating a <xref:System.Drawing.Design.UITypeEditor>.</span></span> <span data-ttu-id="cf0ff-377">자세한 내용은 참조 [하는 방법: UI 형식 편집기 만들기](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-377">For more information, see [How to: Create a UI Type Editor](http://msdn.microsoft.com/library/292c6e33-8d85-4012-9b51-05835a6f6dfd).</span></span>  
  
 <span data-ttu-id="cf0ff-378">`MarqueeBorder` 컨트롤 속성 창에서 여러 가지 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-378">The `MarqueeBorder` control exposes several properties in the Properties window.</span></span> <span data-ttu-id="cf0ff-379">이러한 속성 중 `MarqueeSpinDirection` 및 `MarqueeLightShape` 열거형으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-379">Two of these properties, `MarqueeSpinDirection` and `MarqueeLightShape` are represented by enumerations.</span></span> <span data-ttu-id="cf0ff-380">UI 유형 편집기의 사용을 설명 하기는 `MarqueeLightShape` 속성이 연결 된 갖는 <xref:System.Drawing.Design.UITypeEditor> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-380">To illustrate the use of a UI type editor, the `MarqueeLightShape` property will have an associated <xref:System.Drawing.Design.UITypeEditor> class.</span></span>  
  
#### <a name="to-create-a-custom-ui-type-editor"></a><span data-ttu-id="cf0ff-381">사용자 지정 UI 형식 편집기를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-381">To create a custom UI type editor</span></span>  
  
1.  <span data-ttu-id="cf0ff-382">열기는 `MarqueeBorder` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-382">Open the `MarqueeBorder` source file in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="cf0ff-383">정의에 `MarqueeBorder` 클래스 라는 클래스 선언 `LightShapeEditor` 에서 파생 된 <xref:System.Drawing.Design.UITypeEditor>합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-383">In the definition of the `MarqueeBorder` class, declare a class called `LightShapeEditor` that derives from <xref:System.Drawing.Design.UITypeEditor>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#96)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#96](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#96)]  
  
3.  <span data-ttu-id="cf0ff-384">선언 된 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 라는 인스턴스 변수 `editorService`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-384">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#92)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#92](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#92)]  
  
4.  <span data-ttu-id="cf0ff-385"><xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-385">Override the <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A> method.</span></span> <span data-ttu-id="cf0ff-386">이 구현은 <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, 디자인 환경에서 표시 하는 방법을 지시는 `LightShapeEditor`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-386">This implementation returns <xref:System.Drawing.Design.UITypeEditorEditStyle.DropDown>, which tells the design environment how to display the `LightShapeEditor`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#93)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#93](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#93)]  
  
5.  <span data-ttu-id="cf0ff-387"><xref:System.Drawing.Design.UITypeEditor.EditValue%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-387">Override the <xref:System.Drawing.Design.UITypeEditor.EditValue%2A> method.</span></span> <span data-ttu-id="cf0ff-388">이 구현 디자인 환경에 대 한 쿼리는 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-388">This implementation queries the design environment for an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> object.</span></span> <span data-ttu-id="cf0ff-389">성공적으로 만듭니다는 `LightShapeSelectionControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-389">If successful, it creates a `LightShapeSelectionControl`.</span></span> <span data-ttu-id="cf0ff-390"><xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> 메서드를 호출을 시작 하 여 `LightShapeEditor`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-390">The <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.DropDownControl%2A> method is invoked to start the `LightShapeEditor`.</span></span> <span data-ttu-id="cf0ff-391">이 호출의 반환 값은 디자인 환경에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-391">The return value from this invocation is returned to the design environment.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/marqueeborder.cs#94)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#94](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/marqueeborder.vb#94)]  
  
## <a name="creating-a-view-control-for-your-custom-uitypeeditor"></a><span data-ttu-id="cf0ff-392">사용자 지정 UITypeEditor 사용자에 대 한 View 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-392">Creating a View Control for your Custom UITypeEditor</span></span>  
  
1.  <span data-ttu-id="cf0ff-393">`MarqueeLightShape` 속성에는 두 가지 유형의 밝은 셰이프 지원: `Square` 및 `Circle`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-393">The `MarqueeLightShape` property supports two types of light shapes: `Square` and `Circle`.</span></span> <span data-ttu-id="cf0ff-394">속성 창에서 이러한 값을 그래픽으로 표시 하는 목적 으로만 사용 되는 사용자 지정 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-394">You will create a custom control used solely for the purpose of graphically displaying these values in the Properties window.</span></span> <span data-ttu-id="cf0ff-395">이 사용자 지정 컨트롤에서 사용할 프로그램 <xref:System.Drawing.Design.UITypeEditor> 속성 창와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-395">This custom control will be used by your <xref:System.Drawing.Design.UITypeEditor> to interact with the Properties window.</span></span>  
  
#### <a name="to-create-a-view-control-for-your-custom-ui-type-editor"></a><span data-ttu-id="cf0ff-396">컨트롤을 만들려면 보기에 대 한 사용자 지정 UI 형식 편집기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-396">To create a view control for your custom UI type editor</span></span>  
  
1.  <span data-ttu-id="cf0ff-397">새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-397">Add a new <xref:System.Windows.Forms.UserControl> item to the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="cf0ff-398">새 소스 파일 "쿼리에 성공 합니다."의 기본 이름 지정</span><span class="sxs-lookup"><span data-stu-id="cf0ff-398">Give the new source file a base name of "LightShapeSelectionControl."</span></span>  
  
2.  <span data-ttu-id="cf0ff-399">두 개 <xref:System.Windows.Forms.Panel> 에서 제어는 **도구 상자** 에 `LightShapeSelectionControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-399">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto the `LightShapeSelectionControl`.</span></span> <span data-ttu-id="cf0ff-400">이름을 지정 하 여 `squarePanel` 및 `circlePanel`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-400">Name them `squarePanel` and `circlePanel`.</span></span> <span data-ttu-id="cf0ff-401">나란히 놓고 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-401">Arrange them side by side.</span></span> <span data-ttu-id="cf0ff-402">설정의 <xref:System.Windows.Forms.Control.Size%2A> 모두의 속성이 <xref:System.Windows.Forms.Panel> 하는 제어 (60, 60)입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-402">Set the <xref:System.Windows.Forms.Control.Size%2A> property of both <xref:System.Windows.Forms.Panel> controls to (60, 60).</span></span> <span data-ttu-id="cf0ff-403">설정의 <xref:System.Windows.Forms.Control.Location%2A> 의 속성에서 `squarePanel` 제어를 (8, 10).</span><span class="sxs-lookup"><span data-stu-id="cf0ff-403">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `squarePanel` control to (8, 10).</span></span> <span data-ttu-id="cf0ff-404">설정의 <xref:System.Windows.Forms.Control.Location%2A> 의 속성에서 `circlePanel` 제어를 (80, 10).</span><span class="sxs-lookup"><span data-stu-id="cf0ff-404">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the `circlePanel` control to (80, 10).</span></span> <span data-ttu-id="cf0ff-405">마지막으로 설정 된 <xref:System.Windows.Forms.Control.Size%2A> 속성의는 `LightShapeSelectionControl` 를 (150, 80).</span><span class="sxs-lookup"><span data-stu-id="cf0ff-405">Finally, set the <xref:System.Windows.Forms.Control.Size%2A> property of the `LightShapeSelectionControl` to (150, 80).</span></span>  
  
3.  <span data-ttu-id="cf0ff-406">열기는 `LightShapeSelectionControl` 소스 파일에는 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-406">Open the `LightShapeSelectionControl` source file in the **Code Editor**.</span></span> <span data-ttu-id="cf0ff-407">파일 맨 위에 있는 가져오기는 <xref:System.Windows.Forms.Design?displayProperty=nameWithType> 네임 스페이스:</span><span class="sxs-lookup"><span data-stu-id="cf0ff-407">At the top of the file, import the <xref:System.Windows.Forms.Design?displayProperty=nameWithType> namespace:</span></span>  
  
```vb  
Imports System.Windows.Forms.Design  
```  
  
```csharp  
using System.Windows.Forms.Design;  
```  
  
1.  <span data-ttu-id="cf0ff-408">구현 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기는 `squarePanel` 및 `circlePanel` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-408">Implement <xref:System.Windows.Forms.Control.Click> event handlers for the `squarePanel` and `circlePanel` controls.</span></span> <span data-ttu-id="cf0ff-409">이러한 메서드는 호출 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> 사용자 지정 종료 <xref:System.Drawing.Design.UITypeEditor> 세션을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-409">These methods invoke <xref:System.Windows.Forms.Design.IWindowsFormsEditorService.CloseDropDown%2A> to end the custom <xref:System.Drawing.Design.UITypeEditor> editing session.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#390)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#390](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#390)]  
  
2.  <span data-ttu-id="cf0ff-410">선언 된 <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> 라는 인스턴스 변수 `editorService`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-410">Declare an <xref:System.Windows.Forms.Design.IWindowsFormsEditorService> instance variable called `editorService`.</span></span>  
  
```vb  
Private editorService As IWindowsFormsEditorService  
```  
  
```csharp  
private IWindowsFormsEditorService editorService;  
```  
  
1.  <span data-ttu-id="cf0ff-411">선언 된 `MarqueeLightShape` 라는 인스턴스 변수 `lightShapeValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-411">Declare a `MarqueeLightShape` instance variable called `lightShapeValue`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#330)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#330](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#330)]  
  
2.  <span data-ttu-id="cf0ff-412">에 `LightShapeSelectionControl` 생성자 연결는 <xref:System.Windows.Forms.Control.Click> 에 이벤트 처리기는 `squarePanel` 및 `circlePanel` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-412">In the `LightShapeSelectionControl` constructor, attach the <xref:System.Windows.Forms.Control.Click> event handlers to the `squarePanel` and `circlePanel` controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="cf0ff-413">또한 할당 하는 생성자 오버 로드를 정의 `MarqueeLightShape` 디자인 환경에서 값의 `lightShapeValue` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-413">Also, define a constructor overload that assigns the `MarqueeLightShape` value from the design environment to the `lightShapeValue` field.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#340)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#340](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#340)]  
  
3.  <span data-ttu-id="cf0ff-414">에 <xref:System.ComponentModel.Component.Dispose%2A> 메서드를 분리 된 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-414">In the <xref:System.ComponentModel.Component.Dispose%2A> method, detach the <xref:System.Windows.Forms.Control.Click> event handlers.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#350)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#350](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#350)]  
  
4.  <span data-ttu-id="cf0ff-415">**솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-415">In **Solution Explorer**, click the **Show All Files** button.</span></span> <span data-ttu-id="cf0ff-416">기본 정의 제거 하 고 LightShapeSelectionControl.Designer.cs 또는 LightShapeSelectionControl.Designer.vb 파일을 열고는 <xref:System.ComponentModel.Component.Dispose%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-416">Open the LightShapeSelectionControl.Designer.cs or LightShapeSelectionControl.Designer.vb file, and remove the default definition of the <xref:System.ComponentModel.Component.Dispose%2A> method.</span></span>  
  
5.  <span data-ttu-id="cf0ff-417">`LightShape` 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-417">Implement the `LightShape` property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#360)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#360](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#360)]  
  
6.  <span data-ttu-id="cf0ff-418"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-418">Override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="cf0ff-419">이 구현은 채워진 사각형과 원을 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-419">This implementation will draw a filled square and circle.</span></span> <span data-ttu-id="cf0ff-420">그는 또한 강조 표시 선택 된 값 도형 둘레에 테두리를 그려서 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-420">It will also highlight the selected value by drawing a border around one shape or the other.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/CS/lightshapeselectioncontrol.cs#380)]
     [!code-vb[System.Windows.Forms.Design.DocumentDesigner#380](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Design.DocumentDesigner/VB/lightshapeselectioncontrol.vb#380)]  
  
## <a name="testing-your-custom-control-in-the-designer"></a><span data-ttu-id="cf0ff-421">디자이너에서 사용자 지정 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="cf0ff-421">Testing your Custom Control in the Designer</span></span>  
 <span data-ttu-id="cf0ff-422">이 시점에서 빌드할 수 있습니다는 `MarqueeControlLibrary` 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-422">At this point, you can build the `MarqueeControlLibrary` project.</span></span> <span data-ttu-id="cf0ff-423">상속 되는 컨트롤을 만들어 구현을 테스트는 `MarqueeControl` 클래스 및 폼에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-423">Test your implementation by creating a control that inherits from the `MarqueeControl` class and using it on a form.</span></span>  
  
#### <a name="to-create-a-custom-marqueecontrol-implementation"></a><span data-ttu-id="cf0ff-424">사용자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf0ff-424">To create a custom MarqueeControl implementation</span></span>  
  
1.  <span data-ttu-id="cf0ff-425">Windows Forms 디자이너에서 `DemoMarqueeControl`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-425">Open `DemoMarqueeControl` in the Windows Forms Designer.</span></span> <span data-ttu-id="cf0ff-426">인스턴스를 만들고이 `DemoMarqueeControl` 입력 하 고 인스턴스의 표시는 `MarqueeControlRootDesigner` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-426">This creates an instance of the `DemoMarqueeControl` type and displays it in an instance of the `MarqueeControlRootDesigner` type.</span></span>  
  
2.  <span data-ttu-id="cf0ff-427">에 **도구 상자**열고는 **MarqueeControlLibrary 구성 요소** 탭 합니다. 표시 됩니다는 `MarqueeBorder` 및 `MarqueeText` 선택할 수 있는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-427">In the **Toolbox**, open the **MarqueeControlLibrary Components** tab. You will see the `MarqueeBorder` and `MarqueeText` controls available for selection.</span></span>  
  
3.  <span data-ttu-id="cf0ff-428">인스턴스를 끌어는 `MarqueeBorder` 컨트롤을 끌어와 `DemoMarqueeControl` 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-428">Drag an instance of the `MarqueeBorder` control onto the `DemoMarqueeControl` design surface.</span></span> <span data-ttu-id="cf0ff-429">이 도킹 `MarqueeBorder` 부모 컨트롤을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-429">Dock this `MarqueeBorder` control to the parent control.</span></span>  
  
4.  <span data-ttu-id="cf0ff-430">인스턴스를 끌어는 `MarqueeText` 컨트롤을 끌어와 `DemoMarqueeControl` 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-430">Drag an instance of the `MarqueeText` control onto the `DemoMarqueeControl` design surface.</span></span>  
  
5.  <span data-ttu-id="cf0ff-431">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-431">Build the solution.</span></span>  
  
6.  <span data-ttu-id="cf0ff-432">마우스 오른쪽 단추로 클릭는 `DemoMarqueeControl` 및 바로 가기 메뉴 선택에서은 **테스트 실행** 애니메이션을 시작 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-432">Right-click the `DemoMarqueeControl` and from the shortcut menu select the **Run Test** option to start the animation.</span></span> <span data-ttu-id="cf0ff-433">클릭 **테스트 중지** 여 애니메이션을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-433">Click **Stop Test** to stop the animation.</span></span>  
  
7.  <span data-ttu-id="cf0ff-434">열기 **Form1** 디자인 뷰에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-434">Open **Form1** in Design view.</span></span>  
  
8.  <span data-ttu-id="cf0ff-435">두 개의 배치 <xref:System.Windows.Forms.Button> 폼에서 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-435">Place two <xref:System.Windows.Forms.Button> controls on the form.</span></span> <span data-ttu-id="cf0ff-436">이름을 지정 하 여 `startButton` 및 `stopButton`, 변경 하 고는 <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 **시작** 및 **중지**각각.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-436">Name them `startButton` and `stopButton`, and change the <xref:System.Windows.Forms.Control.Text%2A> property values to **Start** and **Stop**, respectively.</span></span>  
  
9. <span data-ttu-id="cf0ff-437">구현 <xref:System.Windows.Forms.Control.Click> 모두에 대 한 이벤트 처리기 <xref:System.Windows.Forms.Button> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-437">Implement <xref:System.Windows.Forms.Control.Click> event handlers for both <xref:System.Windows.Forms.Button> controls.</span></span>  
  
10. <span data-ttu-id="cf0ff-438">에 **도구 상자**열고는 **MarqueeControlTest 구성 요소** 탭 합니다. 표시 됩니다는 `DemoMarqueeControl` 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-438">In the **Toolbox**, open the **MarqueeControlTest Components** tab. You will see the `DemoMarqueeControl` available for selection.</span></span>  
  
11. <span data-ttu-id="cf0ff-439">인스턴스를 끌어 `DemoMarqueeControl` 에 **Form1** 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-439">Drag an instance of `DemoMarqueeControl` onto the **Form1** design surface.</span></span>  
  
12. <span data-ttu-id="cf0ff-440">에 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 호출의 `Start` 및 `Stop` 에 대 한 메서드는 `DemoMarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-440">In the <xref:System.Windows.Forms.Control.Click> event handlers, invoke the `Start` and `Stop` methods on the `DemoMarqueeControl`.</span></span>  
  
```vb  
Private Sub startButton_Click(sender As Object, e As System.EventArgs)  
    Me.demoMarqueeControl1.Start()  
End Sub 'startButton_Click  
  
Private Sub stopButton_Click(sender As Object, e As System.EventArgs)  
Me.demoMarqueeControl1.Stop()  
End Sub 'stopButton_Click  
```  
  
```csharp  
private void startButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Start();  
}  
  
private void stopButton_Click(object sender, System.EventArgs e)  
{  
    this.demoMarqueeControl1.Stop();  
}  
```  
  
1.  <span data-ttu-id="cf0ff-441">설정의 `MarqueeControlTest` 시작 프로젝트로 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-441">Set the `MarqueeControlTest` project as the startup project and run it.</span></span> <span data-ttu-id="cf0ff-442">표시 하는 폼을 보게 프로그램 `DemoMarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-442">You will see the form displaying your `DemoMarqueeControl`.</span></span> <span data-ttu-id="cf0ff-443">클릭는 **시작** 단추는 애니메이션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-443">Click the **Start** button to start the animation.</span></span> <span data-ttu-id="cf0ff-444">깜박이 텍스트와 테두리 움직이는 조명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-444">You should see the text flashing and the lights moving around the border.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cf0ff-445">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cf0ff-445">Next Steps</span></span>  
 <span data-ttu-id="cf0ff-446">`MarqueeControlLibrary` 사용자 지정 컨트롤과 연결 된 디자이너의 간단한 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-446">The `MarqueeControlLibrary` demonstrates a simple implementation of custom controls and associated designers.</span></span> <span data-ttu-id="cf0ff-447">여러 가지 방법으로이 샘플을 보다 정교한 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-447">You can make this sample more sophisticated in several ways:</span></span>  
  
-   <span data-ttu-id="cf0ff-448">에 대 한 속성 값을 변경는 `DemoMarqueeControl` 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-448">Change the property values for the `DemoMarqueeControl` in the designer.</span></span> <span data-ttu-id="cf0ff-449">더 추가 `MarqueBorder` 제어 하 고 중첩 된 효과를 만들려면 해당 부모 인스턴스 내에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-449">Add more `MarqueBorder` controls and dock them within their parent instances to create a nested effect.</span></span> <span data-ttu-id="cf0ff-450">에 대 한 다른 설정 사용 하 여 실험에서 `UpdatePeriod` 및 조명 관련 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-450">Experiment with different settings for the `UpdatePeriod` and the light-related properties.</span></span>  
  
-   <span data-ttu-id="cf0ff-451">자체 구현을 작성 `IMarqueeWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-451">Author your own implementations of `IMarqueeWidget`.</span></span> <span data-ttu-id="cf0ff-452">예를 들어 이미지가 여러 개 있는 애니메이션된 사인 또는 깜박이 "neon 로그인"을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-452">You could, for example, create a flashing "neon sign" or an animated sign with multiple images.</span></span>  
  
-   <span data-ttu-id="cf0ff-453">디자인 타임 환경을 사용자 지정할.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-453">Further customize the design-time experience.</span></span> <span data-ttu-id="cf0ff-454">보다 더 많은 속성을 숨김을 시도할 수 <xref:System.Windows.Forms.Control.Enabled%2A> 및 <xref:System.Windows.Forms.Control.Visible%2A>, 새 속성을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-454">You could try shadowing more properties than <xref:System.Windows.Forms.Control.Enabled%2A> and <xref:System.Windows.Forms.Control.Visible%2A>, and you could add new properties.</span></span> <span data-ttu-id="cf0ff-455">자식 컨트롤을 도킹과 같은 일반적인 작업을 간소화 하기 위해 새 디자이너 동사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-455">Add new designer verbs to simplify common tasks like docking child controls.</span></span>  
  
-   <span data-ttu-id="cf0ff-456">라이선스는 `MarqueeControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-456">License the `MarqueeControl`.</span></span> <span data-ttu-id="cf0ff-457">자세한 내용은 참조 [하는 방법: 라이선스 구성 요소와 컨트롤](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-457">For more information, see [How to: License Components and Controls](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57).</span></span>  
  
-   <span data-ttu-id="cf0ff-458">컨트롤을 serialize 하는 방법 및 코드에 생성 되는 방식을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-458">Control how your controls are serialized and how code is generated for them.</span></span> <span data-ttu-id="cf0ff-459">자세한 내용은 참조 [동적 소스 코드 생성 및 컴파일](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf0ff-459">For more information, see [Dynamic Source Code Generation and Compilation](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0ff-460">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf0ff-460">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Design.ParentControlDesigner>  
 <xref:System.Windows.Forms.Design.DocumentDesigner>  
 <xref:System.ComponentModel.Design.IRootDesigner>  
 <xref:System.ComponentModel.Design.DesignerVerb>  
 <xref:System.Drawing.Design.UITypeEditor>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="cf0ff-461">방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="cf0ff-461">How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features</span></span>](http://msdn.microsoft.com/library/8e0bad0e-56f3-43d2-bf63-a945c654d97c)  
 [<span data-ttu-id="cf0ff-462">디자인 타임 지원 확장</span><span class="sxs-lookup"><span data-stu-id="cf0ff-462">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 [<span data-ttu-id="cf0ff-463">사용자 지정 디자이너</span><span class="sxs-lookup"><span data-stu-id="cf0ff-463">Custom Designers</span></span>](http://msdn.microsoft.com/library/ca11988e-d38e-44d8-a05d-71362ae7844d)  
 [<span data-ttu-id="cf0ff-464">.NET 셰이프 라이브러리: 샘플 디자이너</span><span class="sxs-lookup"><span data-stu-id="cf0ff-464">.NET Shape Library: A Sample Designer</span></span>](http://windowsforms.net/articles/shapedesigner.aspx)
