---
title: '정규식 예제: HREF 스캐닝'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9df41a404c091bb76490d762b55580c36cf33f62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="1a82d-102">정규식 예제: HREF 스캐닝</span><span class="sxs-lookup"><span data-stu-id="1a82d-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="1a82d-103">다음 예제는 입력 문자열을 검색하고 모든 href="…" 값과 문자열에서의 해당 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="1a82d-104">Regex 개체</span><span class="sxs-lookup"><span data-stu-id="1a82d-104">The Regex Object</span></span>  
 <span data-ttu-id="1a82d-105">`DumpHRefs` 메서드는 사용자 코드에서 여러 번 호출할 수 있으므로 `static`(Visual Basic의 경우 `Shared`) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1a82d-106">그러면 정규식 엔진이 정규식을 캐시할 수 있으며 메서드를 호출할 때마다 새 <xref:System.Text.RegularExpressions.Regex> 개체를 인스턴스화하는 오버헤드를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="1a82d-107">그리고 <xref:System.Text.RegularExpressions.Match> 개체는 문자열의 모든 일치 항목을 반복하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="1a82d-108">다음 예제에서는 `DumpHRefs` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="1a82d-109">정규식 패턴 `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))`는 다음 테이블과 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="1a82d-110">패턴</span><span class="sxs-lookup"><span data-stu-id="1a82d-110">Pattern</span></span>|<span data-ttu-id="1a82d-111">설명</span><span class="sxs-lookup"><span data-stu-id="1a82d-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="1a82d-112">리터럴 문자열 "href"과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-112">Match the literal string "href".</span></span> <span data-ttu-id="1a82d-113">일치 항목 찾기에서는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="1a82d-114">0개 이상의 공백 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="1a82d-115">등호와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="1a82d-116">0개 이상의 공백 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-116">Match zero or more white-space characters.</span></span>|  
|<code>(?:\["'\](?<1>\[^"'\]*)"&#124;(?<1>\S+))</code>|<span data-ttu-id="1a82d-117">캡처된 그룹에 결과를 할당하지 않으며 다음 중 하나와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-117">Match one of the following without assigning the result to a captured group:</span></span><br /> <ul><li><p><span data-ttu-id="1a82d-118">따옴표 또는 아포스트로피 뒤에 따옴표 또는 아포스트로피 이외의 다른 문자가 0개 이상 나오고 그 뒤에 다시 따옴표 또는 아포스트로피가 나오는 항목.</span><span class="sxs-lookup"><span data-stu-id="1a82d-118">A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="1a82d-119">`1`이라는 그룹이 이 패턴에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-119">The group named `1` is included in this pattern.</span></span></p></li><li><p><span data-ttu-id="1a82d-120">하나 이상의 공백이 아닌 문자.</span><span class="sxs-lookup"><span data-stu-id="1a82d-120">One or more non-white-space characters.</span></span> <span data-ttu-id="1a82d-121">`1`이라는 그룹이 이 패턴에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-121">The group named `1` is included in this pattern.</span></span></p></li></ul>|  
|`(?<1>[^"']*)`|<span data-ttu-id="1a82d-122">`1`이라는 캡처 그룹에 따옴표 또는 아포스트로피 이외의 다른 문자 항목을 0개 이상 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="1a82d-123">`1`이라는 캡처링 그룹에 하나 이상의 공백이 아닌 문자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="1a82d-124">일치 결과 클래스</span><span class="sxs-lookup"><span data-stu-id="1a82d-124">Match Result Class</span></span>  
 <span data-ttu-id="1a82d-125">검색 결과는 <xref:System.Text.RegularExpressions.Match> 클래스에 저장되는데, 이 클래스는 검색에서 추출한 모든 부분 문자열에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="1a82d-126">또한 검색 중인 문자열 및 사용 중인 정규식을 기억하므로 <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> 메서드를 호출하여 마지막 검색이 종료된 위치부터 또 다른 검색을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="1a82d-127">명시적으로 명명된 캡처</span><span class="sxs-lookup"><span data-stu-id="1a82d-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="1a82d-128">기존의 정규식에서 캡처링 괄호는 자동으로 순서대로 번호가 매겨집니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="1a82d-129">이 경우에 두 가지 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-129">This leads to two problems.</span></span> <span data-ttu-id="1a82d-130">첫째, 괄호를 삽입하거나 제거하여 정규식을 수정하면 번호가 매겨진 캡처를 참조하는 모든 코드를 다시 작성하여 새로 지정된 번호를 반영해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="1a82d-131">둘째, 괄호의 다른 집합을 사용하여 허용 가능한 일치 항목에 두 개의 대체 식을 제공하기 때문에 둘 중 어느 쪽이 결과를 반환했는지 확인하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="1a82d-132">이러한 문제를 해결하기 위해 <xref:System.Text.RegularExpressions.Regex> 클래스는 `(?<name>…)` 구문이 지정된 슬롯에 일치 항목을 캡처하도록 지원합니다(문자열 또는 정수를 사용하여 슬롯에 이름을 지정할 수 있음. 정수를 더 신속하게 다시 호출할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="1a82d-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="1a82d-133">따라서 동일한 문자열의 대체 일치 항목은 모두 동일한 위치로 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="1a82d-134">충돌이 발생할 경우 슬롯에 삭제된 마지막 일치 항목이 성공적인 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="1a82d-135">(그러나 단일 슬롯에 대한 여러 일치 항목이 있는 경우 전체 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a82d-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="1a82d-136">자세한 내용은 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> 컬렉션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1a82d-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a82d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a82d-137">See Also</span></span>  
 [<span data-ttu-id="1a82d-138">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="1a82d-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
