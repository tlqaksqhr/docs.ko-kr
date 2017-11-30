---
title: "보간된 문자열(C#)"
ms.date: 10/18/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b8a1fe0be82a0e09d61c66ed463199ff626c9faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="009f4-102">보간된 문자열(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="009f4-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="009f4-103">문자열을 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-103">Used to construct strings.</span></span>  <span data-ttu-id="009f4-104">보간된 문자열은 *보간된 식*이 포함된 템플릿 문자열과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="009f4-105">보간된 문자열은 포함하는 보간된 식을 해당 문자열 표현으로 바꾸는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="009f4-106">이 기능은 C# 6 이상 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-106">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="009f4-107">보간된 문자열의 인수는 [복합 형식 문자열](../../../standard/base-types/composite-formatting.md#composite-format-string)보다 더 쉽게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="009f4-108">예를 들어 보간된 문자열</span><span class="sxs-lookup"><span data-stu-id="009f4-108">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
<span data-ttu-id="009f4-109">두 보간된 식 '{name}'을 포함 하 고 ' {시간: hh}'.</span><span class="sxs-lookup"><span data-stu-id="009f4-109">contains two interpolated expressions, '{name}' and '{hour:hh}'.</span></span> <span data-ttu-id="009f4-110">동등한 복합 형식 문자열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-110">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="009f4-111">보간된 문자열의 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-111">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="009f4-112">여기서</span><span class="sxs-lookup"><span data-stu-id="009f4-112">where:</span></span> 

- <span data-ttu-id="009f4-113">*필드 너비*는 필드의 문자 수를 나타내는 부호 있는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="009f4-114">양수이면 필드가 오른쪽에 맞춰지고, 음수이면 왼쪽에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="009f4-115">*형식 문자열*은 형식을 지정할 개체 형식에 적합한 형식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="009f4-116">예를 들어 <xref:System.DateTime> 값의 경우 "D" 또는 "d"와 같은 표준 날짜 및 시간 형식 문자열일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-116">For example, for a <xref:System.DateTime> value, it could be a standard date and time format string such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="009f4-117">사이 공백이 없어야 없어야는 `$` 및 `"` 문자열을 시작 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="009f4-118">이렇게 하면 컴파일 시간 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-118">Doing so causes a compile time error.</span></span>

 <span data-ttu-id="009f4-119">문자열 리터럴을 사용할 수 있는 곳이면 어디든지 보간된 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="009f4-120">보간된 문자열을 포함하는 코드가 실행될 때마다 보간된 문자열이 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="009f4-121">이렇게 하면 보간된 문자열의 정의 및 평가를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="009f4-122">보간된 문자열에 중괄호("{" 또는 "}")를 포함하려면 두 개의 중괄호 "{{" 또는 "}}"를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="009f4-123">자세한 내용은 암시적 변환 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="009f4-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="009f4-124">큰따옴표("), 콜론(:), 쉼표(,) 등 특별한 의미를 가진 다른 문자가 보간된 문자열에 포함된 경우 리터럴 텍스트에 발생하면 이스케이프해야 하거나, 보간된 식에 포함된 언어 요소이면 괄호로 구분된 식에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="009f4-125">다음 예제에서는 따옴표를 이스케이프하여 결과 문자열에 포함하고, 콜론이 형식 문자열의 시작으로 해석되지 않도록 괄호를 사용하여 `(age == 1 ? "" : "s")` 식을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

<span data-ttu-id="009f4-126">정확 하 게 사용 하 여 문자열 보간는 `$` 하 여 다음에 오는 문자는 `@` 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-126">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="009f4-127">축 자 문자열에 대 한 자세한 내용은 참조는 [문자열](string.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-127">For more information about verbatim strings, see the [string](string.md) topic.</span></span> <span data-ttu-id="009f4-128">다음 코드는 약어 보간된 문자열을 사용 하 여 이전 코드의 수정된 된 버전:</span><span class="sxs-lookup"><span data-stu-id="009f4-128">The following code is a modified version of the previous snippet using a verbatim interpolated string:</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

<span data-ttu-id="009f4-129">축 자 문자열을 준수 하지 않는 때문에 서식 지정 변경 내용이 필요한 `\` 이스케이프 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-129">The formatting changes are necessary because verbatim strings do not obey `\` escape sequences.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="009f4-130">`$` 토큰 앞에 나와야 합니다.는 `@` 약어 보간된 문자열에서 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-130">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>


## <a name="implicit-conversions"></a><span data-ttu-id="009f4-131">암시적 변환</span><span class="sxs-lookup"><span data-stu-id="009f4-131">Implicit Conversions</span></span>  

<span data-ttu-id="009f4-132">보간된 문자열에서 다음과 같은 세 가지 암시적 형식 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-132">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="009f4-133">보간된 문자열을 <xref:System.String>으로 변환.</span><span class="sxs-lookup"><span data-stu-id="009f4-133">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="009f4-134">다음 예제에서는 보간된 문자열 식이 해당 문자열 표현으로 바뀐 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-134">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="009f4-135">예:</span><span class="sxs-lookup"><span data-stu-id="009f4-135">For example:</span></span>

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   <span data-ttu-id="009f4-136">이는 문자열 해석의 최종 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-136">This is the final result of a string interpretation.</span></span> <span data-ttu-id="009f4-137">나타나는 모든 이중 중괄호("{{" 및 "}}")가 단일 중괄호로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-137">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="009f4-138">보간된 문자열을 <xref:System.IFormattable> 변수로 변환. 이 변수를 사용하면 단일 <xref:System.IFormattable> 인스턴스의 문화권별 콘텐츠로 여러 결과 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-138">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="009f4-139">이 옵션은 개별 문화권의 올바른 숫자 및 날짜 형식 등을 포함하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-139">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="009f4-140">모든 이중 중괄호("{{" 및 "}}")는 <xref:System.Object.ToString> 메서드를 명시적 또는 암시적으로 호출하여 문자열을 형식을 지정할 때까지 이중 중괄호로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-140">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="009f4-141">포함된 보간 식은 모두 {0}, {1} 등으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-141">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="009f4-142">다음 예제에서는 리플렉션을 사용하여 보간된 문자열에서 생성된 <xref:System.IFormattable> 변수의 필드 및 속성 값뿐 아니라 멤버를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-142">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="009f4-143">또한 전달 된 <xref:System.IFormattable> 변수를 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="009f4-143">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   <span data-ttu-id="009f4-144">보간된 문자열은 리플렉션을 통해서만 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-144">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="009f4-145">와 같은 서식 지정 메서드에 문자열에 전달 된 경우 <xref:System.Console.WriteLine(System.String)>, 형식 항목을 해결 하 고 결과 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-145">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="009f4-146">보간된 문자열을 복합 형식 문자열을 나타내는 <xref:System.FormattableString> 변수로 변환.</span><span class="sxs-lookup"><span data-stu-id="009f4-146">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="009f4-147">예를 들어 복합 형식 문자열 및 복합 형식 문자열이 결과 문자열로 렌더링되는 방식을 검사하면 쿼리를 빌드하는 경우 삽입 공격으로부터 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-147">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="009f4-148"><xref:System.FormattableString>에는 <xref:System.Globalization.CultureInfo.InvariantCulture> 및 <xref:System.Globalization.CultureInfo.CurrentCulture>에 대한 결과 문자열을 생성할 수 있도록 하는 <xref:System.FormattableString.ToString> 오버로드도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-148"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the <xref:System.Globalization.CultureInfo.InvariantCulture> and <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>  <span data-ttu-id="009f4-149">나타나는 모든 이중 중괄호("{{" 및 "}}")는 형식을 지정할 때까지 이중 중괄호로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-149">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="009f4-150">포함된 보간 식은 모두 {0}, {1} 등으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="009f4-150">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a><span data-ttu-id="009f4-151">언어 사양</span><span class="sxs-lookup"><span data-stu-id="009f4-151">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="009f4-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="009f4-152">See Also</span></span>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="009f4-153">C# 참조</span><span class="sxs-lookup"><span data-stu-id="009f4-153">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="009f4-154">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="009f4-154">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
