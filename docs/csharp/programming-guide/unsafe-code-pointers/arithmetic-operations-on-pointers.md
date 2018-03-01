---
title: "포인터에 대한 산술 연산(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 54c439aab8b6cd34a796db8d31f9eabeefddf9f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="800e8-102">포인터에 대한 산술 연산(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="800e8-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="800e8-103">이 항목에서는 산술 연산자 `+` 및 **-**를 사용하여 포인터를 조작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="800e8-104">void 포인터에 대해 산술 연산을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="800e8-105">포인터에 숫자 값 추가 및 포인터에서 숫자 값 빼기</span><span class="sxs-lookup"><span data-stu-id="800e8-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="800e8-106">[int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식의 `n` 값을 `void*`를 제외한 모든 형식의 `p` 포인터에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="800e8-107">결과 `p+n`은 `n * sizeof(p) to the address of p`를 추가한 결과로 생성된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="800e8-108">마찬가지로 `p-n`은 `p` 주소에서 `n * sizeof(p)`를 뺀 결과로 생성된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="800e8-109">포인터 빼기</span><span class="sxs-lookup"><span data-stu-id="800e8-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="800e8-110">같은 형식의 포인터를 뺄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="800e8-111">결과는 항상 `long` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-111">The result is always of the type `long`.</span></span> <span data-ttu-id="800e8-112">예를 들어 `p1` 및 `p2`가 `pointer-type*` 형식의 포인터인 경우 `p1-p2` 식의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="800e8-113">산술 연산이 포인터의 도메인을 오버플로하는 경우 예외가 생성되지 않고 결과는 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="800e8-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="800e8-114">예제</span><span class="sxs-lookup"><span data-stu-id="800e8-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="800e8-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="800e8-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="800e8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="800e8-116">See Also</span></span>  
 [<span data-ttu-id="800e8-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="800e8-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="800e8-118">안전하지 않은 코드 및 포인터</span><span class="sxs-lookup"><span data-stu-id="800e8-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="800e8-119">포인터 식</span><span class="sxs-lookup"><span data-stu-id="800e8-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="800e8-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="800e8-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="800e8-121">포인터 조작</span><span class="sxs-lookup"><span data-stu-id="800e8-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="800e8-122">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="800e8-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="800e8-123">유형</span><span class="sxs-lookup"><span data-stu-id="800e8-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="800e8-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="800e8-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="800e8-125">fixed 문</span><span class="sxs-lookup"><span data-stu-id="800e8-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="800e8-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="800e8-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
