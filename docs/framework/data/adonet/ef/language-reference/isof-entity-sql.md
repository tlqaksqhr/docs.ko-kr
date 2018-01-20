---
title: ISOF(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 78bfcef336ad265b98069ed540f9156cf9cb65bd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="isof-entity-sql"></a><span data-ttu-id="a1c6a-102">ISOF(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-102">ISOF (Entity SQL)</span></span>
<span data-ttu-id="a1c6a-103">식의 형식이 지정된 형식 또는 그 하위 형식인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-103">Determines whether the type of an expression is of the specified type or one of its subtypes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1c6a-104">Syntax</span></span>  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="a1c6a-105">인수</span><span class="sxs-lookup"><span data-stu-id="a1c6a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a1c6a-106">형식을 결정할 수 있는 모든 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-106">Any valid query expression to determine the type of.</span></span>  
  
 <span data-ttu-id="a1c6a-107">NOT</span><span class="sxs-lookup"><span data-stu-id="a1c6a-107">NOT</span></span>  
 <span data-ttu-id="a1c6a-108">IS OF의 EDM.Boolean 결과를 부정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-108">Negates the EDM.Boolean result of IS OF.</span></span>  
  
 <span data-ttu-id="a1c6a-109">ONLY</span><span class="sxs-lookup"><span data-stu-id="a1c6a-109">ONLY</span></span>  
 <span data-ttu-id="a1c6a-110">`true`이 `expression` 형식이며 그 하위 형식이 아닌 경우에만 IS OF가 `type`를 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-110">Specifies that IS OF returns `true` only if `expression` is of type `type` and not any of one its subtypes.</span></span>  
  
 `type`  
 <span data-ttu-id="a1c6a-111">`expression`을 테스트할 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-111">The type to test `expression` against.</span></span> <span data-ttu-id="a1c6a-112">형식은 네임스페이스로 한정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-112">The type must be namespace-qualified.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1c6a-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="a1c6a-113">Return Value</span></span>  
 <span data-ttu-id="a1c6a-114">`true`이 T 형식이며 T가 기본 형식이거나 `expression`의 파생 형식인 경우 `type`이고, `expression`이 런타임에 null인 경우 null이며, 그 이외의 경우 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-114">`true` if `expression` is of type T and T is either a base type, or a derived type of `type`; null if `expression` is null at runtime; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1c6a-115">설명</span><span class="sxs-lookup"><span data-stu-id="a1c6a-115">Remarks</span></span>  
 <span data-ttu-id="a1c6a-116">식 `expression IS NOT OF (type)` 및 `expression IS NOT OF (ONLY type)` 구문상 동일 `NOT (expression IS OF (type))` 및 `NOT (expression IS OF (ONLY type))`각각.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-116">The expressions `expression IS NOT OF (type)` and `expression IS NOT OF (ONLY type)` are syntactically equivalent to `NOT (expression IS OF (type))` and `NOT (expression IS OF (ONLY type))`, respectively.</span></span>  
  
 <span data-ttu-id="a1c6a-117">다음 표에서는 일반 패턴 및 비교적 특수한 패턴에 대한 `IS OF` 연산자의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-117">The following table shows the behavior of `IS OF` operator over some typical- and corner patterns.</span></span> <span data-ttu-id="a1c6a-118">공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-118">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="a1c6a-119">패턴</span><span class="sxs-lookup"><span data-stu-id="a1c6a-119">Pattern</span></span>|<span data-ttu-id="a1c6a-120">동작</span><span class="sxs-lookup"><span data-stu-id="a1c6a-120">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="a1c6a-121">null IS OF(EntityType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-121">null IS OF (EntityType)</span></span>|<span data-ttu-id="a1c6a-122">@FSHO2@throw</span><span class="sxs-lookup"><span data-stu-id="a1c6a-122">Throws</span></span>|  
|<span data-ttu-id="a1c6a-123">null IS OF(ComplexType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-123">null IS OF (ComplexType)</span></span>|<span data-ttu-id="a1c6a-124">@FSHO2@throw</span><span class="sxs-lookup"><span data-stu-id="a1c6a-124">Throws</span></span>|  
|<span data-ttu-id="a1c6a-125">null IS OF(RowType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-125">null IS OF (RowType)</span></span>|<span data-ttu-id="a1c6a-126">@FSHO2@throw</span><span class="sxs-lookup"><span data-stu-id="a1c6a-126">Throws</span></span>|  
|<span data-ttu-id="a1c6a-127">TREAT(null AS EntityType) IS OF(EntityType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-127">TREAT (null AS EntityType) IS OF (EntityType)</span></span>|<span data-ttu-id="a1c6a-128">DBNull 반환</span><span class="sxs-lookup"><span data-stu-id="a1c6a-128">Returns DBNull</span></span>|  
|<span data-ttu-id="a1c6a-129">TREAT(null AS ComplexType) IS OF(ComplexType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-129">TREAT (null AS ComplexType) IS OF (ComplexType)</span></span>|<span data-ttu-id="a1c6a-130">@FSHO2@throw</span><span class="sxs-lookup"><span data-stu-id="a1c6a-130">Throws</span></span>|  
|<span data-ttu-id="a1c6a-131">TREAT(null AS RowType) IS OF(RowType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-131">TREAT (null AS RowType) IS OF (RowType)</span></span>|<span data-ttu-id="a1c6a-132">@FSHO2@throw</span><span class="sxs-lookup"><span data-stu-id="a1c6a-132">Throws</span></span>|  
|<span data-ttu-id="a1c6a-133">EntityType IS OF(EntityType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-133">EntityType IS OF (EntityType)</span></span>|<span data-ttu-id="a1c6a-134">true/false 반환</span><span class="sxs-lookup"><span data-stu-id="a1c6a-134">Returns true/false</span></span>|  
|<span data-ttu-id="a1c6a-135">ComplexType IS OF(ComplexType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-135">ComplexType IS OF (ComplexType)</span></span>|<span data-ttu-id="a1c6a-136">@FSHO2@throw</span><span class="sxs-lookup"><span data-stu-id="a1c6a-136">Throws</span></span>|  
|<span data-ttu-id="a1c6a-137">RowType IS OF(RowType)</span><span class="sxs-lookup"><span data-stu-id="a1c6a-137">RowType IS OF (RowType)</span></span>|<span data-ttu-id="a1c6a-138">@FSHO2@throw</span><span class="sxs-lookup"><span data-stu-id="a1c6a-138">Throws</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a1c6a-139">예</span><span class="sxs-lookup"><span data-stu-id="a1c6a-139">Example</span></span>  
 <span data-ttu-id="a1c6a-140">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 IS OF 연산자를 사용하여 쿼리 식의 형식을 결정한 다음 TREAT 연산자를 사용하여 Course 형식의 개체를 OnsiteCourse 형식의 개체 컬렉션으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-140">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS OF operator to determine the type of a query expression, and then uses the TREAT operator to convert an object of the type Course to a collection of objects of the type OnsiteCourse.</span></span> <span data-ttu-id="a1c6a-141">쿼리 기반는 [School 모델](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c6a-141">The query is based on the [School Model](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac).</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a><span data-ttu-id="a1c6a-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1c6a-142">See Also</span></span>  
 [<span data-ttu-id="a1c6a-143">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a1c6a-143">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
