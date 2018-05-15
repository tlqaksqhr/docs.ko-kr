---
title: DEREF(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: ee3877ca256eb3847b0284ac2a7362a4a60aad48
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="deref-entity-sql"></a><span data-ttu-id="c107c-102">DEREF(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c107c-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="c107c-103">참조 값을 역참조하고 이 역참조의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c107c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c107c-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="c107c-105">인수</span><span class="sxs-lookup"><span data-stu-id="c107c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c107c-106">컬렉션을 반환하는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c107c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c107c-107">Return Value</span></span>  
 <span data-ttu-id="c107c-108">참조되는 엔터티의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c107c-109">설명</span><span class="sxs-lookup"><span data-stu-id="c107c-109">Remarks</span></span>  
 <span data-ttu-id="c107c-110">DEREF 연산자는 참조 값을 역참조하고 이 역참조의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="c107c-111">예를 들어 경우 `r` 대 한 참조 유형 참조입니다\<T >, `Deref``(r)` 형식의 식 `T` 에서 참조 하는 엔터티를 제시 하는 `r`합니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-111">For example, if `r` is a reference of type ref\<T>, `Deref``(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="c107c-112">참조 값이 null이거나 현수 참조(참조 대상이 존재하지 않음)인 경우 DEREF 연산자의 결과는 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c107c-113">예제</span><span class="sxs-lookup"><span data-stu-id="c107c-113">Example</span></span>  
 <span data-ttu-id="c107c-114">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 DEREF 연산자를 사용하여 참조 값을 역참조하고 이 역참조의 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="c107c-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c107c-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c107c-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c107c-117">절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="c107c-118">다음 쿼리를 ExecutePrimitiveTypeQuery 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c107c-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="c107c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c107c-119">See Also</span></span>  
 [<span data-ttu-id="c107c-120">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c107c-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="c107c-121">REF</span><span class="sxs-lookup"><span data-stu-id="c107c-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [<span data-ttu-id="c107c-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="c107c-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [<span data-ttu-id="c107c-123">KEY</span><span class="sxs-lookup"><span data-stu-id="c107c-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [<span data-ttu-id="c107c-124">null 허용 구조적 형식</span><span class="sxs-lookup"><span data-stu-id="c107c-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
