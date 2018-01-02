---
title: "데이터 집합에서 XPath 쿼리 수행"
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
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 62c5cef51e125443d87c47f7f62dc76aa5d352b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="64b94-102">데이터 집합에서 XPath 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="64b94-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="64b94-103">동기화 된 간의 관계 <xref:System.Data.DataSet> 및 <xref:System.Xml.XmlDataDocument> XML을 사용할 수 있습니다, XML 경로 언어 (XPath) 쿼리와 같은 액세스 서비스에는 **XmlDataDocument** 특정 기능을 수행할 수 있습니다 액세스할 때 보다 더 편리 하 게는 **DataSet** 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="64b94-104">예를 들어, 사용 하는 대신는 **선택** 의 메서드는 <xref:System.Data.DataTable> 있는 다른 테이블에는 관계를 탐색 하는 **데이터 집합**, XPath 쿼리를 수행할 수는 **XmlDataDocument**  와 동기화 하는 **데이터 집합**, 형태의 XML 요소의 목록을 가져올 수는 <xref:System.Xml.XmlNodeList>합니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="64b94-105">노드는 **XmlNodeList**로 캐스팅 <xref:System.Xml.XmlElement> 노드에 전달 될 수는 **GetRowFromElement** 의 메서드는 **XmlDataDocument**일치 하는 반환 하려는 경우 <xref:System.Data.DataRow> 동기화 된 테이블의 행에 대 한 참조 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="64b94-106">예를 들어, 다음 코드 샘플에서는 "최하위" XPath 쿼리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="64b94-107">**데이터 집합** 세 테이블으로: **고객**, **Orders**, 및 **OrderDetails**합니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="64b94-108">샘플에서는 부모-자식 관계를 처음 만들 사이 **고객** 및 **주문** 테이블의 경우와 **주문** 및 **OrderDetails** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="64b94-109">반환할 그런 다음 XPath 쿼리가 수행 되어는 **XmlNodeList** 의 **고객** 노드를 갖는 **OrderDetails** 노드에 **ProductID**노드가 값이 43 인 합니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="64b94-110">기본적으로 샘플 쿼리를 사용 하는 XPath가 있는 제품 주문한 고객을 결정 하는 **ProductID** 43입니다.</span><span class="sxs-lookup"><span data-stu-id="64b94-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="64b94-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64b94-111">See Also</span></span>  
 [<span data-ttu-id="64b94-112">데이터 집합 및 XmlDataDocument 동기화</span><span class="sxs-lookup"><span data-stu-id="64b94-112">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="64b94-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="64b94-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
