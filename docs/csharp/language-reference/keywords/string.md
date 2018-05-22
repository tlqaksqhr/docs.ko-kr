---
title: string(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
ms.openlocfilehash: f92a44283e59bd80421758a63b40bc5289c3628b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="string-c-reference"></a><span data-ttu-id="9ff33-102">string(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9ff33-102">string (C# Reference)</span></span>
<span data-ttu-id="9ff33-103">`string` 형식은 0자 이상의 유니코드 문자 시퀀스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="9ff33-104">`string`는 .NET에서 <xref:System.String>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-104">`string` is an alias for <xref:System.String> in .NET.</span></span>  
  
 <span data-ttu-id="9ff33-105">`string`은 참조 형식이지만 같음 연산자(`==` 및 `!=`)는 참조가 아니라 `string` 개체의 값을 비교하도록 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="9ff33-106">이 때문에 좀 더 직관적으로 문자열이 같은지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="9ff33-107">예:</span><span class="sxs-lookup"><span data-stu-id="9ff33-107">For example:</span></span>  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 <span data-ttu-id="9ff33-108">이 코드는 "True"를 표시한 다음 "False"를 표시하며, 이는 문자열의 내용이 동일하지만 `a`와 `b`는 동일한 문자열 인스턴스를 가리키지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>  
  
 <span data-ttu-id="9ff33-109">+ 연산자는 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-109">The + operator concatenates strings:</span></span>  
  
```csharp  
string a = "good " + "morning";  
```  
  
 <span data-ttu-id="9ff33-110">이 경우 "good morning"이 포함된 문자열 개체가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-110">This creates a string object that contains "good morning".</span></span>  
  
 <span data-ttu-id="9ff33-111">문자열은 *변경할 수 없습니다*. 구문상 가능한 것처럼 보여도 개체를 만든 후에는 문자열 개체의 내용을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="9ff33-112">예를 들어 이 코드를 작성하면 컴파일러에서 실제로 새 문자 시퀀스가 포함될 새 문자열 개체를 만들고, 새 개체가 b에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="9ff33-113">그런 다음 문자열 "h"는 가비지 수집 대상이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-113">The string "h" is then eligible for garbage collection.</span></span>  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 <span data-ttu-id="9ff33-114">`string`의 개별 문자에 대한 읽기 전용 액세스를 위해 [] 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 <span data-ttu-id="9ff33-115">문자열 리터럴은 `string` 형식이며, quoted 및 @-quoted의 두 가지 형태로 작성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="9ff33-116">따옴표가 있는 문자열 리터럴은 큰따옴표(")로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>  
  
```csharp  
"good morning"  // a string literal  
```  
  
 <span data-ttu-id="9ff33-117">문자열 리터럴에는 모든 문자 리터럴이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-117">String literals can contain any character literal.</span></span> <span data-ttu-id="9ff33-118">이스케이프 시퀀스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-118">Escape sequences are included.</span></span> <span data-ttu-id="9ff33-119">다음 예제에서는 이스케이프 시퀀스 `\\`를 백슬래시에 사용하고, `\u0066`을 f에 사용하고, `\n`을 줄 바꿈에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>  
  
```csharp  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  <span data-ttu-id="9ff33-120">이스케이프 코드 `\udddd`(여기서 `dddd`는 4자리 숫자)는 유니코드 문자 U+`dddd`를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="9ff33-121">8자리 유니코드 이스케이프 코드 `\Udddddddd`도 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>  
  
 <span data-ttu-id="9ff33-122">축자 문자열 리터럴은 `@`로 시작하며 큰따옴표로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-122">Verbatim string literals start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="9ff33-123">예:</span><span class="sxs-lookup"><span data-stu-id="9ff33-123">For example:</span></span>  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 <span data-ttu-id="9ff33-124">축자 문자열의 장점은 이스케이프 시퀀스가 처리되지 *않으므로*, 정규화된 파일 이름 등을 쉽게 쓸 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 <span data-ttu-id="9ff33-125">@-quoted 문자열에 큰따옴표를 포함하려면 큰따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff33-125">To include a double quotation mark in an @-quoted string, double it:</span></span>  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 <span data-ttu-id="9ff33-126">`@` 특수 문자의 다른 용도는 [@ - 축자 식별자](../tokens/verbatim.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ff33-126">For other uses of the `@` special character, see [@ -- verbatim identifier](../tokens/verbatim.md).</span></span>  
  
 <span data-ttu-id="9ff33-127">C#의 문자열에 대한 자세한 내용은 [문자열](../../../csharp/programming-guide/strings/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ff33-127">For more information about strings in C#, see [Strings](../../../csharp/programming-guide/strings/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ff33-128">예</span><span class="sxs-lookup"><span data-stu-id="9ff33-128">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="9ff33-129">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="9ff33-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9ff33-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ff33-130">See Also</span></span>  
 [<span data-ttu-id="9ff33-131">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9ff33-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9ff33-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9ff33-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9ff33-133">문자열 사용에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="9ff33-133">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)  
 [<span data-ttu-id="9ff33-134">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="9ff33-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="9ff33-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9ff33-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9ff33-136">참조 형식</span><span class="sxs-lookup"><span data-stu-id="9ff33-136">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="9ff33-137">값 형식</span><span class="sxs-lookup"><span data-stu-id="9ff33-137">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="9ff33-138">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="9ff33-138">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="9ff33-139">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="9ff33-139">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="9ff33-140">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="9ff33-140">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)
