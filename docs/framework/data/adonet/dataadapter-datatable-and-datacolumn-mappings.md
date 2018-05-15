---
title: DataAdapter DataTable 및 DataColumn 매핑
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 1b426dbcdc78ecfddeac003616993849ce60b89c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="ab2cd-102">DataAdapter DataTable 및 DataColumn 매핑</span><span class="sxs-lookup"><span data-stu-id="ab2cd-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="ab2cd-103">A **DataAdapter** 0 개 이상의 컬렉션을 포함 <xref:System.Data.Common.DataTableMapping> 개체에 해당 **TableMappings** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="ab2cd-104">A **DataTableMapping** 데이터 원본에 대해 쿼리에서 반환 된 데이터 간의 마스터 매핑을 제공 및 <xref:System.Data.DataTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="ab2cd-105">**DataTableMapping** 이름 자리에 전달 될 수 있습니다는 **DataTable** 이름에 **채우기** 의 메서드는 **DataAdapter**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="ab2cd-106">다음 예제에서는 한 **DataTableMapping** 라는 **AuthorsMapping** 에 대 한는 **작성자** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="ab2cd-107">A **DataTableMapping** 의 열 이름을 사용할 수 있습니다는 **DataTable** 데이터베이스의 다른 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="ab2cd-108">**DataAdapter** 는 테이블이 업데이트 될 때 열을 일치 하는 매핑을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="ab2cd-109">지정 하지 않는 경우는 **TableName** 또는 **DataTableMapping** 이름을 호출 하는 경우는 **채우기** 또는 **업데이트** 의 메서드는  **DataAdapter**, **DataAdapter** 찾습니다는 **DataTableMapping** "Table" 이라는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="ab2cd-110">해당 경우 **DataTableMapping** 존재 하지 않는 **TableName** 의 **DataTable** 은 "Table"입니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="ab2cd-111">기본값을 지정할 수 **DataTableMapping** 만들어는 **DataTableMapping** "Table"의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="ab2cd-112">다음 코드 예제에서는 **DataTableMapping** (에서 <xref:System.Data.Common> 네임 스페이스)에서 지정 된 기본 매핑을 사용 하면 **DataAdapter** "Table" 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="ab2cd-113">이 예제에는 다음 쿼리 결과에서 첫 번째 테이블의에서 열을 매핑합니다 (의 **고객** 테이블의는 **Northwind** 데이터베이스)의 더 친숙 한 이름 집합에는 **Northwind Customers**  테이블에 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ab2cd-114">매핑되지 않는 열의 경우 데이터 소스의 열 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="ab2cd-115">더 고급 시나리오에서는 결정할 수 있습니다 사용할 동일한 **DataAdapter** 다른 매핑 사용 하 여 다른 테이블의 로드를 지원 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="ab2cd-116">이 수행 하려면 추가 하기만 하면 **DataTableMapping** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="ab2cd-117">때는 **채우기** 메서드의 인스턴스를 전달 되는 **데이터 집합** 및 **DataTableMapping** 이름, 해당 이름의 매핑이 있으면이 고, 그렇지 않으면 사용 되는 한  **DataTable** 해당 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="ab2cd-118">다음 예제에서는 한 **DataTableMapping** 의 이름으로 **고객** 및 **DataTable** 이름 **BizTalkSchema**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="ab2cd-119">예제에서는 다음를 SELECT 문에서 반환한 행을 매핑하는 **BizTalkSchema** **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  <span data-ttu-id="ab2cd-120">열 매핑에 소스 열 이름을 제공하지 않거나 테이블 매핑에 소스 테이블 이름을 제공하지 않으면 기본 이름이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="ab2cd-121">열 매핑의 증분 기본 이름인 제공 됩니다 열 매핑에 소스 열 제공 되는 경우 **SourceColumn** *N,* 부터는 **SourceColumn1**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="ab2cd-122">테이블 매핑에 증분 기본 이름인 제공 됩니다 테이블 매핑에 소스 테이블 이름을 제공 되는 경우 **SourceTable** *N*부터 **SourceTable1**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab2cd-123">명명 규칙을 방지 하는 것이 좋습니다 **SourceColumn** *N* 열 매핑에 또는 **SourceTable** *N* 테이블에 대 한 변수에 있는 기존의 기본 열 매핑 이름과 충돌할 수 있기 때문에 매핑하는 **ColumnMappingCollection** 또는 테이블 매핑 이름에는 **DataTableMappingCollection** .</span><span class="sxs-lookup"><span data-stu-id="ab2cd-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="ab2cd-124">이미 있는 이름을 제공하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="ab2cd-125">여러 개의 결과 집합 처리</span><span class="sxs-lookup"><span data-stu-id="ab2cd-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="ab2cd-126">경우에 **SelectCommand** 여러 테이블을 반환 **채우기** 테이블에 대 한 증분 값을 갖는 테이블 이름을 자동으로 생성는 **데이터 집합**부터 테이블 이름 사이에서 형식 지정 **TableName** *N*부터 **TableName1**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="ab2cd-127">테이블 매핑을 사용 하 여 원하는 테이블에 대해 지정 된 이름에 자동으로 생성 된 테이블 이름을 매핑하는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="ab2cd-128">예는 **SelectCommand** 두 테이블을 반환 하는 **고객** 및 **Orders**, 다음 호출을 실행 **채우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="ab2cd-129">두 테이블에서 생성 됩니다는 **DataSet**: **고객** 및 **Customers1**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="ab2cd-130">테이블 매핑을 사용 하 여 두 번째 테이블은 이름이 있는지 확인 하기 위한 **Orders** 대신 **Customers1**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="ab2cd-131">이 수행 하려면 원본 테이블의 매핑 **Customers1** 에 **데이터 집합** 테이블 **Orders**다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab2cd-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab2cd-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab2cd-132">See Also</span></span>  
 [<span data-ttu-id="ab2cd-133">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="ab2cd-133">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="ab2cd-134">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="ab2cd-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="ab2cd-135">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ab2cd-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
