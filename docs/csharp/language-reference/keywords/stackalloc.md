---
title: "stackalloc(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b9c5328bfa1b0fc9a7751763c7d728096886905
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="aa79b-102">stackalloc(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="aa79b-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="aa79b-103">`stackalloc` 키워드는 스택에 메모리 블록을 할당하기 위해 안전하지 않은 코드 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```csharp  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="aa79b-104">설명</span><span class="sxs-lookup"><span data-stu-id="aa79b-104">Remarks</span></span>  
 <span data-ttu-id="aa79b-105">이 키워드는 지역 변수 이니셜라이저에서만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="aa79b-106">다음 코드를 실행하면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-106">The following code causes compiler errors.</span></span>  
  
```csharp  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="aa79b-107">포인터 형식이 사용되므로 `stackalloc`에 [안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="aa79b-108">자세한 내용은 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa79b-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="aa79b-109">`stackalloc`는 C 런타임 라이브러리의 [_alloca](/cpp/c-runtime-library/reference/alloca)와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="aa79b-110">다음 예제에서는 피보나치 시퀀스의 처음 20개 숫자를 계산하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="aa79b-111">각 숫자는 이전 두 숫자의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="aa79b-112">코드에서 `int` 형식의 요소 20개를 포함하기에 충분한 크기의 메모리 블록이 힙이 아니라 스택에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="aa79b-113">블록의 주소는 `fib` 포인터에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="aa79b-114">이 메모리에는 가비지 수집이 적용되지 않으므로 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)를 사용하여 고정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="aa79b-115">메모리 블록의 수명은 이 수명을 정의하는 메서드의 수명으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="aa79b-116">메서드가 반환되기 전에는 메모리를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa79b-117">예</span><span class="sxs-lookup"><span data-stu-id="aa79b-117">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a><span data-ttu-id="aa79b-118">보안</span><span class="sxs-lookup"><span data-stu-id="aa79b-118">Security</span></span>  
 <span data-ttu-id="aa79b-119">안전하지 않은 코드는 안전한 코드보다 보안 수준이 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-119">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="aa79b-120">그러나 `stackalloc`를 사용하면 CLR(공용 언어 런타임)에서 버퍼 오버런 검색 기능이 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-120">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="aa79b-121">버퍼 오버런이 검색되면 악성 코드가 실행될 가능성을 최소화하기 위해 최대한 빨리 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa79b-121">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="aa79b-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="aa79b-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa79b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa79b-123">See Also</span></span>  
 [<span data-ttu-id="aa79b-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="aa79b-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="aa79b-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="aa79b-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="aa79b-126">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="aa79b-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="aa79b-127">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="aa79b-127">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="aa79b-128">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="aa79b-128">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
