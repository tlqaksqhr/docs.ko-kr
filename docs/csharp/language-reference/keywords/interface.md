---
title: interface(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aba9ee66a90216066a47f22e251182caad465818
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="interface-c-reference"></a><span data-ttu-id="8c5de-102">interface(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8c5de-102">interface (C# Reference)</span></span>
<span data-ttu-id="8c5de-103">인터페이스에는 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md), [속성](../../../csharp/programming-guide/classes-and-structs/properties.md), [이벤트](../../../csharp/programming-guide/events/index.md) 또는 [인덱서](../../../csharp/programming-guide/indexers/index.md)의 시그니처만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="8c5de-104">인터페이스를 구현하는 클래스나 구조체는 인터페이스 정의에서 지정된 인터페이스 멤버를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="8c5de-105">다음 예제에서 `ImplementationClass` 클래스는 매개 변수가 없고 `void`를 반환하는 `SampleMethod`라는 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="8c5de-106">자세한 내용과 예제는 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c5de-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c5de-107">예제</span><span class="sxs-lookup"><span data-stu-id="8c5de-107">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]  
  
 <span data-ttu-id="8c5de-108">인터페이스는 네임스페이스 또는 클래스의 멤버일 수 있으며 다음 멤버의 시그니처를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="8c5de-109">메서드</span><span class="sxs-lookup"><span data-stu-id="8c5de-109">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="8c5de-110">속성</span><span class="sxs-lookup"><span data-stu-id="8c5de-110">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="8c5de-111">인덱서</span><span class="sxs-lookup"><span data-stu-id="8c5de-111">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="8c5de-112">이벤트</span><span class="sxs-lookup"><span data-stu-id="8c5de-112">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="8c5de-113">인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-113">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="8c5de-114">기본 형식 목록에 기본 클래스 및 인터페이스가 포함된 경우 기본 클래스가 목록의 첫 번째 항목이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="8c5de-115">인터페이스를 구현하는 클래스는 해당 인터페이스의 멤버를 명시적으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="8c5de-116">명시적으로 구현된 멤버는 클래스 인스턴스를 통해 액세스할 수 없고 인터페이스 인스턴스를 통해서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="8c5de-117">명시적 인터페이스 구현에 대한 자세한 내용과 코드 예제는 [명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c5de-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c5de-118">예제</span><span class="sxs-lookup"><span data-stu-id="8c5de-118">Example</span></span>  
 <span data-ttu-id="8c5de-119">다음 예제에서는 인터페이스의 구현 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="8c5de-120">이 예제에서 인터페이스에는 속성 선언이 포함되어 있고, 클래스에는 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="8c5de-121">`IPoint`를 구현하는 클래스의 모든 인스턴스에는 정수 속성 `x` 및 `y`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5de-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8c5de-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8c5de-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c5de-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c5de-123">See Also</span></span>  
 [<span data-ttu-id="8c5de-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8c5de-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8c5de-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8c5de-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8c5de-126">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8c5de-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8c5de-127">참조 형식</span><span class="sxs-lookup"><span data-stu-id="8c5de-127">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="8c5de-128">인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c5de-128">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="8c5de-129">속성 사용</span><span class="sxs-lookup"><span data-stu-id="8c5de-129">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [<span data-ttu-id="8c5de-130">인덱서 사용</span><span class="sxs-lookup"><span data-stu-id="8c5de-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
 [<span data-ttu-id="8c5de-131">class</span><span class="sxs-lookup"><span data-stu-id="8c5de-131">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="8c5de-132">struct</span><span class="sxs-lookup"><span data-stu-id="8c5de-132">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
 [<span data-ttu-id="8c5de-133">인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c5de-133">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
