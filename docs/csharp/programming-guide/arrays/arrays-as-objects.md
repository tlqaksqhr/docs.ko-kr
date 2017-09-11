---
title: "개체 형식 배열(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
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
ms.openlocfilehash: 396d0df9196b7331e94127730b83782ffc8ea593
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="33c65-102">개체 형식 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="33c65-102">Arrays as Objects (C# Programming Guide)</span></span>
<span data-ttu-id="33c65-103">C#의 배열은 C 및 C++와 같이 인접한 메모리의 주소 지정 가능한 영역이 아니라 실제로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="33c65-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="33c65-104"><xref:System.Array>는 모든 배열 형식의 추상 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="33c65-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="33c65-105"><xref:System.Array>에 포함된 속성 및 다른 클래스 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33c65-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="33c65-106">이러한 예로 <xref:System.Array.Length%2A> 속성을 사용하여 배열의 길이를 가져오는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33c65-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="33c65-107">다음 코드에서는 `numbers` 배열의 길이(`5`)를 `lengthOfNumbers`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="33c65-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 <span data-ttu-id="33c65-108">[!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="33c65-108">[!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]</span></span>  
  
 <span data-ttu-id="33c65-109"><xref:System.Array> 클래스는 배열의 정렬, 검색 및 복사를 위한 다른 여러 유용한 메서드와 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33c65-109">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33c65-110">예제</span><span class="sxs-lookup"><span data-stu-id="33c65-110">Example</span></span>  
 <span data-ttu-id="33c65-111">이 예제에서는 <xref:System.Array.Rank%2A> 속성을 사용하여 배열의 차원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="33c65-111">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 <span data-ttu-id="33c65-112">[!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="33c65-112">[!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c65-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33c65-113">See Also</span></span>  
 <span data-ttu-id="33c65-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="33c65-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="33c65-115">[배열](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="33c65-115">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="33c65-116">[1차원 배열](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="33c65-116">[Single-Dimensional Arrays](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md) </span></span>  
 <span data-ttu-id="33c65-117">[다차원 배열](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="33c65-117">[Multidimensional Arrays](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) </span></span>  
 [<span data-ttu-id="33c65-118">가변 배열</span><span class="sxs-lookup"><span data-stu-id="33c65-118">Jagged Arrays</span></span>](../../../csharp/programming-guide/arrays/jagged-arrays.md)

