---
title: "방법: 포인터로 배열 요소 액세스(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
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
ms.openlocfilehash: 73f14aba63b7f7677a889f18cc1b410e3ecf1438
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="39cb1-102">방법: 포인터로 배열 요소 액세스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="39cb1-102">How to: Access an Array Element with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="39cb1-103">안전하지 않은 컨텍스트에서는 다음 예제와 같이 포인터 요소 액세스를 사용하여 메모리의 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39cb1-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 <span data-ttu-id="39cb1-104">대괄호 안의 식은 암시적으로 `int`, `uint`, `long` 또는 `ulong`으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39cb1-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="39cb1-105">p[e] 연산은 *(p+e)와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="39cb1-105">The operation p[e] is equivalent to *(p+e).</span></span> <span data-ttu-id="39cb1-106">C 및 C++와 마찬가지로 포인터 요소 액세스에서는 범위 이탈 오류를 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39cb1-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39cb1-107">예제</span><span class="sxs-lookup"><span data-stu-id="39cb1-107">Example</span></span>  
 <span data-ttu-id="39cb1-108">이 예제에서는 123개의 메모리 위치가 문자 배열 `charPointer`에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="39cb1-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="39cb1-109">이 배열은 두 개의 [for](../../../csharp/language-reference/keywords/for.md) 루프에서 소문자와 대문자를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="39cb1-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>  
  
 <span data-ttu-id="39cb1-110">`charPointer[i]` 식은 `*(charPointer + i)` 식과 동일하며 두 식 중 어느 식을 사용해도 같은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39cb1-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 <span data-ttu-id="39cb1-111">[!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="39cb1-111">[!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]</span></span>  
  
 <span data-ttu-id="39cb1-112">[!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="39cb1-112">[!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]</span></span>  
  
 <span data-ttu-id="39cb1-113">**대문자:**</span><span class="sxs-lookup"><span data-stu-id="39cb1-113">**Uppercase letters:**</span></span>  
<span data-ttu-id="39cb1-114">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="39cb1-114">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="39cb1-115">**소문자:**</span><span class="sxs-lookup"><span data-stu-id="39cb1-115">**Lowercase letters:**</span></span>  
<span data-ttu-id="39cb1-116">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="39cb1-116">**abcdefghijklmnopqrstuvwxyz**</span></span>   
## <a name="see-also"></a><span data-ttu-id="39cb1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39cb1-117">See Also</span></span>  
 <span data-ttu-id="39cb1-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="39cb1-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="39cb1-119">[포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="39cb1-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="39cb1-120">[포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="39cb1-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="39cb1-121">[형식](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="39cb1-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="39cb1-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="39cb1-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="39cb1-123">[fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="39cb1-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="39cb1-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="39cb1-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

