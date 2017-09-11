---
title: "string(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- string
- string_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
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
ms.openlocfilehash: 56847aad4cb8b0427594a299df2306d21675506b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="string-c-reference"></a><span data-ttu-id="bce0a-102">string(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="bce0a-102">string (C# Reference)</span></span>
<span data-ttu-id="bce0a-103">`string` 형식은 0자 이상의 유니코드 문자 시퀀스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="bce0a-104">`string`은 .NET Framework에서 <xref:System.String>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-104">`string` is an alias for <xref:System.String> in the .NET Framework.</span></span>  
  
 <span data-ttu-id="bce0a-105">`string`은 참조 형식이지만 같음 연산자(`==` 및 `!=`)는 참조가 아니라 `string` 개체의 값을 비교하도록 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="bce0a-106">이 때문에 좀 더 직관적으로 문자열이 같은지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="bce0a-107">예:</span><span class="sxs-lookup"><span data-stu-id="bce0a-107">For example:</span></span>  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 <span data-ttu-id="bce0a-108">이 코드는 "True"를 표시한 다음 "False"를 표시하며, 이는 문자열의 내용이 동일하지만 `a`와 `b`는 동일한 문자열 인스턴스를 가리키지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>  
  
 <span data-ttu-id="bce0a-109">+ 연산자는 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-109">The + operator concatenates strings:</span></span>  
  
```csharp  
string a = "good " + "morning";  
```  
  
 <span data-ttu-id="bce0a-110">이 경우 "good morning"이 포함된 문자열 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-110">This creates a string object that contains "good morning".</span></span>  
  
 <span data-ttu-id="bce0a-111">문자열은 *변경할 수 없습니다*. 구문상 가능한 것처럼 보여도 개체를 만든 후에는 문자열 개체의 내용을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="bce0a-112">예를 들어 이 코드를 작성하면 컴파일러에서 실제로 새 문자 시퀀스가 포함될 새 문자열 개체를 만들고, 새 개체가 b에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="bce0a-113">그런 다음 문자열 "h"는 가비지 수집 대상이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-113">The string "h" is then eligible for garbage collection.</span></span>  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 <span data-ttu-id="bce0a-114">`string`의 개별 문자에 대한 읽기 전용 액세스를 위해 [] 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 <span data-ttu-id="bce0a-115">문자열 리터럴은 `string` 형식이며, quoted 및 @-quoted의 두 가지 형태로 작성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="bce0a-116">따옴표가 있는 문자열 리터럴은 큰따옴표(")로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>  
  
```csharp  
"good morning"  // a string literal  
```  
  
 <span data-ttu-id="bce0a-117">문자열 리터럴에는 모든 문자 리터럴이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-117">String literals can contain any character literal.</span></span> <span data-ttu-id="bce0a-118">이스케이프 시퀀스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-118">Escape sequences are included.</span></span> <span data-ttu-id="bce0a-119">다음 예제에서는 이스케이프 시퀀스 `\\`를 백슬래시에 사용하고, `\u0066`을 f에 사용하고, `\n`을 줄 바꿈에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>  
  
```  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  <span data-ttu-id="bce0a-120">이스케이프 코드 `\udddd`(여기서 `dddd`는 4자리 숫자)는 유니코드 문자 U+`dddd`를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="bce0a-121">8자리 유니코드 이스케이프 코드 `\Udddddddd`도 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>  
  
 <span data-ttu-id="bce0a-122">축자 문자열 리터럴은 @으로 시작하며 큰따옴표로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-122">Verbatim string literals start with @ and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="bce0a-123">예:</span><span class="sxs-lookup"><span data-stu-id="bce0a-123">For example:</span></span>  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 <span data-ttu-id="bce0a-124">축자 문자열의 장점은 이스케이프 시퀀스가 처리되지 *않으므로*, 정규화된 파일 이름 등을 쉽게 쓸 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 <span data-ttu-id="bce0a-125">@-quoted 문자열에 큰따옴표를 포함하려면 큰따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-125">To include a double quotation mark in an @-quoted string, double it:</span></span>  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 <span data-ttu-id="bce0a-126">@ 기호의 또 다른 사용법은 C# 키워드인 참조된([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) 식별자를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bce0a-126">Another use of the @ symbol is to use referenced ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) identifiers that are C# keywords.</span></span>  
  
 <span data-ttu-id="bce0a-127">C#의 문자열에 대한 자세한 내용은 [문자열](../../../csharp/programming-guide/strings/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bce0a-127">For more information about strings in C#, see [Strings](../../../csharp/programming-guide/strings/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bce0a-128">예제</span><span class="sxs-lookup"><span data-stu-id="bce0a-128">Example</span></span>  
 <span data-ttu-id="bce0a-129">[!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bce0a-129">[!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bce0a-130">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="bce0a-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bce0a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bce0a-131">See Also</span></span>  
 <span data-ttu-id="bce0a-132">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bce0a-133">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bce0a-134">[문자열 사용에 대한 모범 사례](../../../standard/base-types/best-practices-strings.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-134">[Best Practices for Using Strings](../../../standard/base-types/best-practices-strings.md) </span></span>  
 <span data-ttu-id="bce0a-135">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-135">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bce0a-136">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bce0a-137">[참조 형식](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-137">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="bce0a-138">[값 형식](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-138">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="bce0a-139">[기본적인 문자열 작업](../../../standard/base-types/basic-string-operations.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-139">[Basic String Operations](../../../standard/base-types/basic-string-operations.md) </span></span>  
 <span data-ttu-id="bce0a-140">[새 문자열 만들기](../../../standard/base-types/creating-new.md) </span><span class="sxs-lookup"><span data-stu-id="bce0a-140">[Creating New Strings](../../../standard/base-types/creating-new.md) </span></span>  
 [<span data-ttu-id="bce0a-141">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="bce0a-141">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)

