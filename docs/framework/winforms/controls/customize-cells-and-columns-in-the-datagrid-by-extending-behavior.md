---
title: "방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정"
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
- DataGridView control [Windows Forms], cell customization
- columns [Windows Forms], customizing in DataGridView control
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 358b5ed2ad201b2dfb0fef7bb960a88234939bf1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-cells-and-columns-in-the-windows-forms-datagridview-control-by-extending-their-behavior-and-appearance"></a><span data-ttu-id="84c3e-102">방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="84c3e-102">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>
<span data-ttu-id="84c3e-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 속성, 이벤트 및 도우미 클래스를 통해 모양과 동작을 사용자 지정하는 다양한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-103">The <xref:System.Windows.Forms.DataGridView> control provides a number of ways to customize its appearance and behavior using properties, events, and companion classes.</span></span> <span data-ttu-id="84c3e-104">경우에 따라 해당 셀에 대해 이러한 기능으로 충족할 수 없는 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-104">Occasionally, you may have requirements for your cells that go beyond what these features can provide.</span></span> <span data-ttu-id="84c3e-105">고유한 사용자 지정 <xref:System.Windows.Forms.DataGridViewCell> 클래스를 만들어 확장 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-105">You can create your own custom <xref:System.Windows.Forms.DataGridViewCell> class to provide extended functionality.</span></span>  
  
 <span data-ttu-id="84c3e-106"><xref:System.Windows.Forms.DataGridViewCell> 기본 클래스 또는 파생 클래스 중 하나에서 파생시켜 사용자 지정 <xref:System.Windows.Forms.DataGridViewCell> 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-106">You create a custom <xref:System.Windows.Forms.DataGridViewCell> class by deriving from the <xref:System.Windows.Forms.DataGridViewCell> base class or one of its derived classes.</span></span> <span data-ttu-id="84c3e-107">모든 유형의 열에 모든 유형의 셀을 표시할 수 있지만 일반적으로 셀 형식을 표시하기 위한 사용자 지정 <xref:System.Windows.Forms.DataGridViewColumn> 클래스도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-107">Although you can display any type of cell in any type of column, you will typically also create a custom <xref:System.Windows.Forms.DataGridViewColumn> class specialized for displaying your cell type.</span></span> <span data-ttu-id="84c3e-108">열 클래스는 <xref:System.Windows.Forms.DataGridViewColumn> 또는 파생 형식 중 하나에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-108">Column classes derive from <xref:System.Windows.Forms.DataGridViewColumn> or one of its derived types.</span></span>  
  
 <span data-ttu-id="84c3e-109">다음 코드 예제에서는 마우스가 셀 경계로 들어오고 나갈 때 이를 감지하는 `DataGridViewRolloverCell`이라는 사용자 지정 셀 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-109">In the following code example, you will create a custom cell class called `DataGridViewRolloverCell` that detects when the mouse enters and leaves the cell boundaries.</span></span> <span data-ttu-id="84c3e-110">마우스가 셀 범위 내에 있는 동안 삽입 사각형이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-110">While the mouse is within the cell's bounds, an inset rectangle is drawn.</span></span> <span data-ttu-id="84c3e-111">이 새로운 형식은 <xref:System.Windows.Forms.DataGridViewTextBoxCell>에서 파생되며 다른 모든 측면에서 기본 클래스처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-111">This new type derives from <xref:System.Windows.Forms.DataGridViewTextBoxCell> and behaves in all other respects as its base class.</span></span> <span data-ttu-id="84c3e-112">도우미 열 클래스는 `DataGridViewRolloverColumn`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-112">The companion column class is called `DataGridViewRolloverColumn`.</span></span>  
  
 <span data-ttu-id="84c3e-113">이러한 클래스를 사용하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼을 만들고 하나 이상의 `DataGridViewRolloverColumn` 개체를 <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션에 추가한 다음 값이 포함된 행으로 컨트롤을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-113">To use these classes, create a form containing a <xref:System.Windows.Forms.DataGridView> control, add one or more `DataGridViewRolloverColumn` objects to the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection, and populate the control with rows containing values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84c3e-114">빈 행을 추가하는 경우에는 이 예제가 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-114">This example will not work correctly if you add empty rows.</span></span> <span data-ttu-id="84c3e-115">예를 들어 <xref:System.Windows.Forms.DataGridView.RowCount%2A> 속성을 설정하여 컨트롤에 행을 추가할 때 빈 행이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-115">Empty rows are created, for example, when you add rows to the control by setting the <xref:System.Windows.Forms.DataGridView.RowCount%2A> property.</span></span> <span data-ttu-id="84c3e-116">이러한 경우에 추가된 행이 자동으로 공유되기 때문이며, 이는 개별 셀을 클릭하여 연결된 행이 공유되지 않도록 할 때까지 `DataGridViewRolloverCell` 개체가 인스턴스화되지 않음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-116">This is because the rows added in this case are automatically shared, which means that `DataGridViewRolloverCell` objects are not instantiated until you click on individual cells, thereby causing the associated rows to become unshared.</span></span>  
  
 <span data-ttu-id="84c3e-117">이 형식의 셀 사용자 지정에는 공유되지 않는 행이 필요하므로 큰 데이터 집합에 사용하기에 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-117">Because this type of cell customization requires unshared rows, it is not appropriate for use with large data sets.</span></span> <span data-ttu-id="84c3e-118">행 공유에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 유용한](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-118">For more information about row sharing, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84c3e-119"><xref:System.Windows.Forms.DataGridViewCell> 또는 <xref:System.Windows.Forms.DataGridViewColumn>에서 파생시키고 파생 클래스에 새 속성을 추가하는 경우 복제 작업 중 새 속성을 복사하도록 `Clone` 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-119">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="84c3e-120">또한 기본 클래스의 속성이 새로운 셀 또는 열에 복사되도록 기본 클래스의 `Clone` 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-120">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
