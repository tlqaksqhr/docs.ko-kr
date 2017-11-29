---
title: "DataGridView 컨트롤 아키텍처(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb44a32e63fd7a0ff0e480c205d5459da2ce2bd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="c1f29-102">DataGridView 컨트롤 아키텍처(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c1f29-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="c1f29-103"><xref:System.Windows.Forms.DataGridView> 컨트롤과 관련 된 클래스는 테이블 형식 데이터 표시 및 편집에 대 한 유연 하 고 확장 가능한 시스템 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="c1f29-104">이러한 클래스에 포함 된 모든는 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스 및 이러한 라는 "DataGridView" 접두사와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="c1f29-105">아키텍처 요소</span><span class="sxs-lookup"><span data-stu-id="c1f29-105">Architecture Elements</span></span>  
 <span data-ttu-id="c1f29-106">주 <xref:System.Windows.Forms.DataGridView> 도우미 클래스에서 파생 <xref:System.Windows.Forms.DataGridViewElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="c1f29-107">다음 개체 모델을 보여 줍니다는 <xref:System.Windows.Forms.DataGridViewElement> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="c1f29-108">![DataGridViewElement 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")</span><span class="sxs-lookup"><span data-stu-id="c1f29-108">![DataGridViewElement Object Model](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")</span></span>  
