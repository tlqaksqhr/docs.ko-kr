---
title: "연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ccd5379d9594ccab02b80fd5fbdba0b202e1c69
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="0f177-102">연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="0f177-102">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>
<span data-ttu-id="0f177-103">폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="0f177-104">**Windows Forms 디자이너** 이를 위해 여러 레이아웃 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-104">The **Windows Forms Designer** gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="0f177-105">가장 중요 한 중 3 개는 <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 모든 Windows Forms 컨트롤에 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>  
  
 <span data-ttu-id="0f177-106"><xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="0f177-107"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="0f177-108">다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="0f177-109">![안쪽 여백 및 여백을 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="0f177-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="0f177-110"><xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 있으면 자동으로 크기를 자동으로 해당 콘텐츠를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="0f177-111">해당 컨트롤의 원래 값 보다 작게 크기가 조정 되지는 <xref:System.Windows.Forms.Control.Size%2A> 속성과 값을 고려 합니다 해당 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>  
  
 <span data-ttu-id="0f177-112">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-112">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="0f177-113">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0f177-113">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="0f177-114">컨트롤에 대 한 여백 설정</span><span class="sxs-lookup"><span data-stu-id="0f177-114">Setting Margins for Your Controls</span></span>  
  
-   <span data-ttu-id="0f177-115">컨트롤에 안쪽 여백 설정</span><span class="sxs-lookup"><span data-stu-id="0f177-115">Setting Padding for Your Controls</span></span>  
  
-   <span data-ttu-id="0f177-116">자동으로 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="0f177-116">Automatically Sizing Your Controls</span></span>  
  
 <span data-ttu-id="0f177-117">작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-117">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f177-118">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-118">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0f177-119">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-119">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0f177-120">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f177-120">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f177-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0f177-121">Prerequisites</span></span>  
 <span data-ttu-id="0f177-122">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-122">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="0f177-123">충분 한 권한이을 만들고 Visual Studio가 설치 된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-123">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="0f177-124">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0f177-124">Creating the Project</span></span>  
 <span data-ttu-id="0f177-125">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-125">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="0f177-126">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="0f177-126">To create the project</span></span>  
  
1.  <span data-ttu-id="0f177-127">만들기는 **Windows 응용 프로그램** 라는 프로젝트 `LayoutExample`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-127">Create a **Windows Application** project called `LayoutExample`.</span></span> <span data-ttu-id="0f177-128">자세한 내용은 참조 [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-128">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) .</span></span>  
  
2.  <span data-ttu-id="0f177-129">폼을 선택는 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-129">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="setting-margins-for-your-controls"></a><span data-ttu-id="0f177-130">컨트롤에 대 한 여백 설정</span><span class="sxs-lookup"><span data-stu-id="0f177-130">Setting Margins for Your Controls</span></span>  
 <span data-ttu-id="0f177-131">사용 하 여 컨트롤 사이의 기본 간격을 설정할 수 있습니다는 <xref:System.Windows.Forms.Control.Margin%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-131">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="0f177-132">컨트롤을 이동 하는 경우 다른 컨트롤에 가까이, 두 컨트롤의 여백을 보여 주는 맞춤선 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-132">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="0f177-133">이동 하는 컨트롤 여백으로 정의 된 거리에도 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-133">The control you are moving will also snap to the distance defined by the margins.</span></span>  
  
#### <a name="to-arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="0f177-134">Margin 속성을 사용 하 여 폼에 컨트롤을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="0f177-134">To arrange controls on your form using the Margin property</span></span>  
  
1.  <span data-ttu-id="0f177-135">두 개 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-135">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0f177-136">중 하나를 선택는 <xref:System.Windows.Forms.Button> 제어 하 고 거의 닿는 될 때까지 다른 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-136">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>  
  
     <span data-ttu-id="0f177-137">서로 표시 되는 맞춤선을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-137">Observe the snapline that appears between them.</span></span> <span data-ttu-id="0f177-138">이 길이 두 컨트롤의 합계인 <xref:System.Windows.Forms.Control.Margin%2A> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-138">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="0f177-139">이동 하는이 간격에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-139">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="0f177-140">자세한 내용은 참조 [연습: 맞춤선 Windows Forms에서 사용 하 여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-140">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
