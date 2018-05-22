---
title: '방법: 포인터 증가 및 감소(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: e1c3ac12a126450781d0ce78e788f39c740b5279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="db227-102">방법: 포인터 증가 및 감소(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="db227-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="db227-103">증가 및 감소 연산자인 `++` 및 `--`를 사용하여 pointer-type\* 형식의 포인터에 대한 포인터 위치를 [sizeof](../../../csharp/language-reference/keywords/sizeof.md)(`pointer-type`)만큼 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db227-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type\*.</span></span> <span data-ttu-id="db227-104">증가 및 감소 식은 다음 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="db227-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="db227-105">`void*` 형식을 제외한 모든 형식의 포인터에 증가 및 감소 연산자를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db227-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="db227-106">`pointer-type` 형식의 포인터에 증가 연산자를 적용할 경우 포인터 변수에 포함된 주소에 [sizeof](../../../csharp/language-reference/keywords/sizeof.md)(`pointer-type`)를 더하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db227-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="db227-107">`pointer-type` 형식의 포인터에 감소 연산자를 적용할 경우 포인터 변수에 포함된 주소에서 `sizeof`(`pointer-type`)를 빼는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db227-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="db227-108">연산이 포인터의 도메인을 오버플로하는 경우 예외가 생성되지 않고 결과는 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="db227-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db227-109">예</span><span class="sxs-lookup"><span data-stu-id="db227-109">Example</span></span>  
 <span data-ttu-id="db227-110">이 예제에서는 포인터를 `int` 크기만큼 증가하여 배열을 단계별로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="db227-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="db227-111">각 단계에서 주소와 배열 요소의 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="db227-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 <span data-ttu-id="db227-112">**Value:0 @ Address:12860272**</span><span class="sxs-lookup"><span data-stu-id="db227-112">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="db227-113">**Value:1 @ Address:12860276**</span><span class="sxs-lookup"><span data-stu-id="db227-113">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="db227-114">**Value:2 @ Address:12860280**</span><span class="sxs-lookup"><span data-stu-id="db227-114">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="db227-115">**Value:3 @ Address:12860284**</span><span class="sxs-lookup"><span data-stu-id="db227-115">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="db227-116">**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="db227-116">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="db227-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db227-117">See Also</span></span>  
 [<span data-ttu-id="db227-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="db227-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="db227-119">포인터 식</span><span class="sxs-lookup"><span data-stu-id="db227-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="db227-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="db227-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="db227-121">포인터 조작</span><span class="sxs-lookup"><span data-stu-id="db227-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="db227-122">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="db227-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="db227-123">유형</span><span class="sxs-lookup"><span data-stu-id="db227-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="db227-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="db227-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="db227-125">fixed 문</span><span class="sxs-lookup"><span data-stu-id="db227-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="db227-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="db227-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
