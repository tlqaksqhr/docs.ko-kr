---
title: "정규식의 기타 구문"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b33d196a7af9bc5a1f81c1624bbd98fea074319
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a><span data-ttu-id="12f97-102">정규식의 기타 구문</span><span class="sxs-lookup"><span data-stu-id="12f97-102">Miscellaneous Constructs in Regular Expressions</span></span>
<span data-ttu-id="12f97-103">.NET의 정규식에는 세 가지 기타 언어 구문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-103">Regular expressions in .NET include three miscellaneous language constructs.</span></span> <span data-ttu-id="12f97-104">한 구문에서는 정규식 패턴 중간에 특정 일치 옵션을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-104">One lets you enable or disable particular matching options in the middle of a regular expression pattern.</span></span> <span data-ttu-id="12f97-105">나머지 두 구문에서는 정규식에 주석을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-105">The remaining two let you include comments in a regular expression.</span></span>  
  
## <a name="inline-options"></a><span data-ttu-id="12f97-106">인라인 옵션</span><span class="sxs-lookup"><span data-stu-id="12f97-106">Inline Options</span></span>  
 <span data-ttu-id="12f97-107">구문을 사용하여 정규식의 일부에 대해 특정 패턴 일치 옵션을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-107">You can set or disable specific pattern matching options for part of a regular expression by using the syntax</span></span>  
  
```  
(?imnsx-imnsx)  
```  
  
 <span data-ttu-id="12f97-108">물음표 뒤에 사용할 옵션을 나열하고, 빼기 기호 뒤에 사용하지 않을 옵션을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-108">You list the options you want to enable after the question mark, and the options you want to disable after the minus sign.</span></span> <span data-ttu-id="12f97-109">다음 표는 각 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-109">The following table describes each option.</span></span> <span data-ttu-id="12f97-110">각 옵션에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12f97-110">For more information about each option, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
|<span data-ttu-id="12f97-111">옵션</span><span class="sxs-lookup"><span data-stu-id="12f97-111">Option</span></span>|<span data-ttu-id="12f97-112">설명</span><span class="sxs-lookup"><span data-stu-id="12f97-112">Description</span></span>|  
|------------|-----------------|  
|`i`|<span data-ttu-id="12f97-113">대/소문자를 구분하지 않는 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-113">Case-insensitive matching.</span></span>|  
|`m`|<span data-ttu-id="12f97-114">여러 줄 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-114">Multiline mode.</span></span>|  
|`n`|<span data-ttu-id="12f97-115">명시적 캡처만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-115">Explicit captures only.</span></span> <span data-ttu-id="12f97-116">괄호는 캡처링 그룹으로 동작하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-116">(Parentheses do not act as capturing groups.)</span></span>|  
|`s`|<span data-ttu-id="12f97-117">한 줄 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-117">Single-line mode.</span></span>|  
|`x`|<span data-ttu-id="12f97-118">이스케이프되지 않은 공백을 무시하고 x-모드 주석을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-118">Ignore unescaped white space, and allow x-mode comments.</span></span>|  
  
 <span data-ttu-id="12f97-119">모든 변경 하 여 정의 된 정규식 옵션에는 `(?imnsx-imnsx)` 포함 그룹의 끝까지 계속 적용 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-119">Any change in regular expression options defined by the `(?imnsx-imnsx)` construct remains in effect until the end of the enclosing group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12f97-120">`(?imnsx-imnsx:` *subexpression* `)` 그룹화 구문은 하위 식에 대 한 동일한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-120">The `(?imnsx-imnsx:`*subexpression*`)` grouping construct provides identical functionality for a subexpression.</span></span> <span data-ttu-id="12f97-121">자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12f97-121">For more information, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="12f97-122">다음 예제에서는 `i`, `n`, 및 `x` 옵션 대/소문자 구분 및 명시적 캡처를 사용 하 고 정규식 중에 정규식 패턴에서 공백은 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-122">The following example uses the `i`, `n`, and `x` options to enable case insensitivity and explicit captures, and to ignore white space in the regular expression pattern in the middle of a regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 <span data-ttu-id="12f97-123">이 예제에서는 두 개의 정규식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-123">The example defines two regular expressions.</span></span> <span data-ttu-id="12f97-124">첫 번째 `\b(D\w+)\s(d\w+)\b` 정규식은 대문자 "D"와 소문자 "d"로 시작하는 두 개의 연속 단어와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-124">The first, `\b(D\w+)\s(d\w+)\b`, matches two consecutive words that begin with an uppercase "D" and a lowercase "d".</span></span> <span data-ttu-id="12f97-125">두 번째 `\b(D\w+)(?ixn) \s (d\w+) \b` 정규식은 다음 표에 설명된 대로 인라인 옵션을 사용하여 이 패턴을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-125">The second regular expression, `\b(D\w+)(?ixn) \s (d\w+) \b`, uses inline options to modify this pattern, as described in the following table.</span></span> <span data-ttu-id="12f97-126">결과를 비교하면 `(?ixn)` 구문의 효과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-126">A comparison of the results confirms the effect of the `(?ixn)` construct.</span></span>  
  
