---
title: "암시적으로 형식화된 배열(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: 13
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
ms.openlocfilehash: 5a042bdebd07062debe70cbea0a9661fbd425804
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="59946-102">암시적으로 형식화된 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="59946-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="59946-103">배열 인스턴스의 형식이 배열 이니셜라이저에 지정된 요소에서 유추되는 암시적으로 형식화된 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59946-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="59946-104">암시적으로 형식화된 변수에 대한 규칙은 암시적으로 형식화된 배열에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59946-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="59946-105">자세한 내용은 [암시적으로 형식화된 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59946-105">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
 <span data-ttu-id="59946-106">암시적으로 형식화된 배열은 일반적으로 무명 형식, 개체 및 컬렉션 이니셜라이저와 함께 쿼리 식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59946-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>  
  
 <span data-ttu-id="59946-107">다음 예제에서는 암시적으로 형식화된 배열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59946-107">The following examples show how to create an implicitly-typed array:</span></span>  
  
 <span data-ttu-id="59946-108">[!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="59946-108">[!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="59946-109">앞의 예제에서 암시적으로 형식화된 배열의 경우 초기화 문의 왼쪽에 대괄호가 사용되지 않는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="59946-109">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="59946-110">또한 가변 배열이 1차원 배열과 마찬가지로 `new []`를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="59946-110">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="59946-111">개체 이니셜라이저의 암시적으로 형식화된 배열</span><span class="sxs-lookup"><span data-stu-id="59946-111">Implicitly-typed Arrays in Object Initializers</span></span>  
 <span data-ttu-id="59946-112">배열이 포함된 무명 형식을 만드는 경우 해당 형식의 개체 이니셜라이저에서 배열을 암시적으로 형식화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59946-112">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="59946-113">다음 예제에서 `contacts`는 각각 `PhoneNumbers`라는 배열이 포함된 무명 형식의 암시적으로 형식화된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="59946-113">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="59946-114">`var` 키워드는 개체 이니셜라이저 내부에서 사용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="59946-114">Note that the `var` keyword is not used inside the object initializers.</span></span>  
  
 <span data-ttu-id="59946-115">[!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="59946-115">[!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59946-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59946-116">See Also</span></span>  
 <span data-ttu-id="59946-117">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="59946-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="59946-118">[암시적 형식 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) </span><span class="sxs-lookup"><span data-stu-id="59946-118">[Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) </span></span>  
 <span data-ttu-id="59946-119">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="59946-119">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="59946-120">[무명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="59946-120">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="59946-121">[개체 이니셜라이저 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="59946-121">[Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 <span data-ttu-id="59946-122">[var](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="59946-122">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 [<span data-ttu-id="59946-123">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="59946-123">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

