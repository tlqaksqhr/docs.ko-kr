---
title: 그룹화 작업에서 하위 쿼리 수행
description: 그룹화 작업에서 하위 쿼리를 수행하는 방법
ms.date: 12/1/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: 209d05c2fe8719fa9116061d199272366146f465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277331"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="47f09-103">그룹화 작업에서 하위 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="47f09-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="47f09-104">이 항목에서는 소스 데이터를 그룹으로 정렬한 다음 각 그룹에 대해 개별적으로 하위 쿼리를 수행하는 쿼리를 만드는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47f09-104">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="47f09-105">각 예제의 기본적인 방법은 `newGroup`이라는 *연속*을 사용하고 `newGroup`에 대한 새 하위 쿼리를 생성하여 소스 요소를 그룹화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47f09-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="47f09-106">이 하위 쿼리는 외부 쿼리에 의해 생성되는 각 새로운 그룹에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f09-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="47f09-107">이 특정 예제에서 최종 출력은 그룹이 아니라 무명 형식의 플랫 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="47f09-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="47f09-108">그룹화하는 방법에 대한 자세한 내용은 [group 절](../language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47f09-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="47f09-109">연속에 대한 자세한 내용은 [into](../language-reference/keywords/into.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47f09-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="47f09-110">다음 예제에서는 메모리 내 데이터 구조를 데이터 소스로 사용하지만 모든 종류의 LINQ 데이터 소스에 대해 동일한 원칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f09-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47f09-111">예</span><span class="sxs-lookup"><span data-stu-id="47f09-111">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="47f09-112">이 예제에는 [개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 샘플 코드에 정의된 개체에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f09-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 [!code-csharp[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]  
   
## <a name="see-also"></a><span data-ttu-id="47f09-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47f09-113">See also</span></span>  
 [<span data-ttu-id="47f09-114">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="47f09-114">LINQ Query Expressions</span></span>](index.md)
