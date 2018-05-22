---
title: 암시적으로 형식화된 배열(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 60d320b233986154c3c51c409bade24d0862dedd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="4c0f4-102">암시적으로 형식화된 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4c0f4-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="4c0f4-103">배열 인스턴스의 형식이 배열 이니셜라이저에 지정된 요소에서 유추되는 암시적으로 형식화된 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="4c0f4-104">암시적으로 형식화된 변수에 대한 규칙은 암시적으로 형식화된 배열에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="4c0f4-105">자세한 내용은 [암시적으로 형식화된 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-105">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
 <span data-ttu-id="4c0f4-106">암시적으로 형식화된 배열은 일반적으로 무명 형식, 개체 및 컬렉션 이니셜라이저와 함께 쿼리 식에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>  
  
 <span data-ttu-id="4c0f4-107">다음 예제에서는 암시적으로 형식화된 배열을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-107">The following examples show how to create an implicitly-typed array:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 <span data-ttu-id="4c0f4-108">앞의 예제에서 암시적으로 형식화된 배열의 경우 초기화 문의 왼쪽에 대괄호가 사용되지 않는 것을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="4c0f4-109">또한 가변 배열이 1차원 배열과 마찬가지로 `new []`를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="4c0f4-110">개체 이니셜라이저의 암시적으로 형식화된 배열</span><span class="sxs-lookup"><span data-stu-id="4c0f4-110">Implicitly-typed Arrays in Object Initializers</span></span>  
 <span data-ttu-id="4c0f4-111">배열이 포함된 무명 형식을 만드는 경우 해당 형식의 개체 이니셜라이저에서 배열을 암시적으로 형식화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="4c0f4-112">다음 예제에서 `contacts`는 각각 `PhoneNumbers`라는 배열이 포함된 무명 형식의 암시적으로 형식화된 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="4c0f4-113">`var` 키워드는 개체 이니셜라이저 내부에서 사용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4c0f4-113">Note that the `var` keyword is not used inside the object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4c0f4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c0f4-114">See Also</span></span>  
 [<span data-ttu-id="4c0f4-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4c0f4-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4c0f4-116">암시적 형식 지역 변수</span><span class="sxs-lookup"><span data-stu-id="4c0f4-116">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)  
 [<span data-ttu-id="4c0f4-117">배열</span><span class="sxs-lookup"><span data-stu-id="4c0f4-117">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="4c0f4-118">익명 형식</span><span class="sxs-lookup"><span data-stu-id="4c0f4-118">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="4c0f4-119">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="4c0f4-119">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [<span data-ttu-id="4c0f4-120">var</span><span class="sxs-lookup"><span data-stu-id="4c0f4-120">var</span></span>](../../../csharp/language-reference/keywords/var.md)  
 [<span data-ttu-id="4c0f4-121">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="4c0f4-121">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
