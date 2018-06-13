---
title: 숫자 시퀀스에서 평균 값 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee3b8673-a2e7-4b2d-9b5c-4972ff9e665d
ms.openlocfilehash: 3e808b836183a23fa6bd80faeb0d3cfc5921f4cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358858"
---
# <a name="return-the-average-value-from-a-numeric-sequence"></a><span data-ttu-id="8b5eb-102">숫자 시퀀스에서 평균 값 반환</span><span class="sxs-lookup"><span data-stu-id="8b5eb-102">Return the Average Value From a Numeric Sequence</span></span>
<span data-ttu-id="8b5eb-103"><xref:System.Linq.Enumerable.Average%2A> 연산자는 숫자 값 시퀀스의 평균을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-103">The <xref:System.Linq.Enumerable.Average%2A> operator computes the average of a sequence of numeric values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b5eb-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 정수 값의 `Average`를 변환하면 두 자리가 아닌 정수로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-104">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Average` of integer values is computed as an integer, not as a double.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b5eb-105">예제</span><span class="sxs-lookup"><span data-stu-id="8b5eb-105">Example</span></span>  
 <span data-ttu-id="8b5eb-106">다음 예제에서는 `Freight` 테이블에서 `Orders` 값의 평균을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-106">The following example returns the average of `Freight` values in the `Orders` table.</span></span>  
  
 <span data-ttu-id="8b5eb-107">샘플 Northwind 데이터베이스의 결과는 `78.2442`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-107">Results from the sample Northwind database would be `78.2442`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#1)]
 [!code-vb[DLinqQueryExamples#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="8b5eb-108">예제</span><span class="sxs-lookup"><span data-stu-id="8b5eb-108">Example</span></span>  
 <span data-ttu-id="8b5eb-109">다음 예제에서는 `Products` 테이블에 있는 모든 `Products` 단가의 평균을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-109">The following example returns the average of the unit price of all `Products` in the `Products` table.</span></span>  
  
 <span data-ttu-id="8b5eb-110">샘플 Northwind 데이터베이스의 결과는 `28.8663`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-110">Results from the sample Northwind database would be `28.8663`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#2)]
 [!code-vb[DLinqQueryExamples#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="8b5eb-111">예제</span><span class="sxs-lookup"><span data-stu-id="8b5eb-111">Example</span></span>  
 <span data-ttu-id="8b5eb-112">다음 예제에서는 `Average` 연산자를 사용하여 제품의 단가가 제품 범주가 속한 단가의 평균보다 비싼 `Products`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-112">The following example uses the `Average` operator to find those `Products` whose unit price is higher than the average unit price of the category it belongs to.</span></span> <span data-ttu-id="8b5eb-113">그룹으로 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-113">The example then displays the results in groups.</span></span>  
  
 <span data-ttu-id="8b5eb-114">이 예제는 반환 형식이 익명이기에 C#에서는 `var` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-114">Note that this example requires the use of the `var` keyword in C#, because the return type is anonymous.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#3)]
 [!code-vb[DLinqQueryExamples#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#3)]  
  
 <span data-ttu-id="8b5eb-115">Northwind 샘플 데이터베이스에 대한 이 쿼리를 실행할 경우 결과는 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8b5eb-115">If you run this query against the Northwind sample database, the results should resemble of the following:</span></span>  
  
 `1`  
  
 `Côte de Blaye`  
  
 `Ipoh Coffee`  
  
 `2`  
  
 `Grandma's Boysenberry Spread`  
  
 `Northwoods Cranberry Sauce`  
  
 `Sirop d'érable`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `Gumbär Gummibärchen`  
  
 `Schoggi Schokolade`  
  
 `Tarte au sucre`  
  
 `4`  
  
 `Queso Manchego La Pastora`  
  
 `Mascarpone Fabioli`  
  
 `Raclette Courdavault`  
  
 `Camembert Pierrot`  
  
 `Gudbrandsdalsost`  
  
 `Mozzarella di Giovanni`  
  
 `5`  
  
 `Gustaf's Knäckebröd`  
  
 `Gnocchi di nonna Alice`  
  
 `Wimmers gute Semmelknödel`  
  
 `6`  
  
 `Mishi Kobe Niku`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Rössle Sauerkraut`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Ikura`  
  
 `Carnarvon Tigers`  
  
 `Nord-Ost Matjeshering`  
  
 `Gravad lax`  
  
## <a name="see-also"></a><span data-ttu-id="8b5eb-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b5eb-116">See Also</span></span>  
 [<span data-ttu-id="8b5eb-117">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="8b5eb-117">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)
