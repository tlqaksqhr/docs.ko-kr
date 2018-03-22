---
title: CREATEREF (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8de4266277be31fd51411d4b994f1b5de45f13df
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="createref-entity-sql"></a><span data-ttu-id="838b1-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="838b1-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="838b1-103">entityset의 엔터티에 대한 참조를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="838b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="838b1-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="838b1-105">인수</span><span class="sxs-lookup"><span data-stu-id="838b1-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="838b1-106">문자열 리터럴이 아니라 entityset 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="838b1-107">엔터티 형식의 키 속성에 해당하는 행 형식의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="838b1-108">설명</span><span class="sxs-lookup"><span data-stu-id="838b1-108">Remarks</span></span>  
 <span data-ttu-id="838b1-109">`row_typed_expression` 은 엔터티의 키 유형과 구조적으로 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="838b1-110">다시 말해서, 필드의 개수와 형식 및 배열 순서가 엔터티 키와 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="838b1-111">아래 예제에서 Order와 BadOrder는 모두 Order 형식의 entityset이며, Id는 Order의 단일 키 속성인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="838b1-112">예제에서는 BadOrder의 엔터티에 대한 참조를 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="838b1-113">이 참조는 현수 참조일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="838b1-114">다시 말해서, 참조가 특정 엔터티를 실제로 나타내지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="838b1-115">이런 경우 해당 참조에 대해 `DEREF` 작업을 수행하면 null이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="838b1-116">예</span><span class="sxs-lookup"><span data-stu-id="838b1-116">Example</span></span>  
 <span data-ttu-id="838b1-117">다음 Entity SQL 쿼리는 CREATEREF 연산자를 사용하여 엔터티 집합 내의 엔터티에 대한 참조를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="838b1-118">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="838b1-119">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="838b1-119">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="838b1-120">[방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="838b1-121">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="838b1-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="838b1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="838b1-122">See Also</span></span>  
 [<span data-ttu-id="838b1-123">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="838b1-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="838b1-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="838b1-124">DEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [<span data-ttu-id="838b1-125">KEY</span><span class="sxs-lookup"><span data-stu-id="838b1-125">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="838b1-126">REF</span><span class="sxs-lookup"><span data-stu-id="838b1-126">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
