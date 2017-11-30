---
title: "쿼리 결과 그룹화"
description: "결과를 그룹화하는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2e4ec27f-06fb-4de7-8973-0189906d4520
ms.openlocfilehash: ca68cf96a2c27bbd1999d5445c14fc93e8e2566c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="group-query-results"></a><span data-ttu-id="3886f-104">쿼리 결과 그룹화</span><span class="sxs-lookup"><span data-stu-id="3886f-104">Group query results</span></span>

<span data-ttu-id="3886f-105">그룹화는 LINQ의 가장 강력한 기능 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-105">Grouping is one of the most powerful capabilities of LINQ.</span></span> <span data-ttu-id="3886f-106">다음 예제에서는 다양한 방법으로 데이터를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-106">The following examples show how to group data in various ways:</span></span>  
  
-   <span data-ttu-id="3886f-107">단일 속성 사용.</span><span class="sxs-lookup"><span data-stu-id="3886f-107">By a single property.</span></span>  
  
-   <span data-ttu-id="3886f-108">문자열 속성의 첫 문자 사용.</span><span class="sxs-lookup"><span data-stu-id="3886f-108">By the first letter of a string property.</span></span>  
  
-   <span data-ttu-id="3886f-109">계산된 숫자 범위 사용.</span><span class="sxs-lookup"><span data-stu-id="3886f-109">By a computed numeric range.</span></span>  
  
-   <span data-ttu-id="3886f-110">부울 조건자 또는 기타 식 사용.</span><span class="sxs-lookup"><span data-stu-id="3886f-110">By Boolean predicate or other expression.</span></span>  
  
