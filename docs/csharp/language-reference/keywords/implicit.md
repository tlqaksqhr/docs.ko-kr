---
title: "implicit(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- implicit
- implicit_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
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
ms.openlocfilehash: e4452a3bb6da2d0d294ca26d6b957f2c1c4402fd
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="implicit-c-reference"></a><span data-ttu-id="c1c80-102">implicit(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c1c80-102">implicit (C# Reference)</span></span>
<span data-ttu-id="c1c80-103">`implicit` 키워드는 암시적 사용자 정의 형식 변환 연산자를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c80-103">The `implicit` keyword is used to declare an implicit user-defined type conversion operator.</span></span> <span data-ttu-id="c1c80-104">변환 시 데이터가 손실되지 않는 경우 이 키워드를 통해 사용자 정의 형식과 다른 형식 간에 암시적 변환을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c80-104">Use it to enable implicit conversions between a user-defined type and another type, if the conversion is guaranteed not to cause a loss of data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1c80-105">예제</span><span class="sxs-lookup"><span data-stu-id="c1c80-105">Example</span></span>  
 <span data-ttu-id="c1c80-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c1c80-106">[!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]</span></span>  
  
 <span data-ttu-id="c1c80-107">암시적 변환은 불필요한 캐스트를 제거하여 소스 코드 가독성을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c80-107">By eliminating unnecessary casts, implicit conversions can improve source code readability.</span></span> <span data-ttu-id="c1c80-108">그러나 암시적 변환 시 프로그래머가 명시적으로 형식 간에 캐스팅할 필요가 없으므로 예기치 않은 결과를 방지하기 위해 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c80-108">However, because implicit conversions do not require programmers to explicitly cast from one type to the other, care must be taken to prevent unexpected results.</span></span> <span data-ttu-id="c1c80-109">일반적으로 암시적 변환 연산자는 예외를 throw하지 않고 정보가 손실되지 않으므로 프로그래머에게 알리지 않고 안전하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c80-109">In general, implicit conversion operators should never throw exceptions and never lose information so that they can be used safely without the programmer's awareness.</span></span> <span data-ttu-id="c1c80-110">변환 연산자가 이러한 조건에 맞지 않는 경우 `explicit`로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c80-110">If a conversion operator cannot meet those criteria, it should be marked `explicit`.</span></span> <span data-ttu-id="c1c80-111">자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1c80-111">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c1c80-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c1c80-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c1c80-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1c80-113">See Also</span></span>  
 <span data-ttu-id="c1c80-114">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1c80-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c1c80-115">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1c80-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c1c80-116">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c1c80-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c1c80-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="c1c80-117">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 <span data-ttu-id="c1c80-118">[연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="c1c80-118">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 [<span data-ttu-id="c1c80-119">방법: 구조체 간의 사용자 정의 변환 구현</span><span class="sxs-lookup"><span data-stu-id="c1c80-119">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

