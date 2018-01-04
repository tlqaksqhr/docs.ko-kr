---
title: "연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 028b66fea2b35e7b36760ec7c606f81ca2301620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a><span data-ttu-id="27e7e-102">연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="27e7e-102">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>
<span data-ttu-id="27e7e-103">폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="27e7e-104">Windows Forms 디자이너가이를 위해 여러 레이아웃 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-104">The Windows Forms Designer gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="27e7e-105">가장 중요 한 중 하나는 <xref:System.Windows.Forms.Design.Behavior.SnapLine> 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-105">One of the most important is the <xref:System.Windows.Forms.Design.Behavior.SnapLine> feature.</span></span>  
  
 <span data-ttu-id="27e7e-106">맞춤선은 정확 하 게 정렬 위치를 다른 제어 기능과 함께 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-106">Snaplines show you precisely where to line up controls with other controls.</span></span> <span data-ttu-id="27e7e-107">또한 보여 있습니다 여백의 Windows 사용자 인터페이스 지침에 지정 된 대로 컨트롤 사이의 권장된 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-107">They also show you the recommended distances for margins between controls, as specified by the Windows User Interface Guidelines.</span></span> <span data-ttu-id="27e7e-108">자세한 내용은 참조 [사용자 인터페이스 디자인 및 개발](http://go.microsoft.com/FWLink/?LinkId=83878)합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-108">For details, see [User Interface Design and Development](http://go.microsoft.com/FWLink/?LinkId=83878).</span></span>  
  
 <span data-ttu-id="27e7e-109">맞춤선 쉽게 보다를 사용자 컨트롤을 맞출 전문적인 모양 및 동작 (모양 및 느낌).</span><span class="sxs-lookup"><span data-stu-id="27e7e-109">Snaplines make it easy to align your controls, for crisp, professional appearance and behavior (look and feel).</span></span>  
  
 <span data-ttu-id="27e7e-110">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="27e7e-111">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="27e7e-111">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="27e7e-112">간격 및 맞춤선을 사용 하 여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="27e7e-112">Spacing and Aligning Controls Using Snaplines</span></span>  
  
-   <span data-ttu-id="27e7e-113">에 폼과 컨테이너 여백</span><span class="sxs-lookup"><span data-stu-id="27e7e-113">Aligning to Form and Container Margins</span></span>  
  
-   <span data-ttu-id="27e7e-114">그룹화 된 컨트롤에 맞춤</span><span class="sxs-lookup"><span data-stu-id="27e7e-114">Aligning to Grouped Controls</span></span>  
  
-   <span data-ttu-id="27e7e-115">맞춤선을 사용 하 여 크기로 윤곽선 지정 하 여 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-115">Using Snaplines to Place a Control by Outlining Its Size</span></span>  
  
-   <span data-ttu-id="27e7e-116">도구 상자에서 컨트롤을 끌어 올 때 맞춤선을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="27e7e-116">Using Snaplines When Dragging a Control from the Toolbox</span></span>  
  
-   <span data-ttu-id="27e7e-117">맞춤선을 사용 하 여 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="27e7e-117">Resizing Controls Using Snaplines</span></span>  
  
-   <span data-ttu-id="27e7e-118">컨트롤의 텍스트에 레이블 맞춤</span><span class="sxs-lookup"><span data-stu-id="27e7e-118">Aligning a Label to a Control's Text</span></span>  
  
-   <span data-ttu-id="27e7e-119">맞춤선을 사용 하 여 키보드 탐색</span><span class="sxs-lookup"><span data-stu-id="27e7e-119">Using Snaplines with Keyboard Navigation</span></span>  
  
-   <span data-ttu-id="27e7e-120">맞춤선 및 레이아웃 패널</span><span class="sxs-lookup"><span data-stu-id="27e7e-120">Snaplines and Layout Panels</span></span>  
  
-   <span data-ttu-id="27e7e-121">맞춤선을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="27e7e-121">Disabling Snaplines</span></span>  
  
 <span data-ttu-id="27e7e-122">완료 되 면 맞춤선 기능에 의해 수행 하는 레이아웃 역할을 이해를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-122">When you are finished, you will have an understanding of the layout role played by the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27e7e-123">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-123">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="27e7e-124">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-124">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="27e7e-125">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27e7e-125">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="27e7e-126">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="27e7e-126">Creating the Project</span></span>  
 <span data-ttu-id="27e7e-127">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-127">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="27e7e-128">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-128">To create the project</span></span>  
  
1.  <span data-ttu-id="27e7e-129">"SnaplineExample" 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-129">Create a Windows-based application project called "SnaplineExample".</span></span> <span data-ttu-id="27e7e-130">자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27e7e-130">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="27e7e-131">폼 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-131">Select the form in the Forms Designer.</span></span>  
  
## <a name="spacing-and-aligning-controls-using-snaplines"></a><span data-ttu-id="27e7e-132">간격 및 맞춤선을 사용 하 여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="27e7e-132">Spacing and Aligning Controls Using Snaplines</span></span>  
 <span data-ttu-id="27e7e-133">맞춤선 폼에서 컨트롤 정렬 하는 정확 하 고 직관적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-133">Snaplines give you an accurate and intuitive way to align controls on your form.</span></span> <span data-ttu-id="27e7e-134">선택한 컨트롤을 다른 컨트롤 또는 컨트롤 집합에 맞출 위치 근처 이동할 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-134">They appear when you are moving a selected control or controls near a position that would align with another control or set of controls.</span></span> <span data-ttu-id="27e7e-135">선택 항목은 "맞춤선" 제안된 된 위치에 다른 컨트롤을 지 나 이동 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-135">Your selection will "snap" to the suggested position as you move it past the other controls.</span></span>  
  
#### <a name="to-arrange-controls-using-snaplines"></a><span data-ttu-id="27e7e-136">맞춤선을 사용 하 여 컨트롤을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-136">To arrange controls using snaplines</span></span>  
  
1.  <span data-ttu-id="27e7e-137">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-137">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="27e7e-138">이동 된 <xref:System.Windows.Forms.Button> 컨트롤을 폼의 오른쪽 아래 모퉁이로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-138">Move the <xref:System.Windows.Forms.Button> control to the lower-right corner of the form.</span></span> <span data-ttu-id="27e7e-139">참고로 표시 되는 맞춤선의 <xref:System.Windows.Forms.Button> 아래쪽 및 오른쪽 테두리 폼의 컨트롤에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-139">Note the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the form.</span></span> <span data-ttu-id="27e7e-140">이러한 맞춤선 폼 컨트롤의 테두리 사이의 권장된 거리를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-140">These snaplines display the recommended distance between the borders of the control and the form.</span></span>  
  
3.  <span data-ttu-id="27e7e-141">이동 된 <xref:System.Windows.Forms.Button> 컨트롤 주위의 테두리 폼 및 맞춤선 나타나는 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-141">Move the <xref:System.Windows.Forms.Button> control around the borders of the form and note where the snaplines appear.</span></span> <span data-ttu-id="27e7e-142">작업을 완료 하는 경우 이동 된 <xref:System.Windows.Forms.Button> 가운데 폼의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-142">When you are finished, move the <xref:System.Windows.Forms.Button> control near the center of the form.</span></span>  
  
4.  <span data-ttu-id="27e7e-143">다른 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-143">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="27e7e-144">두 번째 이동 <xref:System.Windows.Forms.Button> 거의 첫 번째 수준 될 때까지 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-144">Move the second <xref:System.Windows.Forms.Button> control until it is nearly level with the first.</span></span> <span data-ttu-id="27e7e-145">맞춤선이 두 단추의 텍스트 기준선에 표시 되 고 컨트롤이 이동 하는 컨트롤이 다른 컨트롤과 수준의 위치에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-145">Note the snapline that appears at the text baseline of both buttons, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>  
  
6.  <span data-ttu-id="27e7e-146">두 번째 이동 <xref:System.Windows.Forms.Button> 첫 번째 바로 위에 놓을 때까지 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-146">Move the second <xref:System.Windows.Forms.Button> control until it is positioned directly above the first.</span></span> <span data-ttu-id="27e7e-147">컨트롤 사용자는 다른 컨트롤과 정렬 되는 위치에 이동 맞춰집니다 있고 두 단추의 왼쪽 및 오른쪽 가장자리를 따라 표시 되는 맞춤선을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-147">Note the snaplines that appear along the left and right edges of both buttons, and note that the control you are moving snaps to a position that is exactly aligned with the other control.</span></span>  
  
7.  <span data-ttu-id="27e7e-148">중 하나를 선택는 <xref:System.Windows.Forms.Button> 제어 하 고 거의 닿는 될 때까지 다른 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-148">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span> <span data-ttu-id="27e7e-149">사이 나타나는 맞춤선 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-149">Note the snapline that appears between them.</span></span> <span data-ttu-id="27e7e-150">이 간격은 컨트롤 테두리 사이의 권장된 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-150">This distance is the recommended distance between the borders of the controls.</span></span> <span data-ttu-id="27e7e-151">또한 참고는 컨트롤이 이동 하는이 위치에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-151">Also note that the control you are moving snaps to this position.</span></span>  
  
8.  <span data-ttu-id="27e7e-152">두 개 <xref:System.Windows.Forms.Panel> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-152">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto your form.</span></span>  
  
9. <span data-ttu-id="27e7e-153">이동 중 하나는 <xref:System.Windows.Forms.Panel> 거의 첫 번째 수준 될 때까지 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-153">Move one of the <xref:System.Windows.Forms.Panel> controls until it is nearly level with the first.</span></span> <span data-ttu-id="27e7e-154">두 컨트롤의 위쪽 및 아래쪽 가장자리를 따라 표시 되 고 컨트롤이 다른 컨트롤과 수준의 위치로 이동 하는 컨트롤 맞춰집니다 되는 맞춤선을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-154">Note the snaplines that appear along the top and bottom edges of both controls, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>  
  
## <a name="aligning-to-form-and-container-margins"></a><span data-ttu-id="27e7e-155">에 폼과 컨테이너 여백</span><span class="sxs-lookup"><span data-stu-id="27e7e-155">Aligning to Form and Container Margins</span></span>  
 <span data-ttu-id="27e7e-156">맞춤선을 사용 하면 일관 된 방식으로 컨트롤을 폼 및 컨테이너 여백을 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-156">Snaplines help you to align your controls to form and container margins in a consistent manner.</span></span>  
  
#### <a name="to-align-controls-to-form-and-container-margins"></a><span data-ttu-id="27e7e-157">폼 및 컨테이너 여백에 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-157">To align controls to form and container margins</span></span>  
  
1.  <span data-ttu-id="27e7e-158">중 하나를 선택는 <xref:System.Windows.Forms.Button> 제어 하 고 맞춤선 나타날 때까지 폼의 오른쪽 테두리에 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-158">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="27e7e-159">오른쪽 테두리에서 계산 된 맞춤선의 거리는 컨트롤의 합계인 <xref:System.Windows.Forms.Control.Margin%2A> 속성과 양식의 <xref:System.Windows.Forms.Control.Padding%2A> 속성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-159">The snapline's distance from the right border is the sum of the control's <xref:System.Windows.Forms.Control.Margin%2A> property and the form's <xref:System.Windows.Forms.Control.Padding%2A> property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27e7e-160">하는 경우 폼의 <xref:System.Windows.Forms.Control.Padding%2A> 0,0,0,0 속성, Windows Forms 디자이너는 숨겨진 폼 제공 <xref:System.Windows.Forms.Control.Padding%2A> 9,9,9,9의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-160">If the form's <xref:System.Windows.Forms.Control.Padding%2A> property is set to 0,0,0,0, the Windows Forms Designer gives the form a shadowed <xref:System.Windows.Forms.Control.Padding%2A> value of 9,9,9,9.</span></span> <span data-ttu-id="27e7e-161">이 동작을 재정의 하려면 0,0,0,0 이외의 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-161">To override this behavior, assign a value other than 0,0,0,0.</span></span>  
  
1.  <span data-ttu-id="27e7e-162">값을 변경는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 확장은 <xref:System.Windows.Forms.Control.Margin%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성을 0입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-162">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 0.</span></span> <span data-ttu-id="27e7e-163">자세한 내용은 참조 [연습: 레이아웃으로 Windows Forms 컨트롤 Padding, Margins 및 AutoSize 속성](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-163">For details, see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md).</span></span>  
  
