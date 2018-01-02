---
title: "DataTable에 열 추가"
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
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 423b9ed389a5a3750c8e9b0339e0887d6b650741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="0a138-102">DataTable에 열 추가</span><span class="sxs-lookup"><span data-stu-id="0a138-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="0a138-103">A <xref:System.Data.DataTable> 의 컬렉션을 포함 <xref:System.Data.DataColumn> 에서 참조 한 개체는 **열** 테이블의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="0a138-104">이 열 컬렉션과 모든 제약 조건을 함께 사용하여 테이블의 스키마나 구조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="0a138-105">만들 **DataColumn** 사용 하 여 테이블 내에서 개체는 **DataColumn** 생성자를 호출 하 여는 **추가** 의 메서드는 **열**되는 테이블의 속성을 <xref:System.Data.DataColumnCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="0a138-106">**추가** 메서드에 선택적 **ColumnName**, **DataType**, 및 **식** 인수 하 고 새 만듭니다  **DataColumn** 컬렉션의 구성원으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="0a138-107">에서도 기존의 적용 **DataColumn** 개체를 컬렉션에 추가 하며 추가에 대 한 참조를 반환 **DataColumn** 요청 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="0a138-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="0a138-108">때문에 **DataTable** 의 데이터 형식을 지정할 때 사용 되는.NET Framework 형식, 개체를 데이터 소스로 한정 되지 않는 한 **DataColumn**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="0a138-109">다음 예제에서는 4 번째 열에는 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-109">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="0a138-110">예제에서는 다음에 유의 대 한 속성의 **CustID** 열을 허용 하지 않도록 설정 **DBNull** 값 및 값을 고유 값을 제한 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="0a138-111">그러나 정의 하는 경우는 **CustID** 열 테이블의 기본 키 열으로는 **AllowDBNull** 속성으로 자동 설정 **false** 및는 **Unique** 속성으로 자동 설정 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="0a138-112">자세한 내용은 참조 [기본 키 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-112">For more information, see [Defining Primary Keys](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0a138-113">열에는 열에는 증분 기본 이름인 지정할은 열 이름이 열에 대해 제공 되지 않은 경우*N,* "Column1" 부터는 것에 추가 된 경우는 **DataColumnCollection**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="0a138-114">명명 규칙을 방지 하는 것이 좋습니다 "열*N*"에 있는 기존의 기본 열 이름과 충돌이 발생할 수 있습니다 제공 이름을 하기 때문에 열 이름을 제공 하는 경우는 **DataColumnCollection**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="0a138-115">이미 있는 이름을 입력하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="0a138-116"><xref:System.Xml.Linq.XElement>를 <xref:System.Data.DataColumn.DataType%2A>에서 <xref:System.Data.DataColumn>의 <xref:System.Data.DataTable>로 사용하는 경우 데이터를 읽을 때 XML serialization이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="0a138-117">예를 들어 <xref:System.Xml.XmlDocument> 메서드를 사용하여 `DataTable.WriteXml`를 작성하는 경우 XML에 대한 serialization 수행 시 <xref:System.Xml.Linq.XElement>에 추가 부모 노드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="0a138-118">이 문제를 해결하려면 <xref:System.Data.SqlTypes.SqlXml> 대신 <xref:System.Xml.Linq.XElement> 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="0a138-119">`ReadXml` 및 `WriteXml`이 <xref:System.Data.SqlTypes.SqlXml>와 올바르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0a138-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a138-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a138-120">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="0a138-121">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="0a138-121">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="0a138-122">DataTable</span><span class="sxs-lookup"><span data-stu-id="0a138-122">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="0a138-123">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="0a138-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
