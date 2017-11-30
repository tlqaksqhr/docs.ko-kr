---
title: "방법: 문자열에서 유효하지 않은 문자 제거"
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
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f676ca9121498da7c88cdec8b49586bde91b181
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="8e753-102">방법: 문자열에서 유효하지 않은 문자 제거</span><span class="sxs-lookup"><span data-stu-id="8e753-102">How to: Strip Invalid Characters from a String</span></span>
<span data-ttu-id="8e753-103">다음 예제에서는 정적 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> 메서드를 문자열로에서 잘못 된 문자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-103">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e753-104">예제</span><span class="sxs-lookup"><span data-stu-id="8e753-104">Example</span></span>  
 <span data-ttu-id="8e753-105">이 예제에 정의된 `CleanInput` 메서드가 사용하여 사용자 입력을 허용하는 텍스트 필드에 입력한 문제가 될 수 있는 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-105">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="8e753-106">이 경우에 `CleanInput`은 마침표(.), 기호 (@), 하이픈(-)을 제외한 모든 영숫자가 아닌 문자를 제거하고 나머지 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-106">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="8e753-107">그러나 입력 문자열에 포함되어야 하는 모든 문자를 제거하도록 정규식 패턴을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-107">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="8e753-108">정규식 패턴 `[^\w\.@-]`은 단어 문자, 마침표, @ 기호 또는 하이픈이 아닌 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-108">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="8e753-109">단어 문자는 문자, 숫자 또는 밑줄과 같은 문장 부호입니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-109">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="8e753-110">이 패턴과 일치 하는 모든 문자로 대체 됩니다 <xref:System.String.Empty?displayProperty=nameWithType>, 대체 패턴에 의해 정의 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-110">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="8e753-111">사용자 입력에서 추가 문자를 허용하려면 해당 문자를 정규식 패턴의 문자 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-111">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="8e753-112">예를 들어 정규식 패턴 `[^\w\.@-\\%]` 입력된 문자열에 백슬래시 및 백분율 기호를 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e753-112">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e753-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e753-113">See Also</span></span>  
 [<span data-ttu-id="8e753-114">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="8e753-114">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
