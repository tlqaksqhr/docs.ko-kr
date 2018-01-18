---
title: ISNULL(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 57e90f013227f08ce365262da633a79d7abb5a8d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="34ac3-102">ISNULL(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="34ac3-102">ISNULL (Entity SQL)</span></span>
<span data-ttu-id="34ac3-103">쿼리 식이 null인지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ac3-104">구문</span><span class="sxs-lookup"><span data-stu-id="34ac3-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="34ac3-105">인수</span><span class="sxs-lookup"><span data-stu-id="34ac3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="34ac3-106">모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-106">Any valid query expression.</span></span> <span data-ttu-id="34ac3-107">컬렉션이거나, 컬렉션 멤버를 포함하거나, 컬렉션 형식 속성을 가진 레코드 형식일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="34ac3-108">NOT</span><span class="sxs-lookup"><span data-stu-id="34ac3-108">NOT</span></span>  
 <span data-ttu-id="34ac3-109">IS NULL의 EDM 부울 결과를 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34ac3-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="34ac3-110">Return Value</span></span>  
 <span data-ttu-id="34ac3-111">`true`이 null을 반환하면 `expression`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34ac3-112">설명</span><span class="sxs-lookup"><span data-stu-id="34ac3-112">Remarks</span></span>  
 <span data-ttu-id="34ac3-113">외부 조인의 요소가 null인지 여부를 확인하려면 `IS NULL`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="34ac3-114">멤버에 실제 값이 있는지 여부를 확인하려면 `IS NULL`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="34ac3-115">다음 표에서는 일부 패턴에 대한 `IS NULL`의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="34ac3-116">공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="34ac3-117">패턴</span><span class="sxs-lookup"><span data-stu-id="34ac3-117">Pattern</span></span>|<span data-ttu-id="34ac3-118">동작</span><span class="sxs-lookup"><span data-stu-id="34ac3-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="34ac3-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="34ac3-119">null IS NULL</span></span>|<span data-ttu-id="34ac3-120">`true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-120">Returns `true`.</span></span>|  
|<span data-ttu-id="34ac3-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="34ac3-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="34ac3-122">`true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-122">Returns `true`.</span></span>|  
|<span data-ttu-id="34ac3-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="34ac3-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="34ac3-124">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-124">Throws an error.</span></span>|  
|<span data-ttu-id="34ac3-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="34ac3-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="34ac3-126">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-126">Throws an error.</span></span>|  
|<span data-ttu-id="34ac3-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="34ac3-127">EntityType IS NULL</span></span>|<span data-ttu-id="34ac3-128">`true` 또는 `false`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="34ac3-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="34ac3-129">ComplexType IS NULL</span></span>|<span data-ttu-id="34ac3-130">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-130">Throws an error.</span></span>|  
|<span data-ttu-id="34ac3-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="34ac3-131">RowType IS NULL</span></span>|<span data-ttu-id="34ac3-132">오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="34ac3-133">예</span><span class="sxs-lookup"><span data-stu-id="34ac3-133">Example</span></span>  
 <span data-ttu-id="34ac3-134">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 IS NOT NULL 연산자를 사용하여 쿼리 식이 null이 아닌지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="34ac3-135">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="34ac3-136">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="34ac3-136">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="34ac3-137">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="34ac3-138">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="34ac3-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="34ac3-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34ac3-139">See Also</span></span>  
 [<span data-ttu-id="34ac3-140">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="34ac3-140">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
