---
title: CAST(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 97971668430dd7721b15a4ac60e422fe06f0ed1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cast-entity-sql"></a><span data-ttu-id="0e817-102">CAST(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0e817-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="0e817-103">데이터 형식의 식을 다른 형식의 식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e817-104">구문</span><span class="sxs-lookup"><span data-stu-id="0e817-104">Syntax</span></span>  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e817-105">인수</span><span class="sxs-lookup"><span data-stu-id="0e817-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0e817-106">`data_type`으로 변환 가능한 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="0e817-107">대상 시스템 제공 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-107">The target system-supplied data type.</span></span> <span data-ttu-id="0e817-108">기본(스칼라) 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="0e817-109">사용되는 `data_type`은 쿼리 공간에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="0e817-110">쿼리가 <xref:System.Data.EntityClient.EntityCommand>로 실행되는 경우 데이터 형식은 개념적 모델에 정의된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="0e817-111">자세한 내용은 [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0e817-111">For more information, see [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span> <span data-ttu-id="0e817-112">쿼리가 <xref:System.Data.Objects.ObjectQuery%601>로 실행되는 경우 데이터 형식은 CLR(공용 언어 런타임) 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e817-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="0e817-113">Return Value</span></span>  
 <span data-ttu-id="0e817-114">`data_type`과 동일한 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e817-115">설명</span><span class="sxs-lookup"><span data-stu-id="0e817-115">Remarks</span></span>  
 <span data-ttu-id="0e817-116">CAST 식과 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT 식의 의미 체계는 서로 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-116">The cast expression has similar semantics to the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT expression.</span></span> <span data-ttu-id="0e817-117">CAST 식은 한 형식의 값을 다른 형식의 값으로 변환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```  
CAST( e as T )  
```  
  
 <span data-ttu-id="0e817-118">e가 S 형식에 속하고 S가 T로 변환 가능한 경우, 위의 식은 유효한 CAST 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="0e817-119">T는 기본(스칼라) 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="0e817-120">전체 자릿수 및 소수 자릿수 패싯 값은 `Edm.Decimal`로 캐스팅할 때 선택 사항으로 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="0e817-121">전체 자릿수 및 소수 자릿수가 명시적으로 제공되지 않은 경우 기본값은 각각 18과 0입니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="0e817-122">구체적으로 말하면 `Decimal`에 대해 다음 오버로드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="0e817-123">CAST 식 사용은 명시적인 변환으로 간주되며,</span><span class="sxs-lookup"><span data-stu-id="0e817-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="0e817-124">명시적인 변환이 발생하면 데이터가 잘리거나 전체 자릿수가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e817-125">CAST는 기본 형식 및 열거형 멤버 형식에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e817-126">예</span><span class="sxs-lookup"><span data-stu-id="0e817-126">Example</span></span>  
 <span data-ttu-id="0e817-127">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 CAST 연산자를 사용하여 한 데이터 형식의 식을 다른 데이터 형식의 식으로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="0e817-128">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0e817-129">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="0e817-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0e817-130">절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="0e817-131">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0e817-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="0e817-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e817-132">See Also</span></span>  
 [<span data-ttu-id="0e817-133">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="0e817-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
