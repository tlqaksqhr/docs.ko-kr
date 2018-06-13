---
title: '방법: 포인터로 배열 요소 액세스(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 92eb7a79c0e7522d1474537aeefbfdb083a11dc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332041"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="85b2a-102">방법: 포인터로 배열 요소 액세스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="85b2a-102">How to: Access an Array Element with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="85b2a-103">안전하지 않은 컨텍스트에서는 다음 예제와 같이 포인터 요소 액세스를 사용하여 메모리의 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 <span data-ttu-id="85b2a-104">대괄호 안의 식은 암시적으로 `int`, `uint`, `long` 또는 `ulong`으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="85b2a-105">p[e] 연산은 \*(p+e)와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-105">The operation p[e] is equivalent to \*(p+e).</span></span> <span data-ttu-id="85b2a-106">C 및 C++와 마찬가지로 포인터 요소 액세스에서는 범위 이탈 오류를 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85b2a-107">예</span><span class="sxs-lookup"><span data-stu-id="85b2a-107">Example</span></span>  
 <span data-ttu-id="85b2a-108">이 예제에서는 123개의 메모리 위치가 문자 배열 `charPointer`에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="85b2a-109">이 배열은 두 개의 [for](../../../csharp/language-reference/keywords/for.md) 루프에서 소문자와 대문자를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>  
  
 <span data-ttu-id="85b2a-110">`charPointer[i]` 식은 `*(charPointer + i)` 식과 동일하며 두 식 중 어느 식을 사용해도 같은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b2a-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
 <span data-ttu-id="85b2a-111">**대문자:**</span><span class="sxs-lookup"><span data-stu-id="85b2a-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="85b2a-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="85b2a-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="85b2a-113">**소문자:**</span><span class="sxs-lookup"><span data-stu-id="85b2a-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="85b2a-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="85b2a-114">**abcdefghijklmnopqrstuvwxyz**</span></span>   
## <a name="see-also"></a><span data-ttu-id="85b2a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85b2a-115">See Also</span></span>  
 [<span data-ttu-id="85b2a-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="85b2a-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="85b2a-117">포인터 식</span><span class="sxs-lookup"><span data-stu-id="85b2a-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="85b2a-118">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="85b2a-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="85b2a-119">유형</span><span class="sxs-lookup"><span data-stu-id="85b2a-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="85b2a-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="85b2a-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="85b2a-121">fixed 문</span><span class="sxs-lookup"><span data-stu-id="85b2a-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="85b2a-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="85b2a-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
