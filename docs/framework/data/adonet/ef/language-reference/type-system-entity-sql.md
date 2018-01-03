---
title: "형식 시스템(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 333ae9a6b7d85298e02364f583903c2cd4b03d51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="type-system-entity-sql"></a><span data-ttu-id="323ef-102">형식 시스템(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="323ef-102">Type System (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="323ef-103">형식의 수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-103"> supports a number of types:</span></span>  
  
-   <span data-ttu-id="323ef-104">기본(단순) 형식 - `Int32` 및 `String.`</span><span class="sxs-lookup"><span data-stu-id="323ef-104">Primitive (simple) types such as `Int32` and `String.`</span></span>  
  
-   <span data-ttu-id="323ef-105">명목 형식 - 스키마에서 정의됨. <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> 및 <xref:System.Data.Metadata.Edm.RelationshipType></span><span class="sxs-lookup"><span data-stu-id="323ef-105">Nominal types that are defined in the schema, such as <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType>, and <xref:System.Data.Metadata.Edm.RelationshipType>.</span></span>  
  
-   <span data-ttu-id="323ef-106">익명 형식 - 스키마에서 명시적으로 정의되지 않음. <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> 및 <xref:System.Data.Metadata.Edm.RefType></span><span class="sxs-lookup"><span data-stu-id="323ef-106">Anonymous types that are not defined in the schema explicitly: <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType>, and <xref:System.Data.Metadata.Edm.RefType>.</span></span>  
  
 <span data-ttu-id="323ef-107">이 단원에서는 스키마에서 명시적으로 정의되지 않았지만 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 익명 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-107">This section discusses the anonymous types that are not defined in the schema explicitly but are supported by [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="323ef-108">기본 및 일반 형식에 대 한 자세한 내용은 참조 하십시오. [개념적 모델 형식 (CSDL)](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-108">For information on primitive and nominal types, see [Conceptual Model Types (CSDL)](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4).</span></span>  
  
## <a name="rows"></a><span data-ttu-id="323ef-109">행</span><span class="sxs-lookup"><span data-stu-id="323ef-109">Rows</span></span>  
 <span data-ttu-id="323ef-110">행의 구조는 행이 구성된 형식화된 멤버 및 명명된 멤버의 시퀀스에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-110">The structure of a row depends on the sequence of typed and named members that the row consists of.</span></span> <span data-ttu-id="323ef-111">행 형식은 ID를 갖지 않으며 상속받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-111">A row type has no identity and cannot be inherited from.</span></span> <span data-ttu-id="323ef-112">멤버가 각각 동일한 경우 같은 행 형식의 인스턴스는 서로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-112">Instances of the same row type are equivalent if the members are respectively equivalent.</span></span> <span data-ttu-id="323ef-113">행은 구조가 동일한 것을 제외한 어떠한 동작도 갖지 않으며 공용 언어 런타임에 해당하는 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-113">Rows have no behavior beyond their structural equivalence and have no equivalent in the common language runtime.</span></span> <span data-ttu-id="323ef-114">쿼리를 실행하면 행 또는 행 컬렉션이 포함된 구조가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-114">Queries can result in structures that contain rows or collections of rows.</span></span> <span data-ttu-id="323ef-115">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리와 호스트 언어 간의 API 바인딩은 결과를 생성하는 쿼리에서 행이 구현되는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-115">The API binding between the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries and the host language defines how rows are realized in the query that produced the result.</span></span> <span data-ttu-id="323ef-116">행 인스턴스를 생성 하는 방법에 대 한 정보를 참조 하십시오. [생성 형식](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-116">For information on how to construct a row instance, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="323ef-117">컬렉션</span><span class="sxs-lookup"><span data-stu-id="323ef-117">Collections</span></span>  
 <span data-ttu-id="323ef-118">컬렉션 형식은 다른 개체의 0개 이상 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-118">Collection types represent zero or more instances of other objects.</span></span> <span data-ttu-id="323ef-119">컬렉션을 구성 하는 방법에 대 한 정보를 참조 하십시오. [생성 형식](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-119">For information on how to construct collection, see [Constructing Types](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="323ef-120">참조</span><span class="sxs-lookup"><span data-stu-id="323ef-120">References</span></span>  
 <span data-ttu-id="323ef-121">참조는 특정 엔터티 집합 내의 특정 엔터티를 가리키는 논리 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-121">A reference is a logical pointer to a specific entity in a specific entity set.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="323ef-122">에서는 참조를 통한 생성, 해체 및 탐색에 사용되는 다음 연산자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-122"> supports the following operators to construct, deconstruct, and navigate through references:</span></span>  
  
-   [<span data-ttu-id="323ef-123">REF</span><span class="sxs-lookup"><span data-stu-id="323ef-123">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
  
-   [<span data-ttu-id="323ef-124">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="323ef-124">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
  
-   [<span data-ttu-id="323ef-125">KEY</span><span class="sxs-lookup"><span data-stu-id="323ef-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
  
-   [<span data-ttu-id="323ef-126">DEREF</span><span class="sxs-lookup"><span data-stu-id="323ef-126">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
  
 <span data-ttu-id="323ef-127">멤버 액세스(dot) 연산자(`.`)를 사용하여 참조를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-127">You can navigate through a reference by using the member access (dot) operator(`.`).</span></span> <span data-ttu-id="323ef-128">다음 조각에서는 r(참조) 속성을 탐색하여 Id 속성(Order)을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-128">The following snippet extracts the Id property (of Order) by navigating through the r (reference) property.</span></span>  
  
```  
select o2.r.Id   
from (select ref(o) as r from LOB.Orders as o) as o2   
```  
  
 <span data-ttu-id="323ef-129">참조 값이 null이거나 참조 대상이 존재하지 않는 경우 결과는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="323ef-129">If the reference value is null, or if the target of the reference does not exist, the result is null.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="323ef-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="323ef-130">See Also</span></span>  
 [<span data-ttu-id="323ef-131">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="323ef-131">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="323ef-132">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="323ef-132">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="323ef-133">CAST</span><span class="sxs-lookup"><span data-stu-id="323ef-133">CAST</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)  
 [<span data-ttu-id="323ef-134">CSDL, SSDL 및 MSL 사양</span><span class="sxs-lookup"><span data-stu-id="323ef-134">CSDL, SSDL, and MSL Specifications</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