3.  <span data-ttu-id="0f177-141">변경의 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 확장 하 여 컨트롤 중 하나는 <xref:System.Windows.Forms.Control.Margin%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성 20 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-141">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 20.</span></span>  
  
4.  <span data-ttu-id="0f177-142">중 하나를 선택는 <xref:System.Windows.Forms.Button> 제어 하 고 다른 가깝게 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-142">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>  
  
     <span data-ttu-id="0f177-143">맞춤선 정의 하는 여백 값의 합이 긴 및 다른 컨트롤에서 멀리에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-143">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>  
  
5.  <span data-ttu-id="0f177-144">변경은 <xref:System.Windows.Forms.Control.Margin%2A> 를 확장 하 여 선택한 컨트롤의 속성은 <xref:System.Windows.Forms.Control.Margin%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.Top%2A> 속성을 5로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-144">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to 5.</span></span>  
  
6.  <span data-ttu-id="0f177-145">다른 컨트롤의 아래쪽 선택한 컨트롤을 이동 하 고 맞춤선은 짧은 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-145">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="0f177-146">다른 컨트롤의 왼쪽에 선택 된 컨트롤을 이동 하 고 맞춤선 4 단계에서 관찰 된 값을 유지 하도록 관찰 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-146">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>  
  
7.  <span data-ttu-id="0f177-147">각각의 측면을 설정할 수 있습니다는 <xref:System.Windows.Forms.Control.Margin%2A> 속성 <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, 다른 값 또는 있습니다 값과 동일한 값에 모두 설정할 수는 <xref:System.Windows.Forms.Padding.All%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-147">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>  
  
## <a name="setting-padding-for-your-controls"></a><span data-ttu-id="0f177-148">컨트롤에 안쪽 여백 설정</span><span class="sxs-lookup"><span data-stu-id="0f177-148">Setting Padding for Your Controls</span></span>  
 <span data-ttu-id="0f177-149">응용 프로그램에 필요한 정확한 레이아웃을 얻기 위해 컨트롤 자식 컨트롤이 종종 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-149">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="0f177-150">부모 컨트롤의 테두리에 대 한 자식 컨트롤의 테두리의 근접 단어를 지정 하려는 경우 부모 컨트롤을 사용 하 여 <xref:System.Windows.Forms.Control.Padding%2A> 속성과 함께 자식 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-150">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="0f177-151"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 콘텐츠 근접 단어를 제어 하려면 또한 사용 (예를 들어 한 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성) 해당 테두리입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-151">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>  
  
#### <a name="to-arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="0f177-152">패딩을 사용 하 여 폼에 컨트롤을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="0f177-152">To arrange controls on your form using padding</span></span>  
  
1.  <span data-ttu-id="0f177-153">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-153">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0f177-154"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-154">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="0f177-155">변경의 <xref:System.Windows.Forms.Control.Padding%2A> 확장은 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성을 5로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-155">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 5.</span></span>  
  
     <span data-ttu-id="0f177-156">컨트롤 확장 새 안쪽 여백에 확보 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-156">The control expands to provide room for the new padding.</span></span>  
  
4.  <span data-ttu-id="0f177-157">끌어서는 <xref:System.Windows.Forms.GroupBox> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-157">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="0f177-158">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-158">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="0f177-159">위치는 <xref:System.Windows.Forms.Button> 의 오른쪽 아래 모퉁이에 맞도록 제어는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-159">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>  
  
     <span data-ttu-id="0f177-160">로 표시 되는 맞춤선을 관찰는 <xref:System.Windows.Forms.Button> 아래쪽 및 오른쪽 테두리의 가까워질는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-160">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="0f177-161">에 해당 하는 이러한 맞춤선의 <xref:System.Windows.Forms.Control.Margin%2A> 의 속성은 <xref:System.Windows.Forms.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-161">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>  
  
5.  <span data-ttu-id="0f177-162">변경의 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 확장은 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성 20 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-162">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 20.</span></span>  
  
