---
title: "방법: 정규식을 사용하여 문자열 검색(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="a83cd-102">방법: 정규식을 사용하여 문자열 검색(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a83cd-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="a83cd-103"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> 클래스를 사용하여 문자열을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class can be used to search strings.</span></span> <span data-ttu-id="a83cd-104">이러한 검색의 복잡성은 매우 간단한 수준부터 정규식 전체 활용까지 다양할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="a83cd-105">다음은 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용한 문자열 검색의 두 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="a83cd-106">자세한 내용은 [.NET Framework 정규식](https://msdn.microsoft.com/library/hs600312)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a83cd-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a83cd-107">예제</span><span class="sxs-lookup"><span data-stu-id="a83cd-107">Example</span></span>  
 <span data-ttu-id="a83cd-108">다음 코드는 배열에서 대/소문자를 구분하지 않는 단순 문자열 검색을 수행하는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="a83cd-109">정적 메서드 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName>는 검색할 문자열과 검색 패턴을 포함하는 문자열이 제공될 경우 검색을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="a83cd-110">이 경우 세 번째 인수는 대/소문자를 무시하도록 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="a83cd-111">자세한 내용은 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a83cd-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="a83cd-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a83cd-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a83cd-113">예제</span><span class="sxs-lookup"><span data-stu-id="a83cd-113">Example</span></span>  
 <span data-ttu-id="a83cd-114">다음 코드는 정규식을 사용하여 배열에서 각 문자열 형식의 유효성을 검사하는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-114">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="a83cd-115">유효성 검사에서는 각 문자열이 전화 번호의 형식을 사용하도록 요구합니다. 이 경우 3개의 숫자 그룹이 대시로 구분되고, 처음 두 그룹에는 세 자리 숫자가 포함되며, 세 번째 그룹에는 네 자리 숫자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-115">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="a83cd-116">이 작업은 `^\\d{3}-\\d{3}-\\d{4}$` 정규식을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a83cd-116">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="a83cd-117">자세한 내용은 [정규식 언어 - 빠른 참조](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a83cd-117">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 <span data-ttu-id="a83cd-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a83cd-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83cd-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a83cd-119">See Also</span></span>  
 <span data-ttu-id="a83cd-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a83cd-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span></span>   
 <span data-ttu-id="a83cd-121">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a83cd-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a83cd-122">[문자열](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="a83cd-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="a83cd-123">[.NET Framework 정규식](https://msdn.microsoft.com/library/hs600312) </span><span class="sxs-lookup"><span data-stu-id="a83cd-123">[.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312) </span></span>  
 [<span data-ttu-id="a83cd-124">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="a83cd-124">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

