---
title: $ - 문자열 보간(C# 참조)
description: 문자열 보간을 이용한 구문으로 기존의 문자열 합성보다 읽기 쉽고 편리하게 문자열 출력의 서식을 지정할 수 있습니다.
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6873c3b419323fa9f5523143ad607289b6fd6e2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="04306-103">$ - 문자열 보간(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="04306-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="04306-104">`$`특수 문자는 문자열 리터럴을 *보간된 문자열*로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="04306-105">보간된 문자열은 *보간된 식*이 포함된 템플릿 문자열과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-105">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span> <span data-ttu-id="04306-106">예를 들어 대입문이나 메서드 호출에서 보간된 문자열이 확인되면 보간된 식이 결과의 문자열 표현으로 바뀌어 결과 문자열이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="04306-106">When the interpolated string is resolved, for example in an assignment statement or a method call, interpolated expressions are replaced by the string representations of their results to produce the result string.</span></span> <span data-ttu-id="04306-107">이 기능은 C# 6 이상 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04306-107">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="04306-108">문자열 보간은 [문자열 합성 서식 지정](../../../standard/base-types/composite-formatting.md) 기능보다 읽기 쉽고 편리하게 서식이 지정된 문자열을 만들 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="04306-108">String interpolation is a more readable and convenient way to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="04306-109">다음 예제에서는 두 기능을 사용하여 동일한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> <span data-ttu-id="04306-110">문자열을 시작하는 `$` 및 `"` 사이에 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-110">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="04306-111">이렇게 하면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-111">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="04306-112">보간된 식이 있는 항목의 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04306-112">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="04306-113">대괄호 안의 요소는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="04306-113">Elements in square brackets are optional.</span></span> <span data-ttu-id="04306-114">다음 표에서는 각 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-114">The following table describes each element.</span></span>

|<span data-ttu-id="04306-115">요소</span><span class="sxs-lookup"><span data-stu-id="04306-115">Element</span></span>|<span data-ttu-id="04306-116">설명</span><span class="sxs-lookup"><span data-stu-id="04306-116">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="04306-117">서식을 지정할 결과를 얻기 위해 평가할 식입니다.</span><span class="sxs-lookup"><span data-stu-id="04306-117">The expression to evaluate to get a result to be formatted.</span></span> <span data-ttu-id="04306-118">`null` 결과의 문자열 표현은 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="04306-118">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="04306-119">보간된 식의 결과에 대한 문자열 표현의 최소 문자 수를 정의하는 값을 갖는 상수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="04306-119">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="04306-120">양수이면 문자열 표현이 오른쪽에 맞춰지며, 음수이면 왼쪽에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="04306-120">If positive, the string representation is right-aligned; if negative, it is left-aligned.</span></span> <span data-ttu-id="04306-121">자세한 내용은 [맞춤 구성 요소](../../../standard/base-types/composite-formatting.md#alignment-component)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04306-121">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="04306-122">식 결과의 유형을 기준으로 지원되는 표준 또는 사용자 지정 서식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="04306-122">A standard or custom format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="04306-123">자세한 내용은 [서식 문자열 구성 요소](../../../standard/base-types/composite-formatting.md#format-string-component)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04306-123">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="04306-124">다음 예제에서는 위 표에 설명된 선택적 서식 지정 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-124">The following example uses optional formatting components described in the table above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

<span data-ttu-id="04306-125">보간된 문자열로 생성된 문자에 중괄호("{" 또는 "}")를 포함하려면 두 개의 중괄호 "{{" 또는 "}}"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-125">To include a curly brace ("{" or "}") in the text produced by an interpolated string, use two curly braces, "{{" or "}}".</span></span> <span data-ttu-id="04306-126">자세한 내용은 [중괄호 이스케이프](../../../standard/base-types/composite-formatting.md#escaping-braces)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04306-126">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="04306-127">콜론(:)은 보간된 식 항목에서 특별한 의미가 있으므로, 보간된 식에서 [조건부 연산자](../operators/conditional-operator.md)를 사용하려면 해당 식을 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="04306-127">As the colon (:) has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="04306-128">다음 예제에서는 중괄호를 결과 문자열에 포함하는 방법과 보간된 식에서 조건부 연산자를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="04306-128">The following example shows how to include a curly brace into the result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="04306-129">약어 보간된 문자열은 `@` 문자가 뒤에 오는 `$` 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-129">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="04306-130">약어 문자열에 대한 자세한 내용은 [문자열](../keywords/string.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04306-130">For more information about verbatim strings, see the [string](../keywords/string.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="04306-131">`$` 토큰은 약어 보간된 문자열에서 `@` 토큰 앞에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-131">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions"></a><span data-ttu-id="04306-132">암시적 변환</span><span class="sxs-lookup"><span data-stu-id="04306-132">Implicit conversions</span></span>

<span data-ttu-id="04306-133">보간된 문자열에서 다음과 같은 세 가지 암시적 형식 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04306-133">There are three implicit type conversions from an interpolated string:</span></span>

1. <span data-ttu-id="04306-134">보간된 문자열을 <xref:System.String> 인스턴스로 변환. 보간된 식 항목을 사용하여 보간된 문자열을 확인한 결과를 올바르게 서식이 지정된 문자열 표현으로 바꾼 것입니다.</span><span class="sxs-lookup"><span data-stu-id="04306-134">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="04306-135">이 변환은 현재 문화권을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-135">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="04306-136">보간된 문자열을 서식을 지정할 식 결과와 함께 복합 서식 문자열을 나타내는 <xref:System.FormattableString> 변수로 변환.</span><span class="sxs-lookup"><span data-stu-id="04306-136">Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="04306-137">이 변수를 사용하면 단일 <xref:System.FormattableString> 인스턴스에서 문화권별 콘텐츠가 포함된 여러 결과 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04306-137">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="04306-138">이렇게 하려면 다음 메서드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="04306-138">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="04306-139"><xref:System.Globalization.CultureInfo.CurrentCulture>에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.ToString> 오버로드.</span><span class="sxs-lookup"><span data-stu-id="04306-139">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="04306-140"><xref:System.Globalization.CultureInfo.InvariantCulture>에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.Invariant%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="04306-140">A <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="04306-141">지정된 문화에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.ToString(System.IFormatProvider)> 메서드.</span><span class="sxs-lookup"><span data-stu-id="04306-141">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

1. <span data-ttu-id="04306-142">보간된 문자열을 <xref:System.IFormattable> 변수로 변환. 또한 이 변수를 사용하면 단일 <xref:System.IFormattable> 인스턴스의 문화권별 콘텐츠로 여러 결과 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04306-142">Conversion of an interpolated string to an <xref:System.IFormattable> variable that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="04306-143">다음 예제에서는 <xref:System.FormattableString>에 대한 암시적 변환을 사용하여 문화권별 결과 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04306-143">The following example uses implicit conversion to <xref:System.FormattableString> for creating culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-reading"></a><span data-ttu-id="04306-144">추가 참조 항목</span><span class="sxs-lookup"><span data-stu-id="04306-144">Additional reading</span></span>

<span data-ttu-id="04306-145">문자열 보간을 처음 접하는 경우 [보간된 문자열 빠른 시작](../../quick-starts//interpolated-strings.yml)을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="04306-145">If you are new to the string interpolation, check the [interpolated strings quickstart](../../quick-starts//interpolated-strings.yml).</span></span> <span data-ttu-id="04306-146">자세한 내용은 [문자열 보간 자습서](../../tutorials/string-interpolation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04306-146">For more examples, see the [string interpolation tutorial](../../tutorials/string-interpolation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="04306-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04306-147">See also</span></span>  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [<span data-ttu-id="04306-148">복합 형식 지정</span><span class="sxs-lookup"><span data-stu-id="04306-148">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)  
 [<span data-ttu-id="04306-149">문자열</span><span class="sxs-lookup"><span data-stu-id="04306-149">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="04306-150">C# 특수 문자</span><span class="sxs-lookup"><span data-stu-id="04306-150">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)  
 [<span data-ttu-id="04306-151">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="04306-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04306-152">C# 참조</span><span class="sxs-lookup"><span data-stu-id="04306-152">C# Reference</span></span>](../../../csharp/language-reference/index.md)  