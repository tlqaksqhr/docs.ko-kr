---
title: 정규식의 역참조 구문
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b16cfeda88b8e700c4d473962155a8510ce7df2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="backreference-constructs-in-regular-expressions"></a><span data-ttu-id="0b5dd-102">정규식의 역참조 구문</span><span class="sxs-lookup"><span data-stu-id="0b5dd-102">Backreference Constructs in Regular Expressions</span></span>
<span data-ttu-id="0b5dd-103">역참조는 문자열 내에서 반복된 문자 또는 부분 문자열을 식별하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-103">Backreferences provide a convenient way to identify a repeated character or substring within a string.</span></span> <span data-ttu-id="0b5dd-104">예를 들어 입력 문자열에 임의의 부분 문자열이 여러 번 포함되어 있으면 첫 번째 발생을 캡처링 그룹과 일치시킨 다음 역참조를 사용하여 부분 문자열의 후속 발생을 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-104">For example, if the input string contains multiple occurrences of an arbitrary substring, you can match the first occurrence with a capturing group, and then use a backreference to match subsequent occurrences of the substring.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b5dd-105">대체 문자열에서 명명된 캡처링 그룹과 번호가 매겨진 캡처링 그룹을 참조하기 위해 별도의 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-105">A separate syntax is used to refer to named and numbered capturing groups in replacement strings.</span></span> <span data-ttu-id="0b5dd-106">자세한 내용은 [Substitutions](substitutions-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-106">For more information, see [Substitutions](substitutions-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="0b5dd-107">.NET에서는 번호가 매겨진 캡처링 그룹과 명명된 캡처링 그룹을 참조하기 위해 별도의 언어 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-107">.NET defines separate language elements to refer to numbered and named capturing groups.</span></span> <span data-ttu-id="0b5dd-108">캡처링 그룹에 대한 자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-108">For more information about capturing groups, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
## <a name="numbered-backreferences"></a><span data-ttu-id="0b5dd-109">번호가 매겨진 역참조</span><span class="sxs-lookup"><span data-stu-id="0b5dd-109">Numbered Backreferences</span></span>  
 <span data-ttu-id="0b5dd-110">번호가 매겨진 역참조에는 다음 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-110">A numbered backreference uses the following syntax:</span></span>  
  
 <span data-ttu-id="0b5dd-111">`\` *number*</span><span class="sxs-lookup"><span data-stu-id="0b5dd-111">`\` *number*</span></span>  
  
 <span data-ttu-id="0b5dd-112">여기서 *number*는 정규식에서 캡처링 그룹의 서수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-112">where *number* is the ordinal position of the capturing group in the regular expression.</span></span> <span data-ttu-id="0b5dd-113">예를 들어 `\4`는 네 번째 캡처링 그룹의 내용을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-113">For example, `\4` matches the contents of the fourth capturing group.</span></span> <span data-ttu-id="0b5dd-114">*number*가 정규식 패턴에서 정의되지 않은 경우 구문 분석 오류가 발생하고 정규식 엔진이 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-114">If *number* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="0b5dd-115">예를 들어 `\b(\w+)\s\1` 정규식은 `(\w+)`가 식의 첫 번째이자 유일한 캡처링 그룹이기 때문에 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-115">For example, the regular expression `\b(\w+)\s\1` is valid, because `(\w+)` is the first and only capturing group in the expression.</span></span> <span data-ttu-id="0b5dd-116">반면에 `\b(\w+)\s\2`는 `\2`로 번호가 매겨진 캡처링 그룹이 없기 때문에 유효하지 않으며 인수 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-116">On the other hand, `\b(\w+)\s\2` is invalid and throws an argument exception, because there is no capturing group numbered `\2`.</span></span> <span data-ttu-id="0b5dd-117">또한 *번호*가 특정 서수 위치에서 캡처링 그룹을 식별하지만 해당 캡처링 그룹이 서수 위치가 아닌 다른 숫자 이름을 할당받은 경우 정규식 파서는 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-117">In addition, if *number* identifies a capturing group in a particular ordinal position, but that capturing group has been assigned a numeric name different than its ordinal position, the regular expression parser also throws an <xref:System.ArgumentException>.</span></span> 
  
 <span data-ttu-id="0b5dd-118">8진수 이스케이프 코드(예: `\16`)와 동일한 표기법을 사용하는 `\`*number* 역참조 간의 모호성에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-118">Note the ambiguity between octal escape codes (such as `\16`) and `\`*number* backreferences that use the same notation.</span></span> <span data-ttu-id="0b5dd-119">이러한 모호성은 다음과 같이 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-119">This ambiguity is resolved as follows:</span></span>  
  
-   <span data-ttu-id="0b5dd-120">`\1`에서 `\9` 사이의 식은 항상 8진수 코드가 아니라 역참조로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-120">The expressions `\1` through `\9` are always interpreted as backreferences, and not as octal codes.</span></span>  
  
-   <span data-ttu-id="0b5dd-121">다중 숫자 식의 첫 번째 숫자가 8 또는 9이면(예: `\80` 또는 `\91`) 식은 리터럴로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-121">If the first digit of a multidigit expression is 8 or 9 (such as `\80` or `\91`), the expression as interpreted as a literal.</span></span>  
  
-   <span data-ttu-id="0b5dd-122">`\10` 이상인 식은 이 숫자에 해당하는 역참조가 있을 경우 역참조로 간주되고, 없을 경우 8진수 코드로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-122">Expressions from `\10` and greater are considered backreferences if there is a backreference corresponding to that number; otherwise, they are interpreted as octal codes.</span></span>  
  
-   <span data-ttu-id="0b5dd-123">정규식에 정의되지 않은 그룹 번호에 대한 역참조가 포함되어 있으면 구문 분석 오류가 발생하고 정규식 엔진이 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-123">If a regular expression contains a backreference to an undefined group number, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="0b5dd-124">모호성 문제가 발생하는 경우 명확하고 8진수 문자 코드와 혼동되지 않는 `\k<`*name*`>` 표기법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-124">If the ambiguity is a problem, you can use the `\k<`*name*`>` notation, which is unambiguous and cannot be confused with octal character codes.</span></span> <span data-ttu-id="0b5dd-125">마찬가지로, `\xdd` 등의 16진수 코드는 명확하며 역참조와 혼동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-125">Similarly, hexadecimal codes such as `\xdd` are unambiguous and cannot be confused with backreferences.</span></span>  
  
 <span data-ttu-id="0b5dd-126">다음 예제에서는 문자열에서 2배 워드 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-126">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="0b5dd-127">다음과 같은 요소로 구성된 `(\w)\1` 정규식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-127">It defines a regular expression, `(\w)\1`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="0b5dd-128">요소</span><span class="sxs-lookup"><span data-stu-id="0b5dd-128">Element</span></span>|<span data-ttu-id="0b5dd-129">설명</span><span class="sxs-lookup"><span data-stu-id="0b5dd-129">Description</span></span>|  
|-------------|-----------------|  
|`(\w)`|<span data-ttu-id="0b5dd-130">단어 문자를 찾아 첫 번째 캡처링 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-130">Match a word character and assign it to the first capturing group.</span></span>|  
|`\1`|<span data-ttu-id="0b5dd-131">첫 번째 캡처링 그룹의 값과 일치하는 다음 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-131">Match the next character that is the same as the value of the first capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a><span data-ttu-id="0b5dd-132">명명된 역참조</span><span class="sxs-lookup"><span data-stu-id="0b5dd-132">Named Backreferences</span></span>  
 <span data-ttu-id="0b5dd-133">명명된 역참조는 다음 구문을 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-133">A named backreference is defined by using the following syntax:</span></span>  
  
 <span data-ttu-id="0b5dd-134">`\k<` *name* `>`</span><span class="sxs-lookup"><span data-stu-id="0b5dd-134">`\k<` *name* `>`</span></span>  
  
 <span data-ttu-id="0b5dd-135">또는</span><span class="sxs-lookup"><span data-stu-id="0b5dd-135">or:</span></span>  
  
 <span data-ttu-id="0b5dd-136">`\k'` *name* `'`</span><span class="sxs-lookup"><span data-stu-id="0b5dd-136">`\k'` *name* `'`</span></span>  
  
 <span data-ttu-id="0b5dd-137">여기서 *name*은 정규식 패턴에 정의된 캡처링 그룹의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-137">where *name* is the name of a capturing group defined in the regular expression pattern.</span></span> <span data-ttu-id="0b5dd-138">*name*이 정규식 패턴에서 정의되지 않은 경우 구문 분석 오류가 발생하고 정규식 엔진이 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-138">If *name* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="0b5dd-139">다음 예제에서는 문자열에서 2배 워드 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-139">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="0b5dd-140">다음과 같은 요소로 구성된 `(?<char>\w)\k<char>` 정규식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-140">It defines a regular expression, `(?<char>\w)\k<char>`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="0b5dd-141">요소</span><span class="sxs-lookup"><span data-stu-id="0b5dd-141">Element</span></span>|<span data-ttu-id="0b5dd-142">설명</span><span class="sxs-lookup"><span data-stu-id="0b5dd-142">Description</span></span>|  
|-------------|-----------------|  
|`(?<char>\w)`|<span data-ttu-id="0b5dd-143">단어 문자를 찾아 이름이 `char`인 캡처링 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-143">Match a word character and assign it to a capturing group named `char`.</span></span>|  
|`\k<char>`|<span data-ttu-id="0b5dd-144">`char` 캡처링 그룹의 값과 일치하는 다음 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-144">Match the next character that is the same as the value of the `char` capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  

## <a name="named-numeric-backreferences"></a><span data-ttu-id="0b5dd-145">명명된 숫자 역참조</span><span class="sxs-lookup"><span data-stu-id="0b5dd-145">Named numeric backreferences</span></span>

<span data-ttu-id="0b5dd-146">`\k`를 사용하는 명명된 역참조에서 *이름*은 숫자의 문자열 표현일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-146">In a named backreference with `\k`, *name* can also be the string representation of a number.</span></span> <span data-ttu-id="0b5dd-147">예를 들어 다음 예제에서는 `(?<2>\w)\k<2>` 정규식을 사용하여 문자열에서 2배 워드 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-147">For example, the following example uses the regular expression `(?<2>\w)\k<2>` to find doubled word characters in a string.</span></span> <span data-ttu-id="0b5dd-148">이 경우에 예제에서는 명시적으로 "2"라고 명명된 캡처링 그룹을 정의하고 따라서 역참조는 "2"라고 명명됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-148">In this case, the example defines a capturing group that is explicitly named "2", and the backreference is correspondingly named "2".</span></span> 
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  

<span data-ttu-id="0b5dd-149">*이름*이 숫자의 문자열 표현이고 해당 이름을 가 진 캡처링 그룹이 없는 경우 `\k<`*이름*`>`은 역참조 `\` *숫자*와 같습니다. 여기서 *번호*는 캡처의 서수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-149">If *name* is the string representation of a number, and no capturing group has that name, `\k<`*name*`>` is the same as the backreference `\`*number*, where *number* is the ordinal position of the capture.</span></span> <span data-ttu-id="0b5dd-150">다음 예제에는 `char`라는 단일 캡처링 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-150">In the following example, there is a single capturing group named `char`.</span></span> <span data-ttu-id="0b5dd-151">역참조 구문은 `\k<1>`로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-151">The backreference construct refers to it as `\k<1>`.</span></span> <span data-ttu-id="0b5dd-152">예제의 출력이 표시한 대로 `char`가 첫 번째 캡처링 그룹이기 때문에 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>에 대한 호출이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-152">As the output from the example shows, the call to the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> succeeds because `char` is the first capturing group.</span></span>

[!code-csharp[Ordinal.Backreference](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference6.cs)]
[!code-vb[Ordinal.BackReference](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference6.vb)]  

<span data-ttu-id="0b5dd-153">그러나 경우 *이름*이 숫자의 문자열 표현이고 해당 위치에 있는 캡처링 그룹이 명시적으로 숫자 이름을 할당받지 않은 경우 정규식 파서는 서수 위치를 기준으로 캡처링 그룹을 식별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-153">However, if *name* is the string representation of a number and the capturing group in that position has been explicitly assigned a numeric name, the regular expression parser cannot identify the capturing group by its ordinal position.</span></span> <span data-ttu-id="0b5dd-154">대신 <xref:System.ArgumentException>을 throw합니다. 다음 예제의 캡처링 그룹만이 "2"라고 명명됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-154">Instead, it throws an <xref:System.ArgumentException>.The only capturing group in the following example is named "2".</span></span> <span data-ttu-id="0b5dd-155">`\k` 구문을 사용하여 "1"이라는 역참조를 정의하기 때문에 정규식 파서는 첫 번째 캡처링 그룹을 식별할 수 없고 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-155">Because the `\k` construct is used to define a backreference named "1", the regular expression parser is unable to identify the first capturing group and throws an exception.</span></span>

[!code-csharp[Ordinal.Backreference](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference7.cs)]
[!code-vb[Ordinal.BackReference](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference7.vb)]  

## <a name="what-backreferences-match"></a><span data-ttu-id="0b5dd-156">역참조에서 찾는 대상</span><span class="sxs-lookup"><span data-stu-id="0b5dd-156">What Backreferences Match</span></span>  
 <span data-ttu-id="0b5dd-157">역참조는 그룹의 가장 최근 정의(왼쪽에서 오른쪽으로 찾을 경우 가장 왼쪽에 있는 정의)를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-157">A backreference refers to the most recent definition of a group (the definition most immediately to the left, when matching left to right).</span></span> <span data-ttu-id="0b5dd-158">그룹에서 여러 개의 캡처를 만드는 경우 역참조는 가장 최근 캡처를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-158">When a group makes multiple captures, a backreference refers to the most recent capture.</span></span>  
  
 <span data-ttu-id="0b5dd-159">다음 예제에는 이름이 \1인 그룹을 다시 정의하는 정규식 패턴 `(?<1>a)(?<1>\1b)*`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-159">The following example includes a regular expression pattern, `(?<1>a)(?<1>\1b)*`, which redefines the \1 named group.</span></span> <span data-ttu-id="0b5dd-160">다음 표에서는 정규식의 각 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-160">The following table describes each pattern in the regular expression.</span></span>  
  
|<span data-ttu-id="0b5dd-161">무늬</span><span class="sxs-lookup"><span data-stu-id="0b5dd-161">Pattern</span></span>|<span data-ttu-id="0b5dd-162">설명</span><span class="sxs-lookup"><span data-stu-id="0b5dd-162">Description</span></span>|  
|-------------|-----------------|  
|`(?<1>a)`|<span data-ttu-id="0b5dd-163">문자 “a”를 찾은 다음, 이름이 `1`인 캡처링 그룹에 결과를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-163">Match the character "a" and assign the result to the capturing group named `1`.</span></span>|  
|`(?<1>\1b)*`|<span data-ttu-id="0b5dd-164">이름이 `1`과 “b”로 구성된 그룹을 0번 또는 1번 찾은 다음, 이름이 `1`인 캡처링 그룹에 결과를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-164">Match 0 or 1 occurrence of the group named `1` along with a "b", and assign the result to the capturing group named `1`.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 <span data-ttu-id="0b5dd-165">입력 문자열("aababb")과 정규식을 비교할 때 정규식 엔진은 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-165">In comparing the regular expression with the input string ("aababb"), the regular expression engine performs the following operations:</span></span>  
  
1.  <span data-ttu-id="0b5dd-166">문자열의 시작 부분에서 시작하여 `(?<1>a)` 식으로 "a"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-166">It starts at the beginning of the string, and successfully matches "a" with the expression `(?<1>a)`.</span></span> <span data-ttu-id="0b5dd-167">`1` 그룹의 값은 이제 “a”입니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-167">The value of the `1` group is now "a".</span></span>  
  
2.  <span data-ttu-id="0b5dd-168">두 번째 문자로 진행하여 `\1b` 또는 "ab" 식으로 "ab" 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-168">It advances to the second character, and successfully matches the string "ab" with the expression `\1b`, or "ab".</span></span> <span data-ttu-id="0b5dd-169">그런 다음 결과 "ab"를 `\1`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-169">It then assigns the result, "ab" to `\1`.</span></span>  
  
3.  <span data-ttu-id="0b5dd-170">네 번째 문자로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-170">It advances to the fourth character.</span></span> <span data-ttu-id="0b5dd-171">`(?<1>\1b)` 식은 0번 이상 일치할 수 있으므로 `\1b` 식으로 "abb" 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-171">The expression `(?<1>\1b)` is to be matched zero or more times, so it successfully matches the string "abb" with the expression `\1b`.</span></span> <span data-ttu-id="0b5dd-172">결과 "abb"를 `\1`에 다시 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-172">It assigns the result, "abb", back to `\1`.</span></span>  
  
 <span data-ttu-id="0b5dd-173">이 예제에서 `*`는 반복 수량자로, 정규식 엔진이 정의되는 패턴을 찾을 수 없을 때까지 반복해서 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-173">In this example, `*` is a looping quantifier -- it is evaluated repeatedly until the regular expression engine cannot match the pattern it defines.</span></span> <span data-ttu-id="0b5dd-174">반복 수량자는 그룹 정의를 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-174">Looping quantifiers do not clear group definitions.</span></span>  
  
 <span data-ttu-id="0b5dd-175">그룹에서 부분 문자열을 캡처하지 않은 경우 해당 그룹에 대한 역참조가 정의되지 않으며 일치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-175">If a group has not captured any substrings, a backreference to that group is undefined and never matches.</span></span> <span data-ttu-id="0b5dd-176">이 내용은 다음과 같이 정의된 정규식 패턴 `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`를 통해 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-176">This is illustrated by the regular expression pattern `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, which is defined as follows:</span></span>  
  
|<span data-ttu-id="0b5dd-177">무늬</span><span class="sxs-lookup"><span data-stu-id="0b5dd-177">Pattern</span></span>|<span data-ttu-id="0b5dd-178">설명</span><span class="sxs-lookup"><span data-stu-id="0b5dd-178">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="0b5dd-179">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-179">Begin the match on a word boundary.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="0b5dd-180">두 개의 대문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-180">Match two uppercase letters.</span></span> <span data-ttu-id="0b5dd-181">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-181">This is the first capturing group.</span></span>|  
|`(\d{2})?`|<span data-ttu-id="0b5dd-182">두 개의 10진수를 0번 또는 한 번 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-182">Match zero or one occurrence of two decimal digits.</span></span> <span data-ttu-id="0b5dd-183">이 그룹은 두 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-183">This is the second capturing group.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="0b5dd-184">두 개의 대문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-184">Match two uppercase letters.</span></span> <span data-ttu-id="0b5dd-185">이 그룹은 세 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-185">This is the third capturing group.</span></span>|  
|`\b`|<span data-ttu-id="0b5dd-186">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-186">End the match on a word boundary.</span></span>|  
  
 <span data-ttu-id="0b5dd-187">두 번째 캡처링 그룹에서 정의된 두 개의 10진수가 없는 경우에도 입력 문자열이 이 정규식과 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-187">An input string can match this regular expression even if the two decimal digits that are defined by the second capturing group are not present.</span></span> <span data-ttu-id="0b5dd-188">다음 예제에서는 일치가 성공해도 성공적인 두 캡처링 그룹 사이에 빈 캡처링 그룹이 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b5dd-188">The following example shows that even though the match is successful, an empty capturing group is found between two successful capturing groups.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="0b5dd-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b5dd-189">See Also</span></span>  
 [<span data-ttu-id="0b5dd-190">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="0b5dd-190">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
