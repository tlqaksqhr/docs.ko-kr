---
title: implicit(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: c731799fd51397b2bbbb190efcec63321ebae940
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39243737"
---
# <a name="implicit-c-reference"></a><span data-ttu-id="7e8fb-102">implicit(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7e8fb-102">implicit (C# Reference)</span></span>

<span data-ttu-id="7e8fb-103">`implicit` 키워드는 암시적 사용자 정의 형식 변환 연산자를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="7e8fb-104">변환 시 데이터가 손실되지 않는 경우 이 키워드를 통해 사용자 정의 형식과 다른 형식 간에 암시적 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>

## <a name="example"></a><span data-ttu-id="7e8fb-105">예</span><span class="sxs-lookup"><span data-stu-id="7e8fb-105">Example</span></span>

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

<span data-ttu-id="7e8fb-106">암시적 변환은 불필요한 캐스트를 제거하여 소스 코드 가독성을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="7e8fb-107">그러나 암시적 변환 시 프로그래머가 명시적으로 형식 간에 캐스팅할 필요가 없으므로 예기치 않은 결과를 방지하기 위해 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="7e8fb-108">일반적으로 암시적 변환 연산자는 예외를 throw하지 않고 정보가 손실되지 않으므로 프로그래머에게 알리지 않고 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="7e8fb-109">변환 연산자가 이러한 조건에 맞지 않는 경우 `explicit`로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="7e8fb-110">자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e8fb-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="7e8fb-111">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="7e8fb-111">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7e8fb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e8fb-112">See also</span></span>

[<span data-ttu-id="7e8fb-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="7e8fb-113">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="7e8fb-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7e8fb-114">C# Programming Guide</span></span>](../../programming-guide/index.md)  
[<span data-ttu-id="7e8fb-115">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="7e8fb-115">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="7e8fb-116">explicit</span><span class="sxs-lookup"><span data-stu-id="7e8fb-116">explicit</span></span>](explicit.md)  
[<span data-ttu-id="7e8fb-117">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7e8fb-117">operator (C# Reference)</span></span>](operator.md)  
[<span data-ttu-id="7e8fb-118">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="7e8fb-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
