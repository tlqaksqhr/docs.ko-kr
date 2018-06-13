---
title: '쿼리 식 구문 예제: ELEMENT 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: ac10bbcb76e7e4e1feebaffbc85551993626933e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762236"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="69326-102">쿼리 식 구문 예제: ELEMENT 연산자</span><span class="sxs-lookup"><span data-stu-id="69326-102">Query Expression Syntax Examples: Element Operators</span></span>
<span data-ttu-id="69326-103">이 항목의 예제에 사용 하는 방법을 보여 주기는 <xref:System.Linq.Enumerable.First%2A> 메서드 쿼리를는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) 쿼리 식 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="69326-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using the query expression syntax.</span></span> <span data-ttu-id="69326-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="69326-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="69326-105">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="69326-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="69326-106">First</span><span class="sxs-lookup"><span data-stu-id="69326-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="69326-107">예제</span><span class="sxs-lookup"><span data-stu-id="69326-107">Example</span></span>  
 <span data-ttu-id="69326-108">다음 예제에서는 <xref:System.Linq.Enumerable.First%2A> 메서드를 사용하여 이름이 "Brooke"인 첫 번째 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69326-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="69326-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69326-109">See Also</span></span>  
 [<span data-ttu-id="69326-110">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="69326-110">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
