---
title: '방법: URL에서 프로토콜 및 포트 번호 추출'
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffb31030a2e29458165ae6615a51685ed163fbac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="6433b-102">방법: URL에서 프로토콜 및 포트 번호 추출</span><span class="sxs-lookup"><span data-stu-id="6433b-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="6433b-103">다음 예제에서는 URL에서 프로토콜 및 포트 번호를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-103">The following example extracts a protocol and port number from a URL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6433b-104">예</span><span class="sxs-lookup"><span data-stu-id="6433b-104">Example</span></span>  
 <span data-ttu-id="6433b-105">이 예제에서는 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드를 사용하여 프로토콜, 콜론, 포트 번호 순서로 구성된 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="6433b-106">정규식 패턴 `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/`는 다음 표와 같이 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="6433b-107">무늬</span><span class="sxs-lookup"><span data-stu-id="6433b-107">Pattern</span></span>|<span data-ttu-id="6433b-108">설명</span><span class="sxs-lookup"><span data-stu-id="6433b-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="6433b-109">문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="6433b-110">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-110">Match one or more word characters.</span></span> <span data-ttu-id="6433b-111">이 그룹의 이름을 `proto`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="6433b-112">콜론과 두 개의 슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="6433b-113">슬래시 기호 이외의 문자를 한 번 이상(가능한 적게) 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="6433b-114">하나 이상의 숫자 문자 앞에 나오는 콜론을 0번 또는 한 번 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="6433b-115">이 그룹의 이름을 `port`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="6433b-116">슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="6433b-117"><xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드는 정규식 패턴에 캡처된 두 개의 명명된 그룹 값을 연결하는 `${proto}${port}` 대체 시퀀스를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="6433b-118">이 메서드는 <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> 속성으로 반환된 컬렉션 개체에서 검색된 문자열을 명시적으로 연결하는 편리한 대체 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="6433b-119">이 예제에서는 <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> 메서드를 두 개의 대체 즉, `${proto}` 및 `${port}`와 함께 사용하여 캡처된 그룹을 출력 문자열에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="6433b-120">대신, 다음 코드와 같이 일치 항목의 <xref:System.Text.RegularExpressions.GroupCollection> 개체에서 캡처된 그룹을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6433b-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6433b-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6433b-121">See Also</span></span>  
 [<span data-ttu-id="6433b-122">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="6433b-122">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
