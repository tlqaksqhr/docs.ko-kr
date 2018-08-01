---
title: group 절(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 8e3ddea3ba733cb9ba32e510b050a58407a7a477
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404517"
---
# <a name="group-clause-c-reference"></a><span data-ttu-id="430b2-102">group 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="430b2-102">group clause (C# Reference)</span></span>

<span data-ttu-id="430b2-103">`group` 절은 그룹의 키 값과 일치하는 0개 이상의 항목이 포함된 <xref:System.Linq.IGrouping%602> 개체 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-103">The `group` clause returns a sequence of <xref:System.Linq.IGrouping%602> objects that contain zero or more items that match the key value for the group.</span></span> <span data-ttu-id="430b2-104">예를 들어 각 문자열의 첫 번째 문자에 따라 문자열 시퀀스를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-104">For example, you can group a sequence of strings according to the first letter in each string.</span></span> <span data-ttu-id="430b2-105">이 경우 첫 번째 문자는 키로, [char](char.md) 형식이며 각 <xref:System.Linq.IGrouping%602> 개체의 `Key` 속성에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-105">In this case, the first letter is the key and has a type [char](char.md), and is stored in the `Key` property of each <xref:System.Linq.IGrouping%602> object.</span></span> <span data-ttu-id="430b2-106">컴파일러는 키의 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-106">The compiler infers the type of the key.</span></span>

<span data-ttu-id="430b2-107">다음 예제와 같이 쿼리 식을 `group` 절로 끝낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-107">You can end a query expression with a `group` clause, as shown in the following example:</span></span>

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

<span data-ttu-id="430b2-108">각 그룹에서 추가 쿼리 작업을 수행하려는 경우 [into](into.md) 상황별 키워드를 사용하여 임시 식별자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-108">If you want to perform additional query operations on each group, you can specify a temporary identifier by using the [into](into.md) contextual keyword.</span></span> <span data-ttu-id="430b2-109">`into`를 사용하는 경우 쿼리를 계속 진행하고, 다음 예제와 같이 궁극적으로 `select` 문이나 다른 `group` 절로 끝내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-109">When you use `into`, you must continue with the query, and eventually end it with either a `select` statement or another `group` clause, as shown in the following excerpt:</span></span>

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

<span data-ttu-id="430b2-110">`into`를 포함 및 포함하지 않고 `group`을 사용하는 보다 자세한 예제는 이 문서의 예제 섹션에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-110">More complete examples of the use of `group` with and without `into` are provided in the Example section of this article.</span></span>

## <a name="enumerating-the-results-of-a-group-query"></a><span data-ttu-id="430b2-111">그룹 쿼리의 결과 열거</span><span class="sxs-lookup"><span data-stu-id="430b2-111">Enumerating the results of a group query</span></span>

<span data-ttu-id="430b2-112">`group` 쿼리에 의해 생성된 <xref:System.Linq.IGrouping%602> 개체는 기본적으로 목록의 목록이기 때문에 중첩된 [foreach](foreach-in.md) 루프를 사용하여 각 그룹에 있는 항목에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-112">Because the <xref:System.Linq.IGrouping%602> objects produced by a `group` query are essentially a list of lists, you must use a nested [foreach](foreach-in.md) loop to access the items in each group.</span></span> <span data-ttu-id="430b2-113">외부 루프는 그룹 키를 반복하고, 내부 루프는 그룹 자체에 있는 각 항목을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-113">The outer loop iterates over the group keys, and the inner loop iterates over each item in the group itself.</span></span> <span data-ttu-id="430b2-114">그룹에 키가 있지만 요소는 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-114">A group may have a key but no elements.</span></span> <span data-ttu-id="430b2-115">다음은 앞의 코드 예제에서 쿼리를 실행하는 `foreach` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-115">The following is the `foreach` loop that executes the query in the previous code examples:</span></span>

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a><span data-ttu-id="430b2-116">키 형식</span><span class="sxs-lookup"><span data-stu-id="430b2-116">Key types</span></span>

<span data-ttu-id="430b2-117">그룹 키는 문자열, 기본 제공 숫자 형식, 사용자 정의 명명된 형식, 무명 형식 등 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-117">Group keys can be any type, such as a string, a built-in numeric type, or a user-defined named type or anonymous type.</span></span>

### <a name="grouping-by-string"></a><span data-ttu-id="430b2-118">문자열로 그룹화</span><span class="sxs-lookup"><span data-stu-id="430b2-118">Grouping by string</span></span>

<span data-ttu-id="430b2-119">앞의 코드 예제에서는 `char`를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-119">The previous code examples used a `char`.</span></span> <span data-ttu-id="430b2-120">대신, 문자열 키를 전체 성 등으로 쉽게 지정했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-120">A string key could easily have been specified instead, for example the complete last name:</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a><span data-ttu-id="430b2-121">부울로 그룹화</span><span class="sxs-lookup"><span data-stu-id="430b2-121">Grouping by bool</span></span>

<span data-ttu-id="430b2-122">다음 예제에서는 키에 부울 값을 사용하여 결과를 두 그룹으로 나누는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-122">The following example shows the use of a bool value for a key to divide the results into two groups.</span></span> <span data-ttu-id="430b2-123">값은 `group` 절의 하위 식에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-123">Note that the value is produced by a sub-expression in the `group` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a><span data-ttu-id="430b2-124">숫자 범위로 그룹화</span><span class="sxs-lookup"><span data-stu-id="430b2-124">Grouping by numeric range</span></span>

<span data-ttu-id="430b2-125">다음 예제에서는 식을 사용하여 백분위수 범위를 나타내는 숫자 그룹 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-125">The next example uses an expression to create numeric group keys that represent a percentile range.</span></span> <span data-ttu-id="430b2-126">메서드 호출 결과를 저장할 편리한 위치로 [let](let-clause.md)을 사용하여 `group` 절에서 메서드를 두 번 호출할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-126">Note the use of [let](let-clause.md) as a convenient location to store a method call result, so that you don't have to call the method two times in the `group` clause.</span></span> <span data-ttu-id="430b2-127">또한 `group` 절에서 “0으로 나누기” 예외를 방지하기 위해 코드를 통해 학생의 평균이 0이 아닌 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-127">Note also in the `group` clause that to avoid a "divide by zero" exception the code checks to make sure that the student doesn't have an average of zero.</span></span> <span data-ttu-id="430b2-128">쿼리 식에 메서드를 안전하게 사용하는 방법에 대한 자세한 내용은 [방법: 쿼리 식의 예외 처리](../../programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="430b2-128">For more information about how to safely use methods in query expressions, see [How to: Handle Exceptions in Query Expressions](../../programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md).</span></span>

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a><span data-ttu-id="430b2-129">복합 키로 그룹화</span><span class="sxs-lookup"><span data-stu-id="430b2-129">Grouping by composite keys</span></span>

<span data-ttu-id="430b2-130">둘 이상의 키에 따라 요소를 그룹화하려는 경우 복합 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-130">Use a composite key when you want to group elements according to more than one key.</span></span> <span data-ttu-id="430b2-131">무명 형식이나 명명된 형식을 통해 키 요소를 저장하여 복합 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-131">You create a composite key by using an anonymous type or a named type to hold the key element.</span></span> <span data-ttu-id="430b2-132">다음 예제에서는 `Person` 클래스가 `surname` 및 `city`라는 멤버로 선언되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-132">In the following example, assume that a class `Person` has been declared with members named `surname` and `city`.</span></span> <span data-ttu-id="430b2-133">`group` 절은 성과 도시가 동일한 각 개인 집합에 대해 별도 그룹이 생성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-133">The `group` clause causes a separate group to be created for each set of persons with the same last name and the same city.</span></span>

```csharp
group person by new {name = person.surname, city = person.city};
```

<span data-ttu-id="430b2-134">쿼리 변수를 다른 메서드에 전달해야 하는 경우 명명된 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-134">Use a named type if you must pass the query variable to another method.</span></span> <span data-ttu-id="430b2-135">키에 대해 자동 구현 속성을 사용하여 특수 클래스를 만든 다음 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-135">Create a special class using auto-implemented properties for the keys, and then override the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods.</span></span> <span data-ttu-id="430b2-136">구조체를 사용할 수도 있으며, 이 경우 이러한 메서드를 엄격하게 재정의하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-136">You can also use a struct, in which case you do not strictly have to override those methods.</span></span> <span data-ttu-id="430b2-137">자세한 내용은 [방법: 자동으로 구현된 속성을 사용하여 간단한 클래스 구현](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) 및 [방법: 디렉터리 트리에서 중복된 파일 쿼리](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="430b2-137">For more information see [How to: Implement a Lightweight Class with Auto-Implemented Properties](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) and [How to: Query for Duplicate Files in a Directory Tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span></span> <span data-ttu-id="430b2-138">두 번째 문서에는 명명된 형식과 함께 복합 키를 사용하는 방법을 보여 주는 코드 예제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-138">The latter article has a code example that demonstrates how to use a composite key with a named type.</span></span>

## <a name="example"></a><span data-ttu-id="430b2-139">예</span><span class="sxs-lookup"><span data-stu-id="430b2-139">Example</span></span>

<span data-ttu-id="430b2-140">다음 예제에서는 추가 쿼리 논리가 그룹에 적용되지 않는 경우 소스 데이터를 그룹으로 정렬하기 위한 표준 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-140">The following example shows the standard pattern for ordering source data into groups when no additional query logic is applied to the groups.</span></span> <span data-ttu-id="430b2-141">이를 비연속 그룹화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-141">This is called a grouping without a continuation.</span></span> <span data-ttu-id="430b2-142">문자열 배열에 있는 요소는 첫 문자에 따라 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-142">The elements in an array of strings are grouped according to their first letter.</span></span> <span data-ttu-id="430b2-143">쿼리 결과는 그룹에 각 항목을 포함하는 공용 `Key` 속성 형식 `char` 및 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션을 포함하는 <xref:System.Linq.IGrouping%602> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-143">The result of the query is an <xref:System.Linq.IGrouping%602> type that contains a public `Key` property of type `char` and an <xref:System.Collections.Generic.IEnumerable%601> collection that contains each item in the grouping.</span></span>

<span data-ttu-id="430b2-144">`group` 절의 결과는 시퀀스의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-144">The result of a `group` clause is a sequence of sequences.</span></span> <span data-ttu-id="430b2-145">따라서 반환된 각 그룹 내의 개별 요소에 액세스하려면 다음 예제와 같이 그룹 키를 반복하는 루프 안에 중첩된 `foreach` 루프를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-145">Therefore, to access the individual elements within each returned group, use a nested `foreach` loop inside the loop that iterates the group keys, as shown in the following example.</span></span>

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a><span data-ttu-id="430b2-146">예</span><span class="sxs-lookup"><span data-stu-id="430b2-146">Example</span></span>

<span data-ttu-id="430b2-147">이 예제에서는 `into`와 함께 *continuation*을 사용하여 그룹을 만든 후 그룹에서 추가 논리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-147">This example shows how to perform additional logic on the groups after you have created them, by using a *continuation* with `into`.</span></span> <span data-ttu-id="430b2-148">자세한 내용은 [into](into.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="430b2-148">For more information, see [into](into.md).</span></span> <span data-ttu-id="430b2-149">다음 예제에서는 각 그룹을 쿼리하여 키 값이 모음인 그룹만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-149">The following example queries each group to select only those whose key value is a vowel.</span></span>

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a><span data-ttu-id="430b2-150">설명</span><span class="sxs-lookup"><span data-stu-id="430b2-150">Remarks</span></span>

<span data-ttu-id="430b2-151">`group` 절은 컴파일 시간에 <xref:System.Linq.Enumerable.GroupBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="430b2-151">At compile time, `group` clauses are translated into calls to the <xref:System.Linq.Enumerable.GroupBy%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="430b2-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="430b2-152">See also</span></span>

<xref:System.Linq.IGrouping%602>  
<xref:System.Linq.Enumerable.GroupBy%2A>  
<xref:System.Linq.Enumerable.ThenBy%2A>  
<xref:System.Linq.Enumerable.ThenByDescending%2A>  
[<span data-ttu-id="430b2-153">쿼리 키워드</span><span class="sxs-lookup"><span data-stu-id="430b2-153">Query Keywords</span></span>](query-keywords.md)  
[<span data-ttu-id="430b2-154">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="430b2-154">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)  
[<span data-ttu-id="430b2-155">중첩 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="430b2-155">Create a nested group</span></span>](../../linq/create-a-nested-group.md)  
[<span data-ttu-id="430b2-156">쿼리 결과 그룹화</span><span class="sxs-lookup"><span data-stu-id="430b2-156">Group query results</span></span>](../../linq/group-query-results.md)  
[<span data-ttu-id="430b2-157">그룹화 작업에서 하위 쿼리 수행</span><span class="sxs-lookup"><span data-stu-id="430b2-157">Perform a subquery on a grouping operation</span></span>](../../linq/perform-a-subquery-on-a-grouping-operation.md)