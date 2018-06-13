---
title: bool(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 1045a459491b0d0d6a84c60f6e820297b47efd5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215970"
---
# <a name="bool-c-reference"></a><span data-ttu-id="d37d1-102">bool(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d37d1-102">bool (C# Reference)</span></span>
<span data-ttu-id="d37d1-103">`bool` 키워드는 <xref:System.Boolean?displayProperty=nameWithType>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d37d1-104">부울 값 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md)를 저장할 변수를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d37d1-105">`null` 값을 가질 수 있는 부울 변수가 필요한 경우 `bool?`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="d37d1-106">자세한 내용은 [Null 허용 형식](../../../csharp/programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d37d1-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="literals"></a><span data-ttu-id="d37d1-107">리터럴</span><span class="sxs-lookup"><span data-stu-id="d37d1-107">Literals</span></span>  
 <span data-ttu-id="d37d1-108">`bool` 변수에 부울 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="d37d1-109">`bool`로 계산되는 식을 `bool` 변수에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 <span data-ttu-id="d37d1-110">`bool` 변수의 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="d37d1-111">`bool?` 변수의 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-111">The default value of a `bool?` variable is `null`.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="d37d1-112">변환</span><span class="sxs-lookup"><span data-stu-id="d37d1-112">Conversions</span></span>  
 <span data-ttu-id="d37d1-113">C++에서 `bool` 형식의 값은 `int` 형식의 값으로 변환될 수 있습니다. 즉, `false`는 0과 같고 `true`는 0이 아닌 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="d37d1-114">C#에는 `bool` 형식과 다른 형식 간의 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="d37d1-115">예를 들어 다음 `if` 문은 C#에서 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-115">For example, the following `if` statement is invalid in C#:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 <span data-ttu-id="d37d1-116">`int` 형식의 변수를 테스트하려면 다음과 같이 0과 같은 값에 변수를 명시적으로 비교해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="d37d1-117">예</span><span class="sxs-lookup"><span data-stu-id="d37d1-117">Example</span></span>  
 <span data-ttu-id="d37d1-118">이 예제에서는 키보드에서 문자를 입력하면 프로그램에서 입력 문자가 문자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="d37d1-119">문자인 경우 소문자 또는 대문자인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="d37d1-120">이러한 검사는 <xref:System.Char.IsLetter%2A> 및 <xref:System.Char.IsLower%2A>를 사용하여 수행되며, 둘 다 `bool` 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d37d1-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d37d1-121">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d37d1-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d37d1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d37d1-122">See Also</span></span>  
 [<span data-ttu-id="d37d1-123">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d37d1-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d37d1-124">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d37d1-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d37d1-125">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="d37d1-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d37d1-126">정수 계열 형식 표</span><span class="sxs-lookup"><span data-stu-id="d37d1-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="d37d1-127">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="d37d1-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="d37d1-128">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="d37d1-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="d37d1-129">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="d37d1-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
