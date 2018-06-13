---
title: '연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 2d2443f1f7153ed35aecbbb9d69c9e1421269e24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541608"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="fe6f8-102">연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="fe6f8-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="fe6f8-103">응용 프로그램을 제공할 수 있습니다 <xref:System.Windows.Forms.ToolStrip> 에서 파생 되는 고유한 클래스를 작성 하 여 전문적인 모양과 동작을 제어는 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="fe6f8-104">이 연습에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStrip> 비슷한 복합 컨트롤을 만드는 컨트롤은 **탐색 창** Microsoft® Outlook®에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="fe6f8-105">같은 작업을이 연습에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="fe6f8-106">Windows 컨트롤 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="fe6f8-107">StackView 컨트롤을 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="fe6f8-108">사용자 지정 렌더러를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="fe6f8-109">작업을 완료 하는 경우 Microsoft Office® XP 컨트롤의 전문적인 모양으로 다시 사용할 수 있는 사용자 지정 클라이언트 제어를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="fe6f8-110">단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe6f8-111">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fe6f8-112">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fe6f8-113">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-113">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fe6f8-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="fe6f8-114">Prerequisites</span></span>  
 <span data-ttu-id="fe6f8-115">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="fe6f8-116">충분 한 권한이을 만들고 Visual Studio가 설치 된 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="fe6f8-117">Windows 컨트롤 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="fe6f8-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="fe6f8-118">첫 번째 단계는 컨트롤 라이브러리 프로젝트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="fe6f8-119">컨트롤 라이브러리 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="fe6f8-119">To create the control library project</span></span>  
  
