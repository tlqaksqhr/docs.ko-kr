---
title: "비교 의미 체계(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: e20d47e0ae97067d2dcafcf929f717598d4e3e80
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="f6c89-102">비교 의미 체계(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f6c89-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="f6c89-103">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 수행하면 형식 인스턴스 비교가 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="f6c89-104">명시적 비교</span><span class="sxs-lookup"><span data-stu-id="f6c89-104">Explicit comparison</span></span>  
 <span data-ttu-id="f6c89-105">같음 연산:</span><span class="sxs-lookup"><span data-stu-id="f6c89-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="f6c89-106">!=</span><span class="sxs-lookup"><span data-stu-id="f6c89-106">!=</span></span>  
  
 <span data-ttu-id="f6c89-107">정렬 연산:</span><span class="sxs-lookup"><span data-stu-id="f6c89-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   \>  
  
-   \>=  
  
 <span data-ttu-id="f6c89-108">Null 허용 여부 연산:</span><span class="sxs-lookup"><span data-stu-id="f6c89-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="f6c89-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="f6c89-109">IS NULL</span></span>  
  
-   <span data-ttu-id="f6c89-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f6c89-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="f6c89-111">명시적 구분</span><span class="sxs-lookup"><span data-stu-id="f6c89-111">Explicit distinction</span></span>  
 <span data-ttu-id="f6c89-112">같음 구분:</span><span class="sxs-lookup"><span data-stu-id="f6c89-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="f6c89-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="f6c89-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="f6c89-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="f6c89-114">GROUP BY</span></span>  
  
 <span data-ttu-id="f6c89-115">정렬 구분:</span><span class="sxs-lookup"><span data-stu-id="f6c89-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="f6c89-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="f6c89-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="f6c89-117">암시적 구분</span><span class="sxs-lookup"><span data-stu-id="f6c89-117">Implicit distinction</span></span>  
 <span data-ttu-id="f6c89-118">Set 작업 및 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="f6c89-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="f6c89-119">UNION</span><span class="sxs-lookup"><span data-stu-id="f6c89-119">UNION</span></span>  
  
-   <span data-ttu-id="f6c89-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="f6c89-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="f6c89-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="f6c89-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="f6c89-122">SET</span><span class="sxs-lookup"><span data-stu-id="f6c89-122">SET</span></span>  
  
-   <span data-ttu-id="f6c89-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="f6c89-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="f6c89-124">항목 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="f6c89-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="f6c89-125">IN</span><span class="sxs-lookup"><span data-stu-id="f6c89-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="f6c89-126">지원되는 조합</span><span class="sxs-lookup"><span data-stu-id="f6c89-126">Supported Combinations</span></span>  
 <span data-ttu-id="f6c89-127">다음 표에서는 각 종류의 형식에 대해 지원되는 비교 연산자의 조합을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="f6c89-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="f6c89-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="f6c89-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="f6c89-129">**!=**</span></span>|<span data-ttu-id="f6c89-130">**GROUP BY**</span><span class="sxs-lookup"><span data-stu-id="f6c89-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="f6c89-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="f6c89-131">**DISTINCT**</span></span>|<span data-ttu-id="f6c89-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="f6c89-132">**UNION**</span></span><br /><br /> <span data-ttu-id="f6c89-133">**INTERSECT**</span><span class="sxs-lookup"><span data-stu-id="f6c89-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="f6c89-134">**EXCEPT**</span><span class="sxs-lookup"><span data-stu-id="f6c89-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="f6c89-135">**SET**</span><span class="sxs-lookup"><span data-stu-id="f6c89-135">**SET**</span></span><br /><br /> <span data-ttu-id="f6c89-136">**OVERLAPS**</span><span class="sxs-lookup"><span data-stu-id="f6c89-136">**OVERLAPS**</span></span>|<span data-ttu-id="f6c89-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="f6c89-137">**IN**</span></span>|<span data-ttu-id="f6c89-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="f6c89-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="f6c89-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="f6c89-139">**>   >=**</span></span>|<span data-ttu-id="f6c89-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="f6c89-140">**ORDER BY**</span></span>|<span data-ttu-id="f6c89-141">**IS NULL**</span><span class="sxs-lookup"><span data-stu-id="f6c89-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="f6c89-142">**NULL이 아닌**</span><span class="sxs-lookup"><span data-stu-id="f6c89-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="f6c89-143">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="f6c89-143">Entity type</span></span>|<span data-ttu-id="f6c89-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="f6c89-145">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="f6c89-146">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="f6c89-147">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="f6c89-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="f6c89-151">복합 형식</span><span class="sxs-lookup"><span data-stu-id="f6c89-151">Complex type</span></span>|<span data-ttu-id="f6c89-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f6c89-159">행</span><span class="sxs-lookup"><span data-stu-id="f6c89-159">Row</span></span>|<span data-ttu-id="f6c89-160">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="f6c89-161">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="f6c89-162">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="f6c89-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-165">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="f6c89-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f6c89-167">기본 형식</span><span class="sxs-lookup"><span data-stu-id="f6c89-167">Primitive type</span></span>|<span data-ttu-id="f6c89-168">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="f6c89-168">Provider-specific</span></span>|<span data-ttu-id="f6c89-169">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="f6c89-169">Provider-specific</span></span>|<span data-ttu-id="f6c89-170">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="f6c89-170">Provider-specific</span></span>|<span data-ttu-id="f6c89-171">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="f6c89-171">Provider-specific</span></span>|<span data-ttu-id="f6c89-172">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="f6c89-172">Provider-specific</span></span>|<span data-ttu-id="f6c89-173">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="f6c89-173">Provider-specific</span></span>|<span data-ttu-id="f6c89-174">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="f6c89-174">Provider-specific</span></span>|  
|<span data-ttu-id="f6c89-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="f6c89-175">Multiset</span></span>|<span data-ttu-id="f6c89-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="f6c89-183">Ref</span><span class="sxs-lookup"><span data-stu-id="f6c89-183">Ref</span></span>|<span data-ttu-id="f6c89-184">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="f6c89-185">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="f6c89-186">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="f6c89-187">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="f6c89-188">Throw</span><span class="sxs-lookup"><span data-stu-id="f6c89-188">Throw</span></span>|<span data-ttu-id="f6c89-189">Throw</span><span class="sxs-lookup"><span data-stu-id="f6c89-189">Throw</span></span>|<span data-ttu-id="f6c89-190">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="f6c89-191">형식 연결</span><span class="sxs-lookup"><span data-stu-id="f6c89-191">Association</span></span><br /><br /> <span data-ttu-id="f6c89-192">type</span><span class="sxs-lookup"><span data-stu-id="f6c89-192">type</span></span>|<span data-ttu-id="f6c89-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-194">Throw</span><span class="sxs-lookup"><span data-stu-id="f6c89-194">Throw</span></span>|<span data-ttu-id="f6c89-195">Throw</span><span class="sxs-lookup"><span data-stu-id="f6c89-195">Throw</span></span>|<span data-ttu-id="f6c89-196">Throw</span><span class="sxs-lookup"><span data-stu-id="f6c89-196">Throw</span></span>|<span data-ttu-id="f6c89-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="f6c89-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="f6c89-200"><sup>1</sup>다음 예제와 같이 특정된 엔터티 형식 인스턴스의 참조가 암시적으로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="f6c89-201">엔터티 인스턴스는 명시적 참조와 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="f6c89-202">비교를 시도하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="f6c89-203">예를 들어, 다음 쿼리는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="f6c89-204"><sup>2</sup>복합 형식의 속성 (으로 비교할 수는 해당 속성이 모두) 비교할 수 있는 상태가 저장소에 전송 되기 전에 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="f6c89-205">또한 참조 <sup>4입니다.</sup></span><span class="sxs-lookup"><span data-stu-id="f6c89-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="f6c89-206"><sup>3</sup>Entity Framework 런타임에서 지원 되지 않는 경우를 감지 하 고 여 공급자/저장소의 개입 없이도 의미 있는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="f6c89-207"><sup>4</sup>모든 속성을 비교 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="f6c89-208">텍스트, ntext, 이미지와 같이 비교할 수 없는 형식의 속성이 있는 경우 서버 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c89-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="f6c89-209"><sup>5</sup>참조의 모든 개별 요소가 비교 (엔터티 집합 이름 및 엔터티 형식의 모든 키 속성 포함).</span><span class="sxs-lookup"><span data-stu-id="f6c89-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6c89-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6c89-210">See Also</span></span>  
 [<span data-ttu-id="f6c89-211">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="f6c89-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