2.  <span data-ttu-id="27e7e-164">이동 된 <xref:System.Windows.Forms.Button> 맞춤선이 나타날 때까지 폼의 오른쪽 테두리에 가깝게 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-164">Move the <xref:System.Windows.Forms.Button> control close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="27e7e-165">이 간격은 폼의 값에서 제공 됩니다 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-165">This distance is now given by the value of the form's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>  
  
3.  <span data-ttu-id="27e7e-166">끌어서는 <xref:System.Windows.Forms.GroupBox> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-166">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="27e7e-167">값을 변경는 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 확장은 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성을 10입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-167">Change the value of the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 10.</span></span>  
  
5.  <span data-ttu-id="27e7e-168">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-168">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
6.  <span data-ttu-id="27e7e-169">이동 된 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 테두리에 가깝게는 <xref:System.Windows.Forms.GroupBox> 맞춤선이 나타날 때까지 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-169">Move the <xref:System.Windows.Forms.Button> control close to the right border of the <xref:System.Windows.Forms.GroupBox> control until a snapline appears.</span></span> <span data-ttu-id="27e7e-170">이동의 <xref:System.Windows.Forms.Button> 컨트롤 내에서 <xref:System.Windows.Forms.GroupBox> 제어 및 맞춤선 나타나는 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-170">Move the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and note where the snaplines appear.</span></span>  
  
