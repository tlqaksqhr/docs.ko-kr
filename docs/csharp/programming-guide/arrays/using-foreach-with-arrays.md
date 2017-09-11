---
title: "배열에 foreach 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
caps.latest.revision: 14
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
ms.openlocfilehash: a1d0b704233b110b5f499b8186a4a901f9b5408f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="97e2c-102">배열에 foreach 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="97e2c-102">Using foreach with Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="97e2c-103">C#에서는 또한 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 제공하여</span><span class="sxs-lookup"><span data-stu-id="97e2c-103">C# also provides the [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span> <span data-ttu-id="97e2c-104">배열 또는 열거형 컬렉션의 요소를 간단하게 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e2c-104">This statement provides a simple, clean way to iterate through the elements of an array or any enumerable collection.</span></span> <span data-ttu-id="97e2c-105">`foreach` 문은 배열 또는 컬렉션 형식의 열거자에서 반환한 순서대로 요소를 처리합니다(일반적으로 0번째부터 마지막까지).</span><span class="sxs-lookup"><span data-stu-id="97e2c-105">The `foreach` statement processes elements in the order returned by the array or collection type’s enumerator, which is usually from the 0th element to the last.</span></span> <span data-ttu-id="97e2c-106">예를 들어, 다음 코드에서는 `numbers`라는 배열을 만들어 `foreach` 문으로 배열의 요소를 반복하여 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97e2c-106">For example, the following code creates an array called `numbers` and iterates through it with the `foreach` statement:</span></span>  
  
 <span data-ttu-id="97e2c-107">[!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="97e2c-107">[!code-cs[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]</span></span>  
  
 <span data-ttu-id="97e2c-108">다차원 배열의 경우에도 같은 방법으로 요소를 반복 실행할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97e2c-108">With multidimensional arrays, you can use the same method to iterate through the elements, for example:</span></span>  
  
 <span data-ttu-id="97e2c-109">[!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="97e2c-109">[!code-cs[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]</span></span>  
  
 <span data-ttu-id="97e2c-110">그러나 다차원 배열에서 중첩 [for](../../../csharp/language-reference/keywords/for.md) 루프를 사용하면 배열 요소를 보다 강력하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e2c-110">However, with multidimensional arrays, using a nested [for](../../../csharp/language-reference/keywords/for.md) loop gives you more control over the array elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e2c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97e2c-111">See Also</span></span>  
 <span data-ttu-id="97e2c-112"><xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="97e2c-112"><xref:System.Array></span></span>   
 <span data-ttu-id="97e2c-113">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="97e2c-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="97e2c-114">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="97e2c-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="97e2c-115">[1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="97e2c-115">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="97e2c-116">[다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="97e2c-116">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="97e2c-117">가변 배열</span><span class="sxs-lookup"><span data-stu-id="97e2c-117">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

