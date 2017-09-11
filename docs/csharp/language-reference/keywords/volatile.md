---
title: "volatile(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
dev_langs:
- CSharp
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
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
ms.openlocfilehash: c8f9fba15991197be885a973435089098a57db87
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="volatile-c-reference"></a><span data-ttu-id="f0c78-102">volatile(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f0c78-102">volatile (C# Reference)</span></span>
<span data-ttu-id="f0c78-103">`volatile` 키워드는 동시에 실행되는 여러 스레드에 의해 필드가 수정될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="f0c78-104">`volatile`로 선언된 필드에는 단일 스레드에 의한 액세스를 가정하는 컴파일러 최적화가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="f0c78-105">이렇게 하면 필드에 항상 최신 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="f0c78-106">`volatile` 한정자는 대개 여러 스레드가 액세스하는 필드에 사용되며, 액세스를 serialize하는 [lock](../../../csharp/language-reference/keywords/lock-statement.md) 문을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="f0c78-107">`volatile` 키워드는 다음 형식의 필드에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="f0c78-108">참조 형식.</span><span class="sxs-lookup"><span data-stu-id="f0c78-108">Reference types.</span></span>  
  
-   <span data-ttu-id="f0c78-109">포인터 형식(안전하지 않은 컨텍스트에서).</span><span class="sxs-lookup"><span data-stu-id="f0c78-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="f0c78-110">포인터 자체는 volatile이 될 수 있지만, 포인터가 가리키는 개체는 volatile이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="f0c78-111">즉, "pointer to volatile"을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="f0c78-112">sbyte, byte, short, ushort, int, uint, char, float, bool 등의 형식.</span><span class="sxs-lookup"><span data-stu-id="f0c78-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="f0c78-113">byte, sbyte, short, ushort, int 또는 uint 기본 형식 중 하나를 포함하는 열거형 형식.</span><span class="sxs-lookup"><span data-stu-id="f0c78-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="f0c78-114">참조 형식으로 알려진 제네릭 형식 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="f0c78-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="f0c78-115"><xref:System.IntPtr>와 <xref:System.UIntPtr>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c78-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="f0c78-116">Volatile 키워드는 클래스 또는 구조체의 필드에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="f0c78-117">지역 변수는 `volatile`로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c78-118">예제</span><span class="sxs-lookup"><span data-stu-id="f0c78-118">Example</span></span>  
 <span data-ttu-id="f0c78-119">다음 예제에서는 공용 필드 변수를 `volatile`로 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 <span data-ttu-id="f0c78-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0c78-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0c78-121">예제</span><span class="sxs-lookup"><span data-stu-id="f0c78-121">Example</span></span>  
 <span data-ttu-id="f0c78-122">다음 예제에서는 보조 또는 작업자 스레드를 만들어 기본 스레드와 병렬로 처리하는 데 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0c78-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="f0c78-123">다중 스레딩에 대한 배경 정보는 [관리되는 스레딩](../../../standard/threading/index.md) 및 [스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c78-123">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="f0c78-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0c78-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f0c78-125">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f0c78-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0c78-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0c78-126">See Also</span></span>  
 <span data-ttu-id="f0c78-127">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0c78-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f0c78-128">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0c78-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f0c78-129">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0c78-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="f0c78-130">한정자</span><span class="sxs-lookup"><span data-stu-id="f0c78-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

