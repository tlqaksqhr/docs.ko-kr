---
title: C#의 문자열 보간
description: 문자열 보간을 사용하여 C#으로 결과 문자열에 서식이 지정된 식 결과를 포함하는 방법을 알아봅니다.
author: pkulikov
ms.date: 05/09/2018
ms.openlocfilehash: 447e87cd4aae49896f0efbb8ece6097181079266
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058941"
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="54400-103">C#의 문자열 보간</span><span class="sxs-lookup"><span data-stu-id="54400-103">String interpolation in C#</span></span> #

<span data-ttu-id="54400-104">이 자습서에서는 [문자열 보간](../language-reference/tokens/interpolated.md)을 사용하여 결과 문자열에서 식 결과의 서식을 지정하고 포함하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54400-104">This tutorial shows you how to use [string interpolation](../language-reference/tokens/interpolated.md) to format and include expression results in a result string.</span></span> <span data-ttu-id="54400-105">예제에서는 사용자가 기본 C# 개념 및 .NET 형식 서식 지정에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-105">The examples assume that you are familiar with basic C# concepts and .NET type formatting.</span></span> <span data-ttu-id="54400-106">문자열 보간 또는 .NET 형식 서식 지정을 처음 접하는 경우 [대화형 문자열 보간 빠른 시작](../quick-starts/interpolated-strings.yml)을 먼저 체크 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-106">If you are new to string interpolation or .NET type formatting, check out the [interactive string interpolation quickstart](../quick-starts/interpolated-strings.yml) first.</span></span> <span data-ttu-id="54400-107">.NET에서 형식 서식 지정하는 방법에 대한 자세한 내용은 [.NET의 형식 지정](../../standard/base-types/formatting-types.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54400-107">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) topic.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a><span data-ttu-id="54400-108">소개</span><span class="sxs-lookup"><span data-stu-id="54400-108">Introduction</span></span>

<span data-ttu-id="54400-109">[문자열 보간](../language-reference/tokens/interpolated.md) 기능은 [복합 서식 지정](../../standard/base-types/composite-formatting.md) 기능을 기반으로 빌드되고 결과 문자열에 서식이 지정된 식 결과를 포함하는 읽기 쉽고 편리한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-109">The [string interpolation](../language-reference/tokens/interpolated.md) feature is built on top of the [composite formatting](../../standard/base-types/composite-formatting.md) feature and provides a more readable and convenient syntax to include formatted expression results in a result string.</span></span>

<span data-ttu-id="54400-110">문자열 리터럴을 보간된 문자열로 식별하려면 `$` 기호를 사용하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-110">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="54400-111">보간된 문자열에서 값을 반환하는 유효한 C# 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54400-111">You can embed any valid C# expression that returns a value in an interpolated string.</span></span> <span data-ttu-id="54400-112">다음 예제에서는 식이 계산되는 즉시 결과가 문자열로 변환되고 결과 문자열에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="54400-112">In the following example, as soon as an expression is evaluated, its result is converted into a string and included in a result string:</span></span>

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

<span data-ttu-id="54400-113">이 예제에서 볼 수 있듯이 중괄호를 포함하여 보간된 문자열에 식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-113">As the example shows, you include an expression in an interpolated string by enclosing it with braces:</span></span>

```
{<interpolatedExpression>}
```

<span data-ttu-id="54400-114">컴파일 시 보간된 문자열은 일반적으로 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="54400-114">At compile time, an interpolated string is typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="54400-115">[문자열 복합 서식 지정](../../standard/base-types/composite-formatting.md) 기능의 모든 기능을 사용할 수 있도록 하여 보간된 문자열도 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-115">That makes all the capabilities of the [string composite formatting](../../standard/base-types/composite-formatting.md) feature available to you to use with interpolated strings as well.</span></span>

## <a name="how-to-specify-a-format-string-for-an-interpolated-expression"></a><span data-ttu-id="54400-116">보간된 식의 서식 문자열을 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="54400-116">How to specify a format string for an interpolated expression</span></span>

<span data-ttu-id="54400-117">콜론(":")과 형식 문자열을 사용하여 보간된 식에 따라 식 결과의 형식에서 지원하는 형식 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-117">You specify a format string that is supported by the type of the expression result by following the interpolated expression with a colon (":") and the format string:</span></span>

```
{<interpolatedExpression>:<formatString>}
```

<span data-ttu-id="54400-118">다음 예제에서는 날짜 및 시간 또는 숫자 결과를 생성하는 식의 표준 및 사용자 지정 서식 지정 문자열을 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54400-118">The following example shows how to specify standard and custom format strings for expressions that produce date and time or numeric results:</span></span>

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

