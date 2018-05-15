---
title: checked(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: b05af798217a4f312bcf134d531135713efa8c66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="checked-c-reference"></a><span data-ttu-id="a5b99-102">checked(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a5b99-102">checked (C# Reference)</span></span>
<span data-ttu-id="a5b99-103">`checked` 키워드는 정수 형식 산술 연산 및 변환에 대한 오버플로 검사를 명시적으로 사용하도록 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="a5b99-104">상수 값만 포함된 식이 대상 형식의 범위를 벗어난 값을 생성할 경우 기본적으로 이 식에서는 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="a5b99-105">식에 하나 이상의 상수가 아닌 값이 포함된 경우 컴파일러에서는 오버플로를 감지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="a5b99-106">다음 예제에서 `i2`에 할당된 식을 계산하면 컴파일러 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 <span data-ttu-id="a5b99-107">기본적으로 이러한 상수가 아닌 식은 런타임에 오버플로가 있는지 검사되지 않고 오버플로 예외를 일으키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-107">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="a5b99-108">이전 예제는 양의 정수 2개의 합계로 -2,147,483,639를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-108">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="a5b99-109">오버플로 검사는 컴파일러 옵션, 환경 구성 또는 `checked` 키워드 사용을 통해 사용하도록 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-109">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="a5b99-110">다음 예제에서는 `checked` 식 또는 `checked` 블록을 사용하여 런타임에 이전 합계에 의해 생성되는 오버플로를 감지하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-110">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="a5b99-111">두 예제는 모두 오버플로 예외를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-111">Both examples raise an overflow exception.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 <span data-ttu-id="a5b99-112">[unchecked](../../../csharp/language-reference/keywords/unchecked.md) 키워드는 오버플로 검사를 피하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-112">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5b99-113">예</span><span class="sxs-lookup"><span data-stu-id="a5b99-113">Example</span></span>  
 <span data-ttu-id="a5b99-114">이 샘플에서는 `checked`를 사용하여 런타임에 오버플로 검사를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5b99-114">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a5b99-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a5b99-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5b99-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5b99-116">See Also</span></span>  
 [<span data-ttu-id="a5b99-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a5b99-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a5b99-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a5b99-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a5b99-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="a5b99-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a5b99-120">Checked 및 Unchecked</span><span class="sxs-lookup"><span data-stu-id="a5b99-120">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="a5b99-121">unchecked</span><span class="sxs-lookup"><span data-stu-id="a5b99-121">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)
