---
title: "방법: Windows Forms DataGridViewComboBoxCell 드롭다운 목록의 개체 액세스"
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
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0fac2e73e76ad49a5b1ce6942f3ae2b4c0584e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a><span data-ttu-id="89db4-102">방법: Windows Forms DataGridViewComboBoxCell 드롭다운 목록의 개체 액세스</span><span class="sxs-lookup"><span data-stu-id="89db4-102">How to: Access Objects in a Windows Forms DataGridViewComboBoxCell Drop-Down List</span></span>
<span data-ttu-id="89db4-103">와 같은 <xref:System.Windows.Forms.ComboBox> 컨트롤의 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 및 <xref:System.Windows.Forms.DataGridViewComboBoxCell> 형식을 사용 하면 임의의 개체를 드롭 다운 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-103">Like the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and <xref:System.Windows.Forms.DataGridViewComboBoxCell> types enable you to add arbitrary objects to their drop-down lists.</span></span> <span data-ttu-id="89db4-104">이 기능을 별도 컬렉션에 해당 하는 개체를 저장 하지 않고 드롭다운 목록에 복잡 한 상태를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-104">With this feature, you can represent complex states in a drop-down list without having to store corresponding objects in a separate collection.</span></span>  
  
 <span data-ttu-id="89db4-105">와 달리는 <xref:System.Windows.Forms.ComboBox> 컨트롤의 <xref:System.Windows.Forms.DataGridView> 형식 필요는 없습니다는 <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> 현재 선택 된 개체를 검색 하기 위한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-105">Unlike the <xref:System.Windows.Forms.ComboBox> control, the <xref:System.Windows.Forms.DataGridView> types do not have a <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> property for retrieving the currently selected object.</span></span> <span data-ttu-id="89db4-106">대신, 설정 해야 합니다는 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> 속성을 비즈니스 개체에 대 한 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-106">Instead, you must set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> property to the name of a property on your business object.</span></span> <span data-ttu-id="89db4-107">사용자가을 선택 하면, 비즈니스 개체의 지정된 된 속성의 셀을 설정 하는 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-107">When the user makes a selection, the indicated property of the business object sets the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
 <span data-ttu-id="89db4-108">셀 값을 통해 비즈니스 개체를 검색 하는 `ValueMember` 속성에 비즈니스 개체 자체에 대 한 참조를 반환 하는 속성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-108">To retrieve the business object through the cell value, the `ValueMember` property must indicate a property that returns a reference to the business object itself.</span></span> <span data-ttu-id="89db4-109">따라서 사용자가 제어 비즈니스 개체의 형식이 아닌 경우 상속을 통해 형식을 확장 하 여 이러한 속성을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-109">Therefore, if the type of the business object is not under your control, you must add such a property by extending the type through inheritance.</span></span>  
  
 <span data-ttu-id="89db4-110">다음 절차에는 비즈니스 개체와 드롭 다운 목록을 채우는 셀을 통해 개체를 검색 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-110">The following procedures demonstrate how to populate a drop-down list with business objects and retrieve the objects through the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property.</span></span>  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a><span data-ttu-id="89db4-111">드롭다운 목록에 비즈니스 개체를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="89db4-111">To add business objects to the drop-down list</span></span>  
  
