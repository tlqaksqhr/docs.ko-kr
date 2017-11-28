---
title: "연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅"
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
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc5f0fab7c380268dfc041d6105595858c2fed93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="36b4e-102">연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅</span><span class="sxs-lookup"><span data-stu-id="36b4e-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="36b4e-103">사용자 지정 컨트롤을 만들 때는 경우 종종 있습니다의 디자인 타임 동작을 디버깅 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="36b4e-104">사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 제작 하는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="36b4e-105">자세한 내용은 참조 [연습:는 Windows Forms 제어 하는 이점은의 Visual Studio 디자인 타임 기능을 만드는](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="36b4e-106">다른.NET Framework 클래스를 디버그할 때 처럼 Visual Studio를 사용 하 여 사용자 지정 컨트롤을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="36b4e-107">차이점은 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="36b4e-108">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="36b4e-109">사용자 지정 컨트롤을 호스트 하는 Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="36b4e-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="36b4e-110">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="36b4e-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="36b4e-111">사용자 지정 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="36b4e-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="36b4e-112">호스트 폼을 사용자 지정 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="36b4e-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="36b4e-113">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="36b4e-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="36b4e-114">디자인 타임에 사용자 지정 컨트롤 디버깅</span><span class="sxs-lookup"><span data-stu-id="36b4e-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="36b4e-115">작업을 완료 하는 경우 사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하는 데 필요한 작업을 이해를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36b4e-116">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="36b4e-117">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="36b4e-118">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36b4e-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="36b4e-119">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="36b4e-119">Creating the Project</span></span>  
 <span data-ttu-id="36b4e-120">첫 번째 단계는 응용 프로그램 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-120">The first step is to create the application project.</span></span> <span data-ttu-id="36b4e-121">사용자 지정 컨트롤을 호스트 하는 응용 프로그램을 빌드하려면이 프로젝트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="36b4e-122">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="36b4e-122">To create the project</span></span>  
  
-   <span data-ttu-id="36b4e-123">"DebuggingExample" 이라는 Windows 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-123">Create a Windows Application project called "DebuggingExample".</span></span> <span data-ttu-id="36b4e-124">자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36b4e-124">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="36b4e-125">컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="36b4e-125">Creating a Control Library Project</span></span>  
 <span data-ttu-id="36b4e-126">컨트롤 라이브러리 프로젝트를 만들고 사용자 지정 컨트롤을 설정 하는 다음 단계가입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-126">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="36b4e-127">컨트롤 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="36b4e-127">To create the control library project</span></span>  
  
