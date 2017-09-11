---
title: "ref 및 out을 사용하여 배열 전달(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
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
ms.openlocfilehash: 58fc359881295a9e6627ac1269ef17aa298009c7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="3756c-102">ref 및 out을 사용하여 배열 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3756c-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="3756c-103">모든 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수처럼 배열 형식의 `out` 매개 변수는 사용하기 전에 할당해야 합니다. 즉, 호출 수신자가 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="3756c-104">예:</span><span class="sxs-lookup"><span data-stu-id="3756c-104">For example:</span></span>  
  
 <span data-ttu-id="3756c-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3756c-105">[!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]</span></span>  
  
 <span data-ttu-id="3756c-106">모든 [ref](../../../csharp/language-reference/keywords/ref.md) 매개 변수와 마찬가지로 배열 형식의 `ref` 매개 변수에는 호출자에 의해 해당 매개 변수 값이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-106">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="3756c-107">즉, 이 경우의 이 매개 변수에는 피호출자에 의해 해당 값이 한정적으로 할당되지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-107">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="3756c-108">배열 형식의 `ref` 매개 변수는 호출의 결과로 바뀔 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-108">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="3756c-109">예를 들어, 배열에 [null](../../../csharp/language-reference/keywords/null.md) 값을 할당하거나 다른 배열로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-109">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="3756c-110">예:</span><span class="sxs-lookup"><span data-stu-id="3756c-110">For example:</span></span>  
  
 <span data-ttu-id="3756c-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3756c-111">[!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]</span></span>  
  
 <span data-ttu-id="3756c-112">다음 두 예제에서는 메서드에 배열을 전달하는 데 사용된 `out`과 `ref` 사이의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-112">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3756c-113">예제</span><span class="sxs-lookup"><span data-stu-id="3756c-113">Example</span></span>  
 <span data-ttu-id="3756c-114">이 예제에서 `theArray` 배열은 호출자(`Main` 메서드)에서 선언되어 `FillArray` 메서드에서 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-114">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="3756c-115">그런 다음 호출자로 배열 요소가 반환되어 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-115">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="3756c-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="3756c-116">[!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3756c-117">예제</span><span class="sxs-lookup"><span data-stu-id="3756c-117">Example</span></span>  
 <span data-ttu-id="3756c-118">이 예제에서 `theArray` 배열은 호출자(`Main` 메서드)에서 초기화되고 `FillArray` 매개 변수를 사용하여 `ref` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-118">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="3756c-119">일부 배열 요소는 `FillArray` 메서드에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-119">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="3756c-120">그런 다음 호출자로 배열 요소가 반환되어 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3756c-120">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 <span data-ttu-id="3756c-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="3756c-121">[!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3756c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3756c-122">See Also</span></span>  
 <span data-ttu-id="3756c-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="3756c-123">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 <span data-ttu-id="3756c-124">[out 매개 변수 한정자](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="3756c-124">[out parameter modifier](../../../csharp/language-reference/keywords/out-parameter-modifier.md) </span></span>  
 <span data-ttu-id="3756c-125">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3756c-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3756c-126">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="3756c-126">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="3756c-127">[1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="3756c-127">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="3756c-128">[다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="3756c-128">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="3756c-129">가변 배열</span><span class="sxs-lookup"><span data-stu-id="3756c-129">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

