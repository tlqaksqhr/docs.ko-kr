---
title: SplitContainer 컨트롤 개요(Windows Forms)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a553ea1b6dae24b4a0c3bd169edccbd9b52c5203
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="splitcontainer-control-overview-windows-forms"></a><span data-ttu-id="f552c-102">SplitContainer 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f552c-102">SplitContainer Control Overview (Windows Forms)</span></span>
<span data-ttu-id="f552c-103">Windows Forms <xref:System.Windows.Forms.SplitContainer> 컨트롤은 복합으로 간주될 수 있습니다. 이동 가능한 막대로 구분된 두 개의 패널입니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-103">The Windows Forms <xref:System.Windows.Forms.SplitContainer> control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="f552c-104">마우스 포인터가 막대 위에 있으면 포인터 모양이 변경되어 막대를 이동할 수 있음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f552c-105">에 **도구 상자**, <xref:System.Windows.Forms.SplitContainer> 대체 제어는 <xref:System.Windows.Forms.Splitter> 이전 버전의 Visual Studio에 있던 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-105">In the **Toolbox**, <xref:System.Windows.Forms.SplitContainer> control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="f552c-106"><xref:System.Windows.Forms.SplitContainer> 컨트롤이 <xref:System.Windows.Forms.Splitter> 컨트롤보다 훨씬 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-106">The <xref:System.Windows.Forms.SplitContainer> control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="f552c-107"><xref:System.Windows.Forms.Splitter> 클래스에 여전히 포함 되어는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 기존 응용 프로그램과 호환성에 대 한 하지만 좋습니다 사용 하 여 <xref:System.Windows.Forms.SplitContainer> 새 프로젝트에 대 한 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-107">The <xref:System.Windows.Forms.Splitter> class is still included in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for compatibility with existing applications, but we strongly encourage you to use the <xref:System.Windows.Forms.SplitContainer> control for new projects.</span></span>  
  
 <span data-ttu-id="f552c-108">와 <xref:System.Windows.Forms.SplitContainer> 컨트롤, 복잡 한 사용자 인터페이스를 만들 수 있습니다; 다른 패널에 표시 되는 개체가 한 패널에서 선택한 항목을 결정 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-108">With the <xref:System.Windows.Forms.SplitContainer> control, you can create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="f552c-109">이 정렬은 정보를 표시하고 찾는 데 매우 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="f552c-110">두 개의 패널 수 있는 영역에 정보를 집계 하 고 막대 또는 "분할자"를 통해 사용자가 쉽게 패널 크기 조정 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-110">Having two panels lets you aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
 <span data-ttu-id="f552c-111">둘 이상의 <xref:System.Windows.Forms.SplitContainer> 컨트롤 중첩 될 수 있습니다, 두 번째 <xref:System.Windows.Forms.SplitContainer> 제어 가로로 배치 위쪽 및 아래쪽 패널을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-111">More than one <xref:System.Windows.Forms.SplitContainer> control can also be nested, with the second <xref:System.Windows.Forms.SplitContainer> control oriented horizontally, to create top and bottom panels.</span></span>  
  
 <span data-ttu-id="f552c-112">알아야 하는 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 키보드 액세스 가능한 기본적으로 이며 사용자가 경우 분할자 이동 하려면 화살표 키를 눌러 수는 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성이로 설정 된 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-112">Be aware that the <xref:System.Windows.Forms.SplitContainer> control is keyboard-accessible by default; users can press the ARROW keys to move the splitter if the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property is set to `false`.</span></span>  
  
 <span data-ttu-id="f552c-113"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> 의 속성은 <xref:System.Windows.Forms.SplitContainer> 컨트롤 컨트롤 자체 아닌 분할자의 방향을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-113">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span> <span data-ttu-id="f552c-114">이 속성이로 설정 된 경우에 따라서 <xref:System.Windows.Forms.Orientation.Vertical>, 분할자 위쪽에서 아래쪽, 왼쪽 및 오른쪽 패널 만들기를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-114">Hence, when this property is set to <xref:System.Windows.Forms.Orientation.Vertical>, the splitter runs from top to bottom, creating left and right panels.</span></span>  
  
 <span data-ttu-id="f552c-115">또한 하는 값은 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성의 값에 따라 달라 집니다는 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="f552c-115">Additionally, be aware that the value of the <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> property varies depending on the value of the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property.</span></span> <span data-ttu-id="f552c-116">자세한 내용은 참조 <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-116">For more information, see <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> property.</span></span>  
  
 <span data-ttu-id="f552c-117">크기와의 이동을 제한할 수도 있습니다는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-117">You can also restrict the size and movement of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="f552c-118"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성 결정 한 후 같은 크기로 유지할 패널을는 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기 조정 및 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성은 키보드 또는 마우스 이동 가능한 분할자 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-118">The <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> property determines which panel will remain the same size after the <xref:System.Windows.Forms.SplitContainer> control is resized, and the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property determines if the splitter is movable by the keyboard or mouse.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f552c-119">경우에는 <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성이 `true`, 분할자 이동할 수 있습니다 예를 들어, 프로그래밍 방식으로 사용 하 여는 <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-119">Even if the <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property is set to `true`, the splitter may still be moved programmatically; for example, by using the <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property.</span></span>  
  
 <span data-ttu-id="f552c-120">마지막으로, 각 패널에는 <xref:System.Windows.Forms.SplitContainer> 컨트롤에는 개별 크기를 결정 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-120">Finally, each panel of the <xref:System.Windows.Forms.SplitContainer> control has properties to determine its individual size.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="f552c-121">일반적으로 사용되는 속성, 메서드 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="f552c-121">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="f552c-122">이름</span><span class="sxs-lookup"><span data-stu-id="f552c-122">Name</span></span>|<span data-ttu-id="f552c-123">설명</span><span class="sxs-lookup"><span data-stu-id="f552c-123">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="f552c-124"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f552c-124"><xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> property</span></span>|<span data-ttu-id="f552c-125">패널 동일 하 게 결정 한 후 크기가 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-125">Determines which panel will remain the same size after the <xref:System.Windows.Forms.SplitContainer> control is resized.</span></span>|  
