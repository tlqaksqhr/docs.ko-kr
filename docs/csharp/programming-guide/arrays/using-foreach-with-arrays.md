---
title: 배열에 foreach 사용(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 8511d9dd3b7155d2f6bca229f264071b54ed173b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="e0abb-102">배열에 foreach 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e0abb-102">Using foreach with Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="e0abb-103">C#에서는 또한 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 제공하여</span><span class="sxs-lookup"><span data-stu-id="e0abb-103">C# also provides the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="e0abb-104">배열 또는 열거형 컬렉션의 요소를 간단하게 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0abb-104">This statement provides a simple, clean way to iterate through the elements of an array or any enumerable collection.</span></span> <span data-ttu-id="e0abb-105">`foreach` 문은 배열 또는 컬렉션 형식의 열거자에서 반환한 순서대로 요소를 처리합니다(일반적으로 0번째부터 마지막까지).</span><span class="sxs-lookup"><span data-stu-id="e0abb-105">The `foreach` statement processes elements in the order returned by the array or collection type’s enumerator, which is usually from the 0th element to the last.</span></span> <span data-ttu-id="e0abb-106">예를 들어, 다음 코드에서는 `numbers`라는 배열을 만들어 `foreach` 문으로 배열의 요소를 반복하여 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0abb-106">For example, the following code creates an array called `numbers` and iterates through it with the `foreach` statement:</span></span>  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 <span data-ttu-id="e0abb-107">다차원 배열의 경우에도 같은 방법으로 요소를 반복 실행할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0abb-107">With multidimensional arrays, you can use the same method to iterate through the elements, for example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 <span data-ttu-id="e0abb-108">그러나 다차원 배열에서 중첩 [for](../../../csharp/language-reference/keywords/for.md) 루프를 사용하면 배열 요소를 보다 강력하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0abb-108">However, with multidimensional arrays, using a nested [for](../../../csharp/language-reference/keywords/for.md) loop gives you more control over the array elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0abb-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0abb-109">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="e0abb-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e0abb-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e0abb-111">배열</span><span class="sxs-lookup"><span data-stu-id="e0abb-111">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="e0abb-112">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="e0abb-112">Single-Dimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [<span data-ttu-id="e0abb-113">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="e0abb-113">Multidimensional Arrays</span></span>](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [<span data-ttu-id="e0abb-114">가변 배열</span><span class="sxs-lookup"><span data-stu-id="e0abb-114">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)
