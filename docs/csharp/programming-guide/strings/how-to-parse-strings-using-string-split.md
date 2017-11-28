---
title: "방법: String.Split를 사용하여 문자열 구문 분석(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b97d1d89a4c74a4c759d1ed41a0bc2476b3b07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a><span data-ttu-id="cc3ad-102">방법: String.Split를 사용하여 문자열 구문 분석(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="cc3ad-102">How to: Parse Strings Using String.Split (C# Programming Guide)</span></span>
<span data-ttu-id="cc3ad-103">다음 코드 예제에서는 <xref:System.String.Split%2A?displayProperty=nameWithType> 메서드를 사용하여 문자열을 구문 분석하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-103">The following code example demonstrates how a string can be parsed using the <xref:System.String.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cc3ad-104"><xref:System.String.Split%2A> 는 대상 문자열의 흥미로운 하위 문자열을 구분하는 문자를 나타내는 문자 배열을 입력으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-104">As input, <xref:System.String.Split%2A> takes an array of characters that indicate which characters separate interesting sub strings of the target string.</span></span>  <span data-ttu-id="cc3ad-105">함수는 하위 문자열 배열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-105">The function returns an array of the sub strings.</span></span>  
  
 <span data-ttu-id="cc3ad-106">이 예제에서는 공백, 쉼표, 마침표, 콜론 및 탭을 사용하며, 모두 이러한 구분 문자를 포함하는 배열로 <xref:System.String.Split%2A>에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-106">This example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="cc3ad-107">대상 문자열 문장의 각 단어는 결과 문자열 배열과 별도로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-107">Each word in the target string's sentence displays separately from the resulting array of strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc3ad-108">예제</span><span class="sxs-lookup"><span data-stu-id="cc3ad-108">Example</span></span>  
 [!code-csharp[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="cc3ad-109">예제</span><span class="sxs-lookup"><span data-stu-id="cc3ad-109">Example</span></span>  
 <span data-ttu-id="cc3ad-110">기본적으로 String.Split는 두 구분 문자가 대상 문자열에 연속적으로 표시되는 경우 빈 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-110">By default, String.Split returns empty strings when two separating characters appear contiguously in the target string.</span></span>  <span data-ttu-id="cc3ad-111">선택적 StringSplitOptions.RemoveEmptyEntries 매개 변수를 전달하여 출력에서 빈 문자열을 모두 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-111">You can pass an optional StringSplitOptions.RemoveEmptyEntries parameter to exclude any empty strings in the output.</span></span>  
  
 <span data-ttu-id="cc3ad-112">String.Split는 문자열 배열(단일 문자 대신 대상 문자열을 구문 분석하기 위한 구분 기호 역할을 하는 문자 시퀀스)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3ad-112">String.Split can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        string[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc3ad-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc3ad-113">See Also</span></span>  
 [<span data-ttu-id="cc3ad-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cc3ad-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cc3ad-115">문자열</span><span class="sxs-lookup"><span data-stu-id="cc3ad-115">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="cc3ad-116">.NET Framework 정규식</span><span class="sxs-lookup"><span data-stu-id="cc3ad-116">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)