## <a name="aligning-to-grouped-controls"></a><span data-ttu-id="27e7e-171">그룹화 된 컨트롤에 맞춤</span><span class="sxs-lookup"><span data-stu-id="27e7e-171">Aligning to Grouped Controls</span></span>  
 <span data-ttu-id="27e7e-172">맞춤선을 사용 하 여 그룹화 된 컨트롤을 맞출 수 컨트롤 내에서 뿐만 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-172">You can use snaplines to align grouped controls as well as controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
#### <a name="to-align-to-grouped-controls"></a><span data-ttu-id="27e7e-173">그룹화 된 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-173">To align to grouped controls</span></span>  
  
1.  <span data-ttu-id="27e7e-174">두 개의 폼에 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-174">Select two of the controls on your form.</span></span> <span data-ttu-id="27e7e-175">선택 영역을 이동 하 고 선택 항목 및 다른 컨트롤 사이 표시 되는 맞춤선을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-175">Move the selection around and note the snaplines that appear between your selection and the other controls.</span></span>  
  
2.  <span data-ttu-id="27e7e-176">끌어서는 <xref:System.Windows.Forms.GroupBox> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-176">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>  
  
3.  <span data-ttu-id="27e7e-177">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-177">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
4.  <span data-ttu-id="27e7e-178">중 하나를 선택는 <xref:System.Windows.Forms.Button> 컨트롤과 주위로 이동는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-178">Select one of the <xref:System.Windows.Forms.Button> controls and move it around the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="27e7e-179">참고의 가장자리에 표시 되는 맞춤선의 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-179">Note the snaplines that appear at the edges of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="27e7e-180">또한 맞춤선의 가장자리에 표시 되는 <xref:System.Windows.Forms.Button> 컨트롤에 포함 되는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-180">Also note the snaplines that appear at the edges of the <xref:System.Windows.Forms.Button> control that is contained by the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="27e7e-181">컨테이너 컨트롤의 자식 컨트롤에는 또한 맞춤선을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-181">Controls that are children of a container control also support snaplines.</span></span>  
  
## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="27e7e-182">맞춤선을 사용 하 여 크기로 윤곽선 지정 하 여 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-182">Using Snaplines to Place a Control by Outlining Its Size</span></span>  
 <span data-ttu-id="27e7e-183">맞춤선 정렬 때 처음 배치 하는 폼에서 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-183">Snaplines help you align controls when you first place them on a form.</span></span>  
  
#### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="27e7e-184">크기로 윤곽선 지정 하 여 컨트롤을 배치 하려면 맞춤선을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-184">To use snaplines to place a control by outlining its size</span></span>  
  
1.  <span data-ttu-id="27e7e-185">**도구 상자**에서 <xref:System.Windows.Forms.Button> 컨트롤 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-185">In the **Toolbox**, click the <xref:System.Windows.Forms.Button> control icon.</span></span> <span data-ttu-id="27e7e-186">폼으로 끌어다 놓지 마세요.</span><span class="sxs-lookup"><span data-stu-id="27e7e-186">Do not drag it onto the form.</span></span>  
  
2.  <span data-ttu-id="27e7e-187">폼의 디자인 화면 위로 마우스 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-187">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="27e7e-188">포인터가 <xref:System.Windows.Forms.Button> 컨트롤 아이콘이 연결된 십자형으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-188">Note that the pointer changes to a crosshair with the <xref:System.Windows.Forms.Button> control icon attached.</span></span> <span data-ttu-id="27e7e-189">또한 맞춤선 맞춤된 위치를 제안에 게 표시 되는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-189">Also note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
3.  <span data-ttu-id="27e7e-190">마우스 단추를 길게 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-190">Click and hold the mouse button.</span></span>  
  
4.  <span data-ttu-id="27e7e-191">폼에서 마우스 포인터를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-191">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="27e7e-192">참고 개요 그려짐을, 위치 및 컨트롤의 크기를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-192">Note that an outline is drawn, indicating the position and the size of the control.</span></span>  
  
5.  <span data-ttu-id="27e7e-193">폼에 다른 컨트롤과 맞춰질 때까지 포인터를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-193">Drag the pointer until it aligns with another control on the form.</span></span> <span data-ttu-id="27e7e-194">맞춤을 나타내는 맞춤선 나타나는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-194">Note that a snapline appears to indicate alignment.</span></span>  
  
6.  <span data-ttu-id="27e7e-195">마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-195">Release the mouse button.</span></span> <span data-ttu-id="27e7e-196">컨트롤의 윤곽선으로 표시 되는 크기와 위치에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-196">The control is created at the position and size indicated by the outline.</span></span>  
  
## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="27e7e-197">도구 상자에서 컨트롤을 끌어 올 때 맞춤선을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="27e7e-197">Using Snaplines When Dragging a Control from the Toolbox</span></span>  
 <span data-ttu-id="27e7e-198">맞춤선 정렬 컨트롤을 끌어 올 때에서 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-198">Snaplines help you align controls when you drag them from the **Toolbox** onto your form.</span></span>  
  
#### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="27e7e-199">도구 상자에서 컨트롤을 끌어 올 때 맞춤선을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-199">To use snaplines when dragging a control from the Toolbox</span></span>  
  
1.  <span data-ttu-id="27e7e-200">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에서 폼으로 하지만 마우스 단추를 해제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form, but do not release the mouse button.</span></span>  
  
2.  <span data-ttu-id="27e7e-201">폼의 디자인 화면 위로 마우스 포인터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-201">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="27e7e-202">포인터가 변경 되는 위치를 나타내는 새 <xref:System.Windows.Forms.Button> 컨트롤 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-202">Note that the pointer changes to indicate the position at which the new <xref:System.Windows.Forms.Button> control will be created.</span></span>  
  
3.  <span data-ttu-id="27e7e-203">폼에서 마우스 포인터를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-203">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="27e7e-204">맞춤선에 대 한 맞춤된 위치를 제안에 게 표시 되는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-204">Note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="27e7e-205">다른 컨트롤에 정렬 되는 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-205">Find a position that is aligned with other controls.</span></span>  
  
4.  <span data-ttu-id="27e7e-206">마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-206">Release the mouse button.</span></span> <span data-ttu-id="27e7e-207">컨트롤이 맞춤선 나타내는 위치에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-207">The control is created at the position indicated by the snaplines.</span></span>  
  
## <a name="resizing-controls-using-snaplines"></a><span data-ttu-id="27e7e-208">맞춤선을 사용 하 여 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="27e7e-208">Resizing Controls Using Snaplines</span></span>  
 <span data-ttu-id="27e7e-209">맞춤선 하는 데 도움이 크기를 조정할 때 컨트롤을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-209">Snaplines help you align controls as you resize them.</span></span>  
  
#### <a name="to-resize-a-control-using-snaplines"></a><span data-ttu-id="27e7e-210">맞춤선을 사용 하는 컨트롤의 크기를 조정 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-210">To resize a control using snaplines</span></span>  
  