6.  <span data-ttu-id="0f177-163">선택의 <xref:System.Windows.Forms.Button> 컨트롤 내에서 <xref:System.Windows.Forms.GroupBox> 제어의 중심 쪽으로 이동 하 고는 <xref:System.Windows.Forms.GroupBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-163">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>  
  
     <span data-ttu-id="0f177-164">맞춤선의 테두리에서 큰 거리 만큼 떨어진 표시는 <xref:System.Windows.Forms.GroupBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-164">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="0f177-165">이 길이의 합계는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Margin%2A> 속성 및 <xref:System.Windows.Forms.GroupBox> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-165">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>  
  
## <a name="automatically-sizing-your-controls"></a><span data-ttu-id="0f177-166">자동으로 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="0f177-166">Automatically Sizing Your Controls</span></span>  
 <span data-ttu-id="0f177-167">일부 응용 프로그램에서 컨트롤의 크기가 됩니다 동일한 실행 시 디자인 타임에 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-167">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="0f177-168">텍스트는 <xref:System.Windows.Forms.Button> 컨트롤, 예를 들어에서 가져올 수 있지만 데이터베이스 및 길이 미리 알 수 없는 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-168">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length will not be known in advance.</span></span>  
  
 <span data-ttu-id="0f177-169">경우는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이로 설정 되어 `true`, 컨트롤이 해당 내용에 크기가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-169">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="0f177-170">자세한 내용은 참조 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-170">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
#### <a name="to-arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="0f177-171">AutoSize 속성을 사용 하 여 양식에 컨트롤을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="0f177-171">To arrange controls on your form using the AutoSize property</span></span>  
  
1.  <span data-ttu-id="0f177-172">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-172">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0f177-173"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-173">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="0f177-174">변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추에 Text 속성에 대 한 긴 문자열**."</span><span class="sxs-lookup"><span data-stu-id="0f177-174">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property**."</span></span>  
  
     <span data-ttu-id="0f177-175">변경 내용을 커밋하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤 새 텍스트에 맞게 자신의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-175">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>  
  
4.  <span data-ttu-id="0f177-176">다른 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-176">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>  
  
5.  <span data-ttu-id="0f177-177">변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추에 Text 속성에 대 한 긴 문자열.**"</span><span class="sxs-lookup"><span data-stu-id="0f177-177">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>  
  
     <span data-ttu-id="0f177-178">변경 내용을 커밋하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤 자체를 조정 하지 않는 및 텍스트 컨트롤의 오른쪽 가장자리에서 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-178">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>  
  
6.  <span data-ttu-id="0f177-179">변경의 <xref:System.Windows.Forms.Control.Padding%2A> 확장은 <xref:System.Windows.Forms.Control.Padding%2A> 항목에는 **속성** 창과 설정은 <xref:System.Windows.Forms.Padding.All%2A> 속성을 5로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-179">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 5.</span></span>  
  
     <span data-ttu-id="0f177-180">이 컨트롤의 안쪽에 있는 텍스트 네 면에서 모두 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-180">The text in the control's interior is clipped on all four sides.</span></span>  
  
7.  <span data-ttu-id="0f177-181">변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-181">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="0f177-182"><xref:System.Windows.Forms.Button> 컨트롤 크기를 조정 하는 전체 문자열을 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-182">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="0f177-183">텍스트, 주변에 안쪽 여백을 추가 또한 일으키는 <xref:System.Windows.Forms.Button> 컨트롤 네 방향으로 확장을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-183">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>  
  
8.  <span data-ttu-id="0f177-184">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-184">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="0f177-185">폼의 오른쪽 아래 모서리 가까이 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-185">Position it near the lower-right corner of the form.</span></span>  
  
9. <span data-ttu-id="0f177-186"><xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-186">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
10. <span data-ttu-id="0f177-187">설정의 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-187">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>  
  
11. <span data-ttu-id="0f177-188">변경 된 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 "**이 단추에 Text 속성에 대 한 긴 문자열.**"</span><span class="sxs-lookup"><span data-stu-id="0f177-188">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>  
  
     <span data-ttu-id="0f177-189">변경 내용을 커밋하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤 왼쪽으로 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-189">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="0f177-190">일반적으로 자동 크기 조정 반대 방향에서 컨트롤의 크기가 늘어납니다 해당 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-190">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>  
  
## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="0f177-191">AutoSize 및 AutoSizeMode 속성</span><span class="sxs-lookup"><span data-stu-id="0f177-191">AutoSize and AutoSizeMode Properties</span></span>  
 <span data-ttu-id="0f177-192">일부 컨트롤은 지원는 `AutoSizeMode` 속성을 컨트롤의 자동 크기 조정 동작을 보다 세분화 된 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-192">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>  
  
#### <a name="to-use-the-autosizemode-property"></a><span data-ttu-id="0f177-193">AutoSizeMode 속성을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="0f177-193">To use the AutoSizeMode property</span></span>  
  
1.  <span data-ttu-id="0f177-194">끌어서는 <xref:System.Windows.Forms.Panel> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-194">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="0f177-195">값으로 설정 된 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-195">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="0f177-196">끌어서는 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 에 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-196">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
4.  <span data-ttu-id="0f177-197">위치는 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 아래 모퉁이 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-197">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
5.  <span data-ttu-id="0f177-198">선택 된 <xref:System.Windows.Forms.Panel> 제어 하 고 오른쪽 아래 크기 조정 핸들을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-198">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="0f177-199">크기 조정의 <xref:System.Windows.Forms.Panel> 컨트롤이 장기 및 단기 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-199">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f177-200">자유롭게 조정할 수 있습니다는 <xref:System.Windows.Forms.Panel> 컨트롤 있지만 없습니다 크기의 위치 보다 작은 <xref:System.Windows.Forms.Button> 컨트롤의 오른쪽 아래 모서리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-200">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="0f177-201">이 동작의 기본 값으로 지정 된 된 `AutoSizeMode` 속성, 즉 <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-201">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>  
  
6.  <span data-ttu-id="0f177-202">값으로 설정 된 <xref:System.Windows.Forms.Panel> 컨트롤의 `AutoSizeMode` 속성을 <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-202">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>  
  
     <span data-ttu-id="0f177-203"><xref:System.Windows.Forms.Panel> 컨트롤 크기를 묶는 자체는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-203">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="0f177-204">크기를 조정할 수 없습니다는 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-204">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
7.  <span data-ttu-id="0f177-205">끌어서는 <xref:System.Windows.Forms.Button> 컨트롤의 왼쪽 위 모서리 쪽으로 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-205">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>  
  
     <span data-ttu-id="0f177-206"><xref:System.Windows.Forms.Panel> 에 컨트롤 크기가 조정 되는 <xref:System.Windows.Forms.Button> 컨트롤의 새 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-206">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0f177-207">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0f177-207">Next Steps</span></span>  
 <span data-ttu-id="0f177-208">Windows Forms 응용 프로그램에서 컨트롤 정렬에 대 한 다른 레이아웃 기능이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-208">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="0f177-209">다음은 일부 조합이 해 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-209">Here are some combinations you might try:</span></span>  
  
-   <span data-ttu-id="0f177-210">사용 하 여 양식을 작성 한 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-210">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="0f177-211">자세한 내용은 참조 [연습: Windows Forms 사용 하 여 TableLayoutPanel에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-211">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="0f177-212">값을 변경는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성으로 <xref:System.Windows.Forms.Control.Margin%2A> 해당 자식 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-212">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>  
  
-   <span data-ttu-id="0f177-213">사용 하 여 같은 실험 시도 <xref:System.Windows.Forms.FlowLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-213">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="0f177-214">자세한 내용은 참조 [연습: Windows Forms 사용 하 여 FlowLayoutPanel에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-214">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
-   <span data-ttu-id="0f177-215">자식 컨트롤에 도킹 된 실험 한 <xref:System.Windows.Forms.Panel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-215">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="0f177-216"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 보다 일반적으로 구현한은 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> 속성을 만족 하는 사용자가 직접 자식 컨트롤에 삽입 하 여 대/소문자 인지는 <xref:System.Windows.Forms.Panel> 컨트롤과 자식 컨트롤의 설정 <xref:System.Windows.Forms.Control.Dock%2A> 속성 를<xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="0f177-216">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="0f177-217">설정의 <xref:System.Windows.Forms.Panel> 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 다양 한 값과 미치는 영향을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f177-217">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f177-218">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f177-218">See Also</span></span>  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 [<span data-ttu-id="0f177-219">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="0f177-219">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="0f177-220">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="0f177-220">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="0f177-221">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="0f177-221">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="0f177-222">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="0f177-222">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
