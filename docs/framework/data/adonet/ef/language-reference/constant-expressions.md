---
title: 상수 식
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 616f297c261c4309dc0db7a4efe2fcad8cc00966
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762519"
---
# <a name="constant-expressions"></a><span data-ttu-id="5cc6e-102">상수 식</span><span class="sxs-lookup"><span data-stu-id="5cc6e-102">Constant Expressions</span></span>
<span data-ttu-id="5cc6e-103">상수 식은 상수 값으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="5cc6e-104">상수 값은 클라이언트에서 변환하지 않고도 직접 상수 명령 트리 식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="5cc6e-105">여기에는 상수 값을 결과로 제공하는 식도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="5cc6e-106">따라서 상수를 사용하는 모든 식에 대해 데이터 소스 동작이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="5cc6e-107">이로 인해 CLR 동작과 다른 동작이 나올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="5cc6e-108">다음 예제에서는 서버에서 계산되는 상수 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]<span data-ttu-id="5cc6e-109">에서는 상수 형태의 사용자 클래스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-109"> does not support using a user class as a constant.</span></span> <span data-ttu-id="5cc6e-110">하지만 사용자 클래스에서 속성 참조는 상수로 간주되며 명령 트리 상수 식으로 변환되고 데이터 소스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cc6e-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc6e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cc6e-111">See Also</span></span>  
 [<span data-ttu-id="5cc6e-112">LINQ to Entities 쿼리의 식</span><span class="sxs-lookup"><span data-stu-id="5cc6e-112">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
