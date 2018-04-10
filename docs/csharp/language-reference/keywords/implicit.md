---
title: implicit(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c893c7a9afbdc6f715010d537e9ccaf66c5785c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-c-reference"></a><span data-ttu-id="996b5-102">implicit(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="996b5-102">implicit (C# Reference)</span></span>
<span data-ttu-id="996b5-103">`implicit` 키워드는 암시적 사용자 정의 형식 변환 연산자를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="996b5-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="996b5-104">변환 시 데이터가 손실되지 않는 경우 이 키워드를 통해 사용자 정의 형식과 다른 형식 간에 암시적 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="996b5-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="996b5-105">예제</span><span class="sxs-lookup"><span data-stu-id="996b5-105">Example</span></span>  
 [!code-csharp[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 <span data-ttu-id="996b5-106">암시적 변환은 불필요한 캐스트를 제거하여 소스 코드 가독성을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="996b5-106">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="996b5-107">그러나 암시적 변환 시 프로그래머가 명시적으로 형식 간에 캐스팅할 필요가 없으므로 예기치 않은 결과를 방지하기 위해 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="996b5-107">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="996b5-108">일반적으로 암시적 변환 연산자는 예외를 throw하지 않고 정보가 손실되지 않으므로 프로그래머에게 알리지 않고 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="996b5-108">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="996b5-109">변환 연산자가 이러한 조건에 맞지 않는 경우 `explicit`로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="996b5-109">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="996b5-110">자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="996b5-110">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="996b5-111">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="996b5-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="996b5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="996b5-112">See Also</span></span>  
 [<span data-ttu-id="996b5-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="996b5-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="996b5-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="996b5-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="996b5-115">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="996b5-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="996b5-116">explicit</span><span class="sxs-lookup"><span data-stu-id="996b5-116">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)  
 [<span data-ttu-id="996b5-117">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="996b5-117">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="996b5-118">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="996b5-118">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
