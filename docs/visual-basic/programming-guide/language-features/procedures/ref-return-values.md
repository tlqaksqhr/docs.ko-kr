---
title: Ref 반환 값 (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2979359f0ffafe46a62696485bbb87b211c1704
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651243"
---
# <a name="support-for-reference-return-values-visual-basic"></a><span data-ttu-id="e1b84-102">참조 반환 값 (Visual Basic)에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="e1b84-102">Support for reference return values (Visual Basic)</span></span>

<span data-ttu-id="e1b84-103">C# 언어에서 지 원하는 C# 7.0 부터는 *반환 값을 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-103">Starting with C# 7.0, the C# language supports *reference return values*.</span></span> <span data-ttu-id="e1b84-104">참조 반환 값을 이해 하는 한 가지 방법은 이들이 반대 메서드에 참조로 전달 되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-104">One way to understand reference return values is that they are the opposite of arguments that are passed by reference to a method.</span></span> <span data-ttu-id="e1b84-105">참조로 전달 되는 인수를 수정한 경우 변경 내용은 호출자에 변수 값에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-105">When an argument passed by reference is modified, the changes are reflected in value of the variable on the caller.</span></span> <span data-ttu-id="e1b84-106">메서드를 호출자에 게 참조 반환 값을 제공 하는 경우 수정 내용 참조 반환 값에는 호출자가 호출된 된 메서드의 데이터에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-106">When an method provides a reference return value to a caller, modifications made to the reference return value by the caller are reflected in the called method's data.</span></span>

<span data-ttu-id="e1b84-107">Visual Basic 참조를 사용 하 여 만든 메서드 수 값을 반환 하지만 참조 반환 값을 사용할 수 있습니다 수를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-107">Visual Basic does not allow you to author methods with reference return values, but it does allow you to consume reference return values.</span></span> <span data-ttu-id="e1b84-108">즉, 참조 반환 값을 사용 하 여 메서드를 호출 하 고 해당 반환 값을 수정할 수 있습니다 및 참조 반환 값을 변경 하는 호출된 된 메서드의 데이터에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-108">In other words, you can call a method with a reference return value and modify that return value, and changes to the reference return value are reflected in the called method's data.</span></span>

## <a name="modifying-the-ref-return-value-directly"></a><span data-ttu-id="e1b84-109">Ref 반환 값을 직접 수정</span><span class="sxs-lookup"><span data-stu-id="e1b84-109">Modifying the ref return value directly</span></span>

<span data-ttu-id="e1b84-110">항상 실패 하 고 없는 있는 메서드에 대 한 `ByRef` 매개 변수를 직접 참조 반환 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-110">For methods that always succeed and have no `ByRef` parameters, you can modify the reference return value directly.</span></span> <span data-ttu-id="e1b84-111">참조 반환 값을 반환 하는 식에 새 값을 할당 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-111">You do this by assigning the new value to the expressions that returns the reference return value.</span></span> 

<span data-ttu-id="e1b84-112">다음 C# 예제에서는 정의 `NumericValue.IncrementValue` 메서드 내부 값이 증가 하 고 참조로 반환 하는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-112">The following C# example defines a `NumericValue.IncrementValue` method that increments an internal value and returns it as a reference return value.</span></span> 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

<span data-ttu-id="e1b84-113">참조 값이 다음 Visual Basic 예에서 호출자에 의해 수정 다음 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-113">The reference return value is then modified by the caller in the following Visual Basic example.</span></span> <span data-ttu-id="e1b84-114">한 줄으로는 `NumericValue.IncrementValue` 메서드 호출 메서드에 값을 할당 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-114">Note that the line with the `NumericValue.IncrementValue` method call does not assign a value to the method.</span></span> <span data-ttu-id="e1b84-115">대신, 메서드에 의해 반환 되는 참조 반환 값에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-115">Instead, it assigns a value to the reference return value returned by the method.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a><span data-ttu-id="e1b84-116">도우미 메서드를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="e1b84-116">Using a helper method</span></span>

<span data-ttu-id="e1b84-117">다른 경우에는 메서드 호출의 참조 반환 값을 직접 수정 항상 않을 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-117">In other cases, modifying the reference return value of a method call directly may not always be desirable.</span></span> <span data-ttu-id="e1b84-118">예를 들어 문자열을 반환 하는 검색 방법 찾을 수 없습니다 항상 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-118">For example, a search method that returns a string may not always find a match.</span></span> <span data-ttu-id="e1b84-119">이 경우 검색은 성공 하는 경우에 참조 반환 값을 수정 하려면.</span><span class="sxs-lookup"><span data-stu-id="e1b84-119">In that case, you want to modify the reference return value only if the search is successful.</span></span>

<span data-ttu-id="e1b84-120">다음 C# 예제에서는이 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-120">The following C# example illustrates this scenario.</span></span> <span data-ttu-id="e1b84-121">정의 `Sentence` C#으로 작성 된 클래스를 포함 한 `FindNext` 메서드를 지정된 된 부분 문자열으로 시작 하는 문장 내에서 다음 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-121">It defines a `Sentence` class written in C# includes a `FindNext` method that finds the next word in a sentence that begins with a specified substring.</span></span> <span data-ttu-id="e1b84-122">문자열은 참조 반환 값으로 반환되며, 메서드에 참조로 전달된 `Boolean` 변수는 검색에 성공했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-122">The string is returned as a reference return value, and a `Boolean` variable passed by reference to the method indicates whether the search was successful.</span></span> <span data-ttu-id="e1b84-123">참조 반환 값은 호출자에 게 없습니다 읽을 수만 있는지; 반환된 된 값을 나타냅니다. 자신이 수도 수정 하 고 수정 내용이 내부적으로 포함 된 데이터에 반영 되는 `Sentence` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-123">The reference return value indicates that the caller can not only read the returned value; he or she can also modify it, and that modification is reflected in the data contained internally in the `Sentence` class.</span></span>

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

<span data-ttu-id="e1b84-124">참조를 직접 수정 반환 값이 예제의 하지 않으므로 신뢰할 수 있는 일치 하는 것을 문장에 있는 첫 번째 단어를 반환 합니다. 메서드 호출이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-124">Directly modifying the reference return value in this case is not reliable, since the method call may fail to find a match and return the first word in the sentence.</span></span> <span data-ttu-id="e1b84-125">이 경우 호출자는 실수로 문장의 첫 번째 단어를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-125">In that case, the caller will inadvertently modify the first word of the sentence.</span></span> <span data-ttu-id="e1b84-126">이 문제를 방지할 수를 반환 하는 호출자가는 `null` (또는 `Nothing` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="e1b84-126">This could be prevented by the caller returning a `null` (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="e1b84-127">이 경우 값이 인 문자열을 수정 하려고 하지만 `Nothing` throw 한 <xref:System.NullReferenceException>합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-127">But in that case, attempting to modify a string whose value is `Nothing` throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="e1b84-128">호출자에 게 반환 하 여 문제를 방지할 수 또한 경우 <xref:System.String.Empty?displayProperty=nameWithType>, 그러나이 경우 호출자에 게 해당 값이 문자열 변수를 정의 하는 <xref:System.String.Empty?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-128">If could also be prevented by the caller returning <xref:System.String.Empty?displayProperty=nameWithType>, but this requires that the caller define a string variable whose value is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e1b84-129">호출자에 게 해당 문자열을 수정할 수, 하는 동안 자체 수정 어떠한 기능도 수행, 이후 수정된 된 문자열에에서 관계가 없는 단어를 저장 하 여 문장을 `Sentence` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-129">While the caller can modify that string, the modification itself serves no purpose, since the modified string has no relationship to the words in the sentence stored by the `Sentence` class.</span></span>

<span data-ttu-id="e1b84-130">이 시나리오를 처리 하는 가장 좋은 방법은 참조 도우미 메서드를 통해 참조 반환 값을 전달 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-130">The best way to handle this scenario is to pass the reference return value by reference to a helper method.</span></span> <span data-ttu-id="e1b84-131">그런 다음 도우미 메서드는 지 확인 하는 메서드 호출에 성공, 팩트 테이블 수정 참조 값을 반환 하는 논리를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-131">The helper method then contains the logic to determine whether the method call succeeded and, if it did, to modify the reference return value.</span></span> <span data-ttu-id="e1b84-132">다음 예제에서는 가능한 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e1b84-132">The following example provides a possible implementation.</span></span>

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a><span data-ttu-id="e1b84-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1b84-133">See also</span></span>

<span data-ttu-id="e1b84-134">[값 및 참조로 인수 전달](passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e1b84-134">[Passing arguments by value and by reference](passing-arguments-by-value-and-by-reference.md) </span></span>  
[<span data-ttu-id="e1b84-135">Visual Basic의 프로시저</span><span class="sxs-lookup"><span data-stu-id="e1b84-135">Procedures in Visual Basic</span></span>](index.md)   


