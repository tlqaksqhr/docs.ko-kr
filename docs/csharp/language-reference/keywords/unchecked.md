---
title: unchecked(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: d7a48950b7158be3cd589c20fbfe0661f3c9c5af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="6811e-102">unchecked(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6811e-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="6811e-103">`unchecked` 키워드는 정수 형식 산술 연산 및 변환에 대한 오버플로 검사를 비활성화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="6811e-104">unchecked 컨텍스트에서 식이 대상 형식의 범위를 벗어난 값을 생성하는 경우 오버플로에 플래그가 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="6811e-105">예를 들어 다음 예제의 계산은 `unchecked` 블록 또는 식에서 수행되므로 결과가 정수에 비해 너무 크다는 사실이 무시되며 `int1`에 -2,147,483,639 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 <span data-ttu-id="6811e-106">`unchecked` 환경을 제거하면 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="6811e-107">식의 모든 항이 상수이기 때문에 컴파일 시간에 오버플로가 검색될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="6811e-108">상수가 아닌 항을 포함하는 식은 컴파일 시간 및 런타임에 기본적으로 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="6811e-109">checked 환경을 사용하도록 설정하는 방법에 대한 자세한 내용은 [checked](../../../csharp/language-reference/keywords/checked.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6811e-109">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="6811e-110">오버플로를 확인하는 데 시간이 걸리기 때문에 오버플로 위험이 없는 상황에서는 unchecked 코드를 사용하여 성능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="6811e-111">그러나 오버플로가 발생할 가능성이 있는 경우 checked 환경을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-111">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6811e-112">예</span><span class="sxs-lookup"><span data-stu-id="6811e-112">Example</span></span>  
 <span data-ttu-id="6811e-113">이 샘플에서는 `unchecked` 키워드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6811e-113">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6811e-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6811e-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6811e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6811e-115">See Also</span></span>  
 [<span data-ttu-id="6811e-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6811e-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6811e-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6811e-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6811e-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="6811e-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6811e-119">Checked 및 Unchecked</span><span class="sxs-lookup"><span data-stu-id="6811e-119">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="6811e-120">checked</span><span class="sxs-lookup"><span data-stu-id="6811e-120">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)
