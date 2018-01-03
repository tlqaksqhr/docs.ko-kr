---
title: "DataReader를 사용하여 데이터 검색"
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
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b36f76516d4ddf94e177a5ecbb705e1d729318b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="retrieving-data-using-a-datareader"></a><span data-ttu-id="215e2-102">DataReader를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="215e2-102">Retrieving Data Using a DataReader</span></span>
<span data-ttu-id="215e2-103">사용 하 여 데이터를 검색 하는 **DataReader** 의 인스턴스를 만들고는 **명령** 개체 어셈블리 한 후 한 **DataReader** 호출 하 여  **Command.ExecuteReader** 데이터 원본에서 행을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-103">Retrieving data using a **DataReader** involves creating an instance of the **Command** object and then creating a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="215e2-104">다음 예제에서는 사용 하 여는 **DataReader** 여기서 `reader` 유효한 DataReader 나타냅니다 및 `command` 유효한 명령 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-104">The following example illustrates using a **DataReader** where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  
  
```  
reader = command.ExecuteReader();  
```  
  
 <span data-ttu-id="215e2-105">사용 된 **읽기** 의 메서드는 **DataReader** 개체를 쿼리 결과에서 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-105">You use the **Read** method of the **DataReader** object to obtain a row from the results of the query.</span></span> <span data-ttu-id="215e2-106">이름이 나 열을 서 수 참조를 전달 하 여 반환된 된 행의 각 열에 액세스할 수 있습니다는 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-106">You can access each column of the returned row by passing the name or ordinal reference of the column to the **DataReader**.</span></span> <span data-ttu-id="215e2-107">그러나 최고의 성능을 위해는 **DataReader** 일련의 네이티브 데이터 형식으로의 열 값에 액세스할 수 있도록 하는 메서드를 제공 합니다. (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**등).</span><span class="sxs-lookup"><span data-stu-id="215e2-107">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="215e2-108">공급자 관련 데이터에 대 한 형식화 된 접근자 메서드 목록을 **DataReaders**, 참조 <xref:System.Data.OleDb.OleDbDataReader> 및 <xref:System.Data.SqlClient.SqlDataReader>합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-108">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="215e2-109">기본 데이터 형식을 알고 있는 경우 형식화된 접근자 메서드를 사용하면 열 값을 검색할 때 필요한 형식 변환의 양이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-109">Using the typed accessor methods, assuming the underlying data type is known, reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="215e2-110">.NET Framework의 Windows Server 2003 릴리스에에 대 한 추가 속성을 포함 되어는 **DataReader**, **HasRows**, 하는 경우를 확인할 수 있습니다는 **DataReader**가에서 읽기 전에 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-110">The Windows Server 2003 release of the .NET Framework includes an additional property for the **DataReader**, **HasRows**, which enables you to determine if the **DataReader** has returned any results before reading from it.</span></span>  
  
 <span data-ttu-id="215e2-111">다음 코드 예제에서는 반복는 **DataReader** 개체 및 각 행에서 두 열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-111">The following code example iterates through a **DataReader** object, and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
 <span data-ttu-id="215e2-112">**DataReader** 절차적 논리를 효율적으로 데이터 소스에서 결과 순차적으로 처리할 수 있는 데이터의 버퍼링 되지 않은 스트림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-112">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="215e2-113">**DataReader** 데이터가 메모리에 캐시 되지 않으면 때문에 많은 양의 데이터를 검색할 때이 좋은 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-113">The **DataReader** is a good choice when retrieving large amounts of data because the data is not cached in memory.</span></span>  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="215e2-114">DataReader 닫기</span><span class="sxs-lookup"><span data-stu-id="215e2-114">Closing the DataReader</span></span>  
 <span data-ttu-id="215e2-115">항상 호출 해야는 **닫기** 메서드를 사용 하 여 완료 되 면는 **DataReader** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-115">You should always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="215e2-116">경우에 **명령** 출력을 포함 매개 변수 또는 반환 값 됩니다 때까지 사용할 수는 **DataReader** 닫혀 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-116">If your **Command** contains output parameters or return values, they will not be available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="215e2-117">하지만 한 **DataReader** 열려는 **연결** 에서 단독으로 사용 중인 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-117">Note that while a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="215e2-118">에 대 한 모든 명령을 실행할 수 없습니다는 **연결**, 하는 등 다른 **DataReader**, 원래 될 때까지 **DataReader** 닫혀 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-118">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="215e2-119">호출 하지 마십시오 **닫기** 또는 **Dispose** 에 **연결**, **DataReader**, 또는 다른 관리 되는 개체에는 **Finalize**  클래스의 메서드로 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-119">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="215e2-120">종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-120">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="215e2-121">클래스에 관리 되지 않는 리소스가 없는 경우 포함 되지 않습니다는 **Finalize** 클래스 정의에 메서드.</span><span class="sxs-lookup"><span data-stu-id="215e2-121">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="215e2-122">자세한 내용은 참조 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-122">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="215e2-123">NextResult를 사용하여 여러 개의 결과 집합 검색</span><span class="sxs-lookup"><span data-stu-id="215e2-123">Retrieving Multiple Result Sets using NextResult</span></span>  
 <span data-ttu-id="215e2-124">여러 개의 결과 집합이 반환 되는 경우는 **DataReader** 제공는 **NextResult** 결과 반복 하는 메서드 집합을 순서 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-124">If multiple result sets are returned, the **DataReader** provides the **NextResult** method to iterate through the result sets in order.</span></span> <span data-ttu-id="215e2-125">다음 예제에서는 <xref:System.Data.SqlClient.SqlDataReader>가 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 두 가지 SELECT 문 결과를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-125">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="215e2-126">DataReader에서 스키마 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="215e2-126">Getting Schema Information from the DataReader</span></span>  
 <span data-ttu-id="215e2-127">반면는 **DataReader** 은 열려 가져오면 현재 결과 사용 하 여 집합에 대 한 스키마 정보는 **GetSchemaTable** 메서드.</span><span class="sxs-lookup"><span data-stu-id="215e2-127">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="215e2-128">**GetSchemaTable** 반환는 <xref:System.Data.DataTable> 현재 결과 집합에 대 한 스키마 정보를 포함 하는 행과 열으로 채워진 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-128">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="215e2-129">**DataTable** 결과 집합의 각 열에 대해 하나의 행을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-129">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="215e2-130">스키마 테이블 행의 각 열에 반환 된 열의 속성에 매핑됩니다 있는 결과 집합은 **ColumnName** 속성의 이름이 며 열의 값은 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-130">Each column of the schema table row maps to a property of the column returned in the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="215e2-131">다음 코드 예제에 대 한 스키마 정보를 작성 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-131">The following code example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="215e2-132">OLE DB 장 사용</span><span class="sxs-lookup"><span data-stu-id="215e2-132">Working with OLE DB Chapters</span></span>  
 <span data-ttu-id="215e2-133">계층적 행 집합 또는 장 (OLE DB 형식 **DBTYPE_HCHAPTER**, ADO 형식 **adChapter**)를 사용 하 여 검색할 수는 <xref:System.Data.OleDb.OleDbDataReader>합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-133">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**) can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="215e2-134">장을 포함 하는 쿼리로 반환 될 때는 **DataReader**에 있는 열으로 반환 되 **DataReader** 되어으로 노출 되는 **DataReader** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-134">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="215e2-135">ADO.NET **DataSet** 테이블 간의 부모-자식 관계를 사용 하 여 계층적 행 집합을 나타내는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-135">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets using parent-child relationships between tables.</span></span> <span data-ttu-id="215e2-136">자세한 내용은 참조 [데이터 집합, Datatable 및 Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-136">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="215e2-137">다음 코드 예제에서는 MSDataShape 공급자를 사용하여 고객 목록에 있는 각 고객의 주문에 대해 장 열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-137">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")  
  
