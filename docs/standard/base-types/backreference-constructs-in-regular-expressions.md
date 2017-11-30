---
title: "정규식의 역참조 구문"
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
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a884e70f542c2ed7ff63e39cb7eadedf0ef7b4d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a><span data-ttu-id="ec22a-102">정규식의 역참조 구문</span><span class="sxs-lookup"><span data-stu-id="ec22a-102">Backreference Constructs in Regular Expressions</span></span>
<span data-ttu-id="ec22a-103">역참조는 문자열 내에서 반복된 문자 또는 부분 문자열을 식별하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-103">Backreferences provide a convenient way to identify a repeated character or substring within a string.</span></span> <span data-ttu-id="ec22a-104">예를 들어 입력 문자열에 임의의 부분 문자열이 여러 번 포함되어 있으면 첫 번째 발생을 캡처링 그룹과 일치시킨 다음 역참조를 사용하여 부분 문자열의 후속 발생을 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-104">For example, if the input string contains multiple occurrences of an arbitrary substring, you can match the first occurrence with a capturing group, and then use a backreference to match subsequent occurrences of the substring.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec22a-105">대체 문자열에서 명명된 캡처링 그룹과 번호가 매겨진 캡처링 그룹을 참조하기 위해 별도의 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-105">A separate syntax is used to refer to named and numbered capturing groups in replacement strings.</span></span> <span data-ttu-id="ec22a-106">자세한 내용은 [Substitutions](substitutions-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec22a-106">For more information, see [Substitutions](substitutions-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="ec22a-107">.NET에서는 번호가 매겨진 캡처링 그룹과 명명된 캡처링 그룹을 참조하기 위해 별도의 언어 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-107">.NET defines separate language elements to refer to numbered and named capturing groups.</span></span> <span data-ttu-id="ec22a-108">캡처링 그룹에 대 한 자세한 내용은 참조 [그룹화 구문](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-108">For more information about capturing groups, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
## <a name="numbered-backreferences"></a><span data-ttu-id="ec22a-109">번호가 매겨진 역참조</span><span class="sxs-lookup"><span data-stu-id="ec22a-109">Numbered Backreferences</span></span>  
 <span data-ttu-id="ec22a-110">번호가 매겨진 역참조에는 다음 구문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-110">A numbered backreference uses the following syntax:</span></span>  
  
 <span data-ttu-id="ec22a-111">`\` *number*</span><span class="sxs-lookup"><span data-stu-id="ec22a-111">`\` *number*</span></span>  
  
 <span data-ttu-id="ec22a-112">여기서 *number*는 정규식에서 캡처링 그룹의 서수 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-112">where *number* is the ordinal position of the capturing group in the regular expression.</span></span> <span data-ttu-id="ec22a-113">예를 들어 `\4`는 네 번째 캡처링 그룹의 내용을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-113">For example, `\4` matches the contents of the fourth capturing group.</span></span> <span data-ttu-id="ec22a-114">경우 *번호* 은 정규식 패턴에 정의 되어 있지는 구문 분석 오류가 발생 하 고 정규식 엔진은 throw는 <xref:System.ArgumentException>합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-114">If *number* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="ec22a-115">예를 들어 `\b(\w+)\s\1` 정규식은 `(\w+)`가 식의 첫 번째이자 유일한 캡처링 그룹이기 때문에 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-115">For example, the regular expression `\b(\w+)\s\1` is valid, because `(\w+)` is the first and only capturing group in the expression.</span></span> <span data-ttu-id="ec22a-116">반면에 `\b(\w+)\s\2`는 `\2`로 번호가 매겨진 캡처링 그룹이 없기 때문에 유효하지 않으며 인수 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-116">On the other hand, `\b(\w+)\s\2` is invalid and throws an argument exception, because there is no capturing group numbered `\2`.</span></span>  
  
 <span data-ttu-id="ec22a-117">8 진수 이스케이프 코드 사이의 모호성 확인 (같은 `\16`) 및 `\` *번호* 은 동일한 표기법을 사용 하는 역참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-117">Note the ambiguity between octal escape codes (such as `\16`) and `\`*number* backreferences that use the same notation.</span></span> <span data-ttu-id="ec22a-118">이러한 모호성은 다음과 같이 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-118">This ambiguity is resolved as follows:</span></span>  
  
-   <span data-ttu-id="ec22a-119">`\1`에서 `\9` 사이의 식은 항상 8진수 코드가 아니라 역참조로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-119">The expressions `\1` through `\9` are always interpreted as backreferences, and not as octal codes.</span></span>  
  
-   <span data-ttu-id="ec22a-120">다중 숫자 식의 첫 번째 숫자가 8 또는 9이면(예: `\80` 또는 `\91`) 식은 리터럴로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-120">If the first digit of a multidigit expression is 8 or 9 (such as `\80` or `\91`), the expression as interpreted as a literal.</span></span>  
  
-   <span data-ttu-id="ec22a-121">`\10` 이상인 식은 이 숫자에 해당하는 역참조가 있을 경우 역참조로 간주되고, 없을 경우 8진수 코드로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-121">Expressions from `\10` and greater are considered backreferences if there is a backreference corresponding to that number; otherwise, they are interpreted as octal codes.</span></span>  
  
-   <span data-ttu-id="ec22a-122">정의 되지 않은 그룹 번호에 대 한 역참조를 포함 하는 정규식을 구문 분석 오류가 발생 하 고 정규식 엔진은 throw 된 <xref:System.ArgumentException>합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-122">If a regular expression contains a backreference to an undefined group number, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="ec22a-123">모호성 문제가 되는 경우 사용할 수 있습니다는 `\k<` *이름* `>` 표기법을 명확 하 고 8 진수 문자 코드와 혼동 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-123">If the ambiguity is a problem, you can use the `\k<`*name*`>` notation, which is unambiguous and cannot be confused with octal character codes.</span></span> <span data-ttu-id="ec22a-124">마찬가지로, `\xdd` 등의 16진수 코드는 명확하며 역참조와 혼동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-124">Similarly, hexadecimal codes such as `\xdd` are unambiguous and cannot be confused with backreferences.</span></span>  
  
 <span data-ttu-id="ec22a-125">다음 예제에서는 문자열에서 2배 워드 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-125">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="ec22a-126">다음과 같은 요소로 구성된 `(\w)\1` 정규식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-126">It defines a regular expression, `(\w)\1`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="ec22a-127">요소</span><span class="sxs-lookup"><span data-stu-id="ec22a-127">Element</span></span>|<span data-ttu-id="ec22a-128">설명</span><span class="sxs-lookup"><span data-stu-id="ec22a-128">Description</span></span>|  
|-------------|-----------------|  
|`(\w)`|<span data-ttu-id="ec22a-129">단어 문자를 찾아 첫 번째 캡처링 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-129">Match a word character and assign it to the first capturing group.</span></span>|  
|`\1`|<span data-ttu-id="ec22a-130">첫 번째 캡처링 그룹의 값과 일치하는 다음 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-130">Match the next character that is the same as the value of the first capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a><span data-ttu-id="ec22a-131">명명된 역참조</span><span class="sxs-lookup"><span data-stu-id="ec22a-131">Named Backreferences</span></span>  
 <span data-ttu-id="ec22a-132">명명된 역참조는 다음 구문을 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-132">A named backreference is defined by using the following syntax:</span></span>  
  
 <span data-ttu-id="ec22a-133">`\k<` *name* `>`</span><span class="sxs-lookup"><span data-stu-id="ec22a-133">`\k<` *name* `>`</span></span>  
  
 <span data-ttu-id="ec22a-134">또는</span><span class="sxs-lookup"><span data-stu-id="ec22a-134">or:</span></span>  
  
 <span data-ttu-id="ec22a-135">`\k'` *name* `'`</span><span class="sxs-lookup"><span data-stu-id="ec22a-135">`\k'` *name* `'`</span></span>  
  
 <span data-ttu-id="ec22a-136">여기서 *name*은 정규식 패턴에 정의된 캡처링 그룹의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-136">where *name* is the name of a capturing group defined in the regular expression pattern.</span></span> <span data-ttu-id="ec22a-137">경우 *이름* 은 정규식 패턴에 정의 되어 있지는 구문 분석 오류가 발생 하 고 정규식 엔진은 throw는 <xref:System.ArgumentException>합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-137">If *name* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="ec22a-138">다음 예제에서는 문자열에서 2배 워드 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-138">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="ec22a-139">다음과 같은 요소로 구성된 `(?<char>\w)\k<char>` 정규식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-139">It defines a regular expression, `(?<char>\w)\k<char>`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="ec22a-140">요소</span><span class="sxs-lookup"><span data-stu-id="ec22a-140">Element</span></span>|<span data-ttu-id="ec22a-141">설명</span><span class="sxs-lookup"><span data-stu-id="ec22a-141">Description</span></span>|  
|-------------|-----------------|  
|`(?<char>\w)`|<span data-ttu-id="ec22a-142">단어 문자를 명명 된 캡처링 그룹에 할당 `char`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-142">Match a word character and assign it to a capturing group named `char`.</span></span>|  
|`\k<char>`|<span data-ttu-id="ec22a-143">값과 일치 하는 다음 문자를 일치는 `char` 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-143">Match the next character that is the same as the value of the `char` capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 <span data-ttu-id="ec22a-144">*name*은 숫자의 문자열 표현일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-144">Note that *name* can also be the string representation of a number.</span></span> <span data-ttu-id="ec22a-145">예를 들어 다음 예제에서는 `(?<2>\w)\k<2>` 정규식을 사용하여 문자열에서 2배 워드 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-145">For example, the following example uses the regular expression `(?<2>\w)\k<2>` to find doubled word characters in a string.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a><span data-ttu-id="ec22a-146">역참조에서 찾는 대상</span><span class="sxs-lookup"><span data-stu-id="ec22a-146">What Backreferences Match</span></span>  
 <span data-ttu-id="ec22a-147">역참조는 그룹의 가장 최근 정의(왼쪽에서 오른쪽으로 찾을 경우 가장 왼쪽에 있는 정의)를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-147">A backreference refers to the most recent definition of a group (the definition most immediately to the left, when matching left to right).</span></span> <span data-ttu-id="ec22a-148">그룹에서 여러 개의 캡처를 만드는 경우 역참조는 가장 최근 캡처를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-148">When a group makes multiple captures, a backreference refers to the most recent capture.</span></span>  
  
 <span data-ttu-id="ec22a-149">다음 예제에는 이름이 \1인 그룹을 다시 정의하는 정규식 패턴 `(?<1>a)(?<1>\1b)*`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-149">The following example includes a regular expression pattern, `(?<1>a)(?<1>\1b)*`, which redefines the \1 named group.</span></span> <span data-ttu-id="ec22a-150">다음 표에서는 정규식의 각 패턴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-150">The following table describes each pattern in the regular expression.</span></span>  
  
|<span data-ttu-id="ec22a-151">패턴</span><span class="sxs-lookup"><span data-stu-id="ec22a-151">Pattern</span></span>|<span data-ttu-id="ec22a-152">설명</span><span class="sxs-lookup"><span data-stu-id="ec22a-152">Description</span></span>|  
|-------------|-----------------|  
|`(?<1>a)`|<span data-ttu-id="ec22a-153">문자 "a"와 명명 된 캡처링 그룹에 결과 할당 `1`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-153">Match the character "a" and assign the result to the capturing group named `1`.</span></span>|  
|`(?<1>\1b)*`|<span data-ttu-id="ec22a-154">명명 된 그룹의 일치 항목 0 또는 1 개 발생 `1` "b", 및 명명 된 캡처링 그룹에 결과 할당 함께 `1`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-154">Match 0 or 1 occurrence of the group named `1` along with a "b", and assign the result to the capturing group named `1`.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 <span data-ttu-id="ec22a-155">입력 문자열("aababb")과 정규식을 비교할 때 정규식 엔진은 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-155">In comparing the regular expression with the input string ("aababb"), the regular expression engine performs the following operations:</span></span>  
  
1.  <span data-ttu-id="ec22a-156">문자열의 시작 부분에서 시작하여 `(?<1>a)` 식으로 "a"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-156">It starts at the beginning of the string, and successfully matches "a" with the expression `(?<1>a)`.</span></span> <span data-ttu-id="ec22a-157">값은 `1` 그룹은 이제 "a"입니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-157">The value of the `1` group is now "a".</span></span>  
  
2.  <span data-ttu-id="ec22a-158">두 번째 문자로 진행하여 `\1b` 또는 "ab" 식으로 "ab" 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-158">It advances to the second character, and successfully matches the string "ab" with the expression `\1b`, or "ab".</span></span> <span data-ttu-id="ec22a-159">그런 다음 결과 "ab"를 `\1`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-159">It then assigns the result, "ab" to `\1`.</span></span>  
  
3.  <span data-ttu-id="ec22a-160">네 번째 문자로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-160">It advances to the fourth character.</span></span> <span data-ttu-id="ec22a-161">`(?<1>\1b)` 식은 0번 이상 일치할 수 있으므로 `\1b` 식으로 "abb" 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-161">The expression `(?<1>\1b)` is to be matched zero or more times, so it successfully matches the string "abb" with the expression `\1b`.</span></span> <span data-ttu-id="ec22a-162">결과 "abb"를 `\1`에 다시 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-162">It assigns the result, "abb", back to `\1`.</span></span>  
  
 <span data-ttu-id="ec22a-163">이 예제에서 `*`는 반복 수량자로, 정규식 엔진이 정의되는 패턴을 찾을 수 없을 때까지 반복해서 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-163">In this example, `*` is a looping quantifier -- it is evaluated repeatedly until the regular expression engine cannot match the pattern it defines.</span></span> <span data-ttu-id="ec22a-164">반복 수량자는 그룹 정의를 지우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-164">Looping quantifiers do not clear group definitions.</span></span>  
  
 <span data-ttu-id="ec22a-165">그룹에서 부분 문자열을 캡처하지 않은 경우 해당 그룹에 대한 역참조가 정의되지 않으며 일치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-165">If a group has not captured any substrings, a backreference to that group is undefined and never matches.</span></span> <span data-ttu-id="ec22a-166">정규식 패턴에서이 확인할 `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-166">This is illustrated by the regular expression pattern `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, which is defined as follows:</span></span>  
  
|<span data-ttu-id="ec22a-167">패턴</span><span class="sxs-lookup"><span data-stu-id="ec22a-167">Pattern</span></span>|<span data-ttu-id="ec22a-168">설명</span><span class="sxs-lookup"><span data-stu-id="ec22a-168">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="ec22a-169">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-169">Begin the match on a word boundary.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="ec22a-170">두 개의 대문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-170">Match two uppercase letters.</span></span> <span data-ttu-id="ec22a-171">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-171">This is the first capturing group.</span></span>|  
|`(\d{2})?`|<span data-ttu-id="ec22a-172">두 개의 10진수를 0번 또는 한 번 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-172">Match zero or one occurrence of two decimal digits.</span></span> <span data-ttu-id="ec22a-173">이 그룹은 두 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-173">This is the second capturing group.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="ec22a-174">두 개의 대문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-174">Match two uppercase letters.</span></span> <span data-ttu-id="ec22a-175">이 그룹은 세 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-175">This is the third capturing group.</span></span>|  
|`\b`|<span data-ttu-id="ec22a-176">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-176">End the match on a word boundary.</span></span>|  
  
 <span data-ttu-id="ec22a-177">두 번째 캡처링 그룹에서 정의된 두 개의 10진수가 없는 경우에도 입력 문자열이 이 정규식과 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-177">An input string can match this regular expression even if the two decimal digits that are defined by the second capturing group are not present.</span></span> <span data-ttu-id="ec22a-178">다음 예제에서는 일치가 성공해도 성공적인 두 캡처링 그룹 사이에 빈 캡처링 그룹이 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec22a-178">The following example shows that even though the match is successful, an empty capturing group is found between two successful capturing groups.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ec22a-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec22a-179">See Also</span></span>  
 [<span data-ttu-id="ec22a-180">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="ec22a-180">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
