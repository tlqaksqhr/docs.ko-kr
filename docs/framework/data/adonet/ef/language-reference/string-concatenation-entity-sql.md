---
title: "+ (문자열 연결) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 60661a592e23e230c32b1fd7093f5dfd8e6ed87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-string-concatenation-entity-sql"></a><span data-ttu-id="22ec0-102">+ (문자열 연결)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="22ec0-102">+ (String Concatenation) (Entity SQL)</span></span>
<span data-ttu-id="22ec0-103">두 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-103">Concatenates two strings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ec0-104">구문</span><span class="sxs-lookup"><span data-stu-id="22ec0-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="22ec0-105">인수</span><span class="sxs-lookup"><span data-stu-id="22ec0-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="22ec0-106">EDM.String 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-106">Any valid expression of the EDM.String data types.</span></span> <span data-ttu-id="22ec0-107">두 식의 데이터 형식이 같거나 한 식이 다른 식의 데이터 형식으로 암시적으로 변환될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-107">Both expressions must be of the same data type, or one expression must be able to be implicitly converted to the data type of the other expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="22ec0-108">결과 형식</span><span class="sxs-lookup"><span data-stu-id="22ec0-108">Result Types</span></span>  
 <span data-ttu-id="22ec0-109">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="22ec0-110">암시적 형식 승격에 대 한 자세한 내용은 참조 [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-110">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22ec0-111">예제</span><span class="sxs-lookup"><span data-stu-id="22ec0-111">Example</span></span>  
 <span data-ttu-id="22ec0-112">다음 Entity SQL 쿼리에서는 + 연산자를 사용하여 두 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-112">The following Entity SQL query uses the + operator to concatenates two strings.</span></span> <span data-ttu-id="22ec0-113">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="22ec0-114">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="22ec0-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="22ec0-115">절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-115">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="22ec0-116">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="22ec0-116">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## <a name="see-also"></a><span data-ttu-id="22ec0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22ec0-117">See Also</span></span>  
 [<span data-ttu-id="22ec0-118">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="22ec0-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="22ec0-119">개념적 모델 형식 (CSDL)</span><span class="sxs-lookup"><span data-stu-id="22ec0-119">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)
