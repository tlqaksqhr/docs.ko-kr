---
title: "그룹화 조인 수행"
description: "그룹화 조인을 수행하는 방법"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: 5e26473e19a5b6107d7aceea5e9829b48aa522b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="perform-grouped-joins"></a><span data-ttu-id="f8ed5-104">그룹화 조인 수행</span><span class="sxs-lookup"><span data-stu-id="f8ed5-104">Perform grouped joins</span></span>

<span data-ttu-id="f8ed5-105">그룹 조인은 계층적 데이터 구조를 생성하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-105">The group join is useful for producing hierarchical data structures.</span></span> <span data-ttu-id="f8ed5-106">첫 번째 컬렉션의 각 요소와 두 번째 컬렉션에서 상관 관계가 지정된 요소 집합을 쌍으로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-106">It pairs each element from the first collection with a set of correlated elements from the second collection.</span></span>  
  
 <span data-ttu-id="f8ed5-107">예를 들어 `Student`라는 클래스 또는 관계형 데이터베이스 테이블에 `Id` 및 `Name`이라는 두 개의 필드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-107">For example, a class or a relational database table named `Student` might contain two fields: `Id` and `Name`.</span></span> <span data-ttu-id="f8ed5-108">`Course`라는 두 번째 클래스 또는 관계형 데이터베이스 테이블에 `StudentId` 및 `CourseTitle`이라는 두 개의 필드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-108">A second class or relational database table named `Course` might contain two fields: `StudentId` and `CourseTitle`.</span></span> <span data-ttu-id="f8ed5-109">일치하는 `Student.Id` 및 `Course.StudentId`를 기반으로 하는 이러한 두 데이터 소스의 그룹 조인은 각 `Student`를 `Course` 개체 컬렉션(비어 있을 수 있음)과 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-109">A group join of these two data sources, based on matching `Student.Id` and `Course.StudentId`, would group each `Student` with a collection of `Course` objects (which might be empty).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8ed5-110">첫 번째 컬렉션의 각 요소는 상관 관계가 지정된 요소가 두 번째 컬렉션에 있는지 여부에 관계없이 그룹 조인의 결과 집합에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-110">Each element of the first collection appears in the result set of a group join regardless of whether correlated elements are found in the second collection.</span></span> <span data-ttu-id="f8ed5-111">상관 관계가 지정된 요소가 없는 경우 해당 요소에 대해 상관 관계가 지정된 요소의 시퀀스가 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-111">In the case where no correlated elements are found, the sequence of correlated elements for that element is empty.</span></span> <span data-ttu-id="f8ed5-112">따라서 결과 선택기에서 첫 번째 컬렉션의 모든 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-112">The result selector therefore has access to every element of the first collection.</span></span> <span data-ttu-id="f8ed5-113">이는 두 번째 컬렉션에 일치 항목이 없는 첫 번째 컬렉션의 요소에 액세스할 수 없는 비그룹 조인의 결과 선택기와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-113">This differs from the result selector in a non-group join, which cannot access elements from the first collection that have no match in the second collection.</span></span>  
  
 <span data-ttu-id="f8ed5-114">이 항목의 첫 번째 예제에서는 그룹 조인을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-114">The first example in this topic shows you how to perform a group join.</span></span> <span data-ttu-id="f8ed5-115">두 번째 예제에서는 그룹 조인을 사용하여 XML 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-115">The second example shows you how to use a group join to create XML elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8ed5-116">예제</span><span class="sxs-lookup"><span data-stu-id="f8ed5-116">Example</span></span>  
  
### <a name="group-join-example"></a><span data-ttu-id="f8ed5-117">그룹 조인 예제</span><span class="sxs-lookup"><span data-stu-id="f8ed5-117">Group join example</span></span>  
 <span data-ttu-id="f8ed5-118">다음 예제에서는 `Pet.Owner` 속성과 일치하는 `Person`에 따라 `Person` 및 `Pet` 형식 개체의 그룹 조인을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-118">The following example performs a group join of objects of type `Person` and `Pet` based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="f8ed5-119">각 일치 항목에 대한 요소 쌍을 생성하는 비그룹 조인과 달리 그룹 조인은 첫 번째 컬렉션의 각 요소에 대해 하나의 결과 개체(이 예제에서는 `Person` 개체)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-119">Unlike a non-group join, which would produce a pair of elements for each match, the group join produces only one resulting object for each element of the first collection, which in this example is a `Person` object.</span></span> <span data-ttu-id="f8ed5-120">두 번째 컬렉션의 해당 요소(이 예제에서는 `Pet` 개체)는 컬렉션으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-120">The corresponding elements from the second collection, which in this example are `Pet` objects, are grouped into a collection.</span></span> <span data-ttu-id="f8ed5-121">마지막으로, 결과 선택기 함수는 `Person.FirstName` 및 `Pet` 개체 컬렉션으로 구성된 각 일치 항목에 대해 무명 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-121">Finally, the result selector function creates an anonymous type for each match that consists of `Person.FirstName` and a collection of `Pet` objects.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="f8ed5-122">예제</span><span class="sxs-lookup"><span data-stu-id="f8ed5-122">Example</span></span>  
  
### <a name="group-join-to-create-xml-example"></a><span data-ttu-id="f8ed5-123">XML을 만들기 위한 그룹 조인 예제</span><span class="sxs-lookup"><span data-stu-id="f8ed5-123">Group join to create XML example</span></span>  
 <span data-ttu-id="f8ed5-124">그룹 조인은 LINQ to XML을 사용하여 XML을 만드는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-124">Group joins are ideal for creating XML by using LINQ to XML.</span></span> <span data-ttu-id="f8ed5-125">다음 예제는 무명 형식을 만드는 대신 결과 선택기 함수가 조인된 개체를 나타내는 XML 요소를 만든다는 점을 제외하고 앞의 예제와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f8ed5-125">The following example is similar to the previous example except that instead of creating anonymous types, the result selector function creates XML elements that represent the joined objects.</span></span>  
  
 [!code-csharp[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="f8ed5-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8ed5-126">See also</span></span>  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [<span data-ttu-id="f8ed5-127">내부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="f8ed5-127">Perform inner joins</span></span>](perform-inner-joins.md)  
 [<span data-ttu-id="f8ed5-128">왼쪽 우선 외부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="f8ed5-128">Perform left outer joins</span></span>](perform-left-outer-joins.md)  
 [<span data-ttu-id="f8ed5-129">무명 형식</span><span class="sxs-lookup"><span data-stu-id="f8ed5-129">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 
