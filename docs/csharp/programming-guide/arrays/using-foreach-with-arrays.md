---
title: 배열에 foreach 사용(C# 프로그래밍 가이드)
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: b858f35167e24390a729769487ce98908a3d349f
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
ms.locfileid: "34549457"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="ab0ea-102">배열에 foreach 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ab0ea-102">Using foreach with Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="ab0ea-103">[foreach](../../language-reference/keywords/foreach-in.md) 문은 배열의 요소를 반복하는 단순하고 깔끔한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="ab0ea-104">1차원 배열의 경우 `foreach` 문은 인덱스 0으로 시작하고 인덱스 `Length - 1`로 끝나는 늘어나는 인덱스 순서로 요소를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

[!code-csharp[csProgGuideArrays#28](./codesnippet/CSharp/using-foreach-with-arrays_1.cs)]

<span data-ttu-id="ab0ea-105">다차원 배열의 경우 요소는 가장 오른쪽 차원의 인덱스가 먼저 증가한 이후, 다음 왼쪽 차원의 인덱스, 그다음 왼쪽 차원의 인덱스가 증가하는 방식으로 트래버스됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

[!code-csharp[csProgGuideArrays#29](./codesnippet/CSharp/using-foreach-with-arrays_2.cs)]

<span data-ttu-id="ab0ea-106">그러나 다차원 배열에서 중첩 [for](../../language-reference/keywords/for.md) 루프를 사용하면 배열 요소를 처리하는 순서를 더 강력하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab0ea-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab0ea-107">See also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="ab0ea-108">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ab0ea-108">C# Programming Guide</span></span>](../index.md)  
 [<span data-ttu-id="ab0ea-109">배열</span><span class="sxs-lookup"><span data-stu-id="ab0ea-109">Arrays</span></span>](index.md)  
 [<span data-ttu-id="ab0ea-110">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="ab0ea-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)  
 [<span data-ttu-id="ab0ea-111">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="ab0ea-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)  
 [<span data-ttu-id="ab0ea-112">가변 배열</span><span class="sxs-lookup"><span data-stu-id="ab0ea-112">Jagged Arrays</span></span>](jagged-arrays.md)