|<span data-ttu-id="12f97-127">패턴</span><span class="sxs-lookup"><span data-stu-id="12f97-127">Pattern</span></span>|<span data-ttu-id="12f97-128">설명</span><span class="sxs-lookup"><span data-stu-id="12f97-128">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="12f97-129">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-129">Start at a word boundary.</span></span>|  
|`(D\w+)`|<span data-ttu-id="12f97-130">대문자 "D"와 하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-130">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="12f97-131">첫 번째 캡처 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-131">This is the first capture group.</span></span>|  
|`(?ixn)`|<span data-ttu-id="12f97-132">이때부터 대/소문자를 구분하지 않고 비교하고, 명시적 캡처만 수행되며, 정규식 패턴의 공백이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-132">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`\s`|<span data-ttu-id="12f97-133">공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-133">Match a white-space character.</span></span>|  
|`(d\w+)`|<span data-ttu-id="12f97-134">대문자 또는 소문자 "d"와 하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-134">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="12f97-135">때문에이 그룹은 캡처되지 않음는 `n` (명시적 캡처) 옵션을 사용할 수...</span><span class="sxs-lookup"><span data-stu-id="12f97-135">This group is not captured because the `n` (explicit capture) option was enabled..</span></span>|  
|`\b`|<span data-ttu-id="12f97-136">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-136">Match a word boundary.</span></span>|  
  
