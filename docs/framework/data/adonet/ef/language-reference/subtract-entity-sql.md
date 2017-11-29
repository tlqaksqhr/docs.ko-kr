---
title: "- (빼기) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 07921151309486617312a76285eea7be54463d4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="c55ac-102">- (빼기)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c55ac-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="c55ac-103">두 숫자를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="c55ac-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c55ac-105">인수</span><span class="sxs-lookup"><span data-stu-id="c55ac-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="c55ac-106">숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c55ac-107">결과 형식</span><span class="sxs-lookup"><span data-stu-id="c55ac-107">Result Types</span></span>  
 <span data-ttu-id="c55ac-108">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="c55ac-109">암시적 형식 승격에 대 한 자세한 내용은 참조 [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c55ac-110">예제</span><span class="sxs-lookup"><span data-stu-id="c55ac-110">Example</span></span>  
 <span data-ttu-id="c55ac-111">다음 Entity SQL 쿼리에서는 - 산술 연산자를 사용하여 두 숫자를 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="c55ac-112">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c55ac-113">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c55ac-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c55ac-114">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="c55ac-115">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c55ac-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="c55ac-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c55ac-116">See Also</span></span>  
 [<span data-ttu-id="c55ac-117">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c55ac-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
