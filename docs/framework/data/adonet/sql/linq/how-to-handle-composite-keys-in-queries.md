---
title: '방법: 쿼리에서 복합 키 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 26c281445b84d3b3f85980de6ae4076411bb4fba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354241"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="22818-102">방법: 쿼리에서 복합 키 처리</span><span class="sxs-lookup"><span data-stu-id="22818-102">How to: Handle Composite Keys in Queries</span></span>
<span data-ttu-id="22818-103">일부 연산자는 인수를 하나만 받아들일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22818-103">Some operators can take only one argument.</span></span> <span data-ttu-id="22818-104">인수가 데이터베이스에서 둘 이상의 열을 포함하는 경우 조합을 나타내는 익명 형식을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22818-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22818-105">예제</span><span class="sxs-lookup"><span data-stu-id="22818-105">Example</span></span>  
 <span data-ttu-id="22818-106">다음 예제에서는 `GroupBy` 인수를 하나만 사용하는 `key` 연산자를 호출하는 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22818-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="22818-107">예제</span><span class="sxs-lookup"><span data-stu-id="22818-107">Example</span></span>  
 <span data-ttu-id="22818-108">다음 예제와 같이 동일한 경우 조인과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22818-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="22818-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22818-109">See Also</span></span>  
 [<span data-ttu-id="22818-110">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="22818-110">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
