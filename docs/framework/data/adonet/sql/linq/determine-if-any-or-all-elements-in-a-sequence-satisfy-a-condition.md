---
title: "시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c6322e6920ff183a837a896d0853a02248cc7c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="5a2f7-102">시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 확인</span><span class="sxs-lookup"><span data-stu-id="5a2f7-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>
<span data-ttu-id="5a2f7-103">시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Enumerable.All%2A> 연산자에서는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="5a2f7-104">시퀀스의 모든 요소가 조건을 만족하면 <xref:System.Linq.Queryable.Any%2A> 연산자에서는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a2f7-105">예</span><span class="sxs-lookup"><span data-stu-id="5a2f7-105">Example</span></span>  
 <span data-ttu-id="5a2f7-106">다음 예제에서는 적어도 하나의 주문이 있는 고객의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="5a2f7-107">`Where` / `where` 절 `true` 경우는 주어진 `Customer` 있는지 `Order`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="5a2f7-108">예</span><span class="sxs-lookup"><span data-stu-id="5a2f7-108">Example</span></span>  
 <span data-ttu-id="5a2f7-109">다음 Visual Basic 코드에서는 주문을 하지 않은 고객의 목록을 확인하고 해당 목록에 있는 모든 고객에 대한 연락처 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="5a2f7-110">예</span><span class="sxs-lookup"><span data-stu-id="5a2f7-110">Example</span></span>  
 <span data-ttu-id="5a2f7-111">다음 C# 예제에서는 "C"로 시작하는 `ShipCity`가 있는 주문의 고객 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="5a2f7-112">또한 반환에는 주문이 없는 고객도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="5a2f7-113">디자인에 따라 <xref:System.Linq.Queryable.All%2A> 연산자는 빈 시퀀스에 대해 `true`를 반환합니다. 주문이 없는 고객은 `Count` 연산자를 사용하여 콘솔 결과에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a2f7-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="5a2f7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a2f7-114">See Also</span></span>  
 [<span data-ttu-id="5a2f7-115">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="5a2f7-115">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