-   <span data-ttu-id="3886f-111">복합 키 사용.</span><span class="sxs-lookup"><span data-stu-id="3886f-111">By a compound key.</span></span>  
  
 <span data-ttu-id="3886f-112">또한 마지막 두 개의 쿼리는 학생의 이름과 성만 포함된 새 무명 형식으로 결과를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-112">In addition, the last two queries project their results into a new anonymous type that contains only the student's first and last name.</span></span> <span data-ttu-id="3886f-113">자세한 내용은 [group 절](../language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3886f-113">For more information, see the [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3886f-114">예제</span><span class="sxs-lookup"><span data-stu-id="3886f-114">Example</span></span>  
 <span data-ttu-id="3886f-115">이 항목의 모든 예제에는 다음 도우미 클래스 및 데이터 소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-115">All the examples in this topic use the following helper classes and data sources.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="3886f-116">예제</span><span class="sxs-lookup"><span data-stu-id="3886f-116">Example</span></span>  
 <span data-ttu-id="3886f-117">다음 예제에서는 요소의 단일 속성을 그룹 키로 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-117">The following example shows how to group source elements by using a single property of the element as the group key.</span></span> <span data-ttu-id="3886f-118">이 경우 키는 학생의 성인 `string`입니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-118">In this case the key is a `string`, the student's last name.</span></span> <span data-ttu-id="3886f-119">키에 부분 문자열을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-119">It is also possible to use a substring for the key.</span></span> <span data-ttu-id="3886f-120">그룹화 작업에는 형식에 대한 기본 같음 비교자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-120">The grouping operation uses the default equality comparer for the type.</span></span>  
  
 <span data-ttu-id="3886f-121">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-121">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3886f-122">`Main` 메서드에서 호출 문을 `sc.GroupBySingleProperty()`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-122">Change the calling statement in the `Main` method to `sc.GroupBySingleProperty()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#17](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="3886f-123">예제</span><span class="sxs-lookup"><span data-stu-id="3886f-123">Example</span></span>  
 <span data-ttu-id="3886f-124">다음 예제에서는 개체의 속성이 아닌 다른 항목을 그룹 키에 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-124">The following example shows how to group source elements by using something other than a property of the object for the group key.</span></span> <span data-ttu-id="3886f-125">이 예제에서 키는 학생 성의 첫 번째 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-125">In this example, the key is the first letter of the student's last name.</span></span>  
  
 <span data-ttu-id="3886f-126">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-126">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3886f-127">`Main` 메서드에서 호출 문을 `sc.GroupBySubstring()`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-127">Change the calling statement in the `Main` method to `sc.GroupBySubstring()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#18](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="3886f-128">예제</span><span class="sxs-lookup"><span data-stu-id="3886f-128">Example</span></span>  
 <span data-ttu-id="3886f-129">다음 예제에서는 숫자 범위를 그룹 키로 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-129">The following example shows how to group source elements by using a numeric range as a group key.</span></span> <span data-ttu-id="3886f-130">그런 다음 쿼리는 이름과 성 및 학생이 속한 백분위수 범위만 포함된 무명 형식으로 결과를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-130">The query then projects the results into an anonymous type that contains only the first and last name and the percentile range to which the student belongs.</span></span> <span data-ttu-id="3886f-131">결과를 표시하는 데 완전한 `Student` 개체를 사용할 필요가 없으므로 무명 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-131">An anonymous type is used because it is not necessary to use the complete `Student` object to display the results.</span></span> <span data-ttu-id="3886f-132">`GetPercentile`은 학생의 평균 점수를 기준으로 백분위수를 계산하는 도우미 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-132">`GetPercentile` is a helper function that calculates a percentile based on the student's average score.</span></span> <span data-ttu-id="3886f-133">이 메서드는 0~10 사이의 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-133">The method returns an integer between 0 and 10.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#50](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_4.cs)]  
  
 <span data-ttu-id="3886f-134">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-134">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3886f-135">`Main` 메서드에서 호출 문을 `sc.GroupByRange()`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-135">Change the calling statement in the `Main` method to `sc.GroupByRange()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#19](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_5.cs)]  
  
## <a name="example"></a><span data-ttu-id="3886f-136">예제</span><span class="sxs-lookup"><span data-stu-id="3886f-136">Example</span></span>  
 <span data-ttu-id="3886f-137">다음 예제에서는 부울 비교 식을 사용하여 소스 요소를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-137">The following example shows how to group source elements by using a Boolean comparison expression.</span></span> <span data-ttu-id="3886f-138">이 예제에서는 부울 식은 학생의 평균 시험 점수가 75보다 큰지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-138">In this example, the Boolean expression tests whether a student's average exam score is greater than 75.</span></span> <span data-ttu-id="3886f-139">이전 예제처럼 완전한 소스 요소가 필요하지 않으므로 결과는 무명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-139">As in previous examples, the results are projected into an anonymous type because the complete source element is not needed.</span></span> <span data-ttu-id="3886f-140">무명 형식의 속성은 `Key` 멤버에 대한 속성이 되고 쿼리가 실행될 때 이름으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-140">Note that the properties in the anonymous type become properties on the `Key` member and can be accessed by name when the query is executed.</span></span>  
  
 <span data-ttu-id="3886f-141">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-141">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3886f-142">`Main` 메서드에서 호출 문을 `sc.GroupByBoolean()`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-142">Change the calling statement in the `Main` method to `sc.GroupByBoolean()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#20](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="3886f-143">예제</span><span class="sxs-lookup"><span data-stu-id="3886f-143">Example</span></span>  
 <span data-ttu-id="3886f-144">다음 예제에서는 무명 형식을 사용하여 여러 값이 포함된 키를 캡슐화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-144">The following example shows how to use an anonymous type to encapsulate a key that contains multiple values.</span></span> <span data-ttu-id="3886f-145">이 예제에서 첫 번째 키 값은 학생 성의 첫 번째 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-145">In this example, the first key value is the first letter of the student's last name.</span></span> <span data-ttu-id="3886f-146">두 번째 키 값은 첫 번째 시험에서 학생의 점수가 85보다 큰지 여부를 지정하는 부울입니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-146">The second key value is a Boolean that specifies whether the student scored over 85 on the first exam.</span></span> <span data-ttu-id="3886f-147">키의 속성을 기준으로 그룹 순서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-147">You can order the groups by any property in the key.</span></span>  
  
 <span data-ttu-id="3886f-148">`StudentClass` 클래스에 다음 메서드를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-148">Paste the following method into the `StudentClass` class.</span></span> <span data-ttu-id="3886f-149">`Main` 메서드에서 호출 문을 `sc.GroupByCompositeKey()`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3886f-149">Change the calling statement in the `Main` method to `sc.GroupByCompositeKey()`.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#21](../../../samples/snippets/csharp/concepts/linq/how-to-group-query-results_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3886f-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3886f-150">See also</span></span>  
 <xref:System.Linq.Enumerable.GroupBy%2A>  
 <xref:System.Linq.IGrouping%602>  
 [<span data-ttu-id="3886f-151">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="3886f-151">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="3886f-152">group 절</span><span class="sxs-lookup"><span data-stu-id="3886f-152">group clause</span></span>](../language-reference/keywords/group-clause.md)  
 [<span data-ttu-id="3886f-153">익명 형식</span><span class="sxs-lookup"><span data-stu-id="3886f-153">Anonymous Types</span></span>](../programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="3886f-154">그룹화 작업에서 하위 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="3886f-154">Perform a Subquery on a Grouping Operation</span></span>](perform-a-subquery-on-a-grouping-operation.md)  
 [<span data-ttu-id="3886f-155">중첩된 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="3886f-155">Create a Nested Group</span></span>](create-a-nested-group.md)  
 [<span data-ttu-id="3886f-156">데이터 그룹화</span><span class="sxs-lookup"><span data-stu-id="3886f-156">Grouping Data</span></span>](../programming-guide/concepts/linq/grouping-data.md)
