---
title: "쿼리 결과를 통해 페이징"
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
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b4a51eec840b74d04aaab97226191b2ed30d8826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="paging-through-a-query-result"></a><span data-ttu-id="bd124-102">쿼리 결과를 통해 페이징</span><span class="sxs-lookup"><span data-stu-id="bd124-102">Paging Through a Query Result</span></span>
<span data-ttu-id="bd124-103">쿼리 결과 페이징은 쿼리의 결과를 작은 단위의 데이터 하위 집합, 즉 페이지로 반환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="bd124-104">이 방법은 관리하기 쉬운 작은 청크 단위로 결과를 표시하기 위해 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="bd124-105">**DataAdapter** 의 오버 로드를 통해 데이터를 한 페이지씩만 반환 하는 데는 기능을 제공 된 **채우기** 메서드.</span><span class="sxs-lookup"><span data-stu-id="bd124-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="bd124-106">그러나 사용 하지 않을 때 적합 한 하기 때문에 많은 양의 쿼리 결과 통한 페이징을 있지만 **DataAdapter** 대상 채웁니다 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet> 만 요청 된 레코드를 반환 하도록 리소스는 전체 쿼리에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="bd124-107">전체 쿼리를 반환하기 위한 리소스를 사용하지 않고 데이터 소스에서 데이터 페이지를 반환하려면 필요한 쿼리에만 반환되는 행을 줄이도록 쿼리에 추가 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="bd124-108">사용 하는 **채우기** 데이터 페이지를 반환 하는 메서드를 지정는 **startRecord** 데이터 페이지의 첫 번째 레코드에 대 한 매개 변수 및 **maxRecords** 수에 대 한 매개 변수 데이터 페이지의 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="bd124-109">다음 코드 예제를 사용 하는 방법을 보여 줍니다는 **채우기** 메서드를 여기서 페이지 크기는 5 개의 레코드가 쿼리 결과의 첫 번째 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="bd124-110">이전 예에서 **데이터 집합** 다섯 개의 레코드가 있지만 전체 채워집니다만 **Orders** 테이블이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="bd124-111">채울는 **DataSet** 레코드 다섯 개만 반환 되지만 해당 동일한 5 개 레코드를 사용 하 여 위쪽 및 다음 코드 예제와 같이 SQL 문의 WHERE 절.</span><span class="sxs-lookup"><span data-stu-id="bd124-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")   
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 <span data-ttu-id="bd124-112">이 방법으로 쿼리 결과를 페이징할 때는 다음 코드 예제와 같이 행의 순서를 나타내는 고유 ID를 유지하여 다음 레코드 페이지를 반환하기 위해 해당 고유 ID를 명령에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="bd124-113">오버 로드를 사용 하 여 레코드의 다음 페이지를 반환 하는 **채우기** 를 받는 메서드에 **startRecord** 및 **maxRecords** 매개 변수를 하 여 현재 레코드 인덱스를 증가 시킵니다. 페이지 크기와 채우기는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="bd124-114">데이터베이스 서버에 추가 됩니다 한 페이지 레코드의 경우에 전체 쿼리 결과 반환 기억는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="bd124-115">다음 코드 예제에서는 다음 데이터 페이지로 채워지기 전에 테이블 행이 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="bd124-116">데이터베이스 서버로의 트립을 줄이기 위해 반환되는 행의 일부를 로컬 캐시에 보존할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 <span data-ttu-id="bd124-117">데이터베이스 서버에서 전체 쿼리를 반환하지 않고 다음 레코드 페이지를 반환하도록 하려면 SELECT 문에 제한 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="bd124-118">이전 예제에서는 마지막 반환 레코드를 유지하므로 해당 레코드를 WHERE 절에 사용하여 다음 코드 예제와 같이 쿼리에 시작 지점을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd124-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd124-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd124-119">See Also</span></span>  
 [<span data-ttu-id="bd124-120">Dataadapter 및 Datareader</span><span class="sxs-lookup"><span data-stu-id="bd124-120">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="bd124-121">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="bd124-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
