---
title: "사용자 정의 함수(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4e5cfc9685c1e088722b24b54b4a0368d52fda29
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="d1cdf-102">사용자 정의 함수(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d1cdf-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="d1cdf-103">Entity SQL에서는 쿼리에서 사용자 정의 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cdf-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="d1cdf-104">쿼리와 함께 이러한 함수를 인라인으로 정의할 수 있습니다 (참조 [하는 방법: 사용자 정의 함수를 호출](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) 개념적 모델의 일부로 (참조 [하는 방법: 사용자 지정 함수를 개념적 모델에 정의](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span><span class="sxs-lookup"><span data-stu-id="d1cdf-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span></span> <span data-ttu-id="d1cdf-105">Entity SQL 명령으로 개념적 모델 함수를 정의 [DefiningExpression](http://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) 의 요소는 [함수](http://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) 개념적 모델의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cdf-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](http://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) element of a [Function](http://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="d1cdf-106">Entity SQL을 통해 쿼리 명령 자체에서 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cdf-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="d1cdf-107">[함수](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) 연산자는 인라인 함수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cdf-107">The [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="d1cdf-108">함수 시그니처가 고유하면 단일 명령에서 여러 함수를 정의할 수 있으며, 이러한 함수는 이름이 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cdf-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="d1cdf-109">자세한 내용은 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1cdf-109">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1cdf-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1cdf-110">See Also</span></span>  
 [<span data-ttu-id="d1cdf-111">함수</span><span class="sxs-lookup"><span data-stu-id="d1cdf-111">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
