---
title: 제네릭 및 배열(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 2e7ab9ff0dc4a73500c1a452df16af17c720d528
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="45bfc-102">제네릭 및 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="45bfc-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="45bfc-103">C# 2.0 이상에서 하한이 0인 1차원 배열은 자동으로 <xref:System.Collections.Generic.IList%601>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="45bfc-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="45bfc-104">이러한 특성으로 인해 동일한 코드를 사용하여 배열 및 기타 컬렉션 형식에서 반복할 수 있는 제네릭 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45bfc-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="45bfc-105">이 기술은 주로 컬렉션에서 데이터를 읽는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="45bfc-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="45bfc-106"><xref:System.Collections.Generic.IList%601> 인터페이스는 배열에서 요소를 추가하거나 제거하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45bfc-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="45bfc-107">이 컨텍스트의 배열에서 <xref:System.Collections.Generic.IList%601.RemoveAt%2A>과 같은 <xref:System.Collections.Generic.IList%601> 메서드를 호출하려는 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="45bfc-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="45bfc-108">다음 코드 예제는 <xref:System.Collections.Generic.IList%601> 입력 매개 변수를 사용하는 단일 제네릭 메서드가 목록과 배열(여기에서는 정수 배열) 모두를 통해 반복하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45bfc-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="45bfc-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45bfc-109">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="45bfc-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="45bfc-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="45bfc-111">제네릭</span><span class="sxs-lookup"><span data-stu-id="45bfc-111">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
 [<span data-ttu-id="45bfc-112">배열</span><span class="sxs-lookup"><span data-stu-id="45bfc-112">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="45bfc-113">제네릭</span><span class="sxs-lookup"><span data-stu-id="45bfc-113">Generics</span></span>](~/docs/standard/generics/index.md)
