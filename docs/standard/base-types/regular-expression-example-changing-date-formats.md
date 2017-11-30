---
title: "정규식 예제: 날짜 형식 변경"
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
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eeaed0951018c989612691065c027ee46bd6655a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="d75a4-102">정규식 예제: 날짜 형식 변경</span><span class="sxs-lookup"><span data-stu-id="d75a4-102">Regular Expression Example: Changing Date Formats</span></span>
<span data-ttu-id="d75a4-103">다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> 대체할 날짜 형식을 사용 하는 메서드를 *mm*/*dd*/*yy* 하는 날짜 형식으로 되어 *dd*-*mm*-*yy*합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d75a4-104">예제</span><span class="sxs-lookup"><span data-stu-id="d75a4-104">Example</span></span>  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="d75a4-105">다음 코드에서는 응용 프로그램에서 `MDYToDMY` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="d75a4-106">설명</span><span class="sxs-lookup"><span data-stu-id="d75a4-106">Comments</span></span>  
 <span data-ttu-id="d75a4-107">정규식 패턴 `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` 다음 표와 같이 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="d75a4-108">패턴</span><span class="sxs-lookup"><span data-stu-id="d75a4-108">Pattern</span></span>|<span data-ttu-id="d75a4-109">설명</span><span class="sxs-lookup"><span data-stu-id="d75a4-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="d75a4-110">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="d75a4-111">한 개 또는 두 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-111">Match one or two decimal digits.</span></span> <span data-ttu-id="d75a4-112">캡처된 `month` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="d75a4-113">슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="d75a4-114">한 개 또는 두 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-114">Match one or two decimal digits.</span></span> <span data-ttu-id="d75a4-115">캡처된 `day` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="d75a4-116">슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="d75a4-117">2~4개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="d75a4-118">캡처된 `year` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="d75a4-119">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="d75a4-120">`${day}-${month}-${year}` 패턴은 다음 표와 같이 대체 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="d75a4-121">패턴</span><span class="sxs-lookup"><span data-stu-id="d75a4-121">Pattern</span></span>|<span data-ttu-id="d75a4-122">설명</span><span class="sxs-lookup"><span data-stu-id="d75a4-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="d75a4-123">`day` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="d75a4-124">하이픈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="d75a4-125">`month` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="d75a4-126">하이픈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="d75a4-127">`year` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d75a4-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d75a4-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d75a4-128">See Also</span></span>  
 [<span data-ttu-id="d75a4-129">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="d75a4-129">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
