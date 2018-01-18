---
title: EXISTS(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 225487f6a0d7ec29689c01dd6355e7ba1aa6883e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="exists-entity-sql"></a><span data-ttu-id="e5926-102">EXISTS(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e5926-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="e5926-103">컬렉션이 비어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5926-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5926-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="e5926-105">인수</span><span class="sxs-lookup"><span data-stu-id="e5926-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e5926-106">컬렉션을 반환하는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="e5926-107">NOT</span><span class="sxs-lookup"><span data-stu-id="e5926-107">NOT</span></span>  
 <span data-ttu-id="e5926-108">EXISTS의 결과를 부정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5926-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e5926-109">Return Value</span></span>  
 <span data-ttu-id="e5926-110">컬렉션이 비어 있지 않으면 `true`이고 비어 있으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5926-111">설명</span><span class="sxs-lookup"><span data-stu-id="e5926-111">Remarks</span></span>  
 <span data-ttu-id="e5926-112">EXISTS는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="e5926-113">모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="e5926-114">우선 순위에 대 한 정보는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자, 참조 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5926-115">예</span><span class="sxs-lookup"><span data-stu-id="e5926-115">Example</span></span>  
 <span data-ttu-id="e5926-116">다음 Entity SQL 쿼리에서는 EXISTS 연산자를 사용하여 컬렉션이 비어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="e5926-117">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e5926-118">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="e5926-118">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e5926-119">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e5926-120">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="e5926-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="e5926-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5926-121">See Also</span></span>  
 [<span data-ttu-id="e5926-122">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="e5926-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
