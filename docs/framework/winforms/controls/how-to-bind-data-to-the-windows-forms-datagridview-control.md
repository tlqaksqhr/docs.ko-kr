---
title: "방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩"
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
- cpp
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04fee5f753cb4b3786d5ca58f85880f151caf0b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="1380e-102">방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="1380e-102">How to: Bind Data to the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1380e-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원하므로 다양한 데이터 소스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to a variety of data sources.</span></span> <span data-ttu-id="1380e-104">그러나 대부분의 경우 데이터 소스와의 상호 작용에 대한 세부 사항을 관리하는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-104">In most circumstances, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component which will manage the details of interacting with the data source.</span></span> <span data-ttu-id="1380e-105"><xref:System.Windows.Forms.BindingSource> 구성 요소는 모든 Windows Forms 데이터 소스를 나타낼 수 있으며 데이터 위치를 선택하거나 수정할 때 뛰어난 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-105">The <xref:System.Windows.Forms.BindingSource> component can represent any Windows Forms data source and gives you great flexibility when choosing or modifying the location of your data.</span></span> <span data-ttu-id="1380e-106">지 원하는 데이터 원본에 대 한 자세한 내용은 <xref:System.Windows.Forms.DataGridView> 제어, 참조 [DataGridView 컨트롤 개요](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-106">For more information about the data sources supported by the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="1380e-107">Visual Studio에서는 이 작업이 광범위하게 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-107">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="1380e-108">[방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩](http://msdn.microsoft.com/library/33w255ac\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1380e-108">Also see [How to: Bind Data to the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/33w255ac\(v=vs.110\)).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="1380e-109">프로시저</span><span class="sxs-lookup"><span data-stu-id="1380e-109">Procedure</span></span>  
  
#### <a name="to-connect-a-datagridview-control-to-data"></a><span data-ttu-id="1380e-110">DataGridView 컨트롤을 데이터에 연결하려면</span><span class="sxs-lookup"><span data-stu-id="1380e-110">To connect a DataGridView control to data</span></span>  
  
1.  <span data-ttu-id="1380e-111">데이터베이스에서 데이터를 검색하는 세부 과정을 처리하는 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-111">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="1380e-112">다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlDataAdapter> 구성 요소를 초기화하는 `GetData` 메서드를 구현하고 이 메서드를 통해 <xref:System.Data.DataTable>을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="1380e-113">그런 다음 <xref:System.Data.DataTable>이 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-113">The <xref:System.Data.DataTable> is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="1380e-114">`connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-114">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="1380e-115">Northwind SQL Server 샘플 데이터베이스가 설치된 서버에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-115">You will need access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#20)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#20)]  
  
2.  <span data-ttu-id="1380e-116">폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩한 다음 `GetData` 메서드를 호출하여 데이터베이스에서 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-116">In your form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#10)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="1380e-117">예</span><span class="sxs-lookup"><span data-stu-id="1380e-117">Example</span></span>  
 <span data-ttu-id="1380e-118">다음 전체 코드 예제에서는 데이터베이스에서 데이터를 다시 로드하고 변경 내용을 데이터베이스로 제출하는 단추를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-118">The following complete code example provides buttons for reloading data from the database and submitting changes to the database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#00)]
 [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1380e-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1380e-119">Compiling the Code</span></span>  
 <span data-ttu-id="1380e-120">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-120">This example requires:</span></span>  
  
-   <span data-ttu-id="1380e-121">System, System.Windows.Forms, System.Data 및 System.XML 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="1380e-121">References to the System, System.Windows.Forms, System.Data, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="1380e-122">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1380e-122">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1380e-123">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-123">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="1380e-124">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1380e-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1380e-125">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="1380e-125">.NET Framework Security</span></span>  
 <span data-ttu-id="1380e-126">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-126">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="1380e-127">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="1380e-127">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="1380e-128">자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1380e-128">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1380e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1380e-129">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="1380e-130">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="1380e-130">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="1380e-131">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="1380e-131">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