1.  <span data-ttu-id="fe6f8-120">라는 새 Windows 컨트롤 라이브러리 프로젝트를 만듭니다 `StackViewLibrary`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2.  <span data-ttu-id="fe6f8-121">**솔루션 탐색기**, 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1.vb", 원본 파일을 삭제 하 여 프로젝트의 기본 컨트롤을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="fe6f8-122">자세한 내용은 참조 [NIB: 방법: 제거, 삭제 및 항목 제외](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-122">For more information, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
3.  <span data-ttu-id="fe6f8-123">새로 추가 <xref:System.Windows.Forms.UserControl> 항목의 **StackViewLibrary** 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="fe6f8-124">새 소스 파일의 기본 이름 지정 `StackView`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="fe6f8-125">StackView 컨트롤 디자인</span><span class="sxs-lookup"><span data-stu-id="fe6f8-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="fe6f8-126">`StackView` 컨트롤은 하나의 자식에서 합성 컨트롤 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="fe6f8-127">복합 컨트롤에 대 한 자세한 내용은 참조 [종류의 사용자 지정 컨트롤](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-127">For more information about composite controls, see [Varieties of Custom Controls](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="fe6f8-128">StackView 컨트롤을 디자인 하려면</span><span class="sxs-lookup"><span data-stu-id="fe6f8-128">To design the StackView control</span></span>  
  
1.  <span data-ttu-id="fe6f8-129">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2.  <span data-ttu-id="fe6f8-130">에 **속성** 창의 설정의 <xref:System.Windows.Forms.ToolStrip> 다음 표에 따라 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="fe6f8-131">속성</span><span class="sxs-lookup"><span data-stu-id="fe6f8-131">Property</span></span>|<span data-ttu-id="fe6f8-132">값</span><span class="sxs-lookup"><span data-stu-id="fe6f8-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="fe6f8-133">이름</span><span class="sxs-lookup"><span data-stu-id="fe6f8-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="fe6f8-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="fe6f8-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="fe6f8-135">도킹</span><span class="sxs-lookup"><span data-stu-id="fe6f8-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="fe6f8-136">글꼴</span><span class="sxs-lookup"><span data-stu-id="fe6f8-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="fe6f8-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="fe6f8-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="fe6f8-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="fe6f8-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="fe6f8-139">안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="fe6f8-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="fe6f8-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="fe6f8-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  <span data-ttu-id="fe6f8-141">Windows Forms 디자이너에서 클릭는 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 **추가** 단추와 추가 <xref:System.Windows.Forms.ToolStripButton> 에 `stackStrip` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4.  <span data-ttu-id="fe6f8-142">에 **속성** 창의 설정의 <xref:System.Windows.Forms.ToolStripButton> 다음 표에 따라 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="fe6f8-143">속성</span><span class="sxs-lookup"><span data-stu-id="fe6f8-143">Property</span></span>|<span data-ttu-id="fe6f8-144">값</span><span class="sxs-lookup"><span data-stu-id="fe6f8-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="fe6f8-145">이름</span><span class="sxs-lookup"><span data-stu-id="fe6f8-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="fe6f8-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="fe6f8-146">CheckOnClick</span></span>|<span data-ttu-id="fe6f8-147">true</span><span class="sxs-lookup"><span data-stu-id="fe6f8-147">true</span></span>|  
    |<span data-ttu-id="fe6f8-148">CheckState</span><span class="sxs-lookup"><span data-stu-id="fe6f8-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="fe6f8-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="fe6f8-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="fe6f8-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="fe6f8-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="fe6f8-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="fe6f8-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="fe6f8-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="fe6f8-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="fe6f8-153">여백</span><span class="sxs-lookup"><span data-stu-id="fe6f8-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="fe6f8-154">안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="fe6f8-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="fe6f8-155">텍스트</span><span class="sxs-lookup"><span data-stu-id="fe6f8-155">Text</span></span>|<span data-ttu-id="fe6f8-156">**메일**</span><span class="sxs-lookup"><span data-stu-id="fe6f8-156">**Mail**</span></span>|  
    |<span data-ttu-id="fe6f8-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="fe6f8-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  <span data-ttu-id="fe6f8-158">세 개의 추가 대 한 7 단계를 반복 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="fe6f8-159">컨트롤 이름을 `calendarStackButton`, `contactsStackButton`, 및 `tasksStackButton`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="fe6f8-160">값을 설정할는 <xref:System.Windows.Forms.Control.Text%2A> 속성을 **달력**, **연락처**, 및 **작업**각각.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="fe6f8-161">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="fe6f8-161">Handling Events</span></span>  
 <span data-ttu-id="fe6f8-162">두 개의 이벤트를 확인 해야는 `StackView` 컨트롤이 올바르게 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="fe6f8-163">처리는 <xref:System.Windows.Forms.UserControl.Load> 이벤트를 올바르게 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="fe6f8-164">처리는 <xref:System.Windows.Forms.ToolStripItem.Click> 각각에 대 한 이벤트 <xref:System.Windows.Forms.ToolStripButton> 제공 하는 `StackView` 와 유사한 상태 동작을 제어는 <xref:System.Windows.Forms.RadioButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="fe6f8-165">이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="fe6f8-165">To handle events</span></span>  
  
1.  <span data-ttu-id="fe6f8-166">Windows Forms 디자이너에서 선택 된 `StackView` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2.  <span data-ttu-id="fe6f8-167">에 **속성** 창 클릭 **이벤트**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-167">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="fe6f8-168">Load 이벤트 생성에 두 번 클릭 하 여 `StackView_Load` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4.  <span data-ttu-id="fe6f8-169">`StackView_Load` 이벤트 처리기에서 다음 코드를 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  <span data-ttu-id="fe6f8-170">Windows Forms 디자이너에서 선택 된 `mailStackButton` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6.  <span data-ttu-id="fe6f8-171">에 **속성** 창 클릭 **이벤트**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-171">In the **Properties** window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="fe6f8-172">Click 이벤트를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="fe6f8-173">Windows Forms 디자이너에서는 오류가 발생 하는 `mailStackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8.  <span data-ttu-id="fe6f8-174">이름 바꾸기는 `mailStackButton_Click` 이벤트 처리기를 `stackButton_Click`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="fe6f8-175">자세한 내용은 참조 [하는 방법: (Visual Basic) 식별자 이름 바꾸기](http://msdn.microsoft.com/library/e5a5edf8-3dba-4119-81f4-fc2aba180e0c)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-175">For more information, see [How to: Rename an Identifier (Visual Basic)](http://msdn.microsoft.com/library/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).</span></span>  
  
9. <span data-ttu-id="fe6f8-176">에 다음 코드를 삽입은 `stackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="fe6f8-177">Windows Forms 디자이너에서 선택 된 `calendarStackButton` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="fe6f8-178">에 **속성** 창의을 Click 이벤트를 설정의 `stackButton_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="fe6f8-179">10과 11에 대 한 단계를 반복 하는 `contactsStackButton` 및 `tasksStackButton` 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="fe6f8-180">아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="fe6f8-180">Defining Icons</span></span>  
 <span data-ttu-id="fe6f8-181">각 `StackView` 단추에 연결 된 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="fe6f8-182">편의 위해 각 아이콘으로 표현 되는 Base64 인코딩 문자열 하기 전에 deserialize 되는 한 <xref:System.Drawing.Bitmap> 에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="fe6f8-183">프로덕션 환경에서 리소스로 바운딩되어야 비트맵 데이터를 저장 하 고 Windows Forms 디자이너에 아이콘이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="fe6f8-184">자세한 내용은 참조 [하는 방법: Windows Forms에 배경 이미지 추가](http://msdn.microsoft.com/library/7a509ba2-055c-4ae6-b88a-54625c6d9aff)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-184">For more information, see [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/library/7a509ba2-055c-4ae6-b88a-54625c6d9aff).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="fe6f8-185">아이콘을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="fe6f8-185">To define icons</span></span>  
  
1.  <span data-ttu-id="fe6f8-186">코드 편집기에서 다음 코드를 삽입은 `StackView` 클래스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="fe6f8-187">이 코드에 대 한 비트맵을 초기화는 <xref:System.Windows.Forms.ToolStripButton> 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  <span data-ttu-id="fe6f8-188">에 대 한 호출 추가 `InitializeImages` 에서 메서드는 `StackView` 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="fe6f8-189">사용자 지정 렌더러를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="fe6f8-190">대부분의 요소를 사용자 지정할 수는 `StackView` 에서 파생 되는 클래스를 구현 제어는 <xref:System.Windows.Forms.ToolStripRenderer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="fe6f8-191">이 절차에서는 구현는 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 그립을 사용자 지정 하며 그라데이션 배경을 그리는 <xref:System.Windows.Forms.ToolStripButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="fe6f8-192">사용자 지정 렌더러를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="fe6f8-192">To implement a custom renderer</span></span>  
  
1.  <span data-ttu-id="fe6f8-193">에 다음 코드를 삽입는 `StackView` 정의 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="fe6f8-194">이 대 한 정의는 `StackRenderer` 재정의 하는 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, 및 <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> 메서드를 사용자 지정 모양을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  <span data-ttu-id="fe6f8-195">에 `StackView` 컨트롤의 생성자의 새 인스턴스를 만들고는 `StackRenderer` 클래스 하 고이 인스턴스를 할당는 `stackStrip` 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="fe6f8-196">StackView 컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="fe6f8-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="fe6f8-197">`StackView` 컨트롤에서 파생 되는 <xref:System.Windows.Forms.UserControl> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="fe6f8-198">따라서 사용 하 여 컨트롤을 테스트할 수 있습니다는 **UserControl Test Container**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="fe6f8-199">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="fe6f8-200">StackView 컨트롤을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="fe6f8-200">To test the StackView control</span></span>  
  
1.  <span data-ttu-id="fe6f8-201">F5 키를 눌러 프로젝트를 빌드하고 시작 하는 **UserControl Test Container**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="fe6f8-202">단추 위로 포인터를 이동는 `StackView` 컨트롤을 선택한 상태로의 모양을 보려면 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fe6f8-203">다음 단계</span><span class="sxs-lookup"><span data-stu-id="fe6f8-203">Next Steps</span></span>  
 <span data-ttu-id="fe6f8-204">이 연습에서는 Office XP 컨트롤의 전문적인 모양으로 다시 사용할 수 있는 사용자 지정 클라이언트 컨트롤을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="fe6f8-205">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 패밀리 등과 같은 용도로 컨트롤:</span><span class="sxs-lookup"><span data-stu-id="fe6f8-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="fe6f8-206">사용자 컨트롤에 대 한 바로 가기 메뉴 만들기 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="fe6f8-207">자세한 내용은 참조 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-207">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="fe6f8-208">자동으로 채워지는 표준 메뉴가 있는 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="fe6f8-209">자세한 내용은 참조 [연습: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="fe6f8-210">도킹 된 다중 문서 MDI (인터페이스) 폼 만들기 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="fe6f8-211">자세한 내용은 참조 [하는 방법: 메뉴 병합 및 ToolStrip 컨트롤 MDI 폼 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe6f8-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe6f8-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe6f8-212">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="fe6f8-213">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fe6f8-213">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [<span data-ttu-id="fe6f8-214">방법: 양식에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="fe6f8-214">How to: Provide Standard Menu Items to a Form</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
