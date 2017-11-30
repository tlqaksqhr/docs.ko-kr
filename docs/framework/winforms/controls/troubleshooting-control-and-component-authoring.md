---
title: "컨트롤 및 구성 요소 제작 문제 해결"
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
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e027a5b60e066a8d38db530c37a394227f2e892
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-control-and-component-authoring"></a><span data-ttu-id="65bf9-102">컨트롤 및 구성 요소 제작 문제 해결</span><span class="sxs-lookup"><span data-stu-id="65bf9-102">Troubleshooting Control and Component Authoring</span></span>
<span data-ttu-id="65bf9-103">이 항목에서는 구성 요소와 컨트롤을 개발할 때 발생하는 다음과 같은 일반적인 문제를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-103">This topic lists the following common problems that arise when developing components and controls.</span></span> <span data-ttu-id="65bf9-104">자세한 내용은 [구성 요소를 사용한 프로그래밍](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65bf9-104">For more information, see [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
-   <span data-ttu-id="65bf9-105">도구 상자에 컨트롤을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-105">Cannot Add Control to Toolbox</span></span>  
  
-   <span data-ttu-id="65bf9-106">Windows Forms 사용자 정의 컨트롤 또는 구성 요소를 디버깅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-106">Cannot Debug the Windows Forms User Control or Component</span></span>  
  
-   <span data-ttu-id="65bf9-107">상속된 컨트롤 또는 구성 요소에서 이벤트가 두 번 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-107">Event Is Raised Twice in Inherited Control or Component</span></span>  
  
-   <span data-ttu-id="65bf9-108">디자인 타임 오류: "구성 요소 '*구성 요소 이름*'을 만들지 못했습니다."</span><span class="sxs-lookup"><span data-stu-id="65bf9-108">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>  
  
-   <span data-ttu-id="65bf9-109">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="65bf9-109">STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="65bf9-110">도구 상자에 구성 요소 아이콘이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-110">Component Icon Does Not Appear in Toolbox</span></span>  
  
## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="65bf9-111">도구 상자에 컨트롤을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-111">Cannot Add Control to Toolbox</span></span>  
 <span data-ttu-id="65bf9-112">다른 프로젝트에서 만든 사용자 지정 컨트롤 또는 타사 컨트롤을 **도구 상자**에 추가하려는 경우 수동으로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-112">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="65bf9-113">현재 프로젝트가 컨트롤 또는 구성 요소를 포함하는 경우 **도구 상자**에 자동으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-113">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="65bf9-114">자세한 내용은 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65bf9-114">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
#### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="65bf9-115">도구 상자에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="65bf9-115">To add a control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="65bf9-116">바로 가기 메뉴에서 **도구 상자**를 마우스 오른쪽 단추로 클릭하고 **항목 선택**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-116">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="65bf9-117">**도구 상자 항목 선택** 대화 상자에서 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-117">In the **Choose Toolbox Items** dialog box, add the component:</span></span>  
  
    -   <span data-ttu-id="65bf9-118">.NET Framework 구성 요소 또는 컨트롤을 추가하려면 **.NET Framework 구성 요소** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-118">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>  
  
         <span data-ttu-id="65bf9-119">-또는-</span><span class="sxs-lookup"><span data-stu-id="65bf9-119">– or –</span></span>  
  
    -   <span data-ttu-id="65bf9-120">COM 구성 요소 또는 ActiveX 컨트롤을 추가하려면 **COM 구성 요소** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-120">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>  
  
3.  <span data-ttu-id="65bf9-121">컨트롤이 대화 상자에 표시되면 선택되었는지 확인한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-121">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="65bf9-122">컨트롤이 **도구 상자**에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-122">The control is added to the **Toolbox**.</span></span>  
  
4.  <span data-ttu-id="65bf9-123">컨트롤이 대화 상자에 나열되지 않는 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-123">If your control is not listed in the dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="65bf9-124">**찾아보기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-124">Click the **Browse** button.</span></span>  
  
    2.  <span data-ttu-id="65bf9-125">컨트롤을 포함하는 .dll 파일이 포함된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-125">Browse to the folder that contains the .dll file that contains your control.</span></span>  
  
    3.  <span data-ttu-id="65bf9-126">.dll 파일을 선택하고 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-126">Select the .dll file and click **Open**.</span></span>  
  
         <span data-ttu-id="65bf9-127">컨트롤이 대화 상자에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-127">Your control appears in the dialog box.</span></span>  
  
    4.  <span data-ttu-id="65bf9-128">컨트롤이 선택되었는지 확인한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-128">Confirm that your control is selected, and then click **OK**.</span></span>  
  
         <span data-ttu-id="65bf9-129">컨트롤이 **도구 상자**에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-129">Your control is added to the **Toolbox**.</span></span>  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="65bf9-130">Windows Forms 사용자 정의 컨트롤 또는 구성 요소를 디버깅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-130">Cannot Debug the Windows Forms User Control or Component</span></span>  
 <span data-ttu-id="65bf9-131">컨트롤에서 파생 되는 경우는 <xref:System.Windows.Forms.UserControl> 클래스 테스트 컨테이너의 런타임 동작을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-131">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="65bf9-132">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65bf9-132">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="65bf9-133">다른 사용자 지정 컨트롤 및 구성 요소는 독립 실행형 프로젝트가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-133">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="65bf9-134">Windows Forms 프로젝트와 같은 응용 프로그램에 의해 호스팅되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-134">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="65bf9-135">컨트롤 또는 구성 요소를 디버깅하려면 Windows Forms 프로젝트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-135">To debug a control or component, you must add it to a Windows Forms project.</span></span>  
  
#### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="65bf9-136">컨트롤 또는 구성 요소를 디버깅하려면</span><span class="sxs-lookup"><span data-stu-id="65bf9-136">To debug a control or component</span></span>  
  
1.  <span data-ttu-id="65bf9-137">**빌드** 메뉴에서 **솔루션 빌드**를 클릭하여 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-137">From the **Build** menu, click **Build Solution** to build your solution.</span></span>  
  
2.  <span data-ttu-id="65bf9-138">**파일** 메뉴에서 **추가**, **새 프로젝트**를 차례로 선택하여 응용 프로그램에 테스트 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-138">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>  
  
3.  <span data-ttu-id="65bf9-139">**새 프로젝트 추가** 대화 상자에서 프로젝트 형식에 **Windows 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-139">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>  
  
4.  <span data-ttu-id="65bf9-140">**솔루션 탐색기**에서 새 프로젝트에 대한 **참조** 노드를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-140">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="65bf9-141">바로 가기 메뉴에서 **참조 추가**를 클릭하여 컨트롤 또는 구성 요소를 포함하는 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-141">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>  
  
5.  <span data-ttu-id="65bf9-142">테스트 프로젝트에서 컨트롤 또는 구성 요소의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-142">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="65bf9-143">구성 요소가 **도구 상자**에 있는 경우 디자이너 화면으로 끌어 오거나 다음 코드 예제와 같이 프로그래밍 방식으로 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-143">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     <span data-ttu-id="65bf9-144">이제 컨트롤 또는 구성 요소를 정상적으로 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-144">You can now debug your control or component as usual.</span></span>  
  
 <span data-ttu-id="65bf9-145">디버깅에 대한 자세한 내용은 [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio) 및 [연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65bf9-145">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="65bf9-146">상속된 컨트롤 또는 구성 요소에서 이벤트가 두 번 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-146">Event Is Raised Twice in Inherited Control or Component</span></span>  
 <span data-ttu-id="65bf9-147">중복된 `Handles` 절 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-147">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="65bf9-148">자세한 내용은 [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65bf9-148">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="65bf9-149">디자인 타임 오류: "구성 요소 '구성 요소 이름'을 만들지 못했습니다."</span><span class="sxs-lookup"><span data-stu-id="65bf9-149">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>  
 <span data-ttu-id="65bf9-150">구성 요소 또는 컨트롤은 매개 변수가 없는 기본 생성자를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-150">Your component or control must provide a default constructor with no parameters.</span></span> <span data-ttu-id="65bf9-151">디자인 환경에서 구성 요소 또는 컨트롤의 인스턴스를 만드는 경우 매개 변수를 사용하는 생성자 오버로드에 매개 변수를 제공하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-151">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>  
  
## <a name="stathreadattribute"></a><span data-ttu-id="65bf9-152">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="65bf9-152">STAThreadAttribute</span></span>  
 <span data-ttu-id="65bf9-153"><xref:System.STAThreadAttribute> Windows Forms는 단일 스레드 아파트 모델을 사용 하는 공용 언어 런타임 (CLR)에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-153">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="65bf9-154">Windows Forms 응용 프로그램의 `Main` 메서드에 이 특성을 적용하지 않는 경우 의도하지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-154">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="65bf9-155">예를 들어 배경 이미지가 표시 되지 같은 컨트롤 <xref:System.Windows.Forms.ListView>합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-155">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="65bf9-156">일부 컨트롤은 올바른 자동 완성 및 끌어서 놓기 동작에 대해 이 특성을 요구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-156">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="65bf9-157">도구 상자에 구성 요소 아이콘이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-157">Component Icon Does Not Appear in Toolbox</span></span>  
 <span data-ttu-id="65bf9-158">사용 하는 경우 <xref:System.Drawing.ToolboxBitmapAttribute> 아이콘을 사용자 지정 구성 요소를 연결 하는 비트맵은 자동으로 생성 된 구성 요소에 대 한 도구 상자에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-158">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="65bf9-159">비트맵을 보려면 **도구 상자 항목 선택** 대화 상자를 사용하여 컨트롤을 다시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="65bf9-159">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="65bf9-160">자세한 내용은 [방법: 컨트롤에 대한 도구 상자 비트맵 제공](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65bf9-160">For more information, see [How to: Provide a Toolbox Bitmap for a Control](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65bf9-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65bf9-161">See Also</span></span>  
 [<span data-ttu-id="65bf9-162">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="65bf9-162">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="65bf9-163">연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기</span><span class="sxs-lookup"><span data-stu-id="65bf9-163">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="65bf9-164">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="65bf9-164">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 [<span data-ttu-id="65bf9-165">연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅</span><span class="sxs-lookup"><span data-stu-id="65bf9-165">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="65bf9-166">구성 요소 제작</span><span class="sxs-lookup"><span data-stu-id="65bf9-166">Component Authoring</span></span>](http://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 [<span data-ttu-id="65bf9-167">디자인 타임 개발 문제 해결</span><span class="sxs-lookup"><span data-stu-id="65bf9-167">Troubleshooting Design-Time Development</span></span>](http://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [<span data-ttu-id="65bf9-168">구성 요소를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="65bf9-168">Programming with Components</span></span>](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)
