---
title: "DataView에서 DataRowView 컬렉션 쿼리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b17a489552e7b2bcb6044fce99e5f526b8293a25
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="querying-the-datarowview-collection-in-a-dataview"></a><span data-ttu-id="3c5b7-102">DataView에서 DataRowView 컬렉션 쿼리</span><span class="sxs-lookup"><span data-stu-id="3c5b7-102">Querying the DataRowView Collection in a DataView</span></span>
<span data-ttu-id="3c5b7-103"><xref:System.Data.DataView>는 <xref:System.Data.DataRowView> 개체의 열거할 수 있는 컬렉션을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-103">The <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="3c5b7-104"><xref:System.Data.DataRowView>는 <xref:System.Data.DataRow>의 사용자 지정 뷰를 나타내고 컨트롤에 해당 <xref:System.Data.DataRow>의 특정 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-104"><xref:System.Data.DataRowView> represents a customized view of a <xref:System.Data.DataRow> and displays a specific version of that <xref:System.Data.DataRow> in a control.</span></span> <span data-ttu-id="3c5b7-105"><xref:System.Data.DataRow>와 같은 컨트롤을 통해서는 <xref:System.Windows.Forms.DataGridView>의 한 버전만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-105">Only one version of a <xref:System.Data.DataRow> can be displayed through a control, such as a <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="3c5b7-106"><xref:System.Data.DataRow>의 <xref:System.Data.DataRowView> 속성을 통해 <xref:System.Data.DataRowView.Row%2A>에 의해 노출되는 <xref:System.Data.DataRowView>에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-106">You can access the <xref:System.Data.DataRow> that is exposed by the <xref:System.Data.DataRowView> through the <xref:System.Data.DataRowView.Row%2A> property of the <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="3c5b7-107"><xref:System.Data.DataRowView>를 사용하여 값을 보는 경우 <xref:System.Data.DataView.RowStateFilter%2A> 속성에 따라 원본 <xref:System.Data.DataRow>에서 노출되는 행 버전이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-107">When you view values by using a <xref:System.Data.DataRowView>, the <xref:System.Data.DataView.RowStateFilter%2A> property determines which row version of the underlying <xref:System.Data.DataRow> is exposed.</span></span> <span data-ttu-id="3c5b7-108">사용 하 여 다른 행 버전에 액세스 하는 방법에 대 한 내용은 <xref:System.Data.DataRow>, 참조 [행 상태 및 행 버전](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-108">For information about accessing different row versions using a <xref:System.Data.DataRow>, see [Row States and Row Versions](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span> <span data-ttu-id="3c5b7-109"><xref:System.Data.DataRowView>에 의해 노출되는 <xref:System.Data.DataView> 개체의 컬렉션은 열거할 수 있으므로 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하여 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-109">Because the collection of <xref:System.Data.DataRowView> objects exposed by the <xref:System.Data.DataView> is enumerable, you can use [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] to query over it.</span></span>  
  
 <span data-ttu-id="3c5b7-110">다음 예제에서는 `Product` 테이블에서 색상이 빨강인 제품을 쿼리하고 쿼리 결과로부터 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-110">The following example queries the `Product` table for red-colored products and creates a table from that query.</span></span> <span data-ttu-id="3c5b7-111">이 테이블에서 <xref:System.Data.DataView>를 만들고, 삭제되고 수정된 행을 필터링하도록 <xref:System.Data.DataView.RowStateFilter%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-111">A <xref:System.Data.DataView> is created from the table and the <xref:System.Data.DataView.RowStateFilter%2A> property is set to filter on deleted and modified rows.</span></span> <span data-ttu-id="3c5b7-112">그런 다음 LINQ 쿼리의 소스로 <xref:System.Data.DataView>를 사용하고, 수정되고 삭제된 <xref:System.Data.DataRowView> 개체를 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-112">The <xref:System.Data.DataView> is then used as a source in a LINQ query, and the <xref:System.Data.DataRowView> objects that have been modified and deleted are bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 <span data-ttu-id="3c5b7-113">다음 예제에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩된 뷰에서 제품 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-113">The following example creates a table of products from a view that is bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3c5b7-114"><xref:System.Data.DataView>에서 색상이 빨강인 제품을 쿼리하고 정렬된 결과를 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5b7-114">The <xref:System.Data.DataView> is queried for red-colored products and the ordered results are bound to a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## <a name="see-also"></a><span data-ttu-id="3c5b7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c5b7-115">See Also</span></span>  
 [<span data-ttu-id="3c5b7-116">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="3c5b7-116">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