1.  <span data-ttu-id="36b4e-128">추가 **Windows 컨트롤 라이브러리** 프로젝트를 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-128">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="36b4e-129">새로 추가 **UserControl** 항목 DebugControlLibrary 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="36b4e-129">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="36b4e-130">자세한 내용은 참조 [NIB: 방법: 새 프로젝트 항목 추가](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-130">For details, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="36b4e-131">새 소스 파일 "DebugControl"의 기본 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-131">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="36b4e-132">사용 하는 **솔루션 탐색기**, 코드 파일의 기본 이름으로를 삭제 하 여 프로젝트의 기본 컨트롤 삭제 "`UserControl1`"입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-132">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="36b4e-133">자세한 내용은 참조 [NIB: 방법: 제거, 삭제 및 항목 제외](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-133">For details, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/en-us/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="36b4e-134">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-134">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="36b4e-135">검사점</span><span class="sxs-lookup"><span data-stu-id="36b4e-135">Checkpoint</span></span>  
 <span data-ttu-id="36b4e-136">이 시점에서 사용자 지정 컨트롤을 볼 수는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-136">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="36b4e-137">진행률을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="36b4e-137">To check your progress</span></span>  
  
-   <span data-ttu-id="36b4e-138">라는 새 탭 찾기 **DebugControlLibrary 구성 요소** 및 선택 하려면 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-138">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="36b4e-139">으로 나열 된 컨트롤을 열었을 때 나타납니다 **DebugControl** 옆에 있는 기본 아이콘이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-139">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="36b4e-140">사용자 지정 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="36b4e-140">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="36b4e-141">디자인 타임에 사용자 지정 컨트롤의 코드가 실행 되 고 작업을 보여 주기 위해 속성을 추가 쿼리하고 해당 속성을 구현 하는 코드에 중단점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-141">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="36b4e-142">사용자 지정 컨트롤에 속성을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="36b4e-142">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="36b4e-143">열기 **DebugControl** 에 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-143">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="36b4e-144">클래스 정의에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-144">Add the following code to the class definition:</span></span>  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="36b4e-145">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-145">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="36b4e-146">호스트 폼을 사용자 지정 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="36b4e-146">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="36b4e-147">사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 사용자 지정 컨트롤 클래스의 인스턴스를 호스트 폼에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-147">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="36b4e-148">사용자 지정 컨트롤 호스트 폼에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="36b4e-148">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="36b4e-149">"DebuggingExample" 프로젝트를 열고에서 Form1는 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-149">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="36b4e-150">에 **도구 상자**열고는 **DebugControlLibrary 구성 요소** 탭 한 다음 끌어서는 **DebugControl** 폼 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="36b4e-150">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="36b4e-151">찾을 `DemoString` 에 사용자 지정 속성의 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="36b4e-151">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="36b4e-152">참고 다른 속성과 마찬가지로 해당 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-152">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="36b4e-153">또한는 `DemoString` 속성을 선택 하면 속성의 설명 문자열의 맨 아래에 나타나고는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="36b4e-153">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="36b4e-154">디자인 타임 디버깅에 대 한 프로젝트 설정</span><span class="sxs-lookup"><span data-stu-id="36b4e-154">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="36b4e-155">사용자 지정 컨트롤의 디자인 타임 동작을 디버깅 하려면 사용자 지정 컨트롤의 코드를 실행 하는 Visual Studio의 개별 인스턴스를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-155">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="36b4e-156">디자인 타임 디버깅을 위해 프로젝트를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="36b4e-156">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="36b4e-157">마우스 오른쪽 단추로 클릭는 **DebugControlLibrary** 프로젝트에 **솔루션 탐색기** 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-157">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="36b4e-158">에 **DebugControlLibrary** 속성 시트는 **디버그** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-158">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="36b4e-159">에 **시작 작업** 섹션에서 **시작 외부 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-159">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="36b4e-160">됩니다. Visual Studio의 개별 인스턴스 디버깅 이므로 줄임표를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))를 Visual Studio IDE에 대 한 찾아보기 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-160">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="36b4e-161">실행 파일의 이름은 **devenv.exe**와 경로 %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe 기본 위치에 설치한 경우.</span><span class="sxs-lookup"><span data-stu-id="36b4e-161">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="36b4e-162">**확인** 을 클릭하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-162">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="36b4e-163">마우스 오른쪽 단추로 클릭는 **DebugControlLibrary** 프로젝트를 마우스 선택 **시작 프로젝트로 설정** 디버깅이 구성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-163">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="36b4e-164">디자인 타임에 사용자 지정 컨트롤 디버깅</span><span class="sxs-lookup"><span data-stu-id="36b4e-164">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="36b4e-165">이제 디자인 모드에서 실행 되므로 사용자 지정 컨트롤을 디버그할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-165">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="36b4e-166">디버깅 세션을 시작 하면 Visual Studio의 새 인스턴스를 만들 수는, 및 "DebuggingExample" 솔루션을 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-166">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="36b4e-167">Form1를 열 때는 **Forms 디자이너**, 사용자 지정 컨트롤의 인스턴스 만들어지고 실행을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-167">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="36b4e-168">디자인 타임에 사용자 지정 컨트롤을 디버깅 하려면</span><span class="sxs-lookup"><span data-stu-id="36b4e-168">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="36b4e-169">열기는 **DebugControl** 소스 파일에는 **코드 편집기** 중단점을 설정 하 고는 `Set` 의 접근자는 `DemoString` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-169">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="36b4e-170">F5 키를 눌러 디버깅 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-170">Press F5 to start the debugging session.</span></span> <span data-ttu-id="36b4e-171">Note Visual Studio의 새 인스턴스가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-171">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="36b4e-172">두 가지 방법으로 인스턴스를 구별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-172">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="36b4e-173">디버깅 인스턴스에서 이라는 단어가 포함 **실행** 의 제목 표시줄에</span><span class="sxs-lookup"><span data-stu-id="36b4e-173">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="36b4e-174">디버깅 인스턴스는 **시작** 단추 해당 **디버그** 사용 하지 않도록 설정 하는 도구 모음</span><span class="sxs-lookup"><span data-stu-id="36b4e-174">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="36b4e-175">중단점은 디버깅 인스턴스에서 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-175">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="36b4e-176">Visual Studio의 새 인스턴스를 "DebuggingExample" 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-176">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="36b4e-177">선택 하 여 솔루션을 쉽게 찾을 **최근에 사용한 프로젝트** 에서 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="36b4e-177">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="36b4e-178">가장 최근에 사용 된 대로 "DebuggingExample.sln" 솔루션 파일을 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-178">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="36b4e-179">Form1에서 열고는 **Forms 디자이너** 선택 하 고는 **DebugControl** 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-179">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="36b4e-180">값 변경의 `DemoString` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-180">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="36b4e-181">변경 내용을 커밋하는 경우 Visual Studio의 디버깅 인스턴스에 포커스를 획득 및 중단점에서 실행이 중지 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-181">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="36b4e-182">속성 접근자를 통해 단일 단계 수와 마찬가지로 프로그램 다른 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-182">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="36b4e-183">Visual Studio의 호스트 인스턴스를 해제 하거나 클릭 하 여 마쳤으면 디버깅 세션을 종료할 수 있습니다는 **디버깅 중지** 디버깅 인스턴스에서 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-183">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="36b4e-184">다음 단계</span><span class="sxs-lookup"><span data-stu-id="36b4e-184">Next Steps</span></span>  
 <span data-ttu-id="36b4e-185">디자인 타임에 사용자 지정 컨트롤을 디버그할 수 있습니다, 했으므로 Visual Studio IDE와 컨트롤의 상호 작용 확장을 위한 다양 한 비즈니스 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-185">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="36b4e-186">사용할 수는 <xref:System.ComponentModel.Component.DesignMode%2A> 의 속성은 <xref:System.ComponentModel.Component> 디자인 타임에만 실행 되는 코드를 작성 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-186">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="36b4e-187">자세한 내용은 <xref:System.ComponentModel.Component.DesignMode%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36b4e-187">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="36b4e-188">일부의 특성이 디자이너와 사용자 지정 컨트롤의 상호 작용을 조작 하는 컨트롤의 속성에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-188">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="36b4e-189">이러한 특성을 찾을 수 있습니다는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-189">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="36b4e-190">사용자 지정 컨트롤에 대 한 사용자 지정 디자이너를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-190">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="36b4e-191">Visual Studio에서 노출 하는 확장 가능한 디자이너 인프라를 사용 하 여 디자인 환경을 완전히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-191">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="36b4e-192">자세한 내용은 참조 [연습:는 Windows Forms 제어 하는 이점은의 Visual Studio 디자인 타임 기능을 만드는](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36b4e-192">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b4e-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36b4e-193">See Also</span></span>  
 [<span data-ttu-id="36b4e-194">연습: Visual Studio의 디자인 타임 기능을 사용하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="36b4e-194">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="36b4e-195">방법: 디자인 타임 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="36b4e-195">How to: Access Design-Time Services</span></span>](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="36b4e-196">방법: Windows Forms에서 디자인 타임 지원에 액세스</span><span class="sxs-lookup"><span data-stu-id="36b4e-196">How to: Access Design-Time Support in Windows Forms</span></span>](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
