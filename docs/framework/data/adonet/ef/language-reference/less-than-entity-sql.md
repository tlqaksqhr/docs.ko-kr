---
title: "&lt;(보다 작음)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5bf1560c0bebafcfdbf79ca9a9906c9df23b7cae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="lt-less-than-entity-sql"></a><span data-ttu-id="2f4b8-102">&lt;(보다 작음)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2f4b8-102">&lt; (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="2f4b8-103">두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f4b8-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f4b8-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f4b8-105">인수</span><span class="sxs-lookup"><span data-stu-id="2f4b8-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="2f4b8-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-106">Any valid expression.</span></span> <span data-ttu-id="2f4b8-107">비교할 두 식 모두 데이터 형식이 암시적으로 변환 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="2f4b8-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="2f4b8-108">Result Types</span></span>  
 <span data-ttu-id="2f4b8-109">왼쪽 식의 값이 오른쪽 식의 값보다 작으면`true` 이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f4b8-110">예</span><span class="sxs-lookup"><span data-stu-id="2f4b8-110">Example</span></span>  
 <span data-ttu-id="2f4b8-111">다음 Entity SQL 쿼리는 < 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 작은지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="2f4b8-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2f4b8-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="2f4b8-114">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="2f4b8-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2f4b8-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="2f4b8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f4b8-116">See Also</span></span>  
 [<span data-ttu-id="2f4b8-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="2f4b8-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