1.  <span data-ttu-id="27e7e-211">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-211">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="27e7e-212">크기 조정의 <xref:System.Windows.Forms.Button> 모퉁이 끌어서 크기 조정 핸들 중 하나를 선택 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-212">Resize the <xref:System.Windows.Forms.Button> control by grabbing one of the corner sizing handles and dragging.</span></span> <span data-ttu-id="27e7e-213">자세한 내용은 참조 [하는 방법: Windows Forms에서 컨트롤의 크기를 조정](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-213">For details, see [How to: Resize Controls on Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="27e7e-214">중 하나가 때까지 크기 조정 핸들을 끌어는 <xref:System.Windows.Forms.Button> 컨트롤의 테두리는 다른 컨트롤과 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-214">Drag the sizing handle until one of the <xref:System.Windows.Forms.Button> control's borders is aligned with another control.</span></span> <span data-ttu-id="27e7e-215">맞춤선 나타나는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-215">Note that a snapline appears.</span></span> <span data-ttu-id="27e7e-216">또한 메모를 크기 조정 핸들 맞춤선으로 지정 된 위치에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-216">Also note that the sizing handle snaps to the position indicated by the snapline.</span></span>  
  
4.  <span data-ttu-id="27e7e-217">크기 조정 된 <xref:System.Windows.Forms.Button> 방향을 제어 하 고 크기 조정 핸들을 다른 컨트롤에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-217">Resize the <xref:System.Windows.Forms.Button> control in different directions and align the sizing handle to different controls.</span></span> <span data-ttu-id="27e7e-218">Note 맞춤선 맞춤을 나타내는 다양 한 방향에 표시 되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-218">Note how the snaplines appear in various orientations to indicate alignment.</span></span>  
  
## <a name="aligning-a-label-to-a-controls-text"></a><span data-ttu-id="27e7e-219">컨트롤의 텍스트에 레이블 맞춤</span><span class="sxs-lookup"><span data-stu-id="27e7e-219">Aligning a Label to a Control's Text</span></span>  
 <span data-ttu-id="27e7e-220">일부 컨트롤은 다른 컨트롤에 표시 된 텍스트 정렬을 위한 맞춤선을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-220">Some controls offer a snapline for aligning other controls to displayed text.</span></span>  
  
#### <a name="to-align-a-label-to-a-controls-text"></a><span data-ttu-id="27e7e-221">컨트롤의 텍스트에 레이블을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-221">To align a label to a control's text</span></span>  
  
1.  <span data-ttu-id="27e7e-222">끌어서는 <xref:System.Windows.Forms.TextBox> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-222">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="27e7e-223">삭제할 경우는 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼으로, 스마트 태그 문자 모양을 클릭 하 고, 선택는 **텍스트 textBox1를 설정할** 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-223">When you drop the <xref:System.Windows.Forms.TextBox> control onto the form, click the smart-tag glyph and select the **Set text to textBox1** option.</span></span> <span data-ttu-id="27e7e-224">자세한 내용은 참조 [연습: 수행 일반적인 태스크를 사용 하 여 스마트 태그를 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-224">For details, see [Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md).</span></span>  
  
2.  <span data-ttu-id="27e7e-225">끌어서는 <xref:System.Windows.Forms.Label> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-225">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto your form.</span></span>  
  
3.  <span data-ttu-id="27e7e-226"><xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-226">Change the value of the <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="27e7e-227">참고가 컨트롤의 테두리 표시 텍스트에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-227">Note that the control's borders are adjusted to fit the display text.</span></span>  
  
4.  <span data-ttu-id="27e7e-228">이동의 <xref:System.Windows.Forms.Label> 컨트롤의 왼쪽에는 <xref:System.Windows.Forms.TextBox> 의 아래쪽 가장자리에 맞춥니다 이므로 컨트롤는 <xref:System.Windows.Forms.TextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-228">Move the <xref:System.Windows.Forms.Label> control to the left of the <xref:System.Windows.Forms.TextBox> control, so it is aligned with the bottom edge of the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="27e7e-229">두 컨트롤의 아래쪽 가장자리를 따라 나타나는 맞춤선을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-229">Note the snapline that appears along the bottom edges of the two controls.</span></span>  
  
5.  <span data-ttu-id="27e7e-230">이동의 <xref:System.Windows.Forms.Label> 제어 될 때까지 상향 약간는 <xref:System.Windows.Forms.Label> 텍스트 및 <xref:System.Windows.Forms.TextBox> 텍스트를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-230">Move the <xref:System.Windows.Forms.Label> control slightly upward, until the <xref:System.Windows.Forms.Label> text and the <xref:System.Windows.Forms.TextBox> text are aligned.</span></span> <span data-ttu-id="27e7e-231">두 컨트롤의 텍스트 필드 맞춰진 경우를 나타내는 표시 하는 다른 스타일된 맞춤선을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-231">Note the differently styled snapline that appears, indicating when the text fields of both controls are aligned.</span></span>  
  
## <a name="using-snaplines-with-keyboard-navigation"></a><span data-ttu-id="27e7e-232">맞춤선을 사용 하 여 키보드 탐색</span><span class="sxs-lookup"><span data-stu-id="27e7e-232">Using Snaplines with Keyboard Navigation</span></span>  
 <span data-ttu-id="27e7e-233">맞춤선 정렬 키보드의 화살표 키를 사용 하 여 정렬할 때 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-233">Snaplines help you align controls when you are arranging them using the keyboard's arrow keys.</span></span>  
  
#### <a name="to-use-snaplines-with-keyboard-navigation"></a><span data-ttu-id="27e7e-234">키보드 탐색 맞춤선을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-234">To use snaplines with keyboard navigation</span></span>  
  
1.  <span data-ttu-id="27e7e-235">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-235">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="27e7e-236">폼의 왼쪽 위 모퉁이에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-236">Place it in the upper-left corner of the form.</span></span>  
  
2.  <span data-ttu-id="27e7e-237">CTRL + 아래쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-237">Press CTRL+DOWN ARROW.</span></span> <span data-ttu-id="27e7e-238">첫 번째 사용 가능한 가로 맞춤 위치로 컨트롤을 폼 아래로 이동 하는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-238">Note that the control moves down the form to the first available horizontal alignment position.</span></span>  
  
3.  <span data-ttu-id="27e7e-239">컨트롤이 폼의 맨 아래에 도달할 때까지 CTRL + 아래쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-239">Press CTRL+DOWN ARROW until the control reaches the bottom of the form.</span></span> <span data-ttu-id="27e7e-240">Note 양식을 아래로 이동할 때 컨트롤의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-240">Note the positions it occupies as it moves down the form.</span></span>  
  
4.  <span data-ttu-id="27e7e-241">CTRL + 오른쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-241">Press CTRL+RIGHT ARROW.</span></span> <span data-ttu-id="27e7e-242">컨트롤의 첫 번째 세로 맞춤을 사용할 수 있는 위치로 폼으로 이동 하는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-242">Note that the control moves across the form to the first available vertical alignment position.</span></span>  
  
5.  <span data-ttu-id="27e7e-243">컨트롤이 폼의 측면에 도달할 때까지 CTRL + 오른쪽 화살표를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-243">Press CTRL+RIGHT ARROW until the control reaches the side of the form.</span></span> <span data-ttu-id="27e7e-244">폼에서 이동할 때 컨트롤의 위치를 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-244">Note the positions it occupies as it moves across the form.</span></span>  
  
6.  <span data-ttu-id="27e7e-245">화살표 키의 조합으로 컨트롤을 폼 주위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-245">Move the control around the form with a combination of arrow keys.</span></span> <span data-ttu-id="27e7e-246">컨트롤이 차지 하는 위치를 확인 하 고 맞춤선을 함께 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-246">Note the positions the control occupies and the snaplines that accompany them.</span></span>  
  
7.  <span data-ttu-id="27e7e-247">크기를 조정 하려면 SHIFT + 화살표 키를 눌러는 <xref:System.Windows.Forms.Button> 하나의 픽셀 단위로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-247">Press SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control by increments of one pixel.</span></span>  
  
8.  <span data-ttu-id="27e7e-248">크기를 조정 하려면 CTRL + SHIFT + 모든 화살표 키를 눌러는 <xref:System.Windows.Forms.Button> 맞춤선 단위로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-248">Press CTRL+SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control in snapline increments.</span></span>  
  
## <a name="snaplines-and-layout-panels"></a><span data-ttu-id="27e7e-249">맞춤선 및 레이아웃 패널</span><span class="sxs-lookup"><span data-stu-id="27e7e-249">Snaplines and Layout Panels</span></span>  
 <span data-ttu-id="27e7e-250">맞춤선은 레이아웃 패널 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-250">Snaplines are disabled within layout panels.</span></span>  
  
#### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="27e7e-251">맞춤선을 선택적으로 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-251">To selectively disable snaplines</span></span>  
  
1.  <span data-ttu-id="27e7e-252">끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-252">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="27e7e-253"><xref:System.Windows.Forms.Button> 도구 상자 **에서**컨트롤 아이콘을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-253">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox**.</span></span> <span data-ttu-id="27e7e-254">참고 새 단추 컨트롤에 표시 되는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 첫 번째 셀입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-254">Note that a new button control appears in the <xref:System.Windows.Forms.TableLayoutPanel> control's first cell.</span></span>  
  
3.  <span data-ttu-id="27e7e-255">두 번 클릭 하 고 <xref:System.Windows.Forms.Button> 컨트롤 아이콘은 **도구 상자** 두 번 더 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-255">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox** twice more.</span></span> <span data-ttu-id="27e7e-256">이 방법에서 빈 셀이 하나는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-256">This leaves one empty cell in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="27e7e-257">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 의 빈 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-257">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the empty cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="27e7e-258">참고 맞춤선이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-258">Note that no snaplines appear.</span></span>  
  
5.  <span data-ttu-id="27e7e-259">끌어서는 <xref:System.Windows.Forms.Button> 의 제어는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 하 고 주위로 이동는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-259">Drag the <xref:System.Windows.Forms.Button> control out of the <xref:System.Windows.Forms.TableLayoutPanel> control and move it around the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="27e7e-260">맞춤선이 다시 나타납니다 유의 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-260">Note that snaplines appear again.</span></span>  
  
## <a name="disabling-snaplines"></a><span data-ttu-id="27e7e-261">맞춤선을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="27e7e-261">Disabling Snaplines</span></span>  
 <span data-ttu-id="27e7e-262">맞춤선은 기본적으로 켜 집니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-262">Snaplines are turned on by default.</span></span> <span data-ttu-id="27e7e-263">맞춤선을 선택적으로 해제할 수 있습니다 또는 디자인 환경에서 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-263">You can disable snaplines selectively, or you can disable them in the design environment.</span></span>  
  
#### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="27e7e-264">맞춤선을 선택적으로 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-264">To selectively disable snaplines</span></span>  
  
-   <span data-ttu-id="27e7e-265">ALT 키를 누르고 주위 폼 컨트롤을 이동 하는 동안 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-265">Press the ALT key and while moving a control around the form.</span></span>  
  
     <span data-ttu-id="27e7e-266">Note 맞춤선이 나타나지 않고 및 가능한 맞춤 위치에 컨트롤 맞춤 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-266">Note that no snaplines appear and the control does not snap to any potential alignment positions.</span></span>  
  
#### <a name="to-disable-snaplines-in-the-design-environment"></a><span data-ttu-id="27e7e-267">디자인 환경에서 맞춤선을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="27e7e-267">To disable snaplines in the design environment</span></span>  
  
1.  <span data-ttu-id="27e7e-268">**도구** 메뉴를 열고는 **옵션** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="27e7e-268">From the **Tools** menu, open the **Options** dialog box.</span></span> <span data-ttu-id="27e7e-269">Windows Forms 디자이너 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-269">Open the Windows Forms Designer dialog box.</span></span> <span data-ttu-id="27e7e-270">자세한 내용은 참조 [Windows Forms 디자이너, 옵션 대화 상자, 일반](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-270">For details, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834).</span></span>  
  
2.  <span data-ttu-id="27e7e-271">선택 된 **일반** 노드.</span><span class="sxs-lookup"><span data-stu-id="27e7e-271">Select the **General** node.</span></span> <span data-ttu-id="27e7e-272">에 **레이아웃 모드** 섹션, 선택을 변경 **맞춤선** 를 **SnapToGrid**합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-272">In the **Layout Mode** section, change the selection from **SnapLines** to **SnapToGrid**.</span></span>  
  
3.  <span data-ttu-id="27e7e-273">설정을 적용 하려면 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-273">Click OK to apply the setting.</span></span>  
  
4.  <span data-ttu-id="27e7e-274">폼에 컨트롤을 선택 하 고 다른 컨트롤 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-274">Select a control on your form and move it around the other controls.</span></span> <span data-ttu-id="27e7e-275">맞춤선 나타나지 않는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-275">Note that snaplines do not appear.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="27e7e-276">다음 단계</span><span class="sxs-lookup"><span data-stu-id="27e7e-276">Next Steps</span></span>  
 <span data-ttu-id="27e7e-277">맞춤선에 폼 컨트롤을 정렬 하는 직관적인 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-277">Snaplines offer an intuitive means of aligning controls on your form.</span></span> <span data-ttu-id="27e7e-278">다음과 같은 사항을 더 살펴보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-278">Suggestions for more exploration include:</span></span>  
  
-   <span data-ttu-id="27e7e-279">중첩 시도 <xref:System.Windows.Forms.GroupBox> 컨트롤 내에 다른 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-279">Try nesting a <xref:System.Windows.Forms.GroupBox> control within another <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="27e7e-280">위치는 <xref:System.Windows.Forms.Button> 자식 내에서 컨트롤 <xref:System.Windows.Forms.GroupBox> 컨트롤과 부모 내의 다른 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-280">Place a <xref:System.Windows.Forms.Button> control within the child <xref:System.Windows.Forms.GroupBox> control, and another within the parent <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="27e7e-281">이동 된 <xref:System.Windows.Forms.Button> 컨트롤을 맞춤선 컨테이너 경계를 교차 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27e7e-281">Move the <xref:System.Windows.Forms.Button> controls around to see how the snaplines cross container boundaries.</span></span>  
  
-   <span data-ttu-id="27e7e-282">열을 만들 <xref:System.Windows.Forms.TextBox> 컨트롤 및 해당 열 <xref:System.Windows.Forms.Label> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-282">Create a column of <xref:System.Windows.Forms.TextBox> controls and a corresponding column of <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="27e7e-283">값으로 설정 된 <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-283">Set the value of the <xref:System.Windows.Forms.Label> controls' <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="27e7e-284">맞춤선을 사용 하 여 이동 된 <xref:System.Windows.Forms.Label> 컨트롤의 표시 된 텍스트의 텍스트를 맞춥니다는 <xref:System.Windows.Forms.TextBox> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-284">Use snaplines to move the <xref:System.Windows.Forms.Label> controls so their displayed text is aligned with the text in the <xref:System.Windows.Forms.TextBox> controls.</span></span>  
  
 <span data-ttu-id="27e7e-285">Windows 사용자 인터페이스 디자인에 대 한 내용은 책을 참조 하십시오. *Microsoft Windows User Experience, Official Guidelines 사용자 인터페이스 개발자 및 디자이너에 대 한* Redmond, WA: Microsoft Press, 1999 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e7e-285">For information about Windows user interface design, see the book *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999.</span></span> <span data-ttu-id="27e7e-286">(USBN: 0-7356-0566-1).</span><span class="sxs-lookup"><span data-stu-id="27e7e-286">(USBN: 0-7356-0566-1).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e7e-287">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27e7e-287">See Also</span></span>  
 <xref:System.Windows.Forms.Design.Behavior.SnapLine>  
 [<span data-ttu-id="27e7e-288">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="27e7e-288">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="27e7e-289">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="27e7e-289">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="27e7e-290">연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="27e7e-290">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)  
 [<span data-ttu-id="27e7e-291">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="27e7e-291">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
