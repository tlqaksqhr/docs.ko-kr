---
title: 왼쪽 우선 외부 조인 수행
description: 왼쪽 우선 외부 조인을 수행하는 방법
ms.date: 12/1/2016
ms.assetid: f542cee6-3169-4dcf-a631-3a6a79ccd473
ms.openlocfilehash: aacab1ac6f4ab2c10b393cf0b2c578a13d9b9306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="perform-left-outer-joins"></a><span data-ttu-id="60c53-103">왼쪽 우선 외부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="60c53-103">Perform left outer joins</span></span>
<span data-ttu-id="60c53-104">왼쪽 우선 외부 조인은 두 번째 컬렉션에 상호 연결된 요소가 있는지 여부에 관계없이 첫 번째 컬렉션의 각 요소가 반환되는 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-104">A left outer join is a join in which each element of the first collection is returned, regardless of whether it has any correlated elements in the second collection.</span></span> <span data-ttu-id="60c53-105">LINQ를 통해 그룹 조인의 결과에서 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 메서드를 호출하여 왼쪽 우선 외부 조인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-105">You can use LINQ to perform a left outer join by calling the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60c53-106">예</span><span class="sxs-lookup"><span data-stu-id="60c53-106">Example</span></span>  
 <span data-ttu-id="60c53-107">다음 예제에서는 그룹 조인의 결과에서 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> 메서드를 사용하여 왼쪽 우선 외부 조인을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-107">The following example demonstrates how to use the <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> method on the results of a group join to perform a left outer join.</span></span>  
  
 <span data-ttu-id="60c53-108">두 컬렉션의 왼쪽 우선 외부 조인을 생성하는 첫 번째 단계는 그룹 조인을 사용하여 내부 조인을 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-108">The first step in producing a left outer join of two collections is to perform an inner join by using a group join.</span></span> <span data-ttu-id="60c53-109">이 프로세스에 대한 설명은 [내부 조인 수행](perform-inner-joins.md)을 참조하세요. 이 예제에서 `Person` 개체 목록은 `Pet.Owner`와 일치하는 `Person` 개체를 기준으로 `Pet` 개체 목록에 내부 조인됩니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-109">(See [Perform inner joins](perform-inner-joins.md) for an explanation of this process.) In this example, the list of `Person` objects is inner-joined to the list of `Pet` objects based on a `Person` object that matches `Pet.Owner`.</span></span>  
  
 <span data-ttu-id="60c53-110">두 번째 단계는 오른쪽 컬렉션에 일치하는 항목이 없는 경우에도 첫 번째(왼쪽) 컬렉션의 각 요소를 결과 집합에 포함하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-110">The second step is to include each element of the first (left) collection in the result set even if that element has no matches in the right collection.</span></span> <span data-ttu-id="60c53-111">이렇게 하려면 그룹 조인에서 일치하는 요소의 각 시퀀스에 대해 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-111">This is accomplished by calling <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> on each sequence of matching elements from the group join.</span></span> <span data-ttu-id="60c53-112">이 예제에서는 일치하는 `Pet` 개체의 각 시퀀스에서 <xref:System.Linq.Enumerable.DefaultIfEmpty%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-112">In this example, <xref:System.Linq.Enumerable.DefaultIfEmpty%2A> is called on each sequence of matching `Pet` objects.</span></span> <span data-ttu-id="60c53-113">메서드는 `Person` 개체에 대해 일치하는 `Pet` 개체의 시퀀스가 비어 있는 경우 단일 기본값을 포함하는 컬렉션을 반환하여 각 `Person` 개체가 결과 컬렉션에 반환되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-113">The method returns a collection that contains a single, default value if the sequence of matching `Pet` objects is empty for any `Person` object, thereby ensuring that each `Person` object is represented in the result collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60c53-114">참조 형식의 기본값은 `null`이므로 예제에서는 각 `Pet` 컬렉션의 각 요소에 액세스하기 전에 null 참조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60c53-114">The default value for a reference type is `null`; therefore, the example checks for a null reference before accessing each element of each `Pet` collection.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#7](../../../samples/snippets/csharp/concepts/linq/how-to-perform-left-outer-joins_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="60c53-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60c53-115">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="60c53-116">내부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="60c53-116">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="60c53-117">그룹화 조인 수행</span><span class="sxs-lookup"><span data-stu-id="60c53-117">Perform grouped joins</span></span>](perform-grouped-joins.md)  
 [<span data-ttu-id="60c53-118">무명 형식</span><span class="sxs-lookup"><span data-stu-id="60c53-118">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 