|<span data-ttu-id="f552c-126"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f552c-126"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="f552c-127">분할자 키보드 또는 마우스를 이동할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-127">Determines if the splitter can be moved with the keyboard or mouse.</span></span>|  
|<span data-ttu-id="f552c-128"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f552c-128"><xref:System.Windows.Forms.SplitContainer.Orientation%2A> property</span></span>|<span data-ttu-id="f552c-129">분할 자가 가로 또는 세로로 정렬 된 경우를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-129">Determines if the splitter is arranged vertically or horizontally.</span></span>|  
|<span data-ttu-id="f552c-130"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f552c-130"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="f552c-131">이동할 수 있는 분할 막대를 왼쪽 또는 위쪽 가장자리에서 픽셀 거리를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-131">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="f552c-132"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f552c-132"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="f552c-133">최소 거리 (픽셀)를 사용자가 분할자를 이동할 수 있는지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-133">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
|<span data-ttu-id="f552c-134"><xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="f552c-134"><xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A> property</span></span>|<span data-ttu-id="f552c-135">분할자의 픽셀 단위로 두께 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-135">Determines the thickness, in pixels, of the splitter.</span></span>|  
|<span data-ttu-id="f552c-136"><xref:System.Windows.Forms.SplitContainer.SplitterMoving> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f552c-136"><xref:System.Windows.Forms.SplitContainer.SplitterMoving> event</span></span>|<span data-ttu-id="f552c-137">분할자 이동 하는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-137">Occurs when the splitter is moving.</span></span>|  
|<span data-ttu-id="f552c-138"><xref:System.Windows.Forms.SplitContainer.SplitterMoved> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f552c-138"><xref:System.Windows.Forms.SplitContainer.SplitterMoved> event</span></span>|<span data-ttu-id="f552c-139">분할 자가 이동한 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f552c-139">Occurs when the splitter has moved.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f552c-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f552c-140">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="f552c-141">SplitContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f552c-141">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [<span data-ttu-id="f552c-142">SplitContainer 컨트롤 샘플</span><span class="sxs-lookup"><span data-stu-id="f552c-142">SplitContainer Control Sample</span></span>](http://msdn.microsoft.com/library/9015fad0-7108-4d85-a83a-a72d038c4f65)
