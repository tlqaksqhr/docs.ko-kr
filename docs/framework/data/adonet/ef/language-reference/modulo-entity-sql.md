---
title: "% (모듈로)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e204612904aa55b4a0ae9aa65f2bbfd644bbc396
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="7fab9-102">% (모듈로)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7fab9-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="7fab9-103">한 식을 다른 식으로 나눈 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fab9-104">구문</span><span class="sxs-lookup"><span data-stu-id="7fab9-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="7fab9-105">인수</span><span class="sxs-lookup"><span data-stu-id="7fab9-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="7fab9-106">나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-106">The numeric expression to divide.</span></span> <span data-ttu-id="7fab9-107">`dividend` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="7fab9-108">피제수를 나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="7fab9-109">`divisor` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="7fab9-110">결과 형식</span><span class="sxs-lookup"><span data-stu-id="7fab9-110">Result Types</span></span>  
 <span data-ttu-id="7fab9-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="7fab9-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fab9-112">예</span><span class="sxs-lookup"><span data-stu-id="7fab9-112">Example</span></span>  
 <span data-ttu-id="7fab9-113">다음 Entity SQL 쿼리에서는 % 산술 연산자를 사용하여 한 식을 다른 식으로 나눈 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="7fab9-114">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7fab9-115">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="7fab9-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="7fab9-116">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="7fab9-117">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7fab9-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="7fab9-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fab9-118">See Also</span></span>  
 [<span data-ttu-id="7fab9-119">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="7fab9-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
