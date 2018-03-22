---
title: '* (곱하기) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 508ce246-4e86-47dd-a605-4af4bebb9891
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: c7e2bcf15ab8d0cf24fdc6cb7e9db025784bd435
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="-multiply-entity-sql"></a><span data-ttu-id="0b7f3-102">\* (곱하기) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0b7f3-102">\* (Multiply) (Entity SQL)</span></span>
<span data-ttu-id="0b7f3-103">두 식을 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-103">Multiplies two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b7f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="0b7f3-104">Syntax</span></span>  
  
```  
expression * expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b7f3-105">인수</span><span class="sxs-lookup"><span data-stu-id="0b7f3-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="0b7f3-106">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="0b7f3-107">결과 형식</span><span class="sxs-lookup"><span data-stu-id="0b7f3-107">Result Types</span></span>  
 <span data-ttu-id="0b7f3-108">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="0b7f3-109">암시적 형식 승격에 대 한 자세한 내용은 참조 [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b7f3-110">예</span><span class="sxs-lookup"><span data-stu-id="0b7f3-110">Example</span></span>  
 <span data-ttu-id="0b7f3-111">다음 Entity SQL 쿼리에서는 \* 산술 연산자를 사용하여 두 숫자를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-111">The following Entity SQL query uses the \* arithmetic operator to multiply two numbers.</span></span> <span data-ttu-id="0b7f3-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0b7f3-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0b7f3-114">[방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="0b7f3-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0b7f3-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTIPLY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiply)]  
  
## <a name="see-also"></a><span data-ttu-id="0b7f3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b7f3-116">See Also</span></span>  
 [<span data-ttu-id="0b7f3-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="0b7f3-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
