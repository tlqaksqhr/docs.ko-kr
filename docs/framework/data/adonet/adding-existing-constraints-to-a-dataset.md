---
title: "데이터 집합에 기존 제약 조건 추가"
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
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2f2f6c60197b1d71feb13ca351ad19298e09ea56
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="69909-102">데이터 집합에 기존 제약 조건 추가</span><span class="sxs-lookup"><span data-stu-id="69909-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="69909-103">**채우기** 의 메서드는 **DataAdapter** 채웁니다는 <xref:System.Data.DataSet> 는 테이블 열과 데이터 원본의 행만 하지만 제약 조건을 일반적으로 설정 하 여 데이터 원본에서 **채우기** 메서드는이 스키마 정보를 추가 하지 않습니다는 **DataSet** 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="69909-104">채우는 한 **데이터 집합** 데이터 소스의 기존 기본 키 제약 조건 정보로 호출할 수 있습니다는 **FillSchema** 의 메서드는 **DataAdapter**, 설정 또는 **MissingSchemaAction** 의 속성은 **DataAdapter** 를 **AddWithKey** 호출 하기 전에 **채우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="69909-105">이렇게 하면 해당 기본 키 제약 조건에는 **DataSet** 데이터 소스에서 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="69909-106">외래 키 제약 조건 정보에 포함 되며에 표시 된 대로 명시적으로 만들어야 합니다 [DataTable 제약 조건](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="69909-107">스키마 정보를 추가 **DataSet** primary key 제약 조건에 포함 된 사용 하면 데이터로 채우기 전에 <xref:System.Data.DataTable> 개체에 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="69909-108">결과적으로 추가 하는 경우 입력에 대 한 호출의 **데이터 집합** 계산 되는 기본 키 열 정보 각에서 현재 행이 포함 된 데이터 원본에서 새 행과 일치 하는 데 사용 됩니다 **DataTable**, 및의 현재 데이터 데이터 원본의 데이터로 테이블을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="69909-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="69909-109">스키마 정보가 없으면 데이터 원본에서 새 행에 추가 되는 **데이터 집합**로 중복 행.</span><span class="sxs-lookup"><span data-stu-id="69909-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69909-110">데이터 원본의 열에 자동 증분으로 식별 되는 **FillSchema** 메서드, 또는 **채우기** 메서드를 한 **MissingSchemaAction** 의  **AddWithKey**, 만듭니다는 **DataColumn** 와 **AutoIncrement** 속성이로 설정 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="69909-111">그러나 설정 해야 합니다는 **AutoIncrementStep** 및 **AutoIncrementSeed** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="69909-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="69909-112">자동 증가 열에 대 한 자세한 내용은 참조 [AutoIncrement 열 만들기](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="69909-113">사용 하 여 **FillSchema** 또는 설정은 **MissingSchemaAction** 를 **AddWithKey** 기본 키 열 정보를 확인 하려면 데이터 원본에 대 한 추가 처리가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="69909-114">이러한 추가 처리로 인해 성능이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69909-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="69909-115">디자인 타임에 기본 키 정보를 알고 있으면 기본 키 열을 명시적으로 지정하여 최상의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69909-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="69909-116">테이블에 대 한 기본 키 정보를 명시적으로 설정 하는 방법에 대 한 정보를 참조 하십시오. [기본 키 정의](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="69909-117">다음 코드 예제에서는 스키마 정보를 추가 하는 방법을 보여 줍니다.는 **DataSet** 를 사용 하 여 **FillSchema**합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="69909-118">다음 코드 예제에서는 스키마 정보를 추가 하는 방법을 보여 줍니다.는 **데이터 집합** 를 사용 하 여는 **MissingSchemaAction.AddWithKey** 의 속성은 **채우기** 메서드.</span><span class="sxs-lookup"><span data-stu-id="69909-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="69909-119">여러 개의 결과 집합 처리</span><span class="sxs-lookup"><span data-stu-id="69909-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="69909-120">경우는 **DataAdapter** 에서 반환 된 여러 결과 집합에서 발견 된 **SelectCommand**에서 여러 테이블을 만드는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="69909-121">테이블의 0부터 시작 증분 기본 이름인 하 게 할 **테이블** *N*부터 **테이블** "table0"입니다.</span><span class="sxs-lookup"><span data-stu-id="69909-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="69909-122">테이블 이름에 대 한 인수로 전달 됩니다는 **FillSchema** 메서드, 테이블 이름이 지정 됩니다는 0부터 시작 증분의 **TableName** *N* 부터**TableName** "tablename0"입니다.</span><span class="sxs-lookup"><span data-stu-id="69909-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69909-123">경우는 **FillSchema** 의 메서드는 **OleDbDataAdapter** 개체를 여러 개의 결과 집합을 반환 하는 명령에 대 한 호출을 첫 번째 결과 집합의 스키마 정보만 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69909-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="69909-124">여러 결과 대 한 스키마 정보를 반환할가 사용 하 여를 집합 때는 **OleDbDataAdapter**를 지정 하는 것이 좋습니다.는 **MissingSchemaAction** 의 **AddWithKey** 호출할 때 스키마 정보를 가져오려면는 **채우기** 메서드.</span><span class="sxs-lookup"><span data-stu-id="69909-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69909-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69909-125">See Also</span></span>  
 [<span data-ttu-id="69909-126">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="69909-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="69909-127">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="69909-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="69909-128">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="69909-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="69909-129">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="69909-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
