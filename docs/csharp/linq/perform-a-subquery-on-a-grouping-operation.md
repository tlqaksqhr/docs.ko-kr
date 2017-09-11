---
title: "그룹화 작업에서 하위 쿼리 수행"
description: "그룹화 작업에서 하위 쿼리를 수행하는 방법"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 68acc07e0c33d042123d3cd403a73d58a7c3d245
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="60d6f-104">그룹화 작업에서 하위 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="60d6f-104">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="60d6f-105">이 항목에서는 소스 데이터를 그룹으로 정렬한 다음 각 그룹에 대해 개별적으로 하위 쿼리를 수행하는 쿼리를 만드는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60d6f-105">This topic shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="60d6f-106">각 예제의 기본적인 방법은 `newGroup`이라는 *연속*을 사용하고 `newGroup`에 대한 새 하위 쿼리를 생성하여 소스 요소를 그룹화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60d6f-106">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="60d6f-107">이 하위 쿼리는 외부 쿼리에 의해 생성되는 각 새로운 그룹에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d6f-107">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="60d6f-108">이 특정 예제에서 최종 출력은 그룹이 아니라 무명 형식의 플랫 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="60d6f-108">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
 <span data-ttu-id="60d6f-109">그룹화하는 방법에 대한 자세한 내용은 [group 절](../language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60d6f-109">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
 <span data-ttu-id="60d6f-110">연속에 대한 자세한 내용은 [into](../language-reference/keywords/into.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60d6f-110">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="60d6f-111">다음 예제에서는 메모리 내 데이터 구조를 데이터 소스로 사용하지만 모든 종류의 LINQ 데이터 소스에 대해 동일한 원칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d6f-111">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60d6f-112">예제</span><span class="sxs-lookup"><span data-stu-id="60d6f-112">Example</span></span> 

 > [!NOTE]
 > <span data-ttu-id="60d6f-113">이 예제에는 [개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 샘플 코드에 정의된 개체에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="60d6f-113">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

 <span data-ttu-id="60d6f-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="60d6f-114">[!code-cs[csProgGuideLINQ#23](../../../samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]</span></span>  
   
## <a name="see-also"></a><span data-ttu-id="60d6f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60d6f-115">See also</span></span>  
 [<span data-ttu-id="60d6f-116">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="60d6f-116">LINQ Query Expressions</span></span>](index.md)

