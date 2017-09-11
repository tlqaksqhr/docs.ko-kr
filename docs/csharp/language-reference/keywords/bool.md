---
title: "bool(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- bool_CSharpKeyword
- bool
dev_langs:
- CSharp
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f3b7455ab6b0ec780afe7d81b2ff990d47a31d20
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="bool-c-reference"></a><span data-ttu-id="4b530-102">bool(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4b530-102">bool (C# Reference)</span></span>
<span data-ttu-id="4b530-103">`bool` 키워드는 <xref:System.Boolean?displayProperty=fullName>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=fullName>.</span></span> <span data-ttu-id="4b530-104">부울 값 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md)를 저장할 변수를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b530-105">`null` 값을 가질 수 있는 부울 변수가 필요한 경우 `bool?`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="4b530-106">자세한 내용은 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b530-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="literals"></a><span data-ttu-id="4b530-107">리터럴</span><span class="sxs-lookup"><span data-stu-id="4b530-107">Literals</span></span>  
 <span data-ttu-id="4b530-108">`bool` 변수에 부울 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="4b530-109">`bool`로 계산되는 식을 `bool` 변수에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>  
  
 <span data-ttu-id="4b530-110">[!code-cs[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b530-110">[!code-cs[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]</span></span>  
  
 <span data-ttu-id="4b530-111">`bool` 변수의 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="4b530-112">`bool?` 변수의 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-112">The default value of a `bool?` variable is `null`.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="4b530-113">변환</span><span class="sxs-lookup"><span data-stu-id="4b530-113">Conversions</span></span>  
 <span data-ttu-id="4b530-114">C++에서 `bool` 형식의 값은 `int` 형식의 값으로 변환될 수 있습니다. 즉, `false`는 0과 같고 `true`는 0이 아닌 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="4b530-115">C#에는 `bool` 형식과 다른 형식 간의 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="4b530-116">예를 들어 다음 `if` 문은 C#에서 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-116">For example, the following `if` statement is invalid in C#:</span></span>  
  
 <span data-ttu-id="4b530-117">[!code-cs[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b530-117">[!code-cs[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]</span></span>  
  
 <span data-ttu-id="4b530-118">`int` 형식의 변수를 테스트하려면 다음과 같이 0과 같은 값에 변수를 명시적으로 비교해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-118">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>  
  
 <span data-ttu-id="4b530-119">[!code-cs[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b530-119">[!code-cs[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b530-120">예제</span><span class="sxs-lookup"><span data-stu-id="4b530-120">Example</span></span>  
 <span data-ttu-id="4b530-121">이 예제에서는 키보드에서 문자를 입력하면 프로그램에서 입력 문자가 문자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-121">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="4b530-122">문자인 경우 소문자 또는 대문자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-122">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="4b530-123">이러한 검사는 <xref:System.Char.IsLetter%2A> 및 <xref:System.Char.IsLower%2A>를 사용하여 수행되며, 둘 다 `bool` 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4b530-123">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>  
  
 <span data-ttu-id="4b530-124">[!code-cs[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b530-124">[!code-cs[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4b530-125">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4b530-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4b530-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b530-126">See Also</span></span>  
 <span data-ttu-id="4b530-127">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b530-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4b530-128">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b530-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4b530-129">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b530-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4b530-130">[정수 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4b530-130">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="4b530-131">[기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4b530-131">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="4b530-132">[암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="4b530-132">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="4b530-133">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="4b530-133">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

