---
title: '방법: 한 번에 여러 개체 검색'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: fbe1632abf56beca5abfa209bdf269c6757f9c7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359906"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="93c6f-102">방법: 한 번에 여러 개체 검색</span><span class="sxs-lookup"><span data-stu-id="93c6f-102">How to: Retrieve Many Objects At Once</span></span>
<span data-ttu-id="93c6f-103"><xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>를 사용하여 한 쿼리에서 여러 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93c6f-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93c6f-104">예제</span><span class="sxs-lookup"><span data-stu-id="93c6f-104">Example</span></span>  
 <span data-ttu-id="93c6f-105">다음 코드에서는 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 메서드를 사용하여 `Customer` 및 `Order` 개체를 모두 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="93c6f-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="93c6f-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93c6f-106">See Also</span></span>  
 [<span data-ttu-id="93c6f-107">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="93c6f-107">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
