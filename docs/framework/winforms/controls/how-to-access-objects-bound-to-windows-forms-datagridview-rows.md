---
title: "방법: Windows Forms DataGridView 행에 바인딩된 개체에 액세스"
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
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66db5f6ff7b964162f77317f17a9e3a8d3ed22b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="3f40c-102">방법: Windows Forms DataGridView 행에 바인딩된 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="3f40c-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="3f40c-103">때로는 비즈니스 개체 컬렉션에 저장된 정보 테이블을 표시하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="3f40c-104"><xref:System.Windows.Forms.DataGridView> 컨트롤을 이러한 컬렉션에 바인딩하면 속성이 <xref:System.ComponentModel.BrowsableAttribute>를 통해 검색 불가능으로 표시되지 않은 경우 각 공용 속성이 해당 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="3f40c-105">예를 들어 `Customer` 개체 컬렉션에는 **이름** 및 **주소**와 같은 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="3f40c-106">이러한 개체에 포함된 추가 정보 및 코드에 액세스하려는 경우 행 개체를 통해 접근할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="3f40c-107">다음 코드 예제에서는 사용자가 여러 행을 선택하고 단추를 클릭하여 각 해당 고객에게 송장을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="3f40c-108">행 바인딩된 개체에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="3f40c-108">To access row-bound objects</span></span>  
  
-   <span data-ttu-id="3f40c-109"><xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="3f40c-110">예</span><span class="sxs-lookup"><span data-stu-id="3f40c-110">Example</span></span>  
 <span data-ttu-id="3f40c-111">전체 코드 예제는 간단한 `Customer` 구현을 포함하며, 몇 개의 `Customer` 개체가 포함된 <xref:System.Collections.ArrayList>에 <xref:System.Windows.Forms.DataGridView>를 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="3f40c-112"><xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> 이벤트 처리기 외부에서는 고객 컬렉션에 액세스할 수 없기 때문에 <xref:System.Windows.Forms.Button?displayProperty=nameWithType>의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기는 행을 통해 `Customer` 개체에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3f40c-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3f40c-113">Compiling the Code</span></span>  
 <span data-ttu-id="3f40c-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-114">This example requires:</span></span>  
  
-   <span data-ttu-id="3f40c-115">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="3f40c-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="3f40c-116">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f40c-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3f40c-117">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f40c-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="3f40c-118">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f40c-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f40c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f40c-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3f40c-120">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="3f40c-120">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="3f40c-121">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="3f40c-121">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)
