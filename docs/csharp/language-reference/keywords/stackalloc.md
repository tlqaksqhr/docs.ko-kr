---
title: stackalloc(C# 참조)
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 905873cf7f576ff35a9bc1c182ce7ebe17920288
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="c2caf-102">stackalloc(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c2caf-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="c2caf-103">`stackalloc` 키워드는 스택에 메모리 블록을 할당하기 위해 안전하지 않은 코드 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a><span data-ttu-id="c2caf-104">설명</span><span class="sxs-lookup"><span data-stu-id="c2caf-104">Remarks</span></span>

<span data-ttu-id="c2caf-105">이 키워드는 지역 변수 이니셜라이저에서만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="c2caf-106">다음 코드를 실행하면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-106">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

<span data-ttu-id="c2caf-107">C# 7.3부터는 `stackalloc` 배열에 대한 배열 이니셜라이저 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-107">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="c2caf-108">다음 선언은 모두 값이 정수 `1`, `2` 및 `3`인 세 개의 요소가 있는 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-108">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`:</span></span>

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="c2caf-109">포인터 형식이 사용되므로 `stackalloc`에 [안전하지 않은](unsafe.md) 컨텍스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-109">Because pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="c2caf-110">자세한 내용은 [안전하지 않은 코드 및 포인터](../../programming-guide/unsafe-code-pointers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2caf-110">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md)</span></span> 

<span data-ttu-id="c2caf-111">`stackalloc`는 C 런타임 라이브러리의 [_alloca](/cpp/c-runtime-library/reference/alloca)와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-111">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="c2caf-112">예제</span><span class="sxs-lookup"><span data-stu-id="c2caf-112">Examples</span></span>

<span data-ttu-id="c2caf-113">다음 예제에서는 피보나치 시퀀스의 처음 20개 숫자를 계산하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-113">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="c2caf-114">각 숫자는 이전 두 숫자의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-114">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="c2caf-115">코드에서 `int` 형식의 요소 20개를 포함하기에 충분한 크기의 메모리 블록이 힙이 아니라 스택에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-115">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="c2caf-116">블록의 주소는 `fib` 포인터에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-116">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="c2caf-117">이 메모리에는 가비지 수집이 적용되지 않으므로 [fixed](fixed-statement.md)를 사용하여 고정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-117">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="c2caf-118">메모리 블록의 수명은 이 수명을 정의하는 메서드의 수명으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-118">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="c2caf-119">메서드가 반환되기 전에는 메모리를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-119">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="c2caf-120">다음 예제에서는 정수의 `stackalloc` 배열을 각 요소에 하나의 비트가 설정된 비트 마스크로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-120">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="c2caf-121">다음은 C# 7.3부터 사용할 수 있는 새 이니셜라이저 구문을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-121">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="c2caf-122">보안</span><span class="sxs-lookup"><span data-stu-id="c2caf-122">Security</span></span>

<span data-ttu-id="c2caf-123">안전하지 않은 코드는 안전한 코드보다 보안 수준이 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-123">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="c2caf-124">그러나 `stackalloc`를 사용하면 CLR(공용 언어 런타임)에서 버퍼 오버런 검색 기능이 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-124">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="c2caf-125">버퍼 오버런이 검색되면 악성 코드가 실행될 가능성을 최소화하기 위해 최대한 빨리 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2caf-125">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c2caf-126">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c2caf-126">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c2caf-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2caf-127">See Also</span></span>
 [<span data-ttu-id="c2caf-128">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c2caf-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c2caf-129">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c2caf-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c2caf-130">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="c2caf-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c2caf-131">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="c2caf-131">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="c2caf-132">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="c2caf-132">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
