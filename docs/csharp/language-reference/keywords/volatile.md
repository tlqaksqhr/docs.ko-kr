---
title: volatile(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 7f3aafc1255667f2a3917c6e171ce4ddf0343b41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="volatile-c-reference"></a><span data-ttu-id="f8296-102">volatile(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f8296-102">volatile (C# Reference)</span></span>
<span data-ttu-id="f8296-103">`volatile` 키워드는 동시에 실행되는 여러 스레드에 의해 필드가 수정될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="f8296-104">`volatile`로 선언된 필드에는 단일 스레드에 의한 액세스를 가정하는 컴파일러 최적화가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="f8296-105">이렇게 하면 필드에 항상 최신 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="f8296-106">`volatile` 한정자는 대개 여러 스레드가 액세스하는 필드에 사용되며, 액세스를 serialize하는 [lock](../../../csharp/language-reference/keywords/lock-statement.md) 문을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="f8296-107">`volatile` 키워드는 다음 형식의 필드에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="f8296-108">참조 형식.</span><span class="sxs-lookup"><span data-stu-id="f8296-108">Reference types.</span></span>  
  
-   <span data-ttu-id="f8296-109">포인터 형식(안전하지 않은 컨텍스트에서).</span><span class="sxs-lookup"><span data-stu-id="f8296-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="f8296-110">포인터 자체는 volatile이 될 수 있지만, 포인터가 가리키는 개체는 volatile이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="f8296-111">즉, "pointer to volatile"을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="f8296-112">sbyte, byte, short, ushort, int, uint, char, float, bool 등의 형식.</span><span class="sxs-lookup"><span data-stu-id="f8296-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="f8296-113">byte, sbyte, short, ushort, int 또는 uint 기본 형식 중 하나를 포함하는 열거형 형식.</span><span class="sxs-lookup"><span data-stu-id="f8296-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="f8296-114">참조 형식으로 알려진 제네릭 형식 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="f8296-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="f8296-115"><xref:System.IntPtr>와 <xref:System.UIntPtr>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8296-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="f8296-116">Volatile 키워드는 클래스 또는 구조체의 필드에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="f8296-117">지역 변수는 `volatile`로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8296-118">예</span><span class="sxs-lookup"><span data-stu-id="f8296-118">Example</span></span>  
 <span data-ttu-id="f8296-119">다음 예제에서는 공용 필드 변수를 `volatile`로 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="f8296-120">예</span><span class="sxs-lookup"><span data-stu-id="f8296-120">Example</span></span>  
 <span data-ttu-id="f8296-121">다음 예제에서는 보조 또는 작업자 스레드를 만들어 기본 스레드와 병렬로 처리하는 데 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8296-121">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="f8296-122">다중 스레딩에 대한 배경 정보는 [스레딩(C#)](../../../standard/threading/index.md) 및 [관리되는 스레딩](../../programming-guide/concepts/threading/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8296-122">For background information about multithreading, see [Threading (C#)](../../../standard/threading/index.md) and [Managed Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="f8296-123">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f8296-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8296-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8296-124">See Also</span></span>  
 [<span data-ttu-id="f8296-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f8296-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f8296-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f8296-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f8296-127">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="f8296-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f8296-128">한정자</span><span class="sxs-lookup"><span data-stu-id="f8296-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
