---
title: '방법: 자식 테이블에서 선택된 행이 올바른 위치에 유지되도록 설정'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30929c6163a279bc0ea47d1262f54ec5ff75a87c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a><span data-ttu-id="bd216-102">방법: 자식 테이블에서 선택된 행이 올바른 위치에 유지되도록 설정</span><span class="sxs-lookup"><span data-stu-id="bd216-102">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>
<span data-ttu-id="bd216-103">Windows Forms에서 데이터 바인딩을 사용할 때 부모/자식 또는 마스터/세부 정보 뷰에 데이터를 표시하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-103">Oftentimes when you work with data binding in Windows Forms, you will display data in what is called a parent/child or master/details view.</span></span> <span data-ttu-id="bd216-104">이는 동일한 소스의 데이터가 두 컨트롤에 표시되는 데이터 바인딩 시나리오를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-104">This refers to a data-binding scenario where data from the same source is displayed in two controls.</span></span> <span data-ttu-id="bd216-105">한 컨트롤에서 선택 항목을 변경하면 두 번째 컨트롤에 표시되는 데이터가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-105">Changing the selection in one control causes the data displayed in the second control to change.</span></span> <span data-ttu-id="bd216-106">예를 들어 첫 번째 컨트롤에는 고객 목록이 포함되고 두 번째 컨트롤에는 첫 번째 컨트롤에서 선택한 고객과 관련된 주문 목록이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-106">For example, the first control might contain a list of customers and the second a list of orders related to the selected customer in the first control.</span></span>  
  
 <span data-ttu-id="bd216-107">.NET Framework 버전 2.0부터 부모/자식 뷰에 데이터를 표시하는 경우 자식 테이블에서 현재 선택된 행이 테이블의 첫 번째 행으로 다시 설정되지 않도록 추가 단계를 수행해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-107">Starting with the .NET Framework version 2.0, when you display data in a parent/child view you might have to take extra steps to make sure that the currently selected row in the child table is not reset to the first row of the table.</span></span> <span data-ttu-id="bd216-108">이 작업을 수행하려면 자식 테이블 위치를 캐시하고 부모 테이블이 변경된 후 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-108">In order to do this, you will have to cache the child table position and reset it after the parent table changes.</span></span> <span data-ttu-id="bd216-109">일반적으로 자식 다시 설정은 부모 테이블의 행에 있는 필드가 처음 변경될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-109">Typically the child reset occurs the first time a field in a row of the parent table changes.</span></span>  
  
### <a name="to-cache-the-current-child-position"></a><span data-ttu-id="bd216-110">현재 자식 위치를 캐시하려면</span><span class="sxs-lookup"><span data-stu-id="bd216-110">To Cache the Current Child Position</span></span>  
  
1.  <span data-ttu-id="bd216-111">정수 변수를 선언하여 자식 목록 위치를 저장하고, 부울 변수를 선언하여 자식 위치를 캐시할지 여부를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-111">Declare an integer variable to store the child list position and a Boolean variable to store whether to cache the child position.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2.  <span data-ttu-id="bd216-112">바인딩의 <xref:System.Windows.Forms.CurrencyManager>에 대한 <xref:System.Windows.Forms.CurrencyManager.ListChanged> 이벤트를 처리하고 <xref:System.ComponentModel.ListChangedType.Reset>의 <xref:System.ComponentModel.ListChangedType>을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-112">Handle the <xref:System.Windows.Forms.CurrencyManager.ListChanged> event for the binding's <xref:System.Windows.Forms.CurrencyManager> and check for a <xref:System.ComponentModel.ListChangedType> of <xref:System.ComponentModel.ListChangedType.Reset>.</span></span>  
  
3.  <span data-ttu-id="bd216-113"><xref:System.Windows.Forms.CurrencyManager>의 현재 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-113">Check the current position of the <xref:System.Windows.Forms.CurrencyManager>.</span></span> <span data-ttu-id="bd216-114">목록의 첫 번째 항목(일반적으로 0)보다 크면 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-114">If it is greater than first entry in the list (typically 0), save it to a variable.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="bd216-115">부모 통화 관리자에 대한 부모 목록의 <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-115">Handle the parent list's <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> event for the parent currency manager.</span></span> <span data-ttu-id="bd216-116">처리기에서 캐싱 시나리오가 아님을 나타내는 부울 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-116">In the handler, set the Boolean value to indicate it is not a caching scenario.</span></span> <span data-ttu-id="bd216-117"><xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>가 발생하는 경우 부모에 대한 변경 내용은 항목 값 변경이 아니라 목록 위치 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-117">If the <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> occurs, the change to the parent is a list position change and not an item value change.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a><span data-ttu-id="bd216-118">자식 위치를 다시 설정하려면</span><span class="sxs-lookup"><span data-stu-id="bd216-118">To Reset the Child Position</span></span>  
  