## <a name="inline-comment"></a><span data-ttu-id="12f97-137">인라인 주석</span><span class="sxs-lookup"><span data-stu-id="12f97-137">Inline Comment</span></span>  
 <span data-ttu-id="12f97-138">`(?#` *주석* `)` 구문을 사용 하는 정규식에서 인라인 주석을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-138">The `(?#` *comment*`)` construct lets you include an inline comment in a regular expression.</span></span> <span data-ttu-id="12f97-139">정규식 엔진은 주석에서 반환 되는 문자열에 포함 되어 있지만 일부 패턴 일치에서 주석으로 처리를 사용 하지 않습니다는 <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="12f97-139">The regular expression engine does not use any part of the comment in pattern matching, although the comment is included in the string that is returned by the <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="12f97-140">주석이 첫 번째 닫는 괄호 문자에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-140">The comment ends at the first closing parenthesis.</span></span>  
  
 <span data-ttu-id="12f97-141">다음 예제에서는 이전 섹션의 예제에서 사용된 첫 번째 정규식 패턴을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-141">The following example repeats the first regular expression pattern from the example in the previous section.</span></span> <span data-ttu-id="12f97-142">정규식에 두 개의 인라인 주석을 추가하여 비교가 대/소문자를 구분하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-142">It adds two inline comments to the regular expression to indicate whether the comparison is case-sensitive.</span></span> <span data-ttu-id="12f97-143">정규식 패턴 `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-143">The regular expression pattern, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, is defined as follows.</span></span>  
  
|<span data-ttu-id="12f97-144">패턴</span><span class="sxs-lookup"><span data-stu-id="12f97-144">Pattern</span></span>|<span data-ttu-id="12f97-145">설명</span><span class="sxs-lookup"><span data-stu-id="12f97-145">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="12f97-146">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-146">Start at a word boundary.</span></span>|  
|`(?# case-sensitive comparison)`|<span data-ttu-id="12f97-147">주석입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-147">A comment.</span></span> <span data-ttu-id="12f97-148">패턴 일치 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-148">It does not affect pattern-matching behavior.</span></span>|  
|`(D\w+)`|<span data-ttu-id="12f97-149">대문자 "D"와 하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-149">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="12f97-150">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-150">This is the first capturing group.</span></span>|  
|`\s`|<span data-ttu-id="12f97-151">공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-151">Match a white-space character.</span></span>|  
|`(?ixn)`|<span data-ttu-id="12f97-152">이때부터 대/소문자를 구분하지 않고 비교하고, 명시적 캡처만 수행되며, 정규식 패턴의 공백이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-152">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`(?#case-insensitive comparison)`|<span data-ttu-id="12f97-153">주석입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-153">A comment.</span></span> <span data-ttu-id="12f97-154">패턴 일치 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-154">It does not affect pattern-matching behavior.</span></span>|  
|`(d\w+)`|<span data-ttu-id="12f97-155">대문자 또는 소문자 "d"와 하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-155">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="12f97-156">두 번째 캡처 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-156">This is the second capture group.</span></span>|  
|`\b`|<span data-ttu-id="12f97-157">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-157">Match a word boundary.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a><span data-ttu-id="12f97-158">줄의 끝 주석</span><span class="sxs-lookup"><span data-stu-id="12f97-158">End-of-Line Comment</span></span>  
 <span data-ttu-id="12f97-159">숫자 기호 (`#`) 정규식 패턴의 끝에 이스케이프 되지 않은 # 문자부터 시작 하는 줄의 끝까지 계속 됩니다는 x-모드 주석 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-159">A number sign (`#`)marks an x-mode comment, which starts at the unescaped # character at the end of the regular expression pattern and continues until the end of the line.</span></span> <span data-ttu-id="12f97-160">설정 하거나이 구조를 사용 하는 `x` (인라인 옵션)을 통해 다시 실행 하거나 제공는 <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> 값을 `option` 인스턴스화할 때 매개 변수는 <xref:System.Text.RegularExpressions.Regex> 개체 또는 정적 호출 <xref:System.Text.RegularExpressions.Regex> 메서드.</span><span class="sxs-lookup"><span data-stu-id="12f97-160">To use this construct, you must either enable the `x` option (through inline options) or supply the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> value to the `option` parameter when instantiating the <xref:System.Text.RegularExpressions.Regex> object or calling a static <xref:System.Text.RegularExpressions.Regex> method.</span></span>  
  
 <span data-ttu-id="12f97-161">다음 예제에서는 줄의 끝 주석 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-161">The following example illustrates the end-of-line comment construct.</span></span> <span data-ttu-id="12f97-162">문자열이 하나 이상의 형식 항목을 포함하는 복합 형식 문자열인지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-162">It determines whether a string is a composite format string that includes at least one format item.</span></span> <span data-ttu-id="12f97-163">다음 표에서는 정규식 패턴의 구문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-163">The following table describes the constructs in the regular expression pattern:</span></span>  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|<span data-ttu-id="12f97-164">패턴</span><span class="sxs-lookup"><span data-stu-id="12f97-164">Pattern</span></span>|<span data-ttu-id="12f97-165">설명</span><span class="sxs-lookup"><span data-stu-id="12f97-165">Description</span></span>|  
|-------------|-----------------|  
|`\{`|<span data-ttu-id="12f97-166">여는 중괄호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-166">Match an opening brace.</span></span>|  
|`\d+`|<span data-ttu-id="12f97-167">하나 이상의 10진수 숫자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-167">Match one or more decimal digits.</span></span>|  
|`(,-*\d+)*`|<span data-ttu-id="12f97-168">선택적 빼기 기호, 하나 이상의 10진수 앞에 나오는 쉼표를 0번 또는 한 번 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-168">Match zero or one occurrence of a comma, followed by an optional minus sign, followed by one or more decimal digits.</span></span>|  
|`(\:\w{1,4}?)*`|<span data-ttu-id="12f97-169">1-4개(최대한 적은 개수)의 공백 문자 앞에 나오는 콜론을 0번 또는 한 번 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-169">Match zero or one occurrence of a colon, followed by one to four, but as few as possible, white-space characters.</span></span>|  
|`(?#case insensitive comparison)`|<span data-ttu-id="12f97-170">인라인 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-170">An inline comment.</span></span> <span data-ttu-id="12f97-171">패턴 일치 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-171">It has no effect on pattern-matching behavior.</span></span>|  
|`\}`|<span data-ttu-id="12f97-172">닫는 중괄호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-172">Match a closing brace.</span></span>|  
|`(?x)`|<span data-ttu-id="12f97-173">줄의 끝 주석이 인식되도록 패턴 공백 무시 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-173">Enable the ignore pattern white-space option so that the end-of-line comment will be recognized.</span></span>|  
|`# Looks for a composite format item.`|<span data-ttu-id="12f97-174">줄의 끝 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-174">An end-of-line comment.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 <span data-ttu-id="12f97-175">유의 제공 하는 대신는 `(?x)` 생성는 정규식에서 주석 수 인식할 수도 호출 하 여는 <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> 메서드에 전달 하는 <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="12f97-175">Note that, instead of providing the `(?x)` construct in the regular expression, the comment could also have been recognized by calling the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method and passing it the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> enumeration value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f97-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12f97-176">See Also</span></span>  
 [<span data-ttu-id="12f97-177">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="12f97-177">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
