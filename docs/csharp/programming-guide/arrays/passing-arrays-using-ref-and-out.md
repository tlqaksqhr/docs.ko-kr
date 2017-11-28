---
title: "ref 및 out을 사용하여 배열 전달(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: arrays [C#], passing using ref and out
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7f2d4e613491b26e82523d230398af3ec34b4d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-using-ref-and-out-c-programming-guide"></a><span data-ttu-id="f6513-102">ref 및 out을 사용하여 배열 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f6513-102">Passing Arrays Using ref and out (C# Programming Guide)</span></span>
<span data-ttu-id="f6513-103">모든 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수처럼 배열 형식의 `out` 매개 변수는 사용하기 전에 할당해야 합니다. 즉, 호출 수신자가 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-103">Like all [out](../../../csharp/language-reference/keywords/out.md) parameters, an `out` parameter of an array type must be assigned before it is used; that is, it must be assigned by the callee.</span></span> <span data-ttu-id="f6513-104">예:</span><span class="sxs-lookup"><span data-stu-id="f6513-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 <span data-ttu-id="f6513-105">모든 [ref](../../../csharp/language-reference/keywords/ref.md) 매개 변수와 마찬가지로 배열 형식의 `ref` 매개 변수에는 호출자에 의해 해당 매개 변수 값이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-105">Like all [ref](../../../csharp/language-reference/keywords/ref.md) parameters, a `ref` parameter of an array type must be definitely assigned by the caller.</span></span> <span data-ttu-id="f6513-106">즉, 이 경우의 이 매개 변수에는 피호출자에 의해 해당 값이 한정적으로 할당되지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-106">Therefore, there is no need to be definitely assigned by the callee.</span></span> <span data-ttu-id="f6513-107">배열 형식의 `ref` 매개 변수는 호출의 결과로 바뀔 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-107">A `ref` parameter of an array type may be altered as a result of the call.</span></span> <span data-ttu-id="f6513-108">예를 들어, 배열에 [null](../../../csharp/language-reference/keywords/null.md) 값을 할당하거나 다른 배열로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-108">For example, the array can be assigned the [null](../../../csharp/language-reference/keywords/null.md) value or can be initialized to a different array.</span></span> <span data-ttu-id="f6513-109">예:</span><span class="sxs-lookup"><span data-stu-id="f6513-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 <span data-ttu-id="f6513-110">다음 두 예제에서는 메서드에 배열을 전달하는 데 사용된 `out`과 `ref` 사이의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-110">The following two examples demonstrate the difference between `out` and `ref` when used in passing arrays to methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6513-111">예제</span><span class="sxs-lookup"><span data-stu-id="f6513-111">Example</span></span>  
 <span data-ttu-id="f6513-112">이 예제에서 `theArray` 배열은 호출자(`Main` 메서드)에서 선언되어 `FillArray` 메서드에서 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-112">In this example, the array `theArray` is declared in the caller (the `Main` method), and initialized in the `FillArray` method.</span></span> <span data-ttu-id="f6513-113">그런 다음 호출자로 배열 요소가 반환되어 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-113">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="f6513-114">예제</span><span class="sxs-lookup"><span data-stu-id="f6513-114">Example</span></span>  
 <span data-ttu-id="f6513-115">이 예제에서 `theArray` 배열은 호출자(`Main` 메서드)에서 초기화되고 `FillArray` 매개 변수를 사용하여 `ref` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-115">In this example, the array `theArray` is initialized in the caller (the `Main` method), and passed to the `FillArray` method by using the `ref` parameter.</span></span> <span data-ttu-id="f6513-116">일부 배열 요소는 `FillArray` 메서드에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-116">Some of the array elements are updated in the `FillArray` method.</span></span> <span data-ttu-id="f6513-117">그런 다음 호출자로 배열 요소가 반환되어 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6513-117">Then, the array elements are returned to the caller and displayed.</span></span>  
  
 [!code-csharp[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f6513-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6513-118">See Also</span></span>  
 [<span data-ttu-id="f6513-119">ref</span><span class="sxs-lookup"><span data-stu-id="f6513-119">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="f6513-120">out 매개 변수 한정자</span><span class="sxs-lookup"><span data-stu-id="f6513-120">out parameter modifier</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
 [<span data-ttu-id="f6513-121">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f6513-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f6513-122">배열</span><span class="sxs-lookup"><span data-stu-id="f6513-122">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="f6513-123">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="f6513-123">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="f6513-124">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="f6513-124">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="f6513-125">가변 배열</span><span class="sxs-lookup"><span data-stu-id="f6513-125">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
