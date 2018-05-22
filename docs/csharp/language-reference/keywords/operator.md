---
title: 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: d633a46e21f913aa8c05289dccfb63e71efd697e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="operator-c-reference"></a><span data-ttu-id="8291b-102">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8291b-102">operator (C# Reference)</span></span>
<span data-ttu-id="8291b-103">`operator` 키워드를 사용하여 기본 제공 연산자를 오버로드하거나 클래스 또는 구조체 선언에서 사용자 정의 변환을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8291b-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8291b-104">예</span><span class="sxs-lookup"><span data-stu-id="8291b-104">Example</span></span>  
 <span data-ttu-id="8291b-105">다음은 소수에 대한 매우 간단한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8291b-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="8291b-106">`+` 및 `*` 연산자를 오버로드하여 소수 더하기 및 곱하기를 수행하고 `Fraction` 형식을 `double` 형식으로 변환하는 변환 연산자도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8291b-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8291b-107">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8291b-107">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8291b-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8291b-108">See Also</span></span>  
 [<span data-ttu-id="8291b-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8291b-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8291b-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8291b-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8291b-111">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8291b-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8291b-112">implicit</span><span class="sxs-lookup"><span data-stu-id="8291b-112">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="8291b-113">explicit</span><span class="sxs-lookup"><span data-stu-id="8291b-113">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="8291b-114">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="8291b-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
