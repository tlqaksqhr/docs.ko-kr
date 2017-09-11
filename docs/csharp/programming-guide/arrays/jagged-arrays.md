---
title: "가변 배열(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
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
ms.openlocfilehash: cb6c0823af37924235dba7daa20e607cb8402a79
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="aaab9-102">가변 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="aaab9-102">Jagged Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="aaab9-103">가변 배열의 요소에는 배열이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="aaab9-104">가변 배열의 요소는 차원과 크기가 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="aaab9-105">가변 배열을 “배열의 배열”이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="aaab9-106">다음 예제에서는 가변 배열을 선언, 초기화 및 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="aaab9-107">다음은 각각 정수의 1차원 배열인 세 개의 요소를 포함하는 1차원 배열의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 <span data-ttu-id="aaab9-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-108">[!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-109">`jaggedArray`를 사용하려면 먼저 해당 요소를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-109">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="aaab9-110">다음과 같이 요소를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-110">You can initialize the elements like this:</span></span>  
  
 <span data-ttu-id="aaab9-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-111">[!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-112">각 요소는 정수의 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-112">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="aaab9-113">첫 번째 요소는 5개 정수의 배열이고, 두 번째 요소는 4개 정수의 배열이고, 세 번째 요소는 2개 정수의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-113">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="aaab9-114">이니셜라이저를 사용하여 배열 요소에 값을 채울 수도 있으며, 이 경우 배열 크기가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-114">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="aaab9-115">예:</span><span class="sxs-lookup"><span data-stu-id="aaab9-115">For example:</span></span>  
  
 <span data-ttu-id="aaab9-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-116">[!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-117">다음과 같이 선언 시 배열을 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-117">You can also initialize the array upon declaration like this:</span></span>  
  
 <span data-ttu-id="aaab9-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-118">[!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-119">다음과 같은 약식 형태를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-119">You can use the following shorthand form.</span></span> <span data-ttu-id="aaab9-120">요소에 대한 기본 초기화가 없으므로 요소 초기화에서 `new` 연산자를 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-120">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 <span data-ttu-id="aaab9-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-121">[!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-122">가변 배열은 여러 배열로 구성되어 있기 때문에 해당 요소가 참조 형식이며, `null`로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-122">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="aaab9-123">다음 예제처럼 개별 배열 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-123">You can access individual array elements like these examples:</span></span>  
  
 <span data-ttu-id="aaab9-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-124">[!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-125">가변 배열과 다차원 배열을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-125">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="aaab9-126">다음은 서로 다른 크기의 세 가지 2차원 배열 요소를 포함하는 1차원 가변 배열의 선언과 초기화입니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-126">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="aaab9-127">2차원 배열에 대한 자세한 내용은 [다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aaab9-127">For more information about two-dimensional arrays, see [Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).</span></span>  
  
 <span data-ttu-id="aaab9-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-128">[!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-129">이 예제와 같이, 첫 번째 배열의 `[1,0]` 요소 값(값 `5`)을 표시하는 개별 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-129">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 <span data-ttu-id="aaab9-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-130">[!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-131">`Length` 메서드는 가변 배열에 포함된 배열 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-131">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="aaab9-132">예를 들어 이전 배열을 선언했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-132">For example, assuming you have declared the previous array, this line:</span></span>  
  
 <span data-ttu-id="aaab9-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-133">[!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]</span></span>  
  
 <span data-ttu-id="aaab9-134">이 경우 위 줄은 값 3을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-134">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaab9-135">예제</span><span class="sxs-lookup"><span data-stu-id="aaab9-135">Example</span></span>  
 <span data-ttu-id="aaab9-136">이 예제에서는 요소 자체가 배열인 배열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-136">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="aaab9-137">각 배열 요소의 크기가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="aaab9-137">Each one of the array elements has a different size.</span></span>  
  
 <span data-ttu-id="aaab9-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="aaab9-138">[!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaab9-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aaab9-139">See Also</span></span>  
 <span data-ttu-id="aaab9-140"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="aaab9-140"><xref:System.Array></span></span>   
 <span data-ttu-id="aaab9-141">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="aaab9-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="aaab9-142">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="aaab9-142">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="aaab9-143">[1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="aaab9-143">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 [<span data-ttu-id="aaab9-144">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="aaab9-144">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)

