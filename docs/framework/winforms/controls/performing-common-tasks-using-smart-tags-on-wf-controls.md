---
title: "연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7a29b7224a3f4b692fdfb3afaf58d9744bafcc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="82dd9-102">연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행</span><span class="sxs-lookup"><span data-stu-id="82dd9-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="82dd9-103">Windows Forms 응용 프로그램에 대 한 폼과 컨트롤을 구성할 때에 반복 해 서 수행 하는 많은 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="82dd9-104">일반적으로 수행된 하는 작업 중 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="82dd9-105">추가 / 제거를 탭 한 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="82dd9-106">부모 항목에 컨트롤을 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="82dd9-107">방향을 변경는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="82dd9-108">개발 속도 많은 컨트롤을 디자인 타임에는 단일 제스처에 이와 같은 일반적인 태스크를 수행할 수 있도록 하는 상황에 맞는 메뉴 스마트 태그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="82dd9-109">이러한 작업 라고 *스마트 태그 동사*합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="82dd9-110">스마트 태그 한 디자이너의 수명 제어 인스턴스에 연결 된 유지와 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="82dd9-111">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="82dd9-112">Windows Forms 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="82dd9-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="82dd9-113">스마트 태그를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="82dd9-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="82dd9-114">설정 및 해제 스마트 태그</span><span class="sxs-lookup"><span data-stu-id="82dd9-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="82dd9-115">작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82dd9-116">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="82dd9-117">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="82dd9-118">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82dd9-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="82dd9-119">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="82dd9-119">Creating the Project</span></span>  
 <span data-ttu-id="82dd9-120">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="82dd9-121">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="82dd9-121">To create the project</span></span>  
  
1.  <span data-ttu-id="82dd9-122">"SmartTagsExample" 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-122">Create a Windows-based application project called "SmartTagsExample".</span></span> <span data-ttu-id="82dd9-123">자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82dd9-123">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="82dd9-124">폼을 선택는 **Windows Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-124">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="82dd9-125">스마트 태그를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="82dd9-125">Using Smart Tags</span></span>  
 <span data-ttu-id="82dd9-126">스마트 태그는 사용자에 게 제공 하는 컨트롤에 디자인 타임에 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-126">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="82dd9-127">스마트 태그를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="82dd9-127">To use smart tags</span></span>  
  
1.  <span data-ttu-id="82dd9-128">끌어서는 <xref:System.Windows.Forms.TabControl> 에서 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-128">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="82dd9-129">스마트 태그 문자 모양을 확인 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 측면에 표시 되는 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-129">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="82dd9-130">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-130">Click the smart-tag glyph.</span></span> <span data-ttu-id="82dd9-131">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 된 **탭 추가** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-131">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="82dd9-132">새 탭 페이지에 추가 확인 된 <xref:System.Windows.Forms.TabControl>합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-132">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="82dd9-133">끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-133">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="82dd9-134">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-134">Click the smart-tag glyph.</span></span> <span data-ttu-id="82dd9-135">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 된 **열 추가** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-135">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="82dd9-136">새 열에 추가 됩니다 확인는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-136">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="82dd9-137">끌어서는 <xref:System.Windows.Forms.SplitContainer> 에서 제어는 **도구 상자** 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-137">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="82dd9-138">스마트 태그 문자 모양을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-138">Click the smart-tag glyph.</span></span> <span data-ttu-id="82dd9-139">문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 된 **가로 분할자 방향** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-139">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="82dd9-140">참조 하는 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 분할 막대는 이제 가로 방향으로 놓여 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-140">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82dd9-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82dd9-141">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [<span data-ttu-id="82dd9-142">연습: Windows Forms 구성 요소에 스마트 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="82dd9-142">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
