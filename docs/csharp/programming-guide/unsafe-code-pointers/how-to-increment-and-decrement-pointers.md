---
title: "방법: 포인터 증가 및 감소(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
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
ms.openlocfilehash: b474249ed9f7778e44981b292d51f29f46bc420d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="5c69e-102">방법: 포인터 증가 및 감소(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5c69e-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="5c69e-103">증가 및 감소 연산자인 `++` 및 `--`를 사용하여 pointer-type* 형식의 포인터에 대한 포인터 위치를 [sizeof](../../../csharp/language-reference/keywords/sizeof.md)(`pointer-type`)만큼 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="5c69e-104">증가 및 감소 식은 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="5c69e-105">`void*` 형식을 제외한 모든 형식의 포인터에 증가 및 감소 연산자를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="5c69e-106">`pointer-type` 형식의 포인터에 증가 연산자를 적용할 경우 포인터 변수에 포함된 주소에 [sizeof](../../../csharp/language-reference/keywords/sizeof.md)(`pointer-type`)를 더하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="5c69e-107">`pointer-type` 형식의 포인터에 감소 연산자를 적용할 경우 포인터 변수에 포함된 주소에서 `sizeof`(`pointer-type`)를 빼는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="5c69e-108">연산이 포인터의 도메인을 오버플로하는 경우 예외가 생성되지 않고 결과는 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c69e-109">예제</span><span class="sxs-lookup"><span data-stu-id="5c69e-109">Example</span></span>  
 <span data-ttu-id="5c69e-110">이 예제에서는 포인터를 `int` 크기만큼 증가하여 배열을 단계별로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="5c69e-111">각 단계에서 주소와 배열 요소의 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5c69e-111">With each step, you display the address and the content of the array element.</span></span>  
  
 <span data-ttu-id="5c69e-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c69e-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="5c69e-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5c69e-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span></span>  
  
 <span data-ttu-id="5c69e-114">**Value:0 @ Address:12860272**</span><span class="sxs-lookup"><span data-stu-id="5c69e-114">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="5c69e-115">**Value:1 @ Address:12860276**</span><span class="sxs-lookup"><span data-stu-id="5c69e-115">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="5c69e-116">**Value:2 @ Address:12860280**</span><span class="sxs-lookup"><span data-stu-id="5c69e-116">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="5c69e-117">**Value:3 @ Address:12860284**</span><span class="sxs-lookup"><span data-stu-id="5c69e-117">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="5c69e-118">**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="5c69e-118">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="5c69e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c69e-119">See Also</span></span>  
 <span data-ttu-id="5c69e-120">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5c69e-121">[포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="5c69e-122">[C# 연산자](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="5c69e-123">[포인터 조작](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="5c69e-124">[포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="5c69e-125">[형식](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="5c69e-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="5c69e-127">[fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5c69e-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="5c69e-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="5c69e-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

