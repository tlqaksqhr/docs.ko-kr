---
title: fixed 문(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13633e71c863b075eede41c9a18419d65350bdb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="e0afc-102">fixed 문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e0afc-102">fixed Statement (C# Reference)</span></span>
<span data-ttu-id="e0afc-103">`fixed` 문은 가비지 수집기에서 이동 가능한 변수를 재배치할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="e0afc-104">`fixed` 문은 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-104">The `fixed` statement is only permitted in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="e0afc-105">`Fixed`를 사용하여 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-105">`Fixed` can also be used to create [fixed size buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="e0afc-106">`fixed` 문은 관리되는 변수에 대한 포인터를 설정하고 문을 실행하는 동안 해당 변수를 "고정"합니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="e0afc-107">`fixed`를 사용하지 않으면 가비지 수집에서 변수를 예기치 않게 재배치할 수 있으므로 이동 가능한 관리되는 변수에 대한 포인터가 거의 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-107">Without `fixed`, pointers to movable managed variables would be of little use since garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="e0afc-108">C# 컴파일러만 `fixed` 문에서 관리되는 변수에 대한 포인터를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-108">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 <span data-ttu-id="e0afc-109">배열, 문자열, 고정 크기 버퍼 또는 변수의 주소를 사용하여 포인터를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-109">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="e0afc-110">다음 예제에서는 변수 주소, 배열 및 문자열의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-110">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="e0afc-111">고정 크기 버퍼에 대한 자세한 내용은 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0afc-111">For more information about fixed-size buffers, see [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 <span data-ttu-id="e0afc-112">모두 동일한 형식인 경우 여러 포인터를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-112">You can initialize multiple pointers, as long as they are all of the same type.</span></span>  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 <span data-ttu-id="e0afc-113">형식이 다른 포인터를 초기화하려면 다음 예제와 같이 `fixed` 문을 중첩하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-113">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 <span data-ttu-id="e0afc-114">이 문의 코드를 실행하면 고정된 모든 변수가 고정 해제되고 가비지 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-114">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="e0afc-115">따라서 `fixed` 문 외부에서 해당 변수를 가리키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-115">Therefore, do not point to those variables outside the `fixed` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0afc-116">fixed 문에서 초기화된 포인터는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-116">Pointers initialized in fixed statements cannot be modified.</span></span>  
  
 <span data-ttu-id="e0afc-117">안전하지 않은 모드에서는 가비지 수집되지 않아 고정할 필요가 없는 스택에서 메모리를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0afc-117">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="e0afc-118">자세한 내용은 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0afc-118">For more information, see [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0afc-119">예제</span><span class="sxs-lookup"><span data-stu-id="e0afc-119">Example</span></span>  
 [!code-csharp[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e0afc-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e0afc-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0afc-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0afc-121">See Also</span></span>  
 [<span data-ttu-id="e0afc-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e0afc-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e0afc-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e0afc-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e0afc-124">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="e0afc-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="e0afc-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="e0afc-125">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="e0afc-126">고정 크기 버퍼</span><span class="sxs-lookup"><span data-stu-id="e0afc-126">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
