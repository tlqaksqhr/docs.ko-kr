---
title: fixed 문(C# 참조)
ms.date: 04/20/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: e1664f508cb861ffa73b800eeb0da3a1f1cdc432
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="4c62e-102">fixed 문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4c62e-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="4c62e-103">`fixed` 문은 가비지 수집기에서 이동 가능한 변수를 재배치할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="4c62e-104">`fixed` 문은 [unsafe](unsafe.md) 컨텍스트에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="4c62e-105">`Fixed`를 사용하여 [고정 크기 버퍼](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-105">`Fixed` can also be used to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="4c62e-106">`fixed` 문은 관리되는 변수에 대한 포인터를 설정하고 문을 실행하는 동안 해당 변수를 "고정"합니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="4c62e-107">이동 가능한 관리되는 변수에 대한 포인터는 `fixed` 컨텍스트에만 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="4c62e-108">`fixed` 컨텍스트 없는 가비지 수집은 예기치 않게 변수를 재배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="4c62e-109">C# 컴파일러만 `fixed` 문에서 관리되는 변수에 대한 포인터를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="4c62e-110">배열, 문자열, 고정 크기 버퍼 또는 변수의 주소를 사용하여 포인터를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="4c62e-111">다음 예제에서는 변수 주소, 배열 및 문자열의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="4c62e-112">고정 크기 버퍼에 대한 자세한 내용은 [고정 크기 버퍼](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c62e-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="4c62e-113">여러 개의 포인터가 모두 동일한 형식인 경우 하나의 명령문에서 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-113">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="4c62e-114">형식이 다른 포인터를 초기화하려면 다음 예제와 같이 `fixed` 문을 중첩하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-114">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="4c62e-115">이 문의 코드를 실행하면 고정된 모든 변수가 고정 해제되고 가비지 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-115">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="4c62e-116">따라서 `fixed` 문 외부에서 해당 변수를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-116">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="4c62e-117">`fixed` 명령문 내에서 선언된 변수는 해당 명령문에 범위가 지정되어 다음을 더 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-117">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="4c62e-118">`fixed` 명령문에서 초기화된 포인터는 읽기 전용 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-118">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="4c62e-119">포인터 값을 수정하려는 경우 두 번째 포인터 변수를 선언하고 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-119">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="4c62e-120">`fixed` 명령문에서 선언된 변수는 을 수정될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-120">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


<span data-ttu-id="4c62e-121">안전하지 않은 모드에서는 가비지 수집되지 않아 고정할 필요가 없는 스택에서 메모리를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c62e-121">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="4c62e-122">자세한 내용은 [stackalloc](stackalloc.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c62e-122">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="4c62e-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4c62e-123">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4c62e-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c62e-124">See Also</span></span>

 [<span data-ttu-id="4c62e-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4c62e-125">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="4c62e-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4c62e-126">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="4c62e-127">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="4c62e-127">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="4c62e-128">unsafe</span><span class="sxs-lookup"><span data-stu-id="4c62e-128">unsafe</span></span>](unsafe.md)  
 [<span data-ttu-id="4c62e-129">고정 크기 버퍼</span><span class="sxs-lookup"><span data-stu-id="4c62e-129">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
