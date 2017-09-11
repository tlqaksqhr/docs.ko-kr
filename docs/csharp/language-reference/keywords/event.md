---
title: "event(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
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
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="event-c-reference"></a><span data-ttu-id="1d157-102">event(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1d157-102">event (C# Reference)</span></span>
<span data-ttu-id="1d157-103">`event` 키워드는 게시자 클래스에서 이벤트를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-103">The `event` keyword is used to declare an event in a publisher class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d157-104">예제</span><span class="sxs-lookup"><span data-stu-id="1d157-104">Example</span></span>  
 <span data-ttu-id="1d157-105">다음 예제에서는 <xref:System.EventHandler>를 기본 대리자 형식으로 사용하는 이벤트를 선언하고 발생시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-105">The following example shows how to declare and raise an event that uses <xref:System.EventHandler> as the underlying delegate type.</span></span> <span data-ttu-id="1d157-106">제네릭 <xref:System.EventHandler%601> 대리자 형식을 사용하는 방법 및 이벤트를 구독하고 이벤트 처리기 메서드를 만드는 방법을 보여 주는 전체 코드 예제는 [방법: .NET Framework 지침을 따르는 이벤트 게시](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d157-106">For the complete code example that also shows how to use the generic <xref:System.EventHandler%601> delegate type and how to subscribe to an event and create an event handler method, see [How to: Publish Events that Conform to .NET Framework Guidelines](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).</span></span>  
  
 <span data-ttu-id="1d157-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1d157-107">[!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]</span></span>  
  
 <span data-ttu-id="1d157-108">이벤트는 해당 이벤트가 선언되는 클래스(게시자 클래스) 또는 구조체 내에서만 호출할 수 있는 특수한 멀티캐스트 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-108">Events are a special kind of multicast delegate that can only be invoked from within the class or struct where they are declared (the publisher class).</span></span> <span data-ttu-id="1d157-109">다른 클래스 또는 구조체에서 이벤트를 구독하는 경우 해당 이벤트 처리기 메서드는 게시자 클래스에서 이벤트를 발생시킬 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-109">If other classes or structs subscribe to the event, their event handler methods will be called when the publisher class raises the event.</span></span> <span data-ttu-id="1d157-110">자세한 내용 및 코드 예제는 [이벤트](../../../csharp/programming-guide/events/index.md) 및 [대리자](../../../csharp/programming-guide/delegates/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d157-110">For more information and code examples, see [Events](../../../csharp/programming-guide/events/index.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
 <span data-ttu-id="1d157-111">이벤트는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected internal`로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-111">Events can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="1d157-112">이러한 액세스 한정자는 클래스 사용자가 이벤트에 액세스하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-112">These access modifiers define how users of the class can access the event.</span></span> <span data-ttu-id="1d157-113">자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d157-113">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
## <a name="keywords-and-events"></a><span data-ttu-id="1d157-114">키워드 및 이벤트</span><span class="sxs-lookup"><span data-stu-id="1d157-114">Keywords and Events</span></span>  
 <span data-ttu-id="1d157-115">이벤트에 적용되는 키워드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-115">The following keywords apply to events.</span></span>  
  
|<span data-ttu-id="1d157-116">키워드</span><span class="sxs-lookup"><span data-stu-id="1d157-116">Keyword</span></span>|<span data-ttu-id="1d157-117">설명</span><span class="sxs-lookup"><span data-stu-id="1d157-117">Description</span></span>|<span data-ttu-id="1d157-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1d157-118">For more information</span></span>|  
|-------------|-----------------|--------------------------|  
|[<span data-ttu-id="1d157-119">static</span><span class="sxs-lookup"><span data-stu-id="1d157-119">static</span></span>](../../../csharp/language-reference/keywords/static.md)|<span data-ttu-id="1d157-120">클래스의 인스턴스가 없는 경우에도 언제든지 호출자가 이벤트를 사용할 수 있도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-120">Makes the event available to callers at any time, even if no instance of the class exists.</span></span>|[<span data-ttu-id="1d157-121">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="1d157-121">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[<span data-ttu-id="1d157-122">virtual</span><span class="sxs-lookup"><span data-stu-id="1d157-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="1d157-123">파생 클래스에서 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 이벤트 동작을 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-123">Allows derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span>|[<span data-ttu-id="1d157-124">상속</span><span class="sxs-lookup"><span data-stu-id="1d157-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[<span data-ttu-id="1d157-125">sealed</span><span class="sxs-lookup"><span data-stu-id="1d157-125">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)|<span data-ttu-id="1d157-126">파생 클래스에 대해 더 이상 가상이 아니도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-126">Specifies that for derived classes it is no longer virtual.</span></span>||  
|[<span data-ttu-id="1d157-127">abstract</span><span class="sxs-lookup"><span data-stu-id="1d157-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="1d157-128">컴파일러에서 `add` 및 `remove` 이벤트 접근자 블록을 생성하지 않으므로 파생 클래스는 자체 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-128">The compiler will not generate the `add` and `remove` event accessor blocks and therefore derived classes must provide their own implementation.</span></span>||  
  
 <span data-ttu-id="1d157-129">이벤트는 [static](../../../csharp/language-reference/keywords/static.md) 키워드를 사용하여 정적 이벤트로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-129">An event may be declared as a static event by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="1d157-130">그러면 클래스의 인스턴스가 없는 경우에도 언제든지 호출자가 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-130">This makes the event available to callers at any time, even if no instance of the class exists.</span></span> <span data-ttu-id="1d157-131">자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d157-131">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="1d157-132">이벤트는 [virtual](../../../csharp/language-reference/keywords/virtual.md) 키워드를 사용하여 가상 이벤트로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-132">An event can be marked as a virtual event by using the [virtual](../../../csharp/language-reference/keywords/virtual.md) keyword.</span></span> <span data-ttu-id="1d157-133">그러면 파생 클래스에서 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 이벤트 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-133">This enables derived classes to override the event behavior by using the [override](../../../csharp/language-reference/keywords/override.md) keyword.</span></span> <span data-ttu-id="1d157-134">자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d157-134">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span> <span data-ttu-id="1d157-135">또한 가상 이벤트를 재정의하는 이벤트는 [sealed](../../../csharp/language-reference/keywords/sealed.md)일 수 있으며, 파생 클래스에 대해 더 이상 가상이 아니도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-135">An event overriding a virtual event can also be [sealed](../../../csharp/language-reference/keywords/sealed.md), which specifies that for derived classes it is no longer virtual.</span></span> <span data-ttu-id="1d157-136">마지막으로 이벤트를 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언할 수 있으며, 컴파일러에서 `add` 및 `remove` 이벤트 접근자 블록을 생성하지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-136">Lastly, an event can be declared [abstract](../../../csharp/language-reference/keywords/abstract.md), which means that the compiler will not generate the `add` and `remove` event accessor blocks.</span></span> <span data-ttu-id="1d157-137">따라서 파생 클래스는 자체 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d157-137">Therefore derived classes must provide their own implementation.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="1d157-138">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1d157-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1d157-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d157-139">See Also</span></span>  
 <span data-ttu-id="1d157-140">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1d157-140">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1d157-141">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1d157-141">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1d157-142">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1d157-142">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1d157-143">[add](../../../csharp/language-reference/keywords/add.md) </span><span class="sxs-lookup"><span data-stu-id="1d157-143">[add](../../../csharp/language-reference/keywords/add.md) </span></span>  
 <span data-ttu-id="1d157-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span><span class="sxs-lookup"><span data-stu-id="1d157-144">[remove](../../../csharp/language-reference/keywords/remove.md) </span></span>  
 <span data-ttu-id="1d157-145">[한정자](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1d157-145">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 [<span data-ttu-id="1d157-146">방법: 대리자 조합(멀티캐스트 대리자)</span><span class="sxs-lookup"><span data-stu-id="1d157-146">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