### <a name="to-customize-cells-and-columns-in-the-datagridview-control"></a><span data-ttu-id="84c3e-121">DataGridView 컨트롤에서 셀과 열을 사용자 지정하려면</span><span class="sxs-lookup"><span data-stu-id="84c3e-121">To customize cells and columns in the DataGridView control</span></span>  
  
1.  <span data-ttu-id="84c3e-122"><xref:System.Windows.Forms.DataGridViewTextBoxCell> 형식에서 `DataGridViewRolloverCell`이라는 새로운 셀 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-122">Derive a new cell class, called `DataGridViewRolloverCell`, from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2.  <span data-ttu-id="84c3e-123"><xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> 클래스에서 `DataGridViewRolloverCell` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-123">Override the <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> method in the `DataGridViewRolloverCell` class.</span></span> <span data-ttu-id="84c3e-124">재정의에서 먼저 호스트된 텍스트 상자 기능을 처리하는 기본 클래스 구현을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-124">In the override, first call the base class implementation, which handles the hosted text box functionality.</span></span> <span data-ttu-id="84c3e-125">그런 다음 컨트롤의 <xref:System.Windows.Forms.Control.PointToClient%2A> 메서드를 사용하여 커서 위치(화면 좌표)를 <xref:System.Windows.Forms.DataGridView> 클라이언트 영역 좌표로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-125">Then use the control's <xref:System.Windows.Forms.Control.PointToClient%2A> method to transform the cursor position (in screen coordinates) to the <xref:System.Windows.Forms.DataGridView> client area's coordinates.</span></span> <span data-ttu-id="84c3e-126">마우스 좌표가 셀 범위에 속하는 경우 삽입 사각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-126">If the mouse coordinates fall within the bounds of the cell, draw the inset rectangle.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3.  <span data-ttu-id="84c3e-127">`DataGridViewRolloverCell` 클래스의 <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> 및 <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> 메서드를 재정의하여 마우스 포인터가 들어가거나 나올 때 셀이 자동으로 그려지도록 강제합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-127">Override the <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> and <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> methods in the `DataGridViewRolloverCell` class to force cells to repaint themselves when the mouse pointer enters or leaves them.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4.  <span data-ttu-id="84c3e-128"><xref:System.Windows.Forms.DataGridViewColumn> 형식에서 `DataGridViewRolloverCellColumn`이라는 새 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-128">Derive a new class, called `DataGridViewRolloverCellColumn`, from the <xref:System.Windows.Forms.DataGridViewColumn> type.</span></span> <span data-ttu-id="84c3e-129">생성자에서 해당 <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A> 속성에 새 `DataGridViewRolloverCell` 개체를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-129">In the constructor, assign a new `DataGridViewRolloverCell` object to its <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## <a name="example"></a><span data-ttu-id="84c3e-130">예</span><span class="sxs-lookup"><span data-stu-id="84c3e-130">Example</span></span>  
 <span data-ttu-id="84c3e-131">전체 코드 예제에는 사용자 지정 셀 형식의 동작을 보여 주는 작은 테스트 폼이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-131">The complete code example includes a small test form that demonstrates the behavior of the custom cell type.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="84c3e-132">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="84c3e-132">Compiling the Code</span></span>  
 <span data-ttu-id="84c3e-133">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-133">This example requires:</span></span>  
  
-   <span data-ttu-id="84c3e-134">System, System.Windows.Forms 및 System.Drawing 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="84c3e-134">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
 <span data-ttu-id="84c3e-135">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84c3e-135">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="84c3e-136">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84c3e-136">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="84c3e-137">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84c3e-137">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c3e-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84c3e-138">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="84c3e-139">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="84c3e-139">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="84c3e-140">DataGridView 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="84c3e-140">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [<span data-ttu-id="84c3e-141">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="84c3e-141">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="84c3e-142">Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="84c3e-142">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
