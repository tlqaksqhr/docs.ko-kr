---
title: "1차원 배열(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
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
ms.openlocfilehash: cc42640715274b89c4c4a12ced8c0ae6af603318
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="c0469-102">1차원 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="c0469-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="c0469-103">다음 예제와 같이 5개 정수의 1차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 <span data-ttu-id="c0469-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0469-104">[!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="c0469-105">이 배열에는 `array[0]` ~ `array[4]`의 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-105">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="c0469-106">[new](../../../csharp/language-reference/keywords/new.md) 연산자는 배열을 만들고 배열 요소를 기본값으로 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-106">The [new](../../../csharp/language-reference/keywords/new.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="c0469-107">이 예제에서는 모든 배열 요소가 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-107">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="c0469-108">동일한 방식으로 문자열 요소를 저장하는 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-108">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="c0469-109">예:</span><span class="sxs-lookup"><span data-stu-id="c0469-109">For example:</span></span>  
  
 <span data-ttu-id="c0469-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0469-110">[!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_2.cs)]</span></span>  
  
## <a name="array-initialization"></a><span data-ttu-id="c0469-111">배열 초기화</span><span class="sxs-lookup"><span data-stu-id="c0469-111">Array Initialization</span></span>  
 <span data-ttu-id="c0469-112">선언 시 배열을 초기화할 수 있으며, 이 경우 차수 지정자가 초기화 목록에 있는 요소 수에 의해 제공되기 때문에 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-112">It is possible to initialize an array upon declaration, in which case, the rank specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="c0469-113">예:</span><span class="sxs-lookup"><span data-stu-id="c0469-113">For example:</span></span>  
  
 <span data-ttu-id="c0469-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0469-114">[!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="c0469-115">문자열 배열도 동일한 방식으로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-115">A string array can be initialized in the same way.</span></span> <span data-ttu-id="c0469-116">다음은 각 배열 요소가 하루의 이름으로 초기화되는 문자열 배열의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-116">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
  
 <span data-ttu-id="c0469-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0469-117">[!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="c0469-118">선언 시 배열을 초기화하면 다음 바로 가기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-118">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 <span data-ttu-id="c0469-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0469-119">[!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="c0469-120">초기화하지 않고 배열 변수를 선언할 수 있지만 이 변수에 배열을 할당할 때 `new` 연산자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-120">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="c0469-121">예:</span><span class="sxs-lookup"><span data-stu-id="c0469-121">For example:</span></span>  
  
 <span data-ttu-id="c0469-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0469-122">[!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="c0469-123">C# 3.0에서는 암시적으로 형식화된 배열이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-123">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="c0469-124">자세한 내용은 [암시적으로 형식화된 배열](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0469-124">For more information, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="c0469-125">값 형식 및 참조 형식 배열</span><span class="sxs-lookup"><span data-stu-id="c0469-125">Value Type and Reference Type Arrays</span></span>  
 <span data-ttu-id="c0469-126">다음 배열 선언을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="c0469-126">Consider the following array declaration:</span></span>  
  
 <span data-ttu-id="c0469-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="c0469-127">[!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/CSharp/single-dimensional-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="c0469-128">이 문의 결과는 `SomeType`이 값 형식인지 또는 참조 형식인지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-128">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="c0469-129">값 형식인 경우 이 문은 각각 `SomeType` 형식인 10개 요소의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-129">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="c0469-130">`SomeType`이 참조 형식인 경우 이 문은 각각 null 참조로 초기화된 10개 요소의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0469-130">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
 <span data-ttu-id="c0469-131">값 형식과 참조 형식에 대한 자세한 내용은 [형식](../../../csharp/language-reference/keywords/types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c0469-131">For more information about value types and reference types, see [Types](../../../csharp/language-reference/keywords/types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0469-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0469-132">See Also</span></span>  
 <span data-ttu-id="c0469-133"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="c0469-133"><xref:System.Array></span></span>   
 <span data-ttu-id="c0469-134">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0469-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c0469-135">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0469-135">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="c0469-136">[다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="c0469-136">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="c0469-137">가변 배열</span><span class="sxs-lookup"><span data-stu-id="c0469-137">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

