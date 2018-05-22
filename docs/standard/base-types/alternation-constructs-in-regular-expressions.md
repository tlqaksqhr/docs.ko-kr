---
title: 정규식의 교체 구문
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- either/or matching
- alternative matching patterns
- regular expressions, alternation constructs
- alternation constructs
- optional matching patterns
- constructs, alternation
- .NET Framework regular expressions, alternation constructs
ms.assetid: 071e22e9-fbb0-4ecf-add1-8d2424f9f2d1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 956d16b47fb31549de8f25c513d73c43ab41c267
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="alternation-constructs-in-regular-expressions"></a><span data-ttu-id="56850-102">정규식의 교체 구문</span><span class="sxs-lookup"><span data-stu-id="56850-102">Alternation Constructs in Regular Expressions</span></span>
<a name="top"></a> <span data-ttu-id="56850-103">교체 구문은 either/or 또는 조건부 일치를 허용하도록 정규식을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-103">Alternation constructs modify a regular expression to enable either/or or conditional matching.</span></span> <span data-ttu-id="56850-104">.NET에서는 다음 세 가지 교체 구문을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-104">.NET supports three alternation constructs:</span></span>  
  
-   [<span data-ttu-id="56850-105">&#124;를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="56850-105">Pattern matching with &#124;</span></span>](#Either_Or)  
  
-   [<span data-ttu-id="56850-106">(?(expression)yes&#124;no)를 사용한 조건부 일치</span><span class="sxs-lookup"><span data-stu-id="56850-106">Conditional matching with (?(expression)yes&#124;no)</span></span>](#Conditional_Expr)  
  
-   [<span data-ttu-id="56850-107">유효한 캡처 그룹을 기준으로 조건부 일치</span><span class="sxs-lookup"><span data-stu-id="56850-107">Conditional matching based on a valid captured group</span></span>](#Conditional_Group)  
  
<a name="Either_Or"></a>   
## <a name="pattern-matching-with-124"></a><span data-ttu-id="56850-108">&#124;를 사용한 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="56850-108">Pattern Matching with &#124;</span></span>  
 <span data-ttu-id="56850-109">세로 막대(`|`) 문자를 사용하여 일련의 패턴 중 하나를 찾을 수 있습니다. 여기서 `|` 문자는 각 패턴을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-109">You can use the vertical bar (`|`) character to match any one of a series of patterns, where the `|` character separates each pattern.</span></span>  
  
 <span data-ttu-id="56850-110">긍정 문자 클래스처럼 `|` 문자를 사용하여 여러 단일 문자의 하나를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-110">Like the positive character class, the `|` character can be used to match any one of a number of single characters.</span></span> <span data-ttu-id="56850-111">다음 예제에서는 긍정 문자 클래스 및 either/or 패턴 일치를 둘다 `|` 문자와 함께 사용하여 문자열에서 단어 "gray" 또는 "grey" 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-111">The following example uses both a positive character class and either/or pattern matching with the `|` character to locate occurrences of the words "gray" or "grey" in a string.</span></span> <span data-ttu-id="56850-112">이 경우 `|` 문자는 더 자세한 정규식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-112">In this case, the `|` character produces a regular expression that is more verbose.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation1.cs#1)]
 [!code-vb[RegularExpressions.Language.Alternation#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation1.vb#1)]  
  
 <span data-ttu-id="56850-113">`|` 문자를 사용하는 정규식인 `\bgr(a|e)y\b`는 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="56850-113">The regular expression that uses the `|` character, `\bgr(a|e)y\b`, is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="56850-114">무늬</span><span class="sxs-lookup"><span data-stu-id="56850-114">Pattern</span></span>|<span data-ttu-id="56850-115">설명</span><span class="sxs-lookup"><span data-stu-id="56850-115">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="56850-116">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-116">Start at a word boundary.</span></span>|  
|`gr`|<span data-ttu-id="56850-117">문자 "gr"을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-117">Match the characters "gr".</span></span>|  
|<code>(a&#124;e)</code>|<span data-ttu-id="56850-118">"a" 또는 "e"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-118">Match either an "a" or an "e".</span></span>|  
|`y\b`|<span data-ttu-id="56850-119">단어 경계에서 "y"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-119">Match a "y" on a word boundary.</span></span>|  
  
 <span data-ttu-id="56850-120">`|` 문자를 사용하여 문자 리터럴과 정규식 언어 요소의 조합을 포함할 수 있는 여러 문자나 하위 식을 통해 either/or 일치 항목을 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-120">The `|` character can also be used to perform an either/or match with multiple characters or subexpressions, which can include any combination of character literals and regular expression language elements.</span></span> <span data-ttu-id="56850-121">문자 클래스는 이 기능을 제공하지 않습니다. 다음 예제에서는 `|` 문자를 사용하여 미국 SSN(사회 보장 번호)(*ddd*-*dd*-*dddd* 형식의 9자리 숫자) 또는 미국 EIN(고용주 식별 번호)(*dd*-*ddddddd* 형식의 9자리 숫자)을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-121">(The character class does not provide this functionality.) The following example uses the `|` character to extract either a U.S. Social Security Number (SSN), which is a 9-digit number with the format *ddd*-*dd*-*dddd*, or a U.S. Employer Identification Number (EIN), which is a 9-digit number with the format *dd*-*ddddddd*.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation2.cs#2)]
 [!code-vb[RegularExpressions.Language.Alternation#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation2.vb#2)]  
  
 <span data-ttu-id="56850-122">정규식 `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` 는 다음 테이블과 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="56850-122">The regular expression `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="56850-123">무늬</span><span class="sxs-lookup"><span data-stu-id="56850-123">Pattern</span></span>|<span data-ttu-id="56850-124">설명</span><span class="sxs-lookup"><span data-stu-id="56850-124">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="56850-125">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-125">Start at a word boundary.</span></span>|  
|<code>(\d{2}-\d{7}&#124;\d{3}-\d{2}-\d{4})</code>|<span data-ttu-id="56850-126">10진수 2개, 하이픈, 10진수 7개 순의 일치 항목이나 10진수 3개, 하이픈, 10진수 2개, 또 다른 하이픈, 10진수 4개 순의 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-126">Match either of the following: two decimal digits followed by a hyphen followed by seven decimal digits; or three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\d`|<span data-ttu-id="56850-127">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="56850-127">End the match at a word boundary.</span></span>|  
  
 [<span data-ttu-id="56850-128">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="56850-128">Back to top</span></span>](#top)  
  
<a name="Conditional_Expr"></a>   
## <a name="conditional-matching-with-an-expression"></a><span data-ttu-id="56850-129">식을 사용한 조건부 일치</span><span class="sxs-lookup"><span data-stu-id="56850-129">Conditional Matching with an Expression</span></span>  
 <span data-ttu-id="56850-130">이 언어 요소는 초기 패턴을 찾을지 여부에 따라 두 패턴의 하나를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-130">This language element attempts to match one of two patterns depending on whether it can match an initial pattern.</span></span> <span data-ttu-id="56850-131">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-131">Its syntax is:</span></span>  
  
 <span data-ttu-id="56850-132">`(?(` *expression* `)` *yes* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="56850-132">`(?(` *expression* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="56850-133">여기서 *expression* 은 일치 항목을 찾을 초기 패턴이고, *yes* 는 *expression* 과 일치할 경우 일치 항목을 찾을 패턴이고, *no* 는 *expression* 이 일치하지 않을 경우 일치 항목을 찾을 선택적 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="56850-133">where *expression* is the initial pattern to match, *yes* is the pattern to match if *expression* is matched, and *no* is the optional pattern to match if *expression* is not matched.</span></span> <span data-ttu-id="56850-134">정규식 엔진은 *expression* 을 너비가 0인 어설션으로 처리합니다. 즉, 정규식 엔진은 *expression*을 계산한 후 입력 스트림에서 앞으로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-134">The regular expression engine treats *expression* as a zero-width assertion; that is, the regular expression engine does not advance in the input stream after it evaluates *expression*.</span></span> <span data-ttu-id="56850-135">따라서 이 구문은 다음 구문과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-135">Therefore, this construct is equivalent to the following:</span></span>  
  
 <span data-ttu-id="56850-136">`(?(?=` *식* `)` *예* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="56850-136">`(?(?=` *expression* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="56850-137">여기서 `(?=`*expression*`)`은 너비가 0인 어설션 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="56850-137">where `(?=`*expression*`)` is a zero-width assertion construct.</span></span> <span data-ttu-id="56850-138">자세한 내용은 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)을 참조하세요. 정규식 엔진이 *expression*을 앵커(너비가 0인 어설션)로 해석하기 때문에 *expression*은 너비가 0인 어설션(자세한 내용은 [앵커](../../../docs/standard/base-types/anchors-in-regular-expressions.md) 참조) 또는 *yes*에도 포함되는 하위 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-138">(For more information, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).) Because the regular expression engine interprets *expression* as an anchor (a zero-width assertion), *expression* must either be a zero-width assertion (for more information, see [Anchors](../../../docs/standard/base-types/anchors-in-regular-expressions.md)) or a subexpression that is also contained in *yes*.</span></span> <span data-ttu-id="56850-139">그렇지 않으면 *yes* 패턴을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-139">Otherwise, the *yes* pattern cannot be matched.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56850-140">*expression*이 이름이나 숫자가 지정된 캡처 그룹인 경우, 교체 구문은 캡처 테스트로 해석됩니다. 자세한 내용은 다음 섹션인 [유효한 캡처 그룹을 기준으로 조건부 일치](#Conditional_Group)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56850-140">If *expression*is a named or numbered capturing group, the alternation construct is interpreted as a capture test; for more information, see the next section, [Conditional Matching Based on a Valid Capture Group](#Conditional_Group).</span></span> <span data-ttu-id="56850-141">즉, 정규식 엔진은 캡처된 하위 문자열을 찾으려고 하지 않지만, 대신 그룹의 존재 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-141">In other words, the regular expression engine does not attempt to match the captured substring, but instead tests for the presence or absence of the group.</span></span>  
  
 <span data-ttu-id="56850-142">다음 예제는 [&#124;를 사용한 Either/Or 패턴 일치](#Either_Or) 섹션에 나타나는 예제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="56850-142">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="56850-143">조건부 일치를 사용하여 단어 경계 뒤의 처음 문자 3개가 숫자 2개, 하이픈 순의 문자열인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-143">It uses conditional matching to determine whether the first three characters after a word boundary are two digits followed by a hyphen.</span></span> <span data-ttu-id="56850-144">해당 문자열이면 미국 EIN(고용주 식별 번호)을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-144">If they are, it attempts to match a U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="56850-145">그러지 않으면 미국 SSN(사회 보장 번호)을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-145">If not, it attempts to match a U.S. Social Security Number (SSN).</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation3.cs#3)]
 [!code-vb[RegularExpressions.Language.Alternation#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation3.vb#3)]  
  
 <span data-ttu-id="56850-146">정규식 패턴 `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` 는 다음 테이블과 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="56850-146">The regular expression pattern `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="56850-147">패턴</span><span class="sxs-lookup"><span data-stu-id="56850-147">Pattern</span></span>|<span data-ttu-id="56850-148">설명</span><span class="sxs-lookup"><span data-stu-id="56850-148">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="56850-149">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-149">Start at a word boundary.</span></span>|  
|`(?(\d{2}-)`|<span data-ttu-id="56850-150">다음 문자 3개가 숫자 2개, 하이픈 순으로 구성되는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-150">Determine whether the next three characters consist of two digits followed by a hyphen.</span></span>|  
|`\d{2}-\d{7}`|<span data-ttu-id="56850-151">이전 패턴이 일치하면 숫자 2개, 하이픈, 숫자 7개 순의 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-151">If the previous pattern matches, match two digits followed by a hyphen followed by seven digits.</span></span>|  
|`\d{3}-\d{2}-\d{4}`|<span data-ttu-id="56850-152">이전 패턴이 일치하지 않으면 10진수 3개, 하이픈, 10진수 2개, 또 다른 하이픈, 10진수 4개 순의 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-152">If the previous pattern does not match, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="56850-153">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-153">Match a word boundary.</span></span>|  
  
 [<span data-ttu-id="56850-154">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="56850-154">Back to top</span></span>](#top)  
  
<a name="Conditional_Group"></a>   
## <a name="conditional-matching-based-on-a-valid-captured-group"></a><span data-ttu-id="56850-155">유효한 캡처 그룹을 기준으로 조건부 일치</span><span class="sxs-lookup"><span data-stu-id="56850-155">Conditional Matching Based on a Valid Captured Group</span></span>  
 <span data-ttu-id="56850-156">이 언어 요소는 지정된 캡처링 그룹에 일치시켰는지 여부에 따라 두 패턴 중 하나에 일치시키려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-156">This language element attempts to match one of two patterns depending on whether it has matched a specified capturing group.</span></span> <span data-ttu-id="56850-157">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-157">Its syntax is:</span></span>  
  
 <span data-ttu-id="56850-158">`(?(` *name* `)` *예* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="56850-158">`(?(` *name* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="56850-159">또는</span><span class="sxs-lookup"><span data-stu-id="56850-159">or</span></span>  
  
 <span data-ttu-id="56850-160">`(?(` *number* `)` *예* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="56850-160">`(?(` *number* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="56850-161">여기서 *name* 은 이름이고, *number* 는 캡처 그룹 수이고, *yes* 는 *name* 또는 *number* 에 일치 항목이 있을 경우 일치 항목을 찾을 식이고, *no* 는 일치 항목이 없을 경우 일치 항목을 찾을 선택적 식입니다.</span><span class="sxs-lookup"><span data-stu-id="56850-161">where *name* is the name and *number* is the number of a capturing group, *yes* is the expression to match if *name* or *number* has a match, and *no* is the optional expression to match if it does not.</span></span>  
  
 <span data-ttu-id="56850-162">*name* 이 정규식 패턴에서 사용되는 캡처 그룹의 이름에 해당하지 않을 경우에는 교체 구문이 앞 섹션에서 설명한 대로 식 테스트로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="56850-162">If *name* does not correspond to the name of a capturing group that is used in the regular expression pattern, the alternation construct is interpreted as an expression test, as explained in the previous section.</span></span> <span data-ttu-id="56850-163">일반적으로 이는 *expression* 이 `false`로 계산됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-163">Typically, this means that *expression* evaluates to `false`.</span></span> <span data-ttu-id="56850-164">*number* 가 정규식 패턴에 사용되는 번호 매기기 캡처 그룹에 해당하지 않는 경우 정규식 엔진이 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-164">If *number* does not correspond to a numbered capturing group that is used in the regular expression pattern, the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="56850-165">다음 예제는 [&#124;를 사용한 Either/Or 패턴 일치](#Either_Or) 섹션에 나타나는 예제의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="56850-165">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="56850-166">숫자 2개, 하이픈 순으로 구성된 `n2` 라는 캡처 그룹을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-166">It uses a capturing group named `n2` that consists of two digits followed by a hyphen.</span></span> <span data-ttu-id="56850-167">교체 구문은 입력 문자열에서 이 캡처 그룹이 일치했는지를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-167">The alternation construct tests whether this capturing group has been matched in the input string.</span></span> <span data-ttu-id="56850-168">일치한다면 교체 구문은 9자리 미국 EIN(고용주 식별 번호)을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-168">If it has, the alternation construct attempts to match the last seven digits of a nine-digit U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="56850-169">일치하지 않는다면 9자리 미국 SSN(사회 보장 번호)을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-169">If it has not, it attempts to match a nine-digit U.S. Social Security Number (SSN).</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation4.cs#4)]
 [!code-vb[RegularExpressions.Language.Alternation#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation4.vb#4)]  
  
 <span data-ttu-id="56850-170">정규식 패턴 `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b`는 다음 테이블과 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="56850-170">The regular expression pattern `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="56850-171">패턴</span><span class="sxs-lookup"><span data-stu-id="56850-171">Pattern</span></span>|<span data-ttu-id="56850-172">설명</span><span class="sxs-lookup"><span data-stu-id="56850-172">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="56850-173">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-173">Start at a word boundary.</span></span>|  
|`(?<n2>\d{2}-)?`|<span data-ttu-id="56850-174">숫자 2개, 하이픈 순의 일치 항목 0개 또는 1개를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-174">Match zero or one occurrence of two digits followed by a hyphen.</span></span> <span data-ttu-id="56850-175">이 캡처링 그룹의 이름을 `n2`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-175">Name this capturing group `n2`.</span></span>|  
|`(?(n2)`|<span data-ttu-id="56850-176">`n2` 가 입력 문자열에서 일치하는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="56850-176">Test whether `n2` was matched in the input string.</span></span>|  
|`)\d{7}`|<span data-ttu-id="56850-177">`n2` 가 일치하는 경우 일곱 개의 10진수를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="56850-177">If `n2` was matched, match seven decimal digits.</span></span>|  
|<code>&#124;\d{3}-\d{2}-\d{4}</code>|<span data-ttu-id="56850-178">`n2` 가 일치하지 않는 경우 세 10진수, 하이픈, 두 10진수, 다른 하이픈 및 네 10진수를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="56850-178">If `n2` was not matched, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="56850-179">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="56850-179">Match a word boundary.</span></span>|  
  
 <span data-ttu-id="56850-180">다음 예제에서는 명명된 그룹 대신 번호가 있는 그룹을 사용하는 이 예제의 변형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56850-180">A variation of this example that uses a numbered group instead of a named group is shown in the following example.</span></span> <span data-ttu-id="56850-181">정규식 패턴은 `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`입니다.</span><span class="sxs-lookup"><span data-stu-id="56850-181">Its regular expression pattern is `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation5.cs#5)]
 [!code-vb[RegularExpressions.Language.Alternation#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="56850-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56850-182">See Also</span></span>  
 [<span data-ttu-id="56850-183">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="56850-183">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