1.  <span data-ttu-id="bd216-119">자식 바인딩의 <xref:System.Windows.Forms.CurrencyManager>에 대한 <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-119">Handle the <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> event for the child binding's <xref:System.Windows.Forms.CurrencyManager>.</span></span>  
  
2.  <span data-ttu-id="bd216-120">자식 테이블 위치를 이전 절차에서 저장된 캐시된 위치로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-120">Reset the child table position to the cached position saved in the previous procedure.</span></span>  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="bd216-121">예제</span><span class="sxs-lookup"><span data-stu-id="bd216-121">Example</span></span>  
 <span data-ttu-id="bd216-122">다음 예제에서는 <xref:System.Windows.Forms.CurrencyManager>에서 자식 테이블의 현재 위치를 저장하고 부모 테이블에서 편집이 완료된 후 위치를 다시 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-122">The following example demonstrates how to save the current position on the <xref:System.Windows.Forms.CurrencyManager>.for a child table and reset the position after an edit is completed on the parent table.</span></span> <span data-ttu-id="bd216-123">이 예제에는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 <xref:System.Data.DataSet>의 두 테이블에 바인딩된 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-123">This example contains two <xref:System.Windows.Forms.DataGridView> controls bound to two tables in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="bd216-124">두 테이블 간에 관계가 설정되고 <xref:System.Data.DataSet>에 관계가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-124">A relation is established between the two tables and the relation is added to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="bd216-125">자식 테이블의 위치는 데모용으로 초기에 세 번째 행으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-125">The position in the child table is initially set to the third row for demonstration purposes.</span></span>  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 <span data-ttu-id="bd216-126">코드 예제를 테스트하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-126">To test the code example, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="bd216-127">예제를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-127">Run the example.</span></span>  
  
2.  <span data-ttu-id="bd216-128">**Cache and reset position** 확인란이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-128">Make sure the **Cache and reset position** check box is selected.</span></span>  
  
3.  <span data-ttu-id="bd216-129">**Clear parent field** 단추를 클릭하여 부모 테이블의 필드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-129">Click the **Clear parent field** button to cause a change in a field of the parent table.</span></span> <span data-ttu-id="bd216-130">자식 테이블에서 선택한 행은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-130">Notice that the selected row in the child table does not change.</span></span>  
  
4.  <span data-ttu-id="bd216-131">예제를 닫고 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-131">Close and run the example again.</span></span> <span data-ttu-id="bd216-132">다시 설정 동작이 부모 행을 처음 변경할 때만 발생하기 때문에 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-132">You need to do this because the reset behavior occurs only on the first change in the parent row.</span></span>  
  
5.  <span data-ttu-id="bd216-133">**Cache and reset position** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-133">Clear the **Cache and reset position** check box.</span></span>  
  
6.  <span data-ttu-id="bd216-134">**Clear parent field** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-134">Click the **Clear parent field** button.</span></span> <span data-ttu-id="bd216-135">자식 테이블에서 선택한 행이 첫 번째 행으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-135">Notice that the selected row in the child table changes to the first row.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bd216-136">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bd216-136">Compiling the Code</span></span>  
 <span data-ttu-id="bd216-137">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-137">This example requires:</span></span>  
  
-   <span data-ttu-id="bd216-138">System, System.Data, System.Drawing, System.Windows.Forms and System.XML 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="bd216-138">References to the System, System.Data, System.Drawing, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="bd216-139">Visual Basic 또는 Visual C#에 대 한이 예제에서는 명령줄에서 작성 하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 빌드 명령줄](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-139">For information about how to build this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bd216-140">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd216-140">You can also build this example in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="bd216-141">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd216-141">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd216-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd216-142">See Also</span></span>  
 [<span data-ttu-id="bd216-143">방법: 동일한 데이터 소스에 바인딩된 여러 컨트롤의 동기화 상태가 유지되도록 설정</span><span class="sxs-lookup"><span data-stu-id="bd216-143">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 [<span data-ttu-id="bd216-144">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bd216-144">BindingSource Component</span></span>](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="bd216-145">데이터 바인딩 및 Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bd216-145">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
