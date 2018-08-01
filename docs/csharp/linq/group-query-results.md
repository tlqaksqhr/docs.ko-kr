---
title: 쿼리 결과 그룹화(C#의 LINQ)
description: C#에서 LINQ를 사용하여 결과를 그룹화하는 방법을 알아봅니다.
ms.date: 12/1/2016
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: 4da0aac6b406f588ea4f241c72d5700e8a63838c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403867"
---
# <a name="group-query-results"></a><span data-ttu-id="b9444-103">쿼리 결과 그룹화</span><span class="sxs-lookup"><span data-stu-id="b9444-103">Group query results</span></span>

<span data-ttu-id="b9444-104">그룹화는 LINQ의 가장 강력한 기능 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-104">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="b9444-105">다음 예제에서는 다양한 방법으로 데이터를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-105">The following examples show how to group data in various ways:</span></span>

- <span data-ttu-id="b9444-106">단일 속성 사용.</span><span class="sxs-lookup"><span data-stu-id="b9444-106">By a single property.</span></span>

- <span data-ttu-id="b9444-107">문자열 속성의 첫 문자 사용.</span><span class="sxs-lookup"><span data-stu-id="b9444-107">By the first letter of a string property.</span></span>

- <span data-ttu-id="b9444-108">계산된 숫자 범위 사용.</span><span class="sxs-lookup"><span data-stu-id="b9444-108">By a computed numeric range.</span></span>

- <span data-ttu-id="b9444-109">부울 조건자 또는 기타 식 사용.</span><span class="sxs-lookup"><span data-stu-id="b9444-109">By Boolean predicate or other expression.</span></span>

- <span data-ttu-id="b9444-110">복합 키 사용.</span><span class="sxs-lookup"><span data-stu-id="b9444-110">By a compound key.</span></span>

<span data-ttu-id="b9444-111">또한 마지막 두 개의 쿼리는 학생의 이름과 성만 포함된 새 무명 형식으로 결과를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-111">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="b9444-112">자세한 내용은 [group 절](../language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9444-112">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="b9444-113">예</span><span class="sxs-lookup"><span data-stu-id="b9444-113">Example</span></span>

<span data-ttu-id="b9444-114">이 항목의 모든 예제에는 다음 도우미 클래스 및 데이터 소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-114">All the examples in this topic use the following helper classes and data sources.</span></span>

[!code-csharp[csProgGuideLINQ#15](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]

## <a name="example"></a><span data-ttu-id="b9444-115">예</span><span class="sxs-lookup"><span data-stu-id="b9444-115">Example</span></span>

<span data-ttu-id="b9444-116">다음 예제에서는 요소의 단일 속성을 그룹 키로 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-116">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="b9444-117">이 경우 키는 학생의 성인 `string`입니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-117">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="b9444-118">키에 부분 문자열을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-118">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="b9444-119">그룹화 작업에는 형식에 대한 기본 같음 비교자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-119">The grouping operation uses the default equality comparer for the type.</span></span>

<span data-ttu-id="b9444-120">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-120">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b9444-121">`Main` 메서드에서 호출 문을 `sc.GroupBySingleProperty()`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-121">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>

[!code-csharp[csProgGuideLINQ#17](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]

## <a name="example"></a><span data-ttu-id="b9444-122">예</span><span class="sxs-lookup"><span data-stu-id="b9444-122">Example</span></span>

<span data-ttu-id="b9444-123">다음 예제에서는 개체의 속성이 아닌 다른 항목을 그룹 키에 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-123">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="b9444-124">이 예제에서 키는 학생 성의 첫 번째 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-124">In this example, the key is the first letter of the student's last name.</span></span>

<span data-ttu-id="b9444-125">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-125">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b9444-126">`Main` 메서드에서 호출 문을 `sc.GroupBySubstring()`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-126">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>

[!code-csharp[csProgGuideLINQ#18](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]

## <a name="example"></a><span data-ttu-id="b9444-127">예</span><span class="sxs-lookup"><span data-stu-id="b9444-127">Example</span></span>

<span data-ttu-id="b9444-128">다음 예제에서는 숫자 범위를 그룹 키로 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-128">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="b9444-129">그런 다음 쿼리는 이름과 성 및 학생이 속한 백분위수 범위만 포함된 무명 형식으로 결과를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-129">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="b9444-130">결과를 표시하는 데 완전한 `Student` 개체를 사용할 필요가 없으므로 무명 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-130">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="b9444-131">`GetPercentile`은 학생의 평균 점수를 기준으로 백분위수를 계산하는 도우미 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-131">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="b9444-132">이 메서드는 0~10 사이의 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-132">The method returns an integer between 0 and 10.</span></span>

[!code-csharp[csProgGuideLINQ#50](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]

<span data-ttu-id="b9444-133">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-133">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b9444-134">`Main` 메서드에서 호출 문을 `sc.GroupByRange()`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-134">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>

[!code-csharp[csProgGuideLINQ#19](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]

## <a name="example"></a><span data-ttu-id="b9444-135">예</span><span class="sxs-lookup"><span data-stu-id="b9444-135">Example</span></span>

<span data-ttu-id="b9444-136">다음 예제에서는 부울 비교 식을 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-136">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="b9444-137">이 예제에서는 부울 식은 학생의 평균 시험 점수가 75보다 큰지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-137">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="b9444-138">이전 예제처럼 완전한 소스 요소가 필요하지 않으므로 결과는 무명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-138">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="b9444-139">무명 형식의 속성은 `Key` 멤버에 대한 속성이 되고 쿼리가 실행될 때 이름으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-139">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>

<span data-ttu-id="b9444-140">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-140">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b9444-141">`Main` 메서드에서 호출 문을 `sc.GroupByBoolean()`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-141">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>

[!code-csharp[csProgGuideLINQ#20](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]

## <a name="example"></a><span data-ttu-id="b9444-142">예</span><span class="sxs-lookup"><span data-stu-id="b9444-142">Example</span></span>

<span data-ttu-id="b9444-143">다음 예제에서는 무명 형식을 사용하여 여러 값이 포함된 키를 캡슐화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-143">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="b9444-144">이 예제에서 첫 번째 키 값은 학생 성의 첫 번째 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-144">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="b9444-145">두 번째 키 값은 첫 번째 시험에서 학생의 점수가 85보다 큰지 여부를 지정하는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-145">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="b9444-146">키의 속성을 기준으로 그룹 순서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-146">You can order the groups by any property in the key.</span></span>

<span data-ttu-id="b9444-147">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-147">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="b9444-148">`Main` 메서드에서 호출 문을 `sc.GroupByCompositeKey()`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b9444-148">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>

[!code-csharp[csProgGuideLINQ#21](~/samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]

## <a name="see-also"></a><span data-ttu-id="b9444-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9444-149">See also</span></span>

<xref:System.Linq.Enumerable.GroupBy%2A>  
<xref:System.Linq.IGrouping%602>  
[<span data-ttu-id="b9444-150">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="b9444-150">Language Integrated Query (LINQ)</span></span>](index.md)  
[<span data-ttu-id="b9444-151">group 절</span><span class="sxs-lookup"><span data-stu-id="b9444-151">group clause</span></span>](../language-reference/keywords/group-clause.md)  
[<span data-ttu-id="b9444-152">익명 형식</span><span class="sxs-lookup"><span data-stu-id="b9444-152">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
[<span data-ttu-id="b9444-153">그룹화 작업에서 하위 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="b9444-153">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)  
[<span data-ttu-id="b9444-154">중첩 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="b9444-154">Create a Nested Group</span></span>](create-a-nested-group.md)  
[<span data-ttu-id="b9444-155">데이터 그룹화</span><span class="sxs-lookup"><span data-stu-id="b9444-155">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)  