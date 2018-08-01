---
title: 내부 조인 수행(C#의 LINQ)
description: C#에서 LINQ를 사용하여 내부 조인을 수행하는 방법을 알아봅니다.
ms.date: 12/1/2016
ms.assetid: 45bceed6-f549-4114-a9b1-b44feb497742
ms.openlocfilehash: 5dedab3fe83d4c16f8f0879f564cdd39e2b2446c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404202"
---
# <a name="perform-inner-joins"></a><span data-ttu-id="389b0-103">내부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="389b0-103">Perform inner joins</span></span>

<span data-ttu-id="389b0-104">관계형 데이터베이스 용어에서 *내부 조인*은 첫 번째 컬렉션의 각 요소가 두 번째 컬렉션에서 일치하는 모든 요소에 대해 한 번 표시되는 결과 집합을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-104">In relational database terms, an *inner join* produces a result set in which each element of the first collection appears one time for every matching element in the second collection.</span></span> <span data-ttu-id="389b0-105">첫 번째 컬렉션의 요소에 일치하는 요소가 없는 경우에는 결과 집합에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-105">If an element in the first collection has no matching elements, it does not appear in the result set.</span></span> <span data-ttu-id="389b0-106">C#에서 `join` 절에 의해 호출되는 <xref:System.Linq.Enumerable.Join%2A> 메서드는 내부 조인을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-106">The <xref:System.Linq.Enumerable.Join%2A> method, which is called by the `join` clause in C#, implements an inner join.</span></span>

<span data-ttu-id="389b0-107">이 문서에서는 내부 조인의 네 가지 변환을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-107">This article shows you how to perform four variations of an inner join:</span></span>

- <span data-ttu-id="389b0-108">단순 키에 따라 두 데이터 소스의 요소를 상호 연결하는 간단한 내부 조인</span><span class="sxs-lookup"><span data-stu-id="389b0-108">A simple inner join that correlates elements from two data sources based on a simple key.</span></span>

- <span data-ttu-id="389b0-109">*복합* 키에 따라 두 데이터 소스의 요소를 상호 연결하는 내부 조인.</span><span class="sxs-lookup"><span data-stu-id="389b0-109">An inner join that correlates elements from two data sources based on a *composite* key.</span></span> <span data-ttu-id="389b0-110">둘 이상의 값으로 구성된 키인 복합 키를 사용하면 둘 이상의 속성에 따라 요소를 상호 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-110">A composite key, which is a key that consists of more than one value, enables you to correlate elements based on more than one property.</span></span>

- <span data-ttu-id="389b0-111">연속 조인 작업이 서로 추가되는 *여러 조인*</span><span class="sxs-lookup"><span data-stu-id="389b0-111">A *multiple join* in which successive join operations are appended to each other.</span></span>

- <span data-ttu-id="389b0-112">그룹 조인을 사용하여 구현되는 내부 조인</span><span class="sxs-lookup"><span data-stu-id="389b0-112">An inner join that is implemented by using a group join.</span></span>

## <a name="example---simple-key-join"></a><span data-ttu-id="389b0-113">예제 - 단순 키 조인</span><span class="sxs-lookup"><span data-stu-id="389b0-113">Example - Simple key join</span></span>

<span data-ttu-id="389b0-114">다음 예제에서는 두 개의 사용자 정의 형식인 `Person` 및 `Pet`의 개체를 포함하는 두 개의 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-114">The following example creates two collections that contain objects of two user-defined types, `Person` and `Pet`.</span></span> <span data-ttu-id="389b0-115">쿼리는 C#의 `join` 절을 사용하여 `Person` 개체를 `Owner`가 해당 `Person`인 `Pet` 개체와 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-115">The query uses the `join` clause in C# to match `Person` objects with `Pet` objects whose `Owner` is that `Person`.</span></span> <span data-ttu-id="389b0-116">C#의 `select` 절은 결과 개체의 모양을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-116">The `select` clause in C# defines how the resulting objects will look.</span></span> <span data-ttu-id="389b0-117">이 예제에서 결과 개체는 소유자의 이름과 애완 동물의 이름으로 구성된 무명 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-117">In this example the resulting objects are anonymous types that consist of the owner's first name and the pet's name.</span></span>

[!code-csharp[CsLINQProgJoining#1](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_1.cs)]

<span data-ttu-id="389b0-118">`LastName`이 "Huff"인 `Person` 개체는 `Pet.Owner`가 `Person`과 같은 `Pet` 개체가 없기 때문에 결과 집합에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-118">Note that the `Person` object whose `LastName` is "Huff" does not appear in the result set because there is no `Pet` object that has `Pet.Owner` equal to that `Person`.</span></span>

## <a name="example---composite-key-join"></a><span data-ttu-id="389b0-119">예제 - 복합 키 조인</span><span class="sxs-lookup"><span data-stu-id="389b0-119">Example - Composite key join</span></span>

<span data-ttu-id="389b0-120">속성 하나만 기준으로 요소를 상호 연결하는 대신 복합 키를 사용하여 여러 속성을 기준으로 요소를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-120">Instead of correlating elements based on just one property, you can use a composite key to compare elements based on multiple properties.</span></span> <span data-ttu-id="389b0-121">이렇게 하려면 비교하려는 속성으로 구성된 무명 형식을 반환할 각 컬렉션에 대한 키 선택기 함수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-121">To do this, specify the key selector function for each collection to return an anonymous type that consists of the properties you want to compare.</span></span> <span data-ttu-id="389b0-122">속성에 레이블을 지정하는 경우 각 키의 무명 형식에 동일한 레이블이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-122">If you label the properties, they must have the same label in each key's anonymous type.</span></span> <span data-ttu-id="389b0-123">또한 속성은 동일한 순서로 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-123">The properties must also appear in the same order.</span></span>

<span data-ttu-id="389b0-124">다음 예제에서는 `Employee` 개체 목록과 `Student` 개체 목록을 사용하여 학생이기도 한 직원을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-124">The following example uses a list of `Employee` objects and a list of `Student` objects to determine which employees are also students.</span></span> <span data-ttu-id="389b0-125">이러한 형식에는 둘 다 <xref:System.String> 형식의 `FirstName` 및 `LastName` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-125">Both of these types have a `FirstName` and a `LastName` property of type <xref:System.String>.</span></span> <span data-ttu-id="389b0-126">각 목록의 요소에서 조인 키를 만드는 함수는 각 요소의 `FirstName` 및 `LastName` 속성으로 구성된 무명 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-126">The functions that create the join keys from each list's elements return an anonymous type that consists of the `FirstName` and `LastName` properties of each element.</span></span> <span data-ttu-id="389b0-127">조인 작업은 이러한 복합 키가 같은지 비교하고 각 목록에서 이름과 성이 둘 다 일치하는 개체 쌍을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-127">The join operation compares these composite keys for equality and returns pairs of objects from each list where both the first name and the last name match.</span></span>

[!code-csharp[CsLINQProgJoining#2](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_2.cs)]

## <a name="example---multiple-join"></a><span data-ttu-id="389b0-128">예제 - 여러 조인</span><span class="sxs-lookup"><span data-stu-id="389b0-128">Example - Multiple join</span></span>

<span data-ttu-id="389b0-129">개수에 제한없이 조인 작업을 서로 추가하여 여러 조인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-129">Any number of join operations can be appended to each other to perform a multiple join.</span></span> <span data-ttu-id="389b0-130">C#의 각 `join` 절은 지정된 데이터 소스를 이전 조인의 결과와 상호 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-130">Each `join` clause in C# correlates a specified data source with the results of the previous join.</span></span>

<span data-ttu-id="389b0-131">다음 예제에서는 `Person` 개체 목록, `Cat` 개체 목록, `Dog` 개체 목록의 세 가지 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-131">The following example creates three collections: a list of `Person` objects, a list of `Cat` objects, and a list of `Dog` objects.</span></span>

<span data-ttu-id="389b0-132">C#의 첫 번째 `join` 절은 `Cat.Owner`와 일치하는 `Person`을 기준으로 사람과 고양이를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-132">The first `join` clause in C# matches people and cats based on a `Person` object matching `Cat.Owner`.</span></span> <span data-ttu-id="389b0-133">`Person` 개체 및 `Cat.Name`을 포함하는 무명 형식의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-133">It returns a sequence of anonymous types that contain the `Person` object and `Cat.Name`.</span></span>

<span data-ttu-id="389b0-134">C#의 두 번째 `join` 절은 `Person` 형식의 `Owner` 속성과 동물 이름의 첫 글자로 구성된 복합 키를 기준으로 제공된 개 목록의 `Dog` 개체와 첫 번째 조인에서 반환된 무명 형식을 상호 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-134">The second `join` clause in C# correlates the anonymous types returned by the first join with `Dog` objects in the supplied list of dogs, based on a composite key that consists of the `Owner` property of type `Person`, and the first letter of the animal's name.</span></span> <span data-ttu-id="389b0-135">일치하는 각 쌍의 `Cat.Name` 및 `Dog.Name` 속성을 포함하는 무명 형식의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-135">It returns a sequence of anonymous types that contain the `Cat.Name` and `Dog.Name` properties from each matching pair.</span></span> <span data-ttu-id="389b0-136">내부 조인이기 때문에 두 번째 데이터 소스에 일치 항목이 있는 첫 번째 데이터 소스의 개체만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-136">Because this is an inner join, only those objects from the first data source that have a match in the second data source are returned.</span></span>

[!code-csharp[CsLINQProgJoining#3](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_3.cs)]

## <a name="example---inner-join-by-using-grouped-join"></a><span data-ttu-id="389b0-137">예제 - 그룹화된 조인을 사용하는 내부 조인</span><span class="sxs-lookup"><span data-stu-id="389b0-137">Example - Inner join by using grouped join</span></span>

<span data-ttu-id="389b0-138">다음 예제에서는 그룹 조인을 사용하여 내부 조인을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-138">The following example shows you how to implement an inner join by using a group join.</span></span>

<span data-ttu-id="389b0-139">`query1`에서 `Person` 개체 목록은 `Pet.Owner` 속성과 일치하는 `Person`을 기준으로 `Pet` 개체 목록에 그룹 조인됩니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-139">In `query1`, the list of `Person` objects is group-joined to the list of `Pet` objects based on the `Person` matching the `Pet.Owner` property.</span></span> <span data-ttu-id="389b0-140">그룹 조인은 각 그룹이 `Person` 개체 및 일치하는 `Pet` 개체 시퀀스로 구성된 중간 그룹 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-140">The group join creates a collection of intermediate groups, where each group consists of a `Person` object and a sequence of matching `Pet` objects.</span></span>

<span data-ttu-id="389b0-141">두 번째 `from` 절을 쿼리에 추가하여 이 시퀀스의 시퀀스를 더 긴 시퀀스에 결합(또는 평면화)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-141">By adding a second `from` clause to the query, this sequence of sequences is combined (or flattened) into one longer sequence.</span></span> <span data-ttu-id="389b0-142">최종 시퀀스의 요소 형식은 `select` 절에 의해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-142">The type of the elements of the final sequence is specified by the `select` clause.</span></span> <span data-ttu-id="389b0-143">이 예제에서 해당 형식은 일치하는 각 쌍의 `Person.FirstName` 및 `Pet.Name` 속성으로 구성된 무명 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-143">In this example, that type is an anonymous type that consists of the `Person.FirstName` and `Pet.Name` properties for each matching pair.</span></span>

<span data-ttu-id="389b0-144">`query1`의 결과는 `into` 절 없이 `join` 절을 사용해서 내부 조인을 수행하여 얻은 결과 집합과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-144">The result of `query1` is equivalent to the result set that would have been obtained by using the `join` clause without the `into` clause to perform an inner join.</span></span> <span data-ttu-id="389b0-145">`query2` 변수는 이와 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="389b0-145">The `query2` variable demonstrates this equivalent query.</span></span>

[!code-csharp[CsLINQProgJoining#4](~/samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_4.cs)]

## <a name="see-also"></a><span data-ttu-id="389b0-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="389b0-146">See also</span></span>

<xref:System.Linq.Enumerable.Join%2A>  
<xref:System.Linq.Enumerable.GroupJoin%2A>  
[<span data-ttu-id="389b0-147">그룹화 조인 수행</span><span class="sxs-lookup"><span data-stu-id="389b0-147">Perform grouped joins</span></span>](perform-grouped-joins.md)  
[<span data-ttu-id="389b0-148">왼쪽 우선 외부 조인 수행</span><span class="sxs-lookup"><span data-stu-id="389b0-148">Perform left outer joins</span></span>](perform-left-outer-joins.md)  
[<span data-ttu-id="389b0-149">무명 형식</span><span class="sxs-lookup"><span data-stu-id="389b0-149">Anonymous types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  