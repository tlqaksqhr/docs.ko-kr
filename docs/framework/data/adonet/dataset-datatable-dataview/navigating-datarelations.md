---
title: DataRelation 탐색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: c46007fb86a76405fd99d6e943779238d6885aa8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761430"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="85d03-102">DataRelation 탐색</span><span class="sxs-lookup"><span data-stu-id="85d03-102">Navigating DataRelations</span></span>
<span data-ttu-id="85d03-103"><xref:System.Data.DataRelation>의 기본 기능 중 하나는 <xref:System.Data.DataTable> 내에서 <xref:System.Data.DataSet>를 하나씩 탐색할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="85d03-104">모두 검색할 수 있습니다는 관련 <xref:System.Data.DataRow> 하나에서 개체 **DataTable** 단일 지정 되 면 **DataRow** 관련에서 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="85d03-105">예를 들어 설정 된 후 한 **DataRelation** 고객 테이블 사이의 orders 테이블을 사용 하 여 특정 고객 행에 대 한 모든 주문 행을 검색할 수 있습니다 **GetChildRows**합니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="85d03-106">다음 코드 예제에서는 한 **DataRelation** 사이 **고객** 테이블 및 **주문** 목차는 **데이터 집합** 반환 각 고객에 대 한 모든 주문</span><span class="sxs-lookup"><span data-stu-id="85d03-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="85d03-107">다음 예제에서는 이전 예제를 기반으로 네 개의 테이블을 모두 연관시키고 각각의 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="85d03-108">앞의 예와 **CustomerID** 연결 되는 **고객** 테이블는 **Orders** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="85d03-109">에 있는 각 고객에 대 한는 **고객** 테이블의 모든 자식 행은 **Orders** 테이블 결정 되어 특정 고객의 주문 수를 반환 및 해당 **OrderID** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="85d03-110">확장 된 예제에는 값도 반환 된 **OrderDetails** 및 **제품** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="85d03-111">**Orders** 테이블이 관련 되어는 **OrderDetails** 를 사용 하 여 테이블 **OrderID** 각각에 대해 주문 된 고객 주문, 제품과 수량을 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="85d03-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="85d03-112">때문에 **OrderDetails** 만 표에서 **ProductID** 는 주문 된 제품의 **OrderDetails** 관련이 **제품** 사용 하 여 **ProductID** 반환 하기 위해는 **ProductName**합니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="85d03-113">이 관계는 **제품** 테이블은 부모와 **Order Details** 테이블은 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="85d03-114">반복할 때 결과적으로는 **OrderDetails** 테이블 **GetParentRow** 관련 검색을 위해 호출 **ProductName** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="85d03-115">때는 **DataRelation** 만들어집니다는 **고객** 및 **Orders** 테이블에 대 한 지정 된 값은 **createConstraints**플래그 (기본값은 **true**).</span><span class="sxs-lookup"><span data-stu-id="85d03-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="85d03-116">이 가정 하는 모든의 행의 **Orders** 테이블는 **CustomerID** 상위에 있는 값 **고객** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="85d03-117">경우는 **CustomerID** 에 존재는 **Orders** 에 존재 하지 않는 테이블의 **고객** 테이블은 <xref:System.Data.ForeignKeyConstraint> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="85d03-118">자식 열이 포함 되지 않은 부모 열 값을 포함할 수 있습니다 설정는 **createConstraints** 플래그를 **false** 추가 하는 경우는 **DataRelation**합니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="85d03-119">예제에서는 **createConstraints** 플래그가로 설정 되어 **false** 에 대 한는 **DataRelation** 간에 **Orders** 테이블과  **OrderDetails** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="85d03-120">그러면 응용 프로그램에서 모든 레코드를 반환 하는 **OrderDetails** 테이블과에서 레코드의 하위 집합만 **Orders** 런타임 예외를 생성 하지 않고 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="85d03-121">확장된 예제는 다음과 같은 형식의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-121">The expanded sample generates output in the following format.</span></span>  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="85d03-122">다음 코드 예제는 확장 된 샘플은 위치에서 값의 **OrderDetails** 및 **제품** 테이블에 있는 레코드의 하위 집합만 반환 됩니다는 **Orders**반환 되는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="85d03-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="85d03-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85d03-123">See Also</span></span>  
 [<span data-ttu-id="85d03-124">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="85d03-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="85d03-125">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="85d03-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