<span data-ttu-id="54400-119">자세한 내용은 [복합 서식 지정](../../standard/base-types/composite-formatting.md) 항목의 [문자열 구성 요소 서식 지정](../../standard/base-types/composite-formatting.md#format-string-component) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54400-119">For more information, see the [Format String Component](../../standard/base-types/composite-formatting.md#format-string-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span> <span data-ttu-id="54400-120">해당 섹션에서는 .NET 기본 형식에서 지원하는 표준 및 사용자 지정 서식 지정 문자열을 설명하는 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-120">That section provides links to the topics that describe standard and custom format strings supported by .NET base types.</span></span>

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolated-expression"></a><span data-ttu-id="54400-121">필드 너비와 서식이 지정된 보간된 식의 맞춤을 제어하는 방법</span><span class="sxs-lookup"><span data-stu-id="54400-121">How to control the field width and alignment of the formatted interpolated expression</span></span>

<span data-ttu-id="54400-122">쉼표(",") 및 상수 식을 포함한 보간된 식에 따라 최소 필드 너비 및 서식이 지정된 식 결과의 맞춤을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-122">You specify the minimum field width and the alignment of the formatted expression result by following the interpolated expression with a comma (",") and the constant expression:</span></span>

```
{<interpolatedExpression>,<alignment>}
```

<span data-ttu-id="54400-123">*맞춤* 값이 양수이면 서식이 지정된 식 결과는 오른쪽 맞춤입니다. 값이 음수이면 왼쪽 맞춤입니다.</span><span class="sxs-lookup"><span data-stu-id="54400-123">If the *alignment* value is positive, the formatted expression result is right-aligned; if negative, it's left-aligned.</span></span>

<span data-ttu-id="54400-124">맞춤 및 서식 문자열을 모두 지정해야 할 경우 맞춤 구성 요소를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-124">If you need to specify both alignment and a format string, start with the alignment component:</span></span>

```
{<interpolatedExpression>,<alignment>:<formatString>}
```

<span data-ttu-id="54400-125">다음 예제에서는 맞춤을 지정하고 파이프 문자("|")를 사용하여 텍스트 필드를 구분하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54400-125">The following example shows how to specify alignment and uses pipe characters ("|") to delimit text fields:</span></span>

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

<span data-ttu-id="54400-126">출력 표시 예제에서 볼 수 있듯이 서식이 지정된 식 결과의 길이가 지정된 필드 너비를 초과하는 경우 *맞춤* 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54400-126">As the example output shows, if the length of the formatted expression result exceeds specified field width, the *alignment* value is ignored.</span></span>

<span data-ttu-id="54400-127">자세한 내용은 [복합 서식 지정](../../standard/base-types/composite-formatting.md) 항목의 [맞춤 구성 요소](../../standard/base-types/composite-formatting.md#alignment-component) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54400-127">For more information, see the [Alignment Component](../../standard/base-types/composite-formatting.md#alignment-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a><span data-ttu-id="54400-128">보간된 문자열에서 이스케이프 시퀀스를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="54400-128">How to use escape sequences in an interpolated string</span></span>

<span data-ttu-id="54400-129">보간된 문자열에서는 일반 문자열 리터럴을 사용할 수 있는 모든 이스케이프 시퀀스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-129">Interpolated strings support all escape sequences that can be used in ordinary string literals.</span></span> <span data-ttu-id="54400-130">자세한 내용은 [문자열 이스케이프 시퀀스](../programming-guide/strings/index.md#string-escape-sequences)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54400-130">For more information, see [String escape sequences](../programming-guide/strings/index.md#string-escape-sequences).</span></span>

<span data-ttu-id="54400-131">이스케이프 시퀀스를 문자 그대로 해석하려면 [약어](../language-reference/tokens/verbatim.md) 리터럴 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-131">To interpret escape sequences literally, use a [verbatim](../language-reference/tokens/verbatim.md) string literal.</span></span> <span data-ttu-id="54400-132">약어 보간된 문자열은 `@` 문자가 뒤에 오는 `$` 문자로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span>

<span data-ttu-id="54400-133">중괄호("{" 또는 "}")를 포함하려면 결과 문자열에서 2개의 중괄호("{{" 또는 "}}")를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-133">To include a brace, "{" or "}", in a result string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="54400-134">자세한 내용은 [복합 서식 지정](../../standard/base-types/composite-formatting.md) 항목의 [중괄호 이스케이프 처리](../../standard/base-types/composite-formatting.md#escaping-braces) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54400-134">For more information, see the [Escaping Braces](../../standard/base-types/composite-formatting.md#escaping-braces) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

<span data-ttu-id="54400-135">다음 예제에서는 결과 문자열에 중괄호를 포함하고 약어 보간된 문자열을 만드는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54400-135">The following example shows how to include braces in a result string and construct a verbatim interpolated string:</span></span>

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolated-expression"></a><span data-ttu-id="54400-136">보간된 식에서 3개로 구성된 `?:` 조건부 연산자를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="54400-136">How to use a ternary conditional operator `?:` in an interpolated expression</span></span>

<span data-ttu-id="54400-137">보간된 식에서 콜론(":")에 특별한 의미가 있으므로 식에서 [조건부 연산자](../language-reference/operators/conditional-operator.md)를 사용하기 위해 다음 예제에서 볼 수 있듯이 해당 식을 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="54400-137">As the colon (":") has special meaning in an item with an interpolated expression, in order to use a [conditional operator](../language-reference/operators/conditional-operator.md) in an expression, enclose it in parentheses, as the following example shows:</span></span>

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a><span data-ttu-id="54400-138">문자열 보간을 사용하여 문화권별 결과 문자열을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="54400-138">How to create a culture-specific result string with string interpolation</span></span>

<span data-ttu-id="54400-139">기본적으로는 보간된 문자열은 모든 서식 지정 작업에 대해 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> 속성에서 정의한 현재 문화권을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-139">By default, an interpolated string uses the current culture defined by the <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> property for all formatting operations.</span></span> <span data-ttu-id="54400-140"><xref:System.FormattableString?displayProperty=nameWithType> 인스턴스에 대한 보간된 문자열의 암시적 변환을 사용하고 해당 <xref:System.FormattableString.ToString(System.IFormatProvider)> 메서드를 호출하여 문화권별 결과 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="54400-140">Use implicit conversion of an interpolated string to a <xref:System.FormattableString?displayProperty=nameWithType> instance and call its <xref:System.FormattableString.ToString(System.IFormatProvider)> method to create a culture-specific result string.</span></span> <span data-ttu-id="54400-141">다음 예제에서는 해당 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54400-141">The following example shows how to do that:</span></span>

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

<span data-ttu-id="54400-142">이 예제에서 볼 수 있듯이 하나의 <xref:System.FormattableString> 인스턴스를 사용하여 다양한 문화권에 여러 결과 문자열을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54400-142">As the example shows, you can use one <xref:System.FormattableString> instance to generate multiple result strings for various cultures.</span></span>

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a><span data-ttu-id="54400-143">고정 문화권을 사용하여 결과 문자열을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="54400-143">How to create a result string using the invariant culture</span></span>

<span data-ttu-id="54400-144"><xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> 메서드와 함께 고정 <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> 메서드를 사용하여 <xref:System.Globalization.CultureInfo.InvariantCulture>에서 보간된 문자열을 결과 문자열로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54400-144">Along with the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method, you can use the static <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> method to resolve an interpolated string to a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span> <span data-ttu-id="54400-145">다음 예제에서는 해당 작업을 수행하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="54400-145">The following example shows how to do that:</span></span>

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a><span data-ttu-id="54400-146">결론</span><span class="sxs-lookup"><span data-stu-id="54400-146">Conclusion</span></span>

<span data-ttu-id="54400-147">이 자습서에서는 문자열 보간 사용법의 일반적인 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="54400-147">This tutorial describes common scenarios of string interpolation usage.</span></span> <span data-ttu-id="54400-148">문자열 보간에 대한 자세한 내용은 [문자열 보간](../language-reference/tokens/interpolated.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54400-148">For more information about string interpolation, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span> <span data-ttu-id="54400-149">.NET에서 형식 서식 지정하는 방법에 대한 자세한 내용은 [.NET의 형식 지정](../../standard/base-types/formatting-types.md) 및 [복합 서식 지정](../../standard/base-types/composite-formatting.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54400-149">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) and [Composite formatting](../../standard/base-types/composite-formatting.md) topics.</span></span>

## <a name="see-also"></a><span data-ttu-id="54400-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54400-150">See also</span></span>

<xref:System.String.Format%2A?displayProperty=nameWithType>  
<xref:System.FormattableString?displayProperty=nameWithType>  
<xref:System.IFormattable?displayProperty=nameWithType>  
[<span data-ttu-id="54400-151">문자열</span><span class="sxs-lookup"><span data-stu-id="54400-151">Strings</span></span>](../programming-guide/strings/index.md)  
