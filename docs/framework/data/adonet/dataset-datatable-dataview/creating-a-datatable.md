---
title: "DataTable 만들기"
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
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 94fa5507d71fef557baadc6ee8979efeee4acf40
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-datatable"></a><span data-ttu-id="d75d5-102">DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="d75d5-102">Creating a DataTable</span></span>
<span data-ttu-id="d75d5-103"><xref:System.Data.DataTable>은 메모리 내 관계형 데이터가 포함된 하나의 테이블을 나타내며, 독립적으로 만들어 사용하거나 다른 .NET Framework 개체에 의해 사용될 수도 있습니다. 이 경우에는 주로 <xref:System.Data.DataSet>의 멤버로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="d75d5-104">만들 수는 **DataTable** 적절 한 사용 하 여 개체 **DataTable** 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="d75d5-105">에 추가할 수 있습니다는 **DataSet** 를 사용 하 여는 **추가** 메서드를 추가 하는 **DataTable** 개체의 **테이블** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="d75d5-106">만들 수도 있습니다 **DataTable** 내에서 개체는 **DataSet** 를 사용 하 여는 **채우기** 또는 **FillSchema** 의 메서드는  **DataAdapter** 개체 또는 미리 정의 된 또는 유추 된 XML 스키마 사용 하 여는 **ReadXml**, **ReadXmlSchema**, 또는 **InferXmlSchema** 메서드는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="d75d5-107">에 추가 하면 사용자에 게 유의 **DataTable** 의 구성원으로는 **테이블** 하나의 컬렉션 **데이터 집합**, 다른 의테이블컬렉션에추가할수없습니다**DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="d75d5-108">처음 만드는 경우는 **DataTable**, 스키마 (구조)가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="d75d5-109">테이블의 스키마를 정의 하려면 만들고 해야 추가 <xref:System.Data.DataColumn> 개체는 **열** 테이블의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="d75d5-110">있습니다 수는 테이블에 대 한 기본 키 열을 정의 하 고 만들고 추가할 수도 **제약 조건** 개체는 **제약 조건을** 테이블의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="d75d5-111">에 대 한 스키마를 정의 하면는 **DataTable**, 추가 하 여 테이블에 데이터 행을 추가할 수 있습니다 **DataRow** 개체는 **행** 테이블의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="d75d5-112">에 대 한 값을 제공 하지 않아도 됩니다는 <xref:System.Data.DataTable.TableName%2A> 속성 만들 때 한 **DataTable**; 다른 시간에 속성을 지정 하거나 비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="d75d5-113">그러나 없는 테이블을 추가 하는 하면는 **TableName** 값을 한 **데이터 집합**, 테이블에는 증분 기본 이름인 Table 제공 됩니다*N*Table0 "Table"로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d75d5-114">방지 하는 것이 좋습니다는 "테이블*N*" 명명 규칙을 제공 하는 경우는 **TableName** 값을 제공 하는 이름에 있는 기존의 기본 테이블 이름과 충돌이 발생할 수 있습니다는 **데이터 집합** .</span><span class="sxs-lookup"><span data-stu-id="d75d5-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="d75d5-115">이미 있는 이름을 입력하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="d75d5-116">다음 예제에서는의 인스턴스는 **DataTable** 개체 하 고 이름을 "Customers" 할당</span><span class="sxs-lookup"><span data-stu-id="d75d5-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="d75d5-117">다음 예제에서는 인스턴스를 만듭니다는 **DataTable** 추가 하 여는 **테이블** 의 컬렉션을 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="d75d5-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="d75d5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d75d5-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="d75d5-119">DataTable</span><span class="sxs-lookup"><span data-stu-id="d75d5-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="d75d5-120">DataAdapter에서 데이터 집합 채우기</span><span class="sxs-lookup"><span data-stu-id="d75d5-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="d75d5-121">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="d75d5-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="d75d5-122">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="d75d5-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="d75d5-123">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d75d5-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
