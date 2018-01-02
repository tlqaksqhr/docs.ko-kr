---
title: DataTables
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3803d550fe345c6f485dd204cc119f8a927a3501
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="datatables"></a><span data-ttu-id="79f91-102">DataTables</span><span class="sxs-lookup"><span data-stu-id="79f91-102">DataTables</span></span>
<span data-ttu-id="79f91-103"><xref:System.Data.DataSet>은 테이블 컬렉션, 관계 및 제약 조건으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-103">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="79f91-104">Ado.net에서는 <xref:System.Data.DataTable> 개체의 테이블을 표시 하는 데 사용 됩니다는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-104">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="79f91-105">A **DataTable** 하나의 테이블을 메모리 내 관계형 데이터를 나타내며 데이터에 로컬인는 합니다. .NET 기반 응용 프로그램은 상주 하지만 Microsoft SQL Server를 사용 하 여 같은 데이터 원본에서 채울 수 있습니다는 **DataAdapter** 자세한 내용은 참조 [DataAdapter에서 DataSet 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .</span><span class="sxs-lookup"><span data-stu-id="79f91-105">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="79f91-106">**DataTable** 클래스의 멤버는는 **System.Data** 네임 스페이스는.NET Framework 클래스 라이브러리 내에서.</span><span class="sxs-lookup"><span data-stu-id="79f91-106">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="79f91-107">만들고 사용 하는 **DataTable** 독립적으로 또는의 구성원으로는 **DataSet**, 및 **DataTable** 개체 다른.NET Framework 개체와 함께에서 사용할 수도 있습니다 포함 하는 <xref:System.Data.DataView>합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-107">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="79f91-108">테이블 컬렉션에 액세스 한 **데이터 집합** 통해는 **테이블** 속성의는 **데이터 집합** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-108">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="79f91-109">테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-109">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="79f91-110">스키마를 정의 **DataTable** 를 사용 하 여 <xref:System.Data.DataColumn> 개체와 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-110">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="79f91-111">테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-111">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="79f91-112">스키마 이외에 **DataTable** 행을 포함 하 고 주문 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-112">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="79f91-113"><xref:System.Data.DataRow> 클래스는 테이블에 포함된 실제 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-113">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="79f91-114">사용 하면는 **DataRow** 및 해당 속성 및 메서드를 검색 하기 위해 평가 하 고 테이블의 데이터를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-114">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="79f91-115">액세스 하 고 행 데이터를 변경할 때의 **DataRow** 개체의 현재 및 원래의 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-115">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="79f91-116">테이블에서 하나 이상의 관련 열을 사용하면 테이블 간에 부모-자식 관계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-116">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="79f91-117">간의 관계를 만들면 **DataTable** 를 사용 하 여 개체는 <xref:System.Data.DataRelation>합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-117">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="79f91-118">**DataRelation** 개체는 특정 행의 관련된 자식 또는 부모 행을 반환 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-118">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="79f91-119">자세한 내용은 참조 [Datarelation 추가](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-119">For more information, see [Adding DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79f91-120">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="79f91-120">In This Section</span></span>  
 [<span data-ttu-id="79f91-121">DataTable 만들기</span><span class="sxs-lookup"><span data-stu-id="79f91-121">Creating a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 <span data-ttu-id="79f91-122">만드는 방법을 설명는 **DataTable** 에 추가 하는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-122">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="79f91-123">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="79f91-123">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 <span data-ttu-id="79f91-124">만들기 및 사용 하는 방법에 대 한 정보를 제공 **DataColumn** 개체 및 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-124">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="79f91-125">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="79f91-125">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="79f91-126">테이블에서 데이터를 추가, 수정 및 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-126">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="79f91-127">사용 하는 방법에 설명 **DataTable** 데이터 테이블의 변경 내용을 검사 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-127">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="79f91-128">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="79f91-128">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 <span data-ttu-id="79f91-129">사용 하기 위해 사용할 수 있는 이벤트에 대 한 정보를 제공는 **DataTable**, 열 값이 수정 되 고 행이 추가 되거나 삭제 될 때 이벤트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-129">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="79f91-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="79f91-130">Related Sections</span></span>  
 [<span data-ttu-id="79f91-131">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="79f91-131">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="79f91-132">ADO.NET 아키텍처 및 구성 요소에 대해 설명하고, 이를 사용하여 기존 데이터 소스에 액세스하고 응용 프로그램 데이터를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-132">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="79f91-133">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="79f91-133">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="79f91-134">ADO.NET에 대 한 정보를 제공 **DataSet** 테이블 간의 관계를 만드는 방법에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-134">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="79f91-135">에 대 한 참조 정보를 제공는 **제약 조건** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-135">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="79f91-136">에 대 한 참조 정보를 제공는 **DataColumn** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-136">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="79f91-137">에 대 한 참조 정보를 제공는 **DataSet** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-137">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="79f91-138">에 대 한 참조 정보를 제공는 **DataTable** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-138">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="79f91-139">클래스 라이브러리 개요</span><span class="sxs-lookup"><span data-stu-id="79f91-139">Class Library Overview</span></span>](../../../../../docs/standard/class-library-overview.md)  
 <span data-ttu-id="79f91-140">.NET Framework 클래스 라이브러리에 간략하게 포함 하는 **시스템** 네임 스페이스의 2 차 네임 스페이스 뿐만 아니라 **System.Data**합니다.</span><span class="sxs-lookup"><span data-stu-id="79f91-140">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f91-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79f91-141">See Also</span></span>  
 [<span data-ttu-id="79f91-142">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="79f91-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
