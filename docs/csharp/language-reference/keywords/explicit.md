---
title: explicit(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: c8a05aef3318eb34242ed1268ea26663592e4d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216479"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="45a39-102">explicit(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="45a39-102">explicit (C# Reference)</span></span>
<span data-ttu-id="45a39-103">`explicit` 키워드는 캐스트를 통해 호출해야 하는 사용자 정의 형식 변환 연산자를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="45a39-104">예를 들어 이 연산자는 Fahrenheit라는 클래스를 Celsius라는 클래스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 <span data-ttu-id="45a39-105">이 변환 연산자는 다음과 같이 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-105">This conversion operator can be invoked like this:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 <span data-ttu-id="45a39-106">변환 연산자는 소스 형식을 대상 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-106">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="45a39-107">소스 형식은 변환 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-107">The source type provides the conversion operator.</span></span> <span data-ttu-id="45a39-108">암시적 변환과 달리 명시적 변환 연산자는 캐스트를 통해 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-108">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="45a39-109">변환 연산으로 인해 예외가 발생하거나 정보가 손실될 경우 `explicit`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-109">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="45a39-110">이렇게 하면 컴파일러가 결과를 예측할 수 없는 변환 연산을 자동으로 호출하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-110">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="45a39-111">캐스트를 생략하면 컴파일 시간 오류 CS0266이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-111">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="45a39-112">자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45a39-112">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="45a39-113">예</span><span class="sxs-lookup"><span data-stu-id="45a39-113">Example</span></span>  
 <span data-ttu-id="45a39-114">다음 예제에서는 `Fahrenheit` 및 `Celsius` 클래스를 제공하며, 각 클래스는 다른 클래스에 명시적 변환 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-114">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="45a39-115">예</span><span class="sxs-lookup"><span data-stu-id="45a39-115">Example</span></span>  
 <span data-ttu-id="45a39-116">다음 예제에서는 한 자리 숫자를 나타내는 `Digit` 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-116">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="45a39-117">`byte`에서 `Digit`로 변환하는 연산자를 정의하지만 일부 바이트는 `Digit`로 변환할 수 없기 때문에 명시적 변환이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45a39-117">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="45a39-118">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="45a39-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45a39-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45a39-119">See Also</span></span>  
 [<span data-ttu-id="45a39-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="45a39-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="45a39-121">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="45a39-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="45a39-122">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="45a39-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="45a39-123">implicit</span><span class="sxs-lookup"><span data-stu-id="45a39-123">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="45a39-124">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="45a39-124">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="45a39-125">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="45a39-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 <span data-ttu-id="45a39-126">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)(C#의 연결된 사용자 정의 명시적 변환)</span><span class="sxs-lookup"><span data-stu-id="45a39-126">[Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)</span></span>
