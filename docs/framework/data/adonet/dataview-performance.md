---
title: "DataView 성능"
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
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0858dec79f17906647a3244eb1686e91e53ac48d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="dataview-performance"></a><span data-ttu-id="d1389-102">DataView 성능</span><span class="sxs-lookup"><span data-stu-id="d1389-102">DataView Performance</span></span>
<span data-ttu-id="d1389-103">이 항목에서는 <xref:System.Data.DataView.Find%2A> 클래스의 <xref:System.Data.DataView.FindRows%2A> 및 <xref:System.Data.DataView> 메서드를 사용하여 웹 응용 프로그램에서 <xref:System.Data.DataView>를 캐시할 때 얻을 수 있는 성능상의 이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-103">This topic discusses the performance benefits of using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView> class, and of caching a <xref:System.Data.DataView> in a Web application.</span></span>  
  
## <a name="find-and-findrows"></a><span data-ttu-id="d1389-104">Find 및 FindRows</span><span class="sxs-lookup"><span data-stu-id="d1389-104">Find and FindRows</span></span>  
 <span data-ttu-id="d1389-105"><xref:System.Data.DataView>는 인덱스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-105"><xref:System.Data.DataView> constructs an index.</span></span> <span data-ttu-id="d1389-106">인덱스에는 테이블 또는 뷰에 있는 하나 이상의 열에서 작성된 키가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-106">An index contains keys built from one or more columns in the table or view.</span></span> <span data-ttu-id="d1389-107">이러한 키는 <xref:System.Data.DataView>를 사용하여 키 값과 연결된 행을 빠르고 효과적으로 찾을 수 있는 구조체에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-107">These keys are stored in a structure that enables the <xref:System.Data.DataView> to find the row or rows associated with the key values quickly and efficiently.</span></span> <span data-ttu-id="d1389-108">작업에서 필터링 및 정렬과 같은 인덱스를 사용하면 성능이 크게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-108">Operations that use the index, such as filtering and sorting, see signifcant performance increases.</span></span> <span data-ttu-id="d1389-109"><xref:System.Data.DataView>의 인덱스는 <xref:System.Data.DataView>가 만들어지거나 정렬 또는 필터링 정보가 수정될 때 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-109">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="d1389-110"><xref:System.Data.DataView>를 만든 다음 정렬 또는 필터링 정보를 설정하면 <xref:System.Data.DataView>가 만들어질 때와 정렬 또는 필터 속성이 수정될 때 각각 한 번씩 인덱스가 작성되므로 적어도 두 개의 인덱스가 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-110">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span> <span data-ttu-id="d1389-111">필터링 및 정렬 하는 방법에 대 한 자세한 내용은 <xref:System.Data.DataView>, 참조 [DataView로 필터링](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) 및 [DataView로 정렬](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-111">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
 <span data-ttu-id="d1389-112">데이터의 하위 집합에 대한 동적 뷰를 제공하는 것과는 반대로 데이터에 대한 특정 쿼리 결과를 반환하려는 경우 <xref:System.Data.DataView.Find%2A> 속성을 설정하는 대신 <xref:System.Data.DataView.FindRows%2A>의 <xref:System.Data.DataView> 또는 <xref:System.Data.DataView.RowFilter%2A> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-112">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, you can use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>, rather than setting the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="d1389-113"><xref:System.Data.DataView.RowFilter%2A> 속성은 바인딩된 컨트롤이 필터링된 결과를 표시하는 데이터 바인딩된 응용 프로그램에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-113">The <xref:System.Data.DataView.RowFilter%2A> property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="d1389-114"><xref:System.Data.DataView.RowFilter%2A> 속성을 설정하면 데이터의 인덱스가 다시 작성되므로 응용 프로그램에 오버헤드가 발생하여 성능이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-114">Setting the <xref:System.Data.DataView.RowFilter%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="d1389-115"><xref:System.Data.DataView.Find%2A> 및 <xref:System.Data.DataView.FindRows%2A> 메서드는 인덱스를 다시 작성하지 않고 현재 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-115">The <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods use the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="d1389-116"><xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A>를 한 번만 호출할 경우에는 기존 <xref:System.Data.DataView>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-116">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> only once, then you should use the existing <xref:System.Data.DataView>.</span></span> <span data-ttu-id="d1389-117"><xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A>를 여러 번 호출할 경우에는 새 <xref:System.Data.DataView>를 만들어서 검색하려는 열의 인덱스를 다시 작성한 다음 <xref:System.Data.DataView.Find%2A> 또는 <xref:System.Data.DataView.FindRows%2A> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-117">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> multiple times, you should create a new <xref:System.Data.DataView> to rebuild the index on the column you want to search on, and then call the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods.</span></span> <span data-ttu-id="d1389-118">에 대 한 자세한 내용은 <xref:System.Data.DataView.Find%2A> 및 <xref:System.Data.DataView.FindRows%2A> 메서드 참조 [행 찾기](../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-118">For more information about the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods, see [Finding Rows](../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
 <span data-ttu-id="d1389-119">다음 예제에서는 <xref:System.Data.DataView.Find%2A> 메서드를 사용하여 성이 "Zhu"인 연락처를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-119">The following example uses the <xref:System.Data.DataView.Find%2A> method to find a contact with the last name "Zhu".</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 <span data-ttu-id="d1389-120">다음 예제에서는 <xref:System.Data.DataView.FindRows%2A> 메서드를 사용하여 모든 빨간색 제품을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-120">The following example uses the <xref:System.Data.DataView.FindRows%2A> method to find all the red colored products.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a><span data-ttu-id="d1389-121">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d1389-121">ASP.NET</span></span>  
 <span data-ttu-id="d1389-122">ASP.NET에는 만드는 데 많은 서버 자원이 필요한 개체를 메모리에 저장할 수 있는 캐시 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-122">ASP.NET has a caching mechanism that allows you to store objects that require extensive server resources to create in memory.</span></span> <span data-ttu-id="d1389-123">이러한 유형의 자원을 캐시하면 응용 프로그램의 성능을 상당히 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-123">Caching these types of resources can significantly improve the performance of your application.</span></span> <span data-ttu-id="d1389-124">캐시는 <xref:System.Web.Caching.Cache> 클래스에 의해 각 응용 프로그램에 개별적인 캐시 인스턴스로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-124">Caching is implemented by the <xref:System.Web.Caching.Cache> class, with cache instances that are private to each application.</span></span> <span data-ttu-id="d1389-125">새 <xref:System.Data.DataView> 개체를 만들면 많은 자원이 소요될 수 있으므로 웹 응용 프로그램에서 이 캐시 기능을 사용하면 웹 페이지를 새로 고칠 때마다 <xref:System.Data.DataView>를 다시 작성하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-125">Because creating a new <xref:System.Data.DataView> object can be resource intensive, you might want to use this caching functionality in Web applications so that the <xref:System.Data.DataView> does not have to be rebuilt every time the Web page is refreshed.</span></span>  
  
 <span data-ttu-id="d1389-126">다음 예제에서는 <xref:System.Data.DataView>가 캐시되기 때문에 페이지가 새로 고쳐질 때 데이터를 다시 정렬하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1389-126">In the following example, the <xref:System.Data.DataView> is cached so that the data does not have to be re-sorted when the page is refreshed.</span></span>  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.                  
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1389-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1389-127">See Also</span></span>  
 [<span data-ttu-id="d1389-128">데이터 바인딩 및 LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d1389-128">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
