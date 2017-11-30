---
title: "정규식의 수량자"
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
- regular expressions, quantifiers
- metacharacters, quantifiers
- minimal matching quantifiers
- quantifiers in regular expressions
- .NET Framework regular expressions, quantifiers
- quantifiers
- lazy quantifiers
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab06aa0c331c8cbd4c8986cced29334046f30264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="quantifiers-in-regular-expressions"></a><span data-ttu-id="d7412-102">정규식의 수량자</span><span class="sxs-lookup"><span data-stu-id="d7412-102">Quantifiers in Regular Expressions</span></span>
<span data-ttu-id="d7412-103">수량자는 찾을 일치 항목의 입력에 있어야 하는 문자, 그룹 또는 문자 클래스의 인스턴스 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-103">Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.</span></span>  <span data-ttu-id="d7412-104">다음 테이블에서는 .NET에서 지원하는 수량자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-104">The following table lists the quantifiers supported by .NET.</span></span>  
  
|<span data-ttu-id="d7412-105">탐욕적 수량자</span><span class="sxs-lookup"><span data-stu-id="d7412-105">Greedy quantifier</span></span>|<span data-ttu-id="d7412-106">게으른 수량자</span><span class="sxs-lookup"><span data-stu-id="d7412-106">Lazy quantifier</span></span>|<span data-ttu-id="d7412-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-107">Description</span></span>|  
|-----------------------|---------------------|-----------------|  
|`*`|`*?`|<span data-ttu-id="d7412-108">0번 이상 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-108">Match zero or more times.</span></span>|  
|`+`|`+?`|<span data-ttu-id="d7412-109">1번 이상 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-109">Match one or more times.</span></span>|  
|`?`|`??`|<span data-ttu-id="d7412-110">0번 또는 1번 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-110">Match zero or one time.</span></span>|  
|<span data-ttu-id="d7412-111">`{` *n* `}`</span><span class="sxs-lookup"><span data-stu-id="d7412-111">`{` *n* `}`</span></span>|<span data-ttu-id="d7412-112">`{` *n* `}?`</span><span class="sxs-lookup"><span data-stu-id="d7412-112">`{` *n* `}?`</span></span>|<span data-ttu-id="d7412-113">정확히 일치  *n*  시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-113">Match exactly *n* times.</span></span>|  
|<span data-ttu-id="d7412-114">`{` *n* `,}`</span><span class="sxs-lookup"><span data-stu-id="d7412-114">`{` *n* `,}`</span></span>|<span data-ttu-id="d7412-115">`{` *n* `,}?`</span><span class="sxs-lookup"><span data-stu-id="d7412-115">`{` *n* `,}?`</span></span>|<span data-ttu-id="d7412-116">이상과 일치  *n*  시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-116">Match at least *n* times.</span></span>|  
|<span data-ttu-id="d7412-117">`{` *n* `,` *분* `}`</span><span class="sxs-lookup"><span data-stu-id="d7412-117">`{` *n* `,` *m* `}`</span></span>|<span data-ttu-id="d7412-118">`{` *n* `,` *분* `}?`</span><span class="sxs-lookup"><span data-stu-id="d7412-118">`{` *n* `,` *m* `}?`</span></span>|<span data-ttu-id="d7412-119">일치  *n*  를 *m* 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-119">Match from *n* to *m* times.</span></span>|  
  
 <span data-ttu-id="d7412-120">수량 `n` 및 `m` 은 정수 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-120">The quantities `n` and `m` are integer constants.</span></span> <span data-ttu-id="d7412-121">일반적으로 수량자는 탐욕적입니다. 그러면 최대한의 정규식 엔진이 특정 패턴과 일치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-121">Ordinarily, quantifiers are greedy; they cause the regular expression engine to match as many occurrences of particular patterns as possible.</span></span> <span data-ttu-id="d7412-122">`?` 문자를 수량자에 추가하면 게으른 수량자로 만들 수 있습니다. 그러면 최소한의 정규식 엔진이 일치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-122">Appending the `?` character to a quantifier makes it lazy; it causes the regular expression engine to match as few occurrences as possible.</span></span> <span data-ttu-id="d7412-123">탐욕적 수량자와 게으른 수량자 간의 차이에 대한 설명은 이 항목의 뒷부분에 나오는 [탐욕적 및 게으른 수량자](#Greedy) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7412-123">For a complete description of the difference between greedy and lazy quantifiers, see the section [Greedy and Lazy Quantifiers](#Greedy) later in this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7412-124">예를 들어, 정규식 패턴 `(a*)*`과 같이 수량자가 중첩되면 정규식 엔진이 입력 문자열에 있는 문자 수의 지 수 함수로 수행해야 하는 비교의 수를 증가시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-124">Nesting quantifiers (for example, as the regular expression pattern `(a*)*` does) can increase the number of comparisons that the regular expression engine must perform, as an exponential function of the number of characters in the input string.</span></span> <span data-ttu-id="d7412-125">이 문제 및 해결 방법에 대 한 자세한 내용은 참조 [역 추적](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-125">For more information about this behavior and its workarounds, see [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).</span></span>  
  
## <a name="regular-expression-quantifiers"></a><span data-ttu-id="d7412-126">정규식 수량자</span><span class="sxs-lookup"><span data-stu-id="d7412-126">Regular Expression Quantifiers</span></span>  
 <span data-ttu-id="d7412-127">다음 섹션에는 .NET의 정규식에서 지원하는 수량자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-127">The following sections list the quantifiers supported by .NET regular expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7412-128">경우는 *, +,?, {, 및} 문자가 있는 정규식 패턴에서 정규식 엔진에 포함 된 경우가 아니면이 수량자 또는 수량자 구조의 일부로 해석 한 [문자 클래스](../../../docs/standard/base-types/character-classes-in-regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-128">If the *, +, ?, {, and } characters are encountered in a regular expression pattern, the regular expression engine interprets them as quantifiers or part of quantifier constructs unless they are included in a [character class](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).</span></span> <span data-ttu-id="d7412-129">이를 문자 클래스 외부의 리터럴 문자로 해석하려면 앞에 백슬래시를 추가하여 이스케이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-129">To interpret these as literal characters outside a character class, you must escape them by preceding them with a backslash.</span></span> <span data-ttu-id="d7412-130">예를 들어 문자열 `\*` 는 리터럴 별표로 정규식 패턴은 해석 ("\*") 문자.</span><span class="sxs-lookup"><span data-stu-id="d7412-130">For example, the string `\*` in a regular expression pattern is interpreted as a literal asterisk ("\*") character.</span></span>  
  
### <a name="match-zero-or-more-times-"></a><span data-ttu-id="d7412-131">0번 이상 일치: *</span><span class="sxs-lookup"><span data-stu-id="d7412-131">Match Zero or More Times: *</span></span>  
 <span data-ttu-id="d7412-132">`*` 수량자는 이전 요소를 0번 이상 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-132">The `*` quantifier matches the preceding element zero or more times.</span></span> <span data-ttu-id="d7412-133">동일는 `{0,}` 수량자입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-133">It is equivalent to the `{0,}` quantifier.</span></span> <span data-ttu-id="d7412-134">`*`지연 된 진수 표현은 greedy 수량자 `*?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-134">`*` is a greedy quantifier whose lazy equivalent is `*?`.</span></span>  
  
 <span data-ttu-id="d7412-135">다음 예제에서는 이 정규식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-135">The following example illustrates this regular expression.</span></span> <span data-ttu-id="d7412-136">입력 문자열에서 9자리 숫자 중에 5개는 패턴과 일치하고 4개(`95`, `929`, `9129` 및 `9919`)는 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-136">Of the nine digits in the input string, five match the pattern and four (`95`, `929`, `9129`, and `9919`) do not.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 <span data-ttu-id="d7412-137">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-137">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-138">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-138">Pattern</span></span>|<span data-ttu-id="d7412-139">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-139">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-140">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-140">Start at a word boundary.</span></span>|  
|`91*`|<span data-ttu-id="d7412-141">뒤에 0개 이상의 "1" 문자가 있는 "9"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-141">Match a "9" followed by zero or more "1" characters.</span></span>|  
|`9*`|<span data-ttu-id="d7412-142">0개 이상의 "9" 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-142">Match zero or more "9" characters.</span></span>|  
|`\b`|<span data-ttu-id="d7412-143">단어 경계를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-143">End at a word boundary.</span></span>|  
  
### <a name="match-one-or-more-times-"></a><span data-ttu-id="d7412-144">1번 이상 일치: +</span><span class="sxs-lookup"><span data-stu-id="d7412-144">Match One or More Times: +</span></span>  
 <span data-ttu-id="d7412-145">`+` 수량자는 이전 요소를 한 번 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-145">The `+` quantifier matches the preceding element one or more times.</span></span> <span data-ttu-id="d7412-146">동일 `{1,}`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-146">It is equivalent to `{1,}`.</span></span> <span data-ttu-id="d7412-147">`+`지연 된 진수 표현은 greedy 수량자 `+?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-147">`+` is a greedy quantifier whose lazy equivalent is `+?`.</span></span>  
  
 <span data-ttu-id="d7412-148">예를 들어, 정규식 `\ban+\w*?\b`은 `n` 문자의 인스턴스가 하나 이상 뒤에 오는 `a` 문자로 시작하는 전체 단어를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-148">For example, the regular expression `\ban+\w*?\b` tries to match entire words that begin with the letter `a` followed by one or more instances of the letter `n`.</span></span> <span data-ttu-id="d7412-149">다음 예제에서는 이 정규식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-149">The following example illustrates this regular expression.</span></span> <span data-ttu-id="d7412-150">정규식은 `an`, `annual`, `announcement` 및 `antique` 단어를 찾며 `autumn` 및 `all` 단어를 찾는 데 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-150">The regular expression matches the words `an`, `annual`, `announcement`, and `antique`, and correctly fails to match `autumn` and `all`.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 <span data-ttu-id="d7412-151">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-151">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-152">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-152">Pattern</span></span>|<span data-ttu-id="d7412-153">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-153">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-154">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-154">Start at a word boundary.</span></span>|  
|`an+`|<span data-ttu-id="d7412-155">뒤에 하나 이상의 "n" 문자가 있는 "a"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-155">Match an "a" followed by one or more "n" characters.</span></span>|  
|`\w*?`|<span data-ttu-id="d7412-156">단어 문자와 0번 이상의 일치하지만 가능한 적은 수로 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-156">Match a word character zero or more times, but as few times as possible.</span></span>|  
|`\b`|<span data-ttu-id="d7412-157">단어 경계를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-157">End at a word boundary.</span></span>|  
  
### <a name="match-zero-or-one-time-"></a><span data-ttu-id="d7412-158">0번 또는 1번 일치: ?</span><span class="sxs-lookup"><span data-stu-id="d7412-158">Match Zero or One Time: ?</span></span>  
 <span data-ttu-id="d7412-159">`?` 수량자는 이전 요소를 0 개 또는 1 개 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-159">The `?` quantifier matches the preceding element zero or one time.</span></span> <span data-ttu-id="d7412-160">동일 `{0,1}`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-160">It is equivalent to `{0,1}`.</span></span> <span data-ttu-id="d7412-161">`?`지연 된 진수 표현은 greedy 수량자 `??`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-161">`?` is a greedy quantifier whose lazy equivalent is `??`.</span></span>  
  
 <span data-ttu-id="d7412-162">예를 들어, 정규식 `\ban?\b`은 `n` 문자의 인스턴스가 0개 또는 1개 뒤에 오는 `a` 문자로 시작하는 전체 단어를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-162">For example, the regular expression `\ban?\b` tries to match entire words that begin with the letter `a` followed by zero or one instances of the letter `n`.</span></span> <span data-ttu-id="d7412-163">즉, 단어 `a` 및 `an`를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-163">In other words, it tries to match the words `a` and `an`.</span></span> <span data-ttu-id="d7412-164">다음 예제에서는 이 정규식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-164">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 <span data-ttu-id="d7412-165">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-165">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-166">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-166">Pattern</span></span>|<span data-ttu-id="d7412-167">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-167">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-168">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-168">Start at a word boundary.</span></span>|  
|`an?`|<span data-ttu-id="d7412-169">뒤에 0개 또는 1개의 "n" 문자가 있는 "a"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-169">Match an "a" followed by zero or one "n" character.</span></span>|  
|`\b`|<span data-ttu-id="d7412-170">단어 경계를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-170">End at a word boundary.</span></span>|  
  
### <a name="match-exactly-n-times-n"></a><span data-ttu-id="d7412-171">정확히 n번 일치: {n}</span><span class="sxs-lookup"><span data-stu-id="d7412-171">Match Exactly n Times: {n}</span></span>  
 <span data-ttu-id="d7412-172">`{`  *n*  `}` 수량자는 이전 요소를 정확 하 게 일치  *n*  시간, where  *n* 는 모든 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-172">The `{`*n*`}` quantifier matches the preceding element exactly *n* times, where *n* is any integer.</span></span> <span data-ttu-id="d7412-173">`{`*n*`}`지연 된 진수 표현은 greedy 수량자 `{`  *n*  `}?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-173">`{`*n*`}` is a greedy quantifier whose lazy equivalent is `{`*n*`}?`.</span></span>  
  
 <span data-ttu-id="d7412-174">예를 들어, 정규식 `\b\d+\,\d{3}\b`는 뒤에 하나 이상의 10진수 숫자, 세 개의 10진수 숫자와 단어 경계가 있는 단어 경계를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-174">For example, the regular expression `\b\d+\,\d{3}\b` tries to match a word boundary followed by one or more decimal digits followed by three decimal digits followed by a word boundary.</span></span> <span data-ttu-id="d7412-175">다음 예제에서는 이 정규식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-175">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 <span data-ttu-id="d7412-176">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-176">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-177">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-177">Pattern</span></span>|<span data-ttu-id="d7412-178">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-178">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-179">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-179">Start at a word boundary.</span></span>|  
|`\d+`|<span data-ttu-id="d7412-180">하나 이상의 10진수 숫자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-180">Match one or more decimal digits.</span></span>|  
|`\,`|<span data-ttu-id="d7412-181">쉼표 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-181">Match a comma character.</span></span>|  
|`\d{3}`|<span data-ttu-id="d7412-182">세 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-182">Match three decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="d7412-183">단어 경계를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-183">End at a word boundary.</span></span>|  
  
### <a name="match-at-least-n-times-n"></a><span data-ttu-id="d7412-184">적어도 n번 일치: {n,}</span><span class="sxs-lookup"><span data-stu-id="d7412-184">Match at Least n Times: {n,}</span></span>  
 <span data-ttu-id="d7412-185">`{`  *n*  `,}` 수량자는 이전 요소 이상  *n*  시간, where  *n* 는 모든 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-185">The `{`*n*`,}` quantifier matches the preceding element at least *n* times, where *n* is any integer.</span></span> <span data-ttu-id="d7412-186">`{`*n*`,}`지연 된 진수 표현은 greedy 수량자 `{`  *n*  `}?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-186">`{`*n*`,}` is a greedy quantifier whose lazy equivalent is `{`*n*`}?`.</span></span>  
  
 <span data-ttu-id="d7412-187">예를 들어, 정규식 `\b\d{2,}\b\D+`는 뒤에 적어도 두 개의 숫자, 단어 경계와 숫자가 아닌 문자가 있는 단어 경계를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-187">For example, the regular expression `\b\d{2,}\b\D+` tries to match a word boundary followed by at least two digits followed by a word boundary and a non-digit character.</span></span> <span data-ttu-id="d7412-188">다음 예제에서는 이 정규식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-188">The following example illustrates this regular expression.</span></span> <span data-ttu-id="d7412-189">정규식과 라는 구가 일치 하지 `"7 days"` 하나의 10 진수 숫자를 포함 하지만 구과 일치 하기 때문에 `"10 weeks and 300 years"`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-189">The regular expression fails to match the phrase `"7 days"` because it contains just one decimal digit, but it successfully matches the phrases `"10 weeks and 300 years"`.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 <span data-ttu-id="d7412-190">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-190">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-191">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-191">Pattern</span></span>|<span data-ttu-id="d7412-192">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-192">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-193">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-193">Start at a word boundary.</span></span>|  
|`\d{2,}`|<span data-ttu-id="d7412-194">적어도 두 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-194">Match at least two decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="d7412-195">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-195">Match a word boundary.</span></span>|  
|`\D+`|<span data-ttu-id="d7412-196">적어도 하나의 10진수가 아닌 수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-196">Match at least one non-decimal digit.</span></span>|  
  
### <a name="match-between-n-and-m-times-nm"></a><span data-ttu-id="d7412-197">n번에서 m번 사이에 일치: {n, m}</span><span class="sxs-lookup"><span data-stu-id="d7412-197">Match Between n and m Times: {n,m}</span></span>  
 <span data-ttu-id="d7412-198">`{`  *n*  `,` *m* `}` 수량자는 이전 요소 이상  *n*  시간, 하지만 개 이하의 *m* 시간, where  *n*  및 *m* 는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-198">The `{`*n*`,`*m*`}` quantifier matches the preceding element at least *n* times, but no more than *m* times, where *n* and *m* are integers.</span></span> <span data-ttu-id="d7412-199">`{`*n*`,`*m* `}` 지연 표현은 해당 greedy 수량자 `{`  *n*  `,` *m*`}?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-199">`{`*n*`,`*m*`}` is a greedy quantifier whose lazy equivalent is `{`*n*`,`*m*`}?`.</span></span>  
  
 <span data-ttu-id="d7412-200">다음 예제에서 정규식 `(00\s){2,4}`은 뒤에 공백이 있는 두 개의 숫자 0이 2회에서 4회 사이에 발생하는 경우를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-200">In the following example, the regular expression `(00\s){2,4}` tries to match between two and four occurrences of two zero digits followed by a space.</span></span> <span data-ttu-id="d7412-201">입력 문자열의 마지막 부분에는 이 패턴이 5번이나 포함됩니다(최대 4번 아님).</span><span class="sxs-lookup"><span data-stu-id="d7412-201">Note that the final portion of the input string includes this pattern five times rather than the maximum of four.</span></span> <span data-ttu-id="d7412-202">그러나 공백 및 0의 다섯 번째 쌍까지의 하위 문자열의 처음 부분만이 정규식 패턴과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-202">However, only the initial portion of this substring (up to the space and the fifth pair of zeros) matches the regular expression pattern.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### <a name="match-zero-or-more-times-lazy-match-"></a><span data-ttu-id="d7412-203">0번 이상 일치(게으른 일치 항목): *?</span><span class="sxs-lookup"><span data-stu-id="d7412-203">Match Zero or More Times (Lazy Match): *?</span></span>  
 <span data-ttu-id="d7412-204">`*?` 수량자는 이전 요소를 0 개 이상 가능한 한 적은 개수로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-204">The `*?` quantifier matches the preceding element zero or more times, but as few times as possible.</span></span> <span data-ttu-id="d7412-205">그는 greedy 수량자 지연에 관련 `*`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-205">It is the lazy counterpart of the greedy quantifier `*`.</span></span>  
  
 <span data-ttu-id="d7412-206">다음 예제에서 정규식 `\b\w*?oo\w*?\b`은 문자열 `oo`이 포함된 모든 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-206">In the following example, the regular expression `\b\w*?oo\w*?\b` matches all words that contain the string `oo`.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 <span data-ttu-id="d7412-207">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-207">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-208">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-208">Pattern</span></span>|<span data-ttu-id="d7412-209">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-209">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-210">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-210">Start at a word boundary.</span></span>|  
|`\w*?`|<span data-ttu-id="d7412-211">0개 이상의 단어 문자(가능한 한 적은 문자)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-211">Match zero or more word characters, but as few characters as possible.</span></span>|  
|`oo`|<span data-ttu-id="d7412-212">"oo" 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-212">Match the string "oo".</span></span>|  
|`\w*?`|<span data-ttu-id="d7412-213">0개 이상의 단어 문자(가능한 한 적은 문자)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-213">Match zero or more word characters, but as few characters as possible.</span></span>|  
|`\b`|<span data-ttu-id="d7412-214">단어 경계를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-214">End on a word boundary.</span></span>|  
  
### <a name="match-one-or-more-times-lazy-match-"></a><span data-ttu-id="d7412-215">0번 이상 일치(게으른 일치 항목): +?</span><span class="sxs-lookup"><span data-stu-id="d7412-215">Match One or More Times (Lazy Match): +?</span></span>  
 <span data-ttu-id="d7412-216">`+?` 수량자는 이전 요소를 하나 이상 가능한 한 적은 개수로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-216">The `+?` quantifier matches the preceding element one or more times, but as few times as possible.</span></span> <span data-ttu-id="d7412-217">그는 greedy 수량자 지연에 관련 `+`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-217">It is the lazy counterpart of the greedy quantifier `+`.</span></span>  
  
 <span data-ttu-id="d7412-218">예를 들어, 정규식 `\b\w+?\b`은 단어 경계로 구분된 1개 이상의 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-218">For example, the regular expression `\b\w+?\b` matches one or more characters separated by word boundaries.</span></span> <span data-ttu-id="d7412-219">다음 예제에서는 이 정규식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-219">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### <a name="match-zero-or-one-time-lazy-match-"></a><span data-ttu-id="d7412-220">0번 또는 1번 일치(게으른 일치): ??</span><span class="sxs-lookup"><span data-stu-id="d7412-220">Match Zero or One Time (Lazy Match): ??</span></span>  
 <span data-ttu-id="d7412-221">`??` 수량자는 이전 요소를 0 개 또는 1 개, 가능한 한 적은 개수로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-221">The `??` quantifier matches the preceding element zero or one time, but as few times as possible.</span></span> <span data-ttu-id="d7412-222">그는 greedy 수량자 지연에 관련 `?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-222">It is the lazy counterpart of the greedy quantifier `?`.</span></span>  
  
 <span data-ttu-id="d7412-223">예를 들어, 정규식 `^\s*(System.)??Console.Write(Line)??\(??`은 "Console.Write" 또는 "Console.WriteLine" 문자열을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-223">For example, the regular expression `^\s*(System.)??Console.Write(Line)??\(??` attempts to match the strings "Console.Write" or "Console.WriteLine".</span></span> <span data-ttu-id="d7412-224">문자열은 "Console" 앞에 "System."을 포함할 수도 있고</span><span class="sxs-lookup"><span data-stu-id="d7412-224">The string can also include "System."</span></span> <span data-ttu-id="d7412-225">문자열 뒤에 여는 괄호가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-225">before "Console", and it can be followed by an opening parenthesis.</span></span> <span data-ttu-id="d7412-226">문자열 앞에는 공백이 있을 수 있지만 줄의 시작 부분에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-226">The string must be at the beginning of a line, although it can be preceded by white space.</span></span> <span data-ttu-id="d7412-227">다음 예제에서는 이 정규식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-227">The following example illustrates this regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 <span data-ttu-id="d7412-228">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-228">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-229">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-229">Pattern</span></span>|<span data-ttu-id="d7412-230">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-230">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="d7412-231">입력 스트림의 시작 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-231">Match the start of the input stream.</span></span>|  
|`\s*`|<span data-ttu-id="d7412-232">0개 이상의 공백 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-232">Match zero or more white-space characters.</span></span>|  
|`(System.)??`|<span data-ttu-id="d7412-233">"System."이라는 0개 또는 1개의 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-233">Match zero or one occurrence of the string "System.".</span></span>|  
|`Console.Write`|<span data-ttu-id="d7412-234">"Console.Write"라는 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-234">Match the string "Console.Write".</span></span>|  
|`(Line)??`|<span data-ttu-id="d7412-235">"Line"이라는 0개 또는 1개의 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-235">Match zero or one occurrence of the string "Line".</span></span>|  
|`\(??`|<span data-ttu-id="d7412-236">0개 또는 1개의 여는 괄호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-236">Match zero or one occurrence of the opening parenthesis.</span></span>|  
  
### <a name="match-exactly-n-times-lazy-match-n"></a><span data-ttu-id="d7412-237">정확히 n번 일치(게으른 일치): {n}?</span><span class="sxs-lookup"><span data-stu-id="d7412-237">Match Exactly n Times (Lazy Match): {n}?</span></span>  
 <span data-ttu-id="d7412-238">`{`  *n*  `}?` 수량자는 이전 요소를 정확 하 게 일치 `n` 시간, where  *n*  는 모든 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-238">The `{`*n*`}?` quantifier matches the preceding element exactly `n` times, where *n* is any integer.</span></span> <span data-ttu-id="d7412-239">그는 greedy 수량자 지연에 관련 `{`  *n*  `}+`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-239">It is the lazy counterpart of the greedy quantifier `{`*n*`}+`.</span></span>  
  
 <span data-ttu-id="d7412-240">다음 예제에서 정규식 `\b(\w{3,}?\.){2}?\w{3,}?\b`은 웹 사이트 주소를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-240">In the following example, the regular expression `\b(\w{3,}?\.){2}?\w{3,}?\b` is used to identify a Web site address.</span></span> <span data-ttu-id="d7412-241">"www.microsoft.com" 및 "msdn.microsoft.com"과 일치하지만 "mywebsite" 또는 "mycompany.com"과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-241">Note that it matches "www.microsoft.com" and "msdn.microsoft.com", but does not match "mywebsite" or "mycompany.com".</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 <span data-ttu-id="d7412-242">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-242">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-243">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-243">Pattern</span></span>|<span data-ttu-id="d7412-244">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-244">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-245">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-245">Start at a word boundary.</span></span>|  
|`(\w{3,}?\.)`|<span data-ttu-id="d7412-246">뒤에 점 또는 마침표 문자가 있는 가능한 적은 수의 최소한 3개의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-246">Match at least 3 word characters, but as few characters as possible, followed by a dot or period character.</span></span> <span data-ttu-id="d7412-247">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-247">This is the first capturing group.</span></span>|  
|`(\w{3,}?\.){2}?`|<span data-ttu-id="d7412-248">첫 번째 그룹의 패턴과 두 번 일치하지만 가능한 적은 수로 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-248">Match the pattern in the first group two times, but as few times as possible.</span></span>|  
|`\b`|<span data-ttu-id="d7412-249">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-249">End the match on a word boundary.</span></span>|  
  
### <a name="match-at-least-n-times-lazy-match-n"></a><span data-ttu-id="d7412-250">적어도 n번 일치(게으른 일치): {n,}?</span><span class="sxs-lookup"><span data-stu-id="d7412-250">Match at Least n Times (Lazy Match): {n,}?</span></span>  
 <span data-ttu-id="d7412-251">`{`  *n*  `,}?` 수량자는 이전 요소 이상 `n` 시간, where  *n*  은 임의의 정수를 적은 횟수 가능한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-251">The `{`*n*`,}?` quantifier matches the preceding element at least `n` times, where *n* is any integer, but as few times as possible.</span></span> <span data-ttu-id="d7412-252">그는 greedy 수량자 지연에 관련 `{`  *n*  `,}`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-252">It is the lazy counterpart of the greedy quantifier `{`*n*`,}`.</span></span>  
  
 <span data-ttu-id="d7412-253">예를 참조는 `{`  *n*  `}?` 수량자에 대 한 예시는 이전 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-253">See the example for the `{`*n*`}?` quantifier in the previous section for an illustration.</span></span> <span data-ttu-id="d7412-254">이 예에서는 정규식을 사용 하는 `{`  *n*  `,}` 수량자 뒤에 마침표 3 개 이상의 문자가 있는 문자열을 검색 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-254">The regular expression in that example uses the `{`*n*`,}` quantifier to match a string that has at least three characters followed by a period.</span></span>  
  
### <a name="match-between-n-and-m-times-lazy-match-nm"></a><span data-ttu-id="d7412-255">n번에서 m번 사이에 일치(게으른 일치): {n,m}?</span><span class="sxs-lookup"><span data-stu-id="d7412-255">Match Between n and m Times (Lazy Match): {n,m}?</span></span>  
 <span data-ttu-id="d7412-256">`{`  *n*  `,` *m* `}?` 수량자는 이전 요소 `n` 및 `m` 시간, where  *n*  및 *m* 가능한 한 적은 개수로 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-256">The `{`*n*`,`*m*`}?` quantifier matches the preceding element between `n` and `m` times, where *n* and *m* are integers, but as few times as possible.</span></span> <span data-ttu-id="d7412-257">그는 greedy 수량자 지연에 관련 `{`  *n*  `,` *m*`}`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-257">It is the lazy counterpart of the greedy quantifier `{`*n*`,`*m*`}`.</span></span>  
  
 <span data-ttu-id="d7412-258">다음 예제에서 정규식 `\b[A-Z](\w*\s+){1,10}?[.!?]`은 하나에서 열 개 단어 사이를 포함하는 문장을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-258">In the following example, the regular expression `\b[A-Z](\w*\s+){1,10}?[.!?]` matches sentences that contain between one and ten words.</span></span> <span data-ttu-id="d7412-259">18개의 단어가 포함된 한 문장을 제외하고 입력 문자열에 있는 모든 문장을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-259">It matches all the sentences in the input string except for one sentence that contains 18 words.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 <span data-ttu-id="d7412-260">이 정규식 패턴은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-260">The regular expression pattern is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-261">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-261">Pattern</span></span>|<span data-ttu-id="d7412-262">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-262">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d7412-263">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-263">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="d7412-264">A-Z의 대문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-264">Match an uppercase character from A to Z.</span></span>|  
|`(\w*\s+)`|<span data-ttu-id="d7412-265">뒤에 1개 이상의 공백 문자가 있는 0개 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-265">Match zero or more word characters, followed by one or more white-space characters.</span></span> <span data-ttu-id="d7412-266">이 그룹은 첫 번째 캡처 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-266">This is the first capture group.</span></span>|  
|`{1,10}?`|<span data-ttu-id="d7412-267">이전 패턴과 1번에서 10번 사이에 일치하지만 가능한 적은 수로 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-267">Match the previous pattern between 1 and 10 times, but as few times as possible.</span></span>|  
|`[.!?]`|<span data-ttu-id="d7412-268">문장 부호 문자 ".", "!" 또는 "?" 중 하나를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-268">Match any one of the punctuation characters ".", "!", or "?".</span></span>|  
  
<a name="Greedy"></a>   
## <a name="greedy-and-lazy-quantifiers"></a><span data-ttu-id="d7412-269">탐욕적 및 게으른 수량자</span><span class="sxs-lookup"><span data-stu-id="d7412-269">Greedy and Lazy Quantifiers</span></span>  
 <span data-ttu-id="d7412-270">여러 수량자에는 두 가지 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-270">A number of the quantifiers have two versions:</span></span>  
  
-   <span data-ttu-id="d7412-271">탐욕적 버전</span><span class="sxs-lookup"><span data-stu-id="d7412-271">A greedy version.</span></span>  
  
     <span data-ttu-id="d7412-272">탐욕적 수량자는 요소를 최대한 많이 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-272">A greedy quantifier tries to match an element as many times as possible.</span></span>  
  
-   <span data-ttu-id="d7412-273">식별 (또는 지연) 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-273">A non-greedy (or lazy) version.</span></span>  
  
     <span data-ttu-id="d7412-274">탐욕적이 아닌 수량자는 요소를 최대한 적게 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-274">A non-greedy quantifier tries to match an element as few times as possible.</span></span> <span data-ttu-id="d7412-275">추가 하기만 하면 lazy 수량자도 greedy 수량자를 바꿀 수 있습니다는 `?`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-275">You can turn a greedy quantifier into a lazy quantifier by simply adding a `?`.</span></span>  
  
 <span data-ttu-id="d7412-276">신용 카드 번호와 같은 숫자 문자열에서 마지막 4자리를 추출하기 위한 간단한 정규식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-276">Consider a simple regular expression that is intended to extract the last four digits from a string of numbers such as a credit card number.</span></span> <span data-ttu-id="d7412-277">사용 하는 정규식의 버전은 `*` greedy 수량자는 `\b.*([0-9]{4})\b`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-277">The version of the regular expression that uses the `*` greedy quantifier is `\b.*([0-9]{4})\b`.</span></span> <span data-ttu-id="d7412-278">그러나 문자열이 두 개의 숫자를 포함하는 경우 다음 예제와 같이 정규식은 두 번째 숫자의 마지막 4자리가 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-278">However, if a string contains two numbers, this regular expression matches the last four digits of the second number only, as the following example shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 <span data-ttu-id="d7412-279">정규식과 때문에 첫 번째 숫자 일치 하지는 `*` 수량자는 전체 문자열에서 최대한 많이 이전 요소를 일치 시 키 려 고 문자열의 끝에서 찾기를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-279">The regular expression fails to match the first number because the `*` quantifier tries to match the previous element as many times as possible in the entire string, and so it finds its match at the end of the string.</span></span>  
  
 <span data-ttu-id="d7412-280">이러한 동작이 발생하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-280">This is not the desired behavior.</span></span> <span data-ttu-id="d7412-281">대신 사용할 수는 `*?`lazy 수량자 다음 예제와 같이 두 숫자 모두에서 숫자를 추출 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-281">Instead, you can use the `*?`lazy quantifier to extract digits from both numbers, as the following example shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 <span data-ttu-id="d7412-282">대부분의 경우 탐욕적 및 게으른 수량자를 포함하는 정규식은 동일한 일치 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-282">In most cases, regular expressions with greedy and lazy quantifiers return the same matches.</span></span> <span data-ttu-id="d7412-283">와일드 카드 사용 될 때 가장 일반적으로 서로 다른 결과 반환 (`.`) 메타 문자가 있는 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-283">They most commonly return different results when they are used with the wildcard (`.`) metacharacter, which matches any character.</span></span>  
  
## <a name="quantifiers-and-empty-matches"></a><span data-ttu-id="d7412-284">수량자 및 빈 일치 항목</span><span class="sxs-lookup"><span data-stu-id="d7412-284">Quantifiers and Empty Matches</span></span>  
 <span data-ttu-id="d7412-285">수량자 `*`, `+`, 및 `{`  *n*  `,` *m* `}` 지연 대응 하지는 빈 후 반복 일치 하는 최소한의 캡처를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-285">The quantifiers `*`, `+`, and `{`*n*`,`*m*`}` and their lazy counterparts never repeat after an empty match when the minimum number of captures has been found.</span></span> <span data-ttu-id="d7412-286">가능한 그룹 캡처의 최대 수가 무한 또는 거의 무한인 경우 이 규칙은 수량자가 빈 하위 식을 찾기 위해 무한 루프를 입력하지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-286">This rule prevents quantifiers from entering infinite loops on empty subexpression matches when the maximum number of possible group captures is infinite or near infinite.</span></span>  
  
 <span data-ttu-id="d7412-287">다음 코드에 대 한 호출의 결과 표시 하는 예를 들어는 <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> 메서드는 정규식 패턴을 가진 `(a?)*`, 0 개 또는 1 "a" 문자 0 회 이상 찾는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-287">For example, the following code shows the result of a call to the <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> method with the regular expression pattern `(a?)*`, which matches zero or one "a" character zero or more times.</span></span> <span data-ttu-id="d7412-288">단일 캡처링 그룹 결과 캡처할 "a"를 참고 뿐만 아니라 <xref:System.String.Empty?displayProperty=nameWithType>는 없지만 첫 번째 빈 일치 인해 수량자가 반복을 멈추기 때문에 두 번째 빈 일치 하지 않는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-288">Note that the single capturing group captures each "a" as well as <xref:System.String.Empty?displayProperty=nameWithType>, but that there is no second empty match, because the first empty match causes the quantifier to stop repeating.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 <span data-ttu-id="d7412-289">캡처의 최소 및 최대 수를 정의하는 캡처링 그룹과 캡처의 고정 수를 정의하는 그룹 사이의 실질적인 차이를 확인하려면 정규식 패턴 `(a\1|(?(1)\1)){0,2}` 및 `(a\1|(?(1)\1)){2}`를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-289">To see the practical difference between a capturing group that defines a minimum and a maximum number of captures and one that defines a fixed number of captures, consider the regular expression patterns `(a\1|(?(1)\1)){0,2}` and `(a\1|(?(1)\1)){2}`.</span></span> <span data-ttu-id="d7412-290">두 정규식은 단일 캡처링 그룹으로 구성되며 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-290">Both regular expressions consist of a single capturing group, which is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="d7412-291">패턴</span><span class="sxs-lookup"><span data-stu-id="d7412-291">Pattern</span></span>|<span data-ttu-id="d7412-292">설명</span><span class="sxs-lookup"><span data-stu-id="d7412-292">Description</span></span>|  
|-------------|-----------------|  
|`(a\1`|<span data-ttu-id="d7412-293">첫 번째 캡처된 그룹의 값과 함께 "a"를 찾거나…</span><span class="sxs-lookup"><span data-stu-id="d7412-293">Either match "a" along with the value of the first captured group …</span></span>|  
|`&#124;(?(1)`|<span data-ttu-id="d7412-294">…</span><span class="sxs-lookup"><span data-stu-id="d7412-294">…</span></span> <span data-ttu-id="d7412-295">또는 첫 번째 캡처된 그룹이 정의되어 있는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-295">or test whether the first captured group has been defined.</span></span> <span data-ttu-id="d7412-296">(유의 `(?(1)` 구문의 캡처링 그룹을 정의 하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="d7412-296">(Note that the `(?(1)` construct does not define a capturing group.)</span></span>|  
|`\1))`|<span data-ttu-id="d7412-297">첫 번째 캡처된 그룹이 있는 경우 해당 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-297">If the first captured group exists, match its value.</span></span> <span data-ttu-id="d7412-298">해당 그룹이 그룹 일치 합니다 <xref:System.String.Empty?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-298">If the group does not exist, the group will match <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|  
  
 <span data-ttu-id="d7412-299">첫 번째 정규식이 0번과 두 번 사이에 이 패턴을 찾으려 합니다. 두 번째 정규식은 정확히 두 번입니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-299">The first regular expression tries to match this pattern between zero and two times; the second, exactly two times.</span></span> <span data-ttu-id="d7412-300">첫 번째 패턴의 첫 번째 캡처와 캡처의 최소 수에 도달 하기 때문에 <xref:System.String.Empty?displayProperty=nameWithType>를 일치 시 키 려 반복 하지 않습니다 `a\1`; `{0,2}` 수량자 마지막 반복에서 빈만 일치 항목을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-300">Because the first pattern reaches its minimum number of captures with its first capture of <xref:System.String.Empty?displayProperty=nameWithType>, it never repeats to try to match `a\1`; the `{0,2}` quantifier allows only empty matches in the last iteration.</span></span> <span data-ttu-id="d7412-301">두 번째 정규식이 `a\1`을 두 번째로 평가하기 때문에 "a"를 찾는 반면 반복의 최소수인 2는 빈 일치 항목 뒤에 엔진이 반복되도록 강제합니다.</span><span class="sxs-lookup"><span data-stu-id="d7412-301">In contrast, the second regular expression does match "a" because it evaluates `a\1` a second time; the minimum number of iterations, 2, forces the engine to repeat after an empty match.</span></span>  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d7412-302">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7412-302">See Also</span></span>  
 [<span data-ttu-id="d7412-303">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="d7412-303">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 [<span data-ttu-id="d7412-304">역추적</span><span class="sxs-lookup"><span data-stu-id="d7412-304">Backtracking</span></span>](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