<span data-ttu-id="c1f29-109">DataGridViewElement 개체 모델</span><span class="sxs-lookup"><span data-stu-id="c1f29-109">DataGridViewElement object model</span></span>  
  
 <span data-ttu-id="c1f29-110"><xref:System.Windows.Forms.DataGridViewElement> 클래스는 부모에 대 한 참조를 제공 <xref:System.Windows.Forms.DataGridView> 컨트롤는 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성의 값 조합을 나타내는 값을 보유 하 고 <xref:System.Windows.Forms.DataGridViewElementStates> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-110">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="c1f29-111">다음 섹션에 설명 된 <xref:System.Windows.Forms.DataGridView> 도우미 클래스를 더 자세하게에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-111">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="c1f29-112">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="c1f29-112">DataGridViewElementStates</span></span>  
 <span data-ttu-id="c1f29-113"><xref:System.Windows.Forms.DataGridViewElementStates> 열거형에는 다음 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-113">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="c1f29-114">이 열거형의 값 비트 논리 연산자와 함께 사용할 수 있으므로 <xref:System.Windows.Forms.DataGridViewElement.State%2A> 속성 하나 이상의 상태를 한 번에 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-114">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="c1f29-115">예를 들어 한 <xref:System.Windows.Forms.DataGridViewElement> 동시에 수 있는 <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, 및 <xref:System.Windows.Forms.DataGridViewElementStates.Visible>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-115">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="c1f29-116">셀 및 밴드</span><span class="sxs-lookup"><span data-stu-id="c1f29-116">Cells and Bands</span></span>  
 <span data-ttu-id="c1f29-117"><xref:System.Windows.Forms.DataGridView> 기본적인 두 종류의 개체를 구성 하는 컨트롤: 셀과 밴드입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-117">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="c1f29-118">모든 셀에서 파생 되는 <xref:System.Windows.Forms.DataGridViewCell> 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-118">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="c1f29-119">두 종류의 밴드 <xref:System.Windows.Forms.DataGridViewColumn> 및 <xref:System.Windows.Forms.DataGridViewRow>에서 파생 되는 <xref:System.Windows.Forms.DataGridViewBand> 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-119">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="c1f29-120"><xref:System.Windows.Forms.DataGridView> 컨트롤 몇 가지 클래스와 상호 운용 있지만 가장 일반적으로 발생는 <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, 및 <xref:System.Windows.Forms.DataGridViewRow>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-120">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="c1f29-121">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="c1f29-121">DataGridViewCell</span></span>  
 <span data-ttu-id="c1f29-122">셀이에 대 한 상호 작용의 기본 단위는 <xref:System.Windows.Forms.DataGridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-122">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="c1f29-123">표시는 셀을 중심으로 하 고 데이터 입력 셀을 통해 자주 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-123">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="c1f29-124">사용 하 여 셀에 액세스할 수는 <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> 의 컬렉션은 <xref:System.Windows.Forms.DataGridViewRow> 클래스 및 있습니다를 사용 하 여 선택한 셀에 액세스할 수는 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> 의 컬렉션은 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-124">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c1f29-125">다음 개체 모델이이 사용법을 보여 줍니다 및 표시는 <xref:System.Windows.Forms.DataGridViewCell> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-125">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="c1f29-126">![DataGridViewCell 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")</span><span class="sxs-lookup"><span data-stu-id="c1f29-126">![DataGridViewCell Object Model](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")</span></span>  
<span data-ttu-id="c1f29-127">DataGridViewCell 개체 모델</span><span class="sxs-lookup"><span data-stu-id="c1f29-127">DataGridViewCell object model</span></span>  
  
 <span data-ttu-id="c1f29-128"><xref:System.Windows.Forms.DataGridViewCell> 유형 모든 셀 형식에서 파생 된 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-128">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="c1f29-129"><xref:System.Windows.Forms.DataGridViewCell>및 Windows Forms 컨트롤, 하지만 일부 호스트 Windows Forms 컨트롤 파생된 형식의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-129"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="c1f29-130">셀에서 지원 되는 모든 편집 기능은 호스팅된 컨트롤에서 일반적으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-130">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="c1f29-131"><xref:System.Windows.Forms.DataGridViewCell>개체 제어 하지 않을 자신의 모양 및 그리기 기능 같은 방식으로 Windows Forms 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-131"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="c1f29-132">대신,는 <xref:System.Windows.Forms.DataGridView> 의 모양에 대 한 책임이 해당 <xref:System.Windows.Forms.DataGridViewCell> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-132">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="c1f29-133">상호 작용 하 여 모양 및 동작 셀를 크게 저하 될 수는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 속성 및 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-133">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="c1f29-134">기능을 초과 하는 사용자 지정에 대 한 특별 한 요구 사항이 있는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 파생 되는 고유한 클래스를 구현할 수 있습니다 <xref:System.Windows.Forms.DataGridViewCell> 또는 그 자식 클래스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-134">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="c1f29-135">다음 목록에서 파생 된 클래스를 보여 줍니다. <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="c1f29-135">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   <span data-ttu-id="c1f29-136">사용자 지정 셀 형식</span><span class="sxs-lookup"><span data-stu-id="c1f29-136">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="c1f29-137">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="c1f29-137">DataGridViewColumn</span></span>  
 <span data-ttu-id="c1f29-138">스키마는 <xref:System.Windows.Forms.DataGridView> 제어의 연결 된 데이터 저장소로 표시 됩니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-138">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="c1f29-139">에 액세스할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 를 사용 하 여 컨트롤의 열은 <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-139">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="c1f29-140">사용 하 여 선택한 열에 액세스할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-140">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="c1f29-141">다음 개체 모델이이 사용법을 보여 줍니다 및 표시는 <xref:System.Windows.Forms.DataGridViewColumn> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-141">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="c1f29-142">![DataGridViewColumn 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")</span><span class="sxs-lookup"><span data-stu-id="c1f29-142">![DataGridViewColumn Object Model](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")</span></span>  
<span data-ttu-id="c1f29-143">DataGridViewColumn 개체 모델</span><span class="sxs-lookup"><span data-stu-id="c1f29-143">DataGridViewColumn object model</span></span>  
  
 <span data-ttu-id="c1f29-144">키 셀 유형 중 일부에 해당 열 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-144">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="c1f29-145">파생 된 <xref:System.Windows.Forms.DataGridViewColumn> 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-145">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="c1f29-146">다음 목록에서 파생 된 클래스를 보여 줍니다. <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="c1f29-146">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="c1f29-147">사용자 지정 열 형식</span><span class="sxs-lookup"><span data-stu-id="c1f29-147">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="c1f29-148">DataGridView 편집 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c1f29-148">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="c1f29-149">고급 편집 기능을 일반적으로 지원 되는 셀 호스팅된 Windows Forms 컨트롤에서 파생 된 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-149">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="c1f29-150">이러한 컨트롤은 또한 구현 된 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-150">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="c1f29-151">다음 개체 모델에서는 이러한 컨트롤의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-151">The following object model illustrates the usage of these controls.</span></span>  
  
 <span data-ttu-id="c1f29-152">![DataGridView 편집 컨트롤 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")</span><span class="sxs-lookup"><span data-stu-id="c1f29-152">![DataGridView Editing Control Object Model](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")</span></span>  
<span data-ttu-id="c1f29-153">DataGridView 편집 컨트롤 개체 모델</span><span class="sxs-lookup"><span data-stu-id="c1f29-153">DataGridView editing control object model</span></span>  
  
 <span data-ttu-id="c1f29-154">다음과 같은 편집 컨트롤이 함께 제공 되는 <xref:System.Windows.Forms.DataGridView> 제어:</span><span class="sxs-lookup"><span data-stu-id="c1f29-154">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="c1f29-155">고유한 편집 컨트롤을 만드는 방법은 참조 [하는 방법: Windows Forms DataGridView 셀에서 호스트 컨트롤](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-155">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="c1f29-156">다음 표에서 셀 형식, 열 유형 및 편집 컨트롤 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-156">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="c1f29-157">셀 형식</span><span class="sxs-lookup"><span data-stu-id="c1f29-157">Cell type</span></span>|<span data-ttu-id="c1f29-158">호스팅된 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c1f29-158">Hosted control</span></span>|<span data-ttu-id="c1f29-159">열 유형</span><span class="sxs-lookup"><span data-stu-id="c1f29-159">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="c1f29-160">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c1f29-160">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="c1f29-161">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c1f29-161">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="c1f29-162">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c1f29-162">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="c1f29-163">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c1f29-163">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="c1f29-164">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="c1f29-164">DataGridViewRow</span></span>  
 <span data-ttu-id="c1f29-165"><xref:System.Windows.Forms.DataGridViewRow> 클래스 표시는 레코드의 데이터 필드에서 데이터 저장소에 있는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-165">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="c1f29-166">에 액세스할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 를 사용 하 여 컨트롤의 행은 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-166">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="c1f29-167">사용 하 여 선택 된 행에 액세스할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-167">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="c1f29-168">다음 개체 모델이이 사용법을 보여 줍니다 및 표시는 <xref:System.Windows.Forms.DataGridViewRow> 상속 계층 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-168">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="c1f29-169">![DataGridViewRow 개체 모델](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")</span><span class="sxs-lookup"><span data-stu-id="c1f29-169">![DataGridViewRow Object Model](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")</span></span>  
<span data-ttu-id="c1f29-170">DataGridViewRow 개체 모델</span><span class="sxs-lookup"><span data-stu-id="c1f29-170">DataGridViewRow object model</span></span>  
  
 <span data-ttu-id="c1f29-171">사용자 고유의 형식을 파생 시킬 수 있습니다는 <xref:System.Windows.Forms.DataGridViewRow> 클래스를이 일반적으로 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-171">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="c1f29-172"><xref:System.Windows.Forms.DataGridView> 여러 행 관련 이벤트 및 속성의 동작을 사용자 지정 컨트롤에 해당 <xref:System.Windows.Forms.DataGridViewRow> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-172">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="c1f29-173">사용 하도록 설정 하면는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성을 새 행을 추가 하기 위한 특별 한 행이 마지막 행으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-173">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="c1f29-174">이 행의 일부인는 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션 이어야 하는데이 주의가 요구 될 수 있는 특별 한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-174">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="c1f29-175">자세한 내용은 참조 [Windows Forms DataGridView 컨트롤에서 새 레코드에 대 한 행을 사용 하 여](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1f29-175">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f29-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1f29-176">See Also</span></span>  
 [<span data-ttu-id="c1f29-177">DataGridView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="c1f29-177">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [<span data-ttu-id="c1f29-178">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c1f29-178">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="c1f29-179">Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용</span><span class="sxs-lookup"><span data-stu-id="c1f29-179">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
