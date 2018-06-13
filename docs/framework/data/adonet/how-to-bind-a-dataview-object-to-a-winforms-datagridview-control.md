---
title: '방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 98b3afcded257bc11dc3bca7d9a9310dc1a7cc89
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765024"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="d8883-102">방법: Windows Forms DataGridView 컨트롤에 DataView 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="d8883-102">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d8883-103"><xref:System.Windows.Forms.DataGridView> 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-103">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="d8883-104"><xref:System.Windows.Forms.DataGridView> 컨트롤은 표준 Windows Forms 데이터 바인딩 모델을 지원하므로 <xref:System.Data.DataView> 및 다양한 데이터 소스에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="d8883-105">그러나 대부분의 경우 데이터 소스와의 상호 작용에 대한 세부 사항을 관리하는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-105">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="d8883-106">에 대 한 자세한 내용은 <xref:System.Windows.Forms.DataGridView> 제어, 참조 [DataGridView 컨트롤 개요](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-106">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="d8883-107">DataGridView 컨트롤을 DataView에 연결하려면</span><span class="sxs-lookup"><span data-stu-id="d8883-107">To connect a DataGridView control to a DataView</span></span>  
  
1.  <span data-ttu-id="d8883-108">데이터베이스에서 데이터를 검색하는 세부 과정을 처리하는 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-108">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="d8883-109">다음 코드 예제에서는 `GetData` 구성 요소를 초기화한 다음 이 구성 요소를 사용하여 <xref:System.Data.SqlClient.SqlDataAdapter>을 채우는 <xref:System.Data.DataSet> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-109">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d8883-110">`connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-110">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="d8883-111">AdventureWorks SQL Server 샘플 데이터베이스가 설치된 서버에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-111">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2.  <span data-ttu-id="d8883-112">폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩한 다음 `GetData` 메서드를 호출하여 데이터베이스에서 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-112">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="d8883-113">Contact <xref:System.Data.DataView>에 대한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리에서 <xref:System.Data.DataTable>가 만들어진 다음 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8883-113">The <xref:System.Data.DataView> is created from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="d8883-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8883-114">See Also</span></span>  
 [<span data-ttu-id="d8883-115">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d8883-115">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
