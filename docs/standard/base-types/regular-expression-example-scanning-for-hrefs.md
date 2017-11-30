---
title: "정규식 예제: HREF 스캐닝"
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
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="016b4-102">정규식 예제: HREF 스캐닝</span><span class="sxs-lookup"><span data-stu-id="016b4-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="016b4-103">다음 예제는 입력 문자열을 검색하고 모든 href="…" 값과 문자열에서의 해당 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="016b4-104">Regex 개체</span><span class="sxs-lookup"><span data-stu-id="016b4-104">The Regex Object</span></span>  
 <span data-ttu-id="016b4-105">때문에 `DumpHRefs` 메서드 사용자 코드에서 여러 번 호출할 수 있습니다, 사용 하 여는 `static` (`Shared` Visual basic에서) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="016b4-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="016b4-106">정규식을 캐시 하도록 정규식 엔진을 사용 하면이 새 인스턴스화하는 오버 헤드를 방지할 수 <xref:System.Text.RegularExpressions.Regex> 메서드가 호출 될 때마다 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="016b4-107">A <xref:System.Text.RegularExpressions.Match> 개체는 다음 문자열에 일치 하는 모든 항목을 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="016b4-108">다음 예제에서는 `DumpHRefs` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="016b4-109">정규식 패턴 `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))`는 다음 테이블과 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="016b4-110">패턴</span><span class="sxs-lookup"><span data-stu-id="016b4-110">Pattern</span></span>|<span data-ttu-id="016b4-111">설명</span><span class="sxs-lookup"><span data-stu-id="016b4-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="016b4-112">리터럴 문자열 "href"과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-112">Match the literal string "href".</span></span> <span data-ttu-id="016b4-113">일치 항목 찾기에서는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="016b4-114">0개 이상의 공백 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="016b4-115">등호 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="016b4-116">0개 이상의 공백 문자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-116">Match zero or more white-space characters.</span></span>|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|<span data-ttu-id="016b4-117">캡처된 그룹에 결과 할당 하지 않고 다음 중 하나를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-117">Match one of the following without assigning the result to a captured group:</span></span><br /><br /> <span data-ttu-id="016b4-118">-따옴표 또는 아포스트로피, 따옴표 또는 아포스트로피 뒤에 따옴표 또는 아포스트로피 이외의 다른 문자가 0 개 이상의 개.</span><span class="sxs-lookup"><span data-stu-id="016b4-118">-   A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="016b4-119">`1`이라는 그룹이 이 패턴에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-119">The group named `1` is included in this pattern.</span></span><br /><span data-ttu-id="016b4-120">-하나 이상의 공백이 아닌 문자.</span><span class="sxs-lookup"><span data-stu-id="016b4-120">-   One or more non-white-space characters.</span></span> <span data-ttu-id="016b4-121">`1`이라는 그룹이 이 패턴에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-121">The group named `1` is included in this pattern.</span></span>|  
|`(?<1>[^"']*)`|<span data-ttu-id="016b4-122">`1`이라는 캡처 그룹에 따옴표 또는 아포스트로피 이외의 다른 문자 항목을 0개 이상 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="016b4-123">`1`이라는 캡처링 그룹에 하나 이상의 공백이 아닌 문자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="016b4-124">일치 결과 클래스</span><span class="sxs-lookup"><span data-stu-id="016b4-124">Match Result Class</span></span>  
 <span data-ttu-id="016b4-125">검색 결과에 저장 됩니다는 <xref:System.Text.RegularExpressions.Match> 클래스를 검색 하 여 추출 된 모든 부분 문자열에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="016b4-126">또한를 기억 하 여 검색 중인 문자열과 사용 되는 정규식을 호출할 수 있도록는 <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> 메서드 마지막 트랜잭션이 종료 된 다른 검색 시작을 수행 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="016b4-127">명시적으로 명명된 캡처</span><span class="sxs-lookup"><span data-stu-id="016b4-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="016b4-128">기존의 정규식에서 캡처링 괄호는 자동으로 순서대로 번호가 매겨집니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="016b4-129">이 경우에 두 가지 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-129">This leads to two problems.</span></span> <span data-ttu-id="016b4-130">첫째, 괄호를 삽입하거나 제거하여 정규식을 수정하면 번호가 매겨진 캡처를 참조하는 모든 코드를 다시 작성하여 새로 지정된 번호를 반영해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="016b4-131">둘째, 괄호의 다른 집합을 사용하여 허용 가능한 일치 항목에 두 개의 대체 식을 제공하기 때문에 둘 중 어느 쪽이 결과를 반환했는지 확인하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="016b4-132">이러한 문제를 해결 하기 위해는 <xref:System.Text.RegularExpressions.Regex> 클래스 구문을 지원 `(?<name>…)` 지정 된 슬롯에 일치 하는 캡처링 (슬롯 이름을 지정할 수는 문자열 또는 정수를 사용 하 여; 정수 보다 신속 하 게 회수할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="016b4-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="016b4-133">따라서 동일한 문자열의 대체 일치 항목은 모두 동일한 위치로 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="016b4-134">충돌이 발생할 경우 슬롯에 삭제된 마지막 일치 항목이 성공적인 일치입니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="016b4-135">(그러나 단일 슬롯에 대한 여러 일치 항목이 있는 경우 전체 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016b4-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="016b4-136">참조는 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> 세부 정보에 대 한 컬렉션입니다.)</span><span class="sxs-lookup"><span data-stu-id="016b4-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016b4-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="016b4-137">See Also</span></span>  
 [<span data-ttu-id="016b4-138">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="016b4-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