1.  <span data-ttu-id="89db4-112">새 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 채웁니다 해당 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-112">Create a new <xref:System.Windows.Forms.DataGridViewComboBoxColumn> and populate its <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> collection.</span></span> <span data-ttu-id="89db4-113">또는 열을 설정할 수 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> 속성을 비즈니스 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-113">Alternatively, you can set the column <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> property to the collection of business objects.</span></span> <span data-ttu-id="89db4-114">그러나이 경우 추가할 수 없습니다 "할당 되지 않은" 드롭 다운 목록에 사용자의 컬렉션에서 해당 비즈니스 개체를 만들지 않고 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-114">In that case, however, you cannot add "unassigned" to the drop-down list without creating a corresponding business object in your collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  <span data-ttu-id="89db4-115"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> 및 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-115">Set the <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> and <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> properties.</span></span> <span data-ttu-id="89db4-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A>드롭다운 목록에 표시할 수는 비즈니스 개체의 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-116"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> indicates the property of the business object to display in the drop-down list.</span></span> <span data-ttu-id="89db4-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A>비즈니스 개체에 대 한 참조를 반환 하는 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-117"><xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> indicates the property that returns a reference to the business object.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  <span data-ttu-id="89db4-118">비즈니스 개체 형식에 현재 인스턴스에 대 한 참조를 반환 하는 속성이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-118">Make sure that your business object type contains a property that returns a reference to the current instance.</span></span> <span data-ttu-id="89db4-119">이 속성에 할당 된 값으로 이름을 지정 해야 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> 이전 단계에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-119">This property must be named with the value assigned to <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> in the previous step.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a><span data-ttu-id="89db4-120">현재 선택한 비즈니스 개체를 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="89db4-120">To retrieve the currently selected business object</span></span>  
  
-   <span data-ttu-id="89db4-121">셀 가져오기 <xref:System.Windows.Forms.DataGridViewCell.Value%2A> 속성 비즈니스 개체 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-121">Get the cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A> property and cast it to the business object type.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a><span data-ttu-id="89db4-122">예제</span><span class="sxs-lookup"><span data-stu-id="89db4-122">Example</span></span>  
 <span data-ttu-id="89db4-123">전체 예제 드롭 다운 목록에서 비즈니스 개체의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-123">The complete example demonstrates the use of business objects in a drop-down list.</span></span> <span data-ttu-id="89db4-124">예제에서는 한 <xref:System.Windows.Forms.DataGridView> 컨트롤의 컬렉션에 바인딩된 `Task` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-124">In the example, a <xref:System.Windows.Forms.DataGridView> control is bound to a collection of `Task` objects.</span></span> <span data-ttu-id="89db4-125">각 `Task` 개체에는 `AssignedTo` 나타내는 속성을는 `Employee` 해당 작업에 현재 할당 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-125">Each `Task` object has an `AssignedTo` property that indicates the `Employee` object currently assigned to that task.</span></span> <span data-ttu-id="89db4-126">`Assigned To` 열에 표시 됩니다는 `Name` 직원, 또는 "할당 되지 않은" 경우 각 속성 값이 지정 된 `Task.AssignedTo` 속성 값은 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-126">The `Assigned To` column displays the `Name` property value for each assigned employee, or "unassigned" if the `Task.AssignedTo` property value is `null`.</span></span>  
  
 <span data-ttu-id="89db4-127">이 예제에서는의 동작을 보려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-127">To view the behavior of this example, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="89db4-128">에 할당 된 변경의 `Assigned To` 드롭 다운 목록에서 다른 값을 선택 하거나 CTRL + 0 콤보 상자 셀에를 눌러 열입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-128">Change assignments in the `Assigned To` column by selecting different values from the drop-down lists or pressing CTRL+0 in a combo-box cell.</span></span>  
  
2.  <span data-ttu-id="89db4-129">클릭 `Generate Report` 현재 할당을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-129">Click `Generate Report` to display the current assignments.</span></span> <span data-ttu-id="89db4-130">이렇게 하는 변경에는 `Assigned To` 열을 자동으로 업데이트는 `tasks` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-130">This demonstrates that a change in the `Assigned To` column automatically updates the `tasks` collection.</span></span>  
  
3.  <span data-ttu-id="89db4-131">클릭는 `Request Status` 호출 하는 단추는 `RequestStatus` 현재 메서드 `Employee` 해당 행에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-131">Click a `Request Status` button to call the `RequestStatus` method of the current `Employee` object for that row.</span></span> <span data-ttu-id="89db4-132">이 선택된 된 개체 성공적으로 검색 된 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-132">This demonstrates that the selected object has been successfully retrieved.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="89db4-133">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="89db4-133">Compiling the Code</span></span>  
 <span data-ttu-id="89db4-134">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89db4-134">This example requires:</span></span>  
  
-   <span data-ttu-id="89db4-135">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="89db4-135">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89db4-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89db4-136">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ComboBox>  
 [<span data-ttu-id="89db4-137">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="89db4-137">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