Dim custCMD As OleDbCommand = New OleDbCommand( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
connection.Open()  
  
Dim custReader As OleDbDataReader = custCMD.ExecuteReader()  
Dim orderReader As OleDbDataReader  
  
Do While custReader.Read()  
  Console.WriteLine("Orders for " & custReader.GetString(1))   
  ' custReader.GetString(1) = CompanyName  
  
  orderReader = custReader.GetValue(2)  
  ' custReader.GetValue(2) = Orders chapter as DataReader  
  
  Do While orderReader.Read()  
    Console.WriteLine(vbTab & orderReader.GetInt32(1))  
    ' orderReader.GetInt32(1) = OrderID  
  Loop  
  orderReader.Close()  
Loop  
' Make sure to always close readers and connections.  
custReader.Close()  
End Using  
```  
  
```csharp  
Using (OleDbConnection connection = new OleDbConnection(  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"));  
{  
OleDbCommand custCMD = new OleDbCommand(  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
connection.Open();  
  
OleDbDataReader custReader = custCMD.ExecuteReader();  
OleDbDataReader orderReader;  
  
while (custReader.Read())  
{  
  Console.WriteLine("Orders for " + custReader.GetString(1));   
  // custReader.GetString(1) = CompanyName  
  
  orderReader = (OleDbDataReader)custReader.GetValue(2);        
  // custReader.GetValue(2) = Orders chapter as DataReader  
  
  while (orderReader.Read())  
    Console.WriteLine("\t" + orderReader.GetInt32(1));          
    // orderReader.GetInt32(1) = OrderID  
  orderReader.Close();  
}  
// Make sure to always close readers and connections.  
custReader.Close();  
}  
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="215e2-138">Oracle REF CURSOR를 사용하여 결과 반환</span><span class="sxs-lookup"><span data-stu-id="215e2-138">Returning Results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="215e2-139">.NET Framework Data Provider for Oracle을 사용하면 Oracle REF CURSOR를 사용하여 쿼리 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-139">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="215e2-140">Oracle REF CURSOR는 <xref:System.Data.OracleClient.OracleDataReader>로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-140">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="215e2-141">검색할 수 있습니다는 **OracleDataReader** 개체를 사용 하 여 Oracle REF CURSOR 나타내는 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> 메서드를 지정할 수도 <xref:System.Data.OracleClient.OracleCommand> 으로 하나 이상의 Oracle REF Cursor를 반환 하는  **SelectCommand** 에 대 한 프로그램 <xref:System.Data.OracleClient.OracleDataAdapter> 채우는 데 사용 되는 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-141">You can retrieve an **OracleDataReader** object, that represents an Oracle REF CURSOR using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method, and you can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="215e2-142">Oracle 데이터 원본에서 반환 된 REF CURSOR에 액세스 하려면 만듭니다는 **OracleCommand** 쿼리에 대 한 출력 매개 변수를 REF CURSOR를 참조 하는 추가 된 **매개 변수** 프로그램 의컬렉션 **OracleCommand**합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-142">To access a REF CURSOR returned from an Oracle data source, create an **OracleCommand** for your query and add an output parameter that references the REF CURSOR to the **Parameters** collection of your **OracleCommand**.</span></span> <span data-ttu-id="215e2-143">매개 변수 이름은 쿼리의 REF CURSOR 매개 변수 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="215e2-144">매개 변수의 유형을 설정 **OracleType.Cursor**합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-144">Set the type of the parameter to **OracleType.Cursor**.</span></span> <span data-ttu-id="215e2-145">**ExecuteReader** 방식의 프로그램 **OracleCommand** 돌아갑니다는 **OracleDataReader** REF CURSOR에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-145">The **ExecuteReader** method of your **OracleCommand** will return an **OracleDataReader** for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="215e2-146">경우에 **OracleCommand** 여러 multiple REF CURSOR를 반환 합니다. 여러 출력 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-146">If your **OracleCommand** returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="215e2-147">호출 하 여 서로 다른 REF Cursor에 액세스할 수 있습니다는 **OracleCommand.ExecuteReader** 메서드.</span><span class="sxs-lookup"><span data-stu-id="215e2-147">You can access the different REF CURSORs by calling the **OracleCommand.ExecuteReader** method.</span></span> <span data-ttu-id="215e2-148">에 대 한 호출 **ExecuteReader** 반환는 **OracleDataReader** 첫 REF CURSOR를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-148">The call to **ExecuteReader** returns an **OracleDataReader** referencing the first REF CURSOR.</span></span> <span data-ttu-id="215e2-149">호출할 수 있습니다는 **OracleDataReader.NextResult** 에 나오는 REF Cursor에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-149">You can then call the **OracleDataReader.NextResult** method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="215e2-150">하지만 매개 변수 여 **OracleCommand.Parameters** 컬렉션 REF CURSOR 출력 매개 변수 이름으로는 **OracleDataReader** 는 에추가된순서대로액세스 **매개 변수** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-150">Although the parameters in your **OracleCommand.Parameters** collection match the REF CURSOR output parameters by name, the **OracleDataReader** accesses them in the order that they were added to the **Parameters** collection.</span></span>  
  
 <span data-ttu-id="215e2-151">예를 들어, 다음과 같은 Oracle 패키지 및 패키지 본문이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-151">For example, consider the following Oracle package and package body.</span></span>  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 <span data-ttu-id="215e2-152">다음 코드에서는 **OracleCommand** 형식의 두 매개 변수를 추가 하 여 이전 Oracle 패키지에서 REF Cursor를 반환 하는 **OracleType.Cursor** 에 **매개변수** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-152">The following code creates an **OracleCommand** that returns the REF CURSORs from the previous Oracle package by adding two parameters of type **OracleType.Cursor** to the **Parameters** collection.</span></span>  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 <span data-ttu-id="215e2-153">사용 하 여 이전 명령의 결과 반환 하는 다음 코드는 **읽기** 및 **NextResult** 의 메서드는 **OracleDataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-153">The following code returns the results of the previous command using the **Read** and **NextResult** methods of the **OracleDataReader**.</span></span> <span data-ttu-id="215e2-154">REF CURSOR 매개 변수가 순서대로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-154">The REF CURSOR parameters are returned in order.</span></span>  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 <span data-ttu-id="215e2-155">다음 예제에서는 이전 명령을 채우는 데 사용 하 여 한 **데이터 집합** Oracle 패키지의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-155">The following example uses the previous command to populate a **DataSet** with the results of the Oracle package.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="215e2-156">방지 하기 위해는 **OverflowException**, 모든에서 변환 Oracle NUMBER 형식 유효한.NET Framework 형식에 값을 저장 하기 전에 처리 하는 것이 좋습니다는 **DataRow**합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a **DataRow**.</span></span> <span data-ttu-id="215e2-157">사용할 수는 **FillError** 여부를 확인 하는 이벤트는 **OverflowException** 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-157">You can use the **FillError** event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="215e2-158">대 한 자세한 내용은 **FillError** 이벤트 참조 [DataAdapter 이벤트 처리](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="215e2-158">For more information on the **FillError** event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```  
  
## <a name="see-also"></a><span data-ttu-id="215e2-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="215e2-159">See Also</span></span>  
 [<span data-ttu-id="215e2-160">DataReaders 작업</span><span class="sxs-lookup"><span data-stu-id="215e2-160">Working with DataReaders</span></span>](http://msdn.microsoft.com/en-us/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="215e2-161">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="215e2-161">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="215e2-162">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="215e2-162">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="215e2-163">데이터베이스 스키마 정보 검색</span><span class="sxs-lookup"><span data-stu-id="215e2-163">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [<span data-ttu-id="215e2-164">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="215e2-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
