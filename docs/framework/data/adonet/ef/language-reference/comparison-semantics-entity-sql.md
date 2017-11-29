---
title: "비교 의미 체계(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f1fd1c21fc4f156bfe7a5abf9f76bd341e2d0f10
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="comparison-semantics-entity-sql"></a><span data-ttu-id="a142f-102">비교 의미 체계(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a142f-102">Comparison Semantics (Entity SQL)</span></span>
<span data-ttu-id="a142f-103">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 수행하면 형식 인스턴스 비교가 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-103">Performing any of the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operators involves comparison of type instances:</span></span>  
  
## <a name="explicit-comparison"></a><span data-ttu-id="a142f-104">명시적 비교</span><span class="sxs-lookup"><span data-stu-id="a142f-104">Explicit comparison</span></span>  
 <span data-ttu-id="a142f-105">같음 연산:</span><span class="sxs-lookup"><span data-stu-id="a142f-105">Equality operations:</span></span>  
  
-   =  
  
-   <span data-ttu-id="a142f-106">!=</span><span class="sxs-lookup"><span data-stu-id="a142f-106">!=</span></span>  
  
 <span data-ttu-id="a142f-107">정렬 연산:</span><span class="sxs-lookup"><span data-stu-id="a142f-107">Ordering operations:</span></span>  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 <span data-ttu-id="a142f-108">Null 허용 여부 연산:</span><span class="sxs-lookup"><span data-stu-id="a142f-108">Nullability operations:</span></span>  
  
-   <span data-ttu-id="a142f-109">IS NULL</span><span class="sxs-lookup"><span data-stu-id="a142f-109">IS NULL</span></span>  
  
-   <span data-ttu-id="a142f-110">IS NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a142f-110">IS NOT NULL</span></span>  
  
## <a name="explicit-distinction"></a><span data-ttu-id="a142f-111">명시적 구분</span><span class="sxs-lookup"><span data-stu-id="a142f-111">Explicit distinction</span></span>  
 <span data-ttu-id="a142f-112">같음 구분:</span><span class="sxs-lookup"><span data-stu-id="a142f-112">Equality distinction:</span></span>  
  
-   <span data-ttu-id="a142f-113">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="a142f-113">DISTINCT</span></span>  
  
-   <span data-ttu-id="a142f-114">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="a142f-114">GROUP BY</span></span>  
  
 <span data-ttu-id="a142f-115">정렬 구분:</span><span class="sxs-lookup"><span data-stu-id="a142f-115">Ordering distinction:</span></span>  
  
-   <span data-ttu-id="a142f-116">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="a142f-116">ORDER BY</span></span>  
  
## <a name="implicit-distinction"></a><span data-ttu-id="a142f-117">암시적 구분</span><span class="sxs-lookup"><span data-stu-id="a142f-117">Implicit distinction</span></span>  
 <span data-ttu-id="a142f-118">Set 작업 및 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="a142f-118">Set operations and predicates (equality):</span></span>  
  
-   <span data-ttu-id="a142f-119">UNION</span><span class="sxs-lookup"><span data-stu-id="a142f-119">UNION</span></span>  
  
-   <span data-ttu-id="a142f-120">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="a142f-120">INTERSECT</span></span>  
  
-   <span data-ttu-id="a142f-121">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="a142f-121">EXCEPT</span></span>  
  
-   <span data-ttu-id="a142f-122">SET</span><span class="sxs-lookup"><span data-stu-id="a142f-122">SET</span></span>  
  
-   <span data-ttu-id="a142f-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="a142f-123">OVERLAPS</span></span>  
  
 <span data-ttu-id="a142f-124">항목 조건자(같음):</span><span class="sxs-lookup"><span data-stu-id="a142f-124">Item predicates (equality):</span></span>  
  
-   <span data-ttu-id="a142f-125">IN</span><span class="sxs-lookup"><span data-stu-id="a142f-125">IN</span></span>  
  
## <a name="supported-combinations"></a><span data-ttu-id="a142f-126">지원되는 조합</span><span class="sxs-lookup"><span data-stu-id="a142f-126">Supported Combinations</span></span>  
 <span data-ttu-id="a142f-127">다음 표에서는 각 종류의 형식에 대해 지원되는 비교 연산자의 조합을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-127">The following table shows all the supported combinations of comparison operators for each kind of type:</span></span>  
  
|<span data-ttu-id="a142f-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="a142f-128">**Type**</span></span>|**=**<br /><br /> <span data-ttu-id="a142f-129">**!=**</span><span class="sxs-lookup"><span data-stu-id="a142f-129">**!=**</span></span>|<span data-ttu-id="a142f-130">**기준으로 그룹화**</span><span class="sxs-lookup"><span data-stu-id="a142f-130">**GROUP BY**</span></span><br /><br /> <span data-ttu-id="a142f-131">**DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="a142f-131">**DISTINCT**</span></span>|<span data-ttu-id="a142f-132">**UNION**</span><span class="sxs-lookup"><span data-stu-id="a142f-132">**UNION**</span></span><br /><br /> <span data-ttu-id="a142f-133">**교차**</span><span class="sxs-lookup"><span data-stu-id="a142f-133">**INTERSECT**</span></span><br /><br /> <span data-ttu-id="a142f-134">**제외 하**</span><span class="sxs-lookup"><span data-stu-id="a142f-134">**EXCEPT**</span></span><br /><br /> <span data-ttu-id="a142f-135">**설정**</span><span class="sxs-lookup"><span data-stu-id="a142f-135">**SET**</span></span><br /><br /> <span data-ttu-id="a142f-136">**겹치는 항목이 있습니다**</span><span class="sxs-lookup"><span data-stu-id="a142f-136">**OVERLAPS**</span></span>|<span data-ttu-id="a142f-137">**IN**</span><span class="sxs-lookup"><span data-stu-id="a142f-137">**IN**</span></span>|<span data-ttu-id="a142f-138">**<   <=**</span><span class="sxs-lookup"><span data-stu-id="a142f-138">**<   <=**</span></span><br /><br /> <span data-ttu-id="a142f-139">**>   >=**</span><span class="sxs-lookup"><span data-stu-id="a142f-139">**>   >=**</span></span>|<span data-ttu-id="a142f-140">**ORDER BY**</span><span class="sxs-lookup"><span data-stu-id="a142f-140">**ORDER BY**</span></span>|<span data-ttu-id="a142f-141">**NULL**</span><span class="sxs-lookup"><span data-stu-id="a142f-141">**IS NULL**</span></span><br /><br /> <span data-ttu-id="a142f-142">**NULL이 아닌**</span><span class="sxs-lookup"><span data-stu-id="a142f-142">**IS NOT NULL**</span></span>|  
|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="a142f-143">엔터티 형식</span><span class="sxs-lookup"><span data-stu-id="a142f-143">Entity type</span></span>|<span data-ttu-id="a142f-144">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-144">Ref<sup>1</sup></span></span>|<span data-ttu-id="a142f-145">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-145">All properties<sup>2</sup></span></span>|<span data-ttu-id="a142f-146">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-146">All properties<sup>2</sup></span></span>|<span data-ttu-id="a142f-147">모든 속성<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-147">All properties<sup>2</sup></span></span>|<span data-ttu-id="a142f-148">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-148">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-149">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-149">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-150">Ref<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-150">Ref<sup>1</sup></span></span>|  
|<span data-ttu-id="a142f-151">복합 형식</span><span class="sxs-lookup"><span data-stu-id="a142f-151">Complex type</span></span>|<span data-ttu-id="a142f-152">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-152">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-153">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-153">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-154">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-154">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-155">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-155">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-156">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-156">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-157">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-157">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-158">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-158">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="a142f-159">행</span><span class="sxs-lookup"><span data-stu-id="a142f-159">Row</span></span>|<span data-ttu-id="a142f-160">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-160">All properties<sup>4</sup></span></span>|<span data-ttu-id="a142f-161">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-161">All properties<sup>4</sup></span></span>|<span data-ttu-id="a142f-162">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-162">All properties<sup>4</sup></span></span>|<span data-ttu-id="a142f-163">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-163">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-164">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-164">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-165">모든 속성<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-165">All properties<sup>4</sup></span></span>|<span data-ttu-id="a142f-166">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-166">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="a142f-167">기본 형식</span><span class="sxs-lookup"><span data-stu-id="a142f-167">Primitive type</span></span>|<span data-ttu-id="a142f-168">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="a142f-168">Provider-specific</span></span>|<span data-ttu-id="a142f-169">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="a142f-169">Provider-specific</span></span>|<span data-ttu-id="a142f-170">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="a142f-170">Provider-specific</span></span>|<span data-ttu-id="a142f-171">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="a142f-171">Provider-specific</span></span>|<span data-ttu-id="a142f-172">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="a142f-172">Provider-specific</span></span>|<span data-ttu-id="a142f-173">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="a142f-173">Provider-specific</span></span>|<span data-ttu-id="a142f-174">@FSHO2@공급자 고유</span><span class="sxs-lookup"><span data-stu-id="a142f-174">Provider-specific</span></span>|  
|<span data-ttu-id="a142f-175">Multiset</span><span class="sxs-lookup"><span data-stu-id="a142f-175">Multiset</span></span>|<span data-ttu-id="a142f-176">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-176">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-177">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-177">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-178">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-178">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-179">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-179">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-180">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-180">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-181">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-181">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-182">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-182">Throw<sup>3</sup></span></span>|  
|<span data-ttu-id="a142f-183">Ref</span><span class="sxs-lookup"><span data-stu-id="a142f-183">Ref</span></span>|<span data-ttu-id="a142f-184">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-184">Yes<sup>5</sup></span></span>|<span data-ttu-id="a142f-185">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-185">Yes<sup>5</sup></span></span>|<span data-ttu-id="a142f-186">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-186">Yes<sup>5</sup></span></span>|<span data-ttu-id="a142f-187">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-187">Yes<sup>5</sup></span></span>|<span data-ttu-id="a142f-188">Throw</span><span class="sxs-lookup"><span data-stu-id="a142f-188">Throw</span></span>|<span data-ttu-id="a142f-189">Throw</span><span class="sxs-lookup"><span data-stu-id="a142f-189">Throw</span></span>|<span data-ttu-id="a142f-190">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-190">Yes<sup>5</sup></span></span>|  
|<span data-ttu-id="a142f-191">형식 연결</span><span class="sxs-lookup"><span data-stu-id="a142f-191">Association</span></span><br /><br /> <span data-ttu-id="a142f-192">type</span><span class="sxs-lookup"><span data-stu-id="a142f-192">type</span></span>|<span data-ttu-id="a142f-193">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-193">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-194">Throw</span><span class="sxs-lookup"><span data-stu-id="a142f-194">Throw</span></span>|<span data-ttu-id="a142f-195">Throw</span><span class="sxs-lookup"><span data-stu-id="a142f-195">Throw</span></span>|<span data-ttu-id="a142f-196">Throw</span><span class="sxs-lookup"><span data-stu-id="a142f-196">Throw</span></span>|<span data-ttu-id="a142f-197">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-197">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-198">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-198">Throw<sup>3</sup></span></span>|<span data-ttu-id="a142f-199">Throw<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-199">Throw<sup>3</sup></span></span>|  
  
 <span data-ttu-id="a142f-200"><sup>1</sup>다음 예제와 같이 특정된 엔터티 형식 인스턴스의 참조가 암시적으로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-200"><sup>1</sup>The references of the given entity type instances are implicitly compared, as shown in the following example:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 <span data-ttu-id="a142f-201">엔터티 인스턴스는 명시적 참조와 비교할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-201">An entity instance cannot be compared to an explicit reference.</span></span> <span data-ttu-id="a142f-202">비교를 시도하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-202">If this is attempted, an exception is thrown.</span></span> <span data-ttu-id="a142f-203">예를 들어, 다음 쿼리는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-203">For example, the following query will throw an exception:</span></span>  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <span data-ttu-id="a142f-204"><sup>2</sup>복합 형식의 속성 (으로 비교할 수는 해당 속성이 모두) 비교할 수 있는 상태가 저장소에 전송 되기 전에 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-204"><sup>2</sup>Properties of complex types are flattened out before being sent to the store, so they become comparable (as long as all their properties are comparable).</span></span> <span data-ttu-id="a142f-205">또한 참조 <sup>4입니다.</sup></span><span class="sxs-lookup"><span data-stu-id="a142f-205">Also see <sup>4.</sup></span></span>  
  
 <span data-ttu-id="a142f-206"><sup>3</sup>Entity Framework 런타임에서 지원 되지 않는 경우를 감지 하 고 여 공급자/저장소의 개입 없이도 의미 있는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-206"><sup>3</sup>The Entity Framework runtime detects the unsupported case and throws a meaningful exception without engaging the provider/store.</span></span>  
  
 <span data-ttu-id="a142f-207"><sup>4</sup>모든 속성을 비교 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-207"><sup>4</sup>An attempt is made to compare all properties.</span></span> <span data-ttu-id="a142f-208">텍스트, ntext, 이미지와 같이 비교할 수 없는 형식의 속성이 있는 경우 서버 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a142f-208">If there is a property that is of a non-comparable type, such as text, ntext, or image, a server exception might be thrown.</span></span>  
  
 <span data-ttu-id="a142f-209"><sup>5</sup>참조의 모든 개별 요소가 비교 (엔터티 집합 이름 및 엔터티 형식의 모든 키 속성 포함).</span><span class="sxs-lookup"><span data-stu-id="a142f-209"><sup>5</sup>All individual elements of the references are compared (this includes the entity set name and all the key properties of the entity type).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a142f-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a142f-210">See Also</span></span>  
 [<span data-ttu-id="a142f-211">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="a142f-211">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
