---
title: 인터페이스(C# 프로그래밍 가이드)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
caps.latest.revision: 45
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f14d4bf48d117558a4019a8f016e194af27a9ebf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="interfaces-c-programming-guide"></a><span data-ttu-id="ab3dc-102">인터페이스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ab3dc-102">Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="ab3dc-103">인터페이스에는 [클래스](../../../csharp/language-reference/keywords/class.md) 또는[ 구조체](../../../csharp/language-reference/keywords/struct.md)에서 구현할 수 있는 관련 기능 그룹에 대한 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-103">An interface contains definitions for a group of related functionalities that a [class](../../../csharp/language-reference/keywords/class.md) or a [struct](../../../csharp/language-reference/keywords/struct.md) can implement.</span></span>  
  
 <span data-ttu-id="ab3dc-104">예를 들어 인터페이스를 사용하면 여러 소스의 동작을 클래스에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-104">By using interfaces, you can, for example, include behavior from multiple sources in a class.</span></span> <span data-ttu-id="ab3dc-105">해당 기능은 언어가 클래스의 여러 상속을 지원하지 않기 때문에 C#에서 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-105">That capability is important in C# because the language doesn't support multiple inheritance of classes.</span></span> <span data-ttu-id="ab3dc-106">또한 구조체는 다른 구조체나 클래스에서 실제로 상속할 수 없기 때문에 구조체에 대한 상속을 시뮬레이트하려는 경우 인터페이스를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-106">In addition, you must use an interface if you want to simulate inheritance for structs, because they can't actually inherit from another struct or class.</span></span>  
  
 <span data-ttu-id="ab3dc-107">다음 예제와 같이 [인터페이스](../../../csharp/language-reference/keywords/interface.md) 키워드를 사용하여 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-107">You define an interface by using the [interface](../../../csharp/language-reference/keywords/interface.md) keyword, as the following example shows.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#47](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]  
  
 <span data-ttu-id="ab3dc-108"><xref:System.IEquatable%601> 인터페이스를 구현하는 모든 클래스나 구조체에는 인터페이스에서 지정한 서명과 일치하는 <xref:System.IEquatable%601.Equals%2A> 메서드에 대한 정의가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-108">Any class or struct that implements the <xref:System.IEquatable%601> interface must contain a definition for an <xref:System.IEquatable%601.Equals%2A> method that matches the signature that the interface specifies.</span></span> <span data-ttu-id="ab3dc-109">따라서 `IEquatable<T>`을 구현하는 클래스를 계산하여 클래스의 인스턴스에서 동일한 클래스의 다른 인스턴스와 동일한지 여부를 확인할 수 있는 `Equals` 메서드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-109">As a result, you can count on a class that implements `IEquatable<T>` to contain an `Equals` method with which an instance of the class can determine whether it's equal to another instance of the same class.</span></span>  
  
 <span data-ttu-id="ab3dc-110">`IEquatable<T>`의 정의에서는 `Equals`에 대한 구현을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-110">The definition of `IEquatable<T>` doesn’t provide an implementation for `Equals`.</span></span> <span data-ttu-id="ab3dc-111">인터페이스는 서명만 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-111">The interface defines only the signature.</span></span> <span data-ttu-id="ab3dc-112">이런 방식으로 C#의 인터페이스는 모든 메서드가 추상인 추상 클래스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-112">In that way, an interface in C# is similar to an abstract class in which all the methods are abstract.</span></span> <span data-ttu-id="ab3dc-113">그러나 클래스 또는 구조체는 여러 인터페이스를 구현할 수 있지만 클래스는 추상인지 여부에 관계없이 단일 클래스만 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-113">However, a class or struct can implement multiple interfaces, but a class can inherit only a single class, abstract or not.</span></span> <span data-ttu-id="ab3dc-114">따라서 인터페이스를 사용하여 여러 소스의 동작을 클래스에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-114">Therefore, by using interfaces, you can include behavior from multiple sources in a class.</span></span>  
  
 <span data-ttu-id="ab3dc-115">추상 클래스에 대한 자세한 내용은 [추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-115">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="ab3dc-116">인터페이스에는 메서드, 속성, 이벤트, 인덱서 또는 이러한 네 가지 멤버 형식의 조합이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-116">Interfaces can contain methods, properties, events, indexers, or any combination of those four member types.</span></span> <span data-ttu-id="ab3dc-117">예제에 대한 링크는[관련 단원](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-117">For links to examples, see [Related Sections](../../../csharp/programming-guide/interfaces/index.md#BKMK_RelatedSections).</span></span> <span data-ttu-id="ab3dc-118">인터페이스에는 상수, 필드, 연산자, 인스턴스 생성자, 종료자 또는 형식이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-118">An interface can't contain constants, fields, operators, instance constructors, finalizers, or types.</span></span> <span data-ttu-id="ab3dc-119">인터페이스 멤버는 자동으로 공용이 되며 액세스 한정자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-119">Interface members are automatically public, and they can't include any access modifiers.</span></span> <span data-ttu-id="ab3dc-120">또한 멤버는 [정적](../../../csharp/language-reference/keywords/static.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-120">Members also can't be [static](../../../csharp/language-reference/keywords/static.md).</span></span>  
  
 <span data-ttu-id="ab3dc-121">인터페이스 멤버를 구현하려면 구현 클래스의 해당 멤버가 공용이고 비정적이어야 하며 인터페이스 멤버와 동일한 이름 및 서명을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-121">To implement an interface member, the corresponding member of the implementing class must be public, non-static, and have the same name and signature as the interface member.</span></span>  
  
 <span data-ttu-id="ab3dc-122">클래스 또는 구조체에서 인터페이스를 구현하는 경우 인터페이스에서 정의하는 모든 멤버에 대해 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-122">When a class or struct implements an interface, the class or struct must provide an implementation for all of the members that the interface defines.</span></span> <span data-ttu-id="ab3dc-123">인터페이스 자체는 클래스 또는 구조체에서 기본 클래스 기능을 상속하는 방식으로 상속할 수 있는 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-123">The interface itself provides no functionality that a class or struct can inherit in the way that it can inherit base class functionality.</span></span> <span data-ttu-id="ab3dc-124">그러나 기본 클래스에서 인터페이스를 구현하는 경우에는 기본 클래스에서 파생되는 모든 클래스가 해당 구현을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-124">However, if a base class implements an interface, any class that's derived from the base class inherits that implementation.</span></span>  
  
 <span data-ttu-id="ab3dc-125">다음 예제에서는 IEquatable<T\> 인터페이스의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-125">The following example shows an implementation of the IEquatable<T\> interface.</span></span> <span data-ttu-id="ab3dc-126">구현 클래스 `Car`는 <xref:System.IEquatable%601.Equals%2A> 메서드의 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-126">The implementing class, `Car`, must provide an implementation of the <xref:System.IEquatable%601.Equals%2A> method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#48](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]  
  
 <span data-ttu-id="ab3dc-127">클래스의 속성 및 인덱서는 인터페이스에 정의된 속성이나 인덱서에 대해 추가 접근자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-127">Properties and indexers of a class can define extra accessors for a property or indexer that's defined in an interface.</span></span> <span data-ttu-id="ab3dc-128">예를 들어 인터페이스는 [get](../../../csharp/language-reference/keywords/get.md) 접근자가 있는 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-128">For example, an interface might declare a property that has a [get](../../../csharp/language-reference/keywords/get.md) accessor.</span></span> <span data-ttu-id="ab3dc-129">인터페이스를 구현하는 클래스는 `get` 및 [set](../../../csharp/language-reference/keywords/set.md) 접근자를 둘 다 사용하는 동일한 속성을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-129">The class that implements the interface can declare the same property with both a `get` and [set](../../../csharp/language-reference/keywords/set.md) accessor.</span></span> <span data-ttu-id="ab3dc-130">그러나 속성 또는 인덱서에서 명시적 구현을 사용하는 경우에는 접근자가 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-130">However, if the property or indexer uses explicit implementation, the accessors must match.</span></span> <span data-ttu-id="ab3dc-131">명시적 구현에 대한 자세한 내용은 [명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) 및 [인터페이스 속성(C# 프로그래밍 가이드)](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-131">For more information about explicit implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) and [Interface Properties](../../../csharp/programming-guide/classes-and-structs/interface-properties.md).</span></span>  
  
 <span data-ttu-id="ab3dc-132">인터페이스는 다른 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-132">Interfaces can implement other interfaces.</span></span> <span data-ttu-id="ab3dc-133">클래스는 상속하는 기본 클래스 또는 다른 인터페이스에서 구현하는 인터페이스를 통해 인터페이스를 여러 번 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-133">A class might include an interface multiple times through base classes that it inherits or through interfaces that other interfaces implement.</span></span> <span data-ttu-id="ab3dc-134">그러나 클래스는 인터페이스의 구현을 한 번만 제공할 수 있으며 클래스가 인터페이스를 클래스 정의의 일부로 선언하는 경우에만 제공할 수 있습니다(`class ClassName : InterfaceName`).</span><span class="sxs-lookup"><span data-stu-id="ab3dc-134">However, the class can provide an implementation of an interface only one time and only if the class declares the interface as part of the definition of the class (`class ClassName : InterfaceName`).</span></span> <span data-ttu-id="ab3dc-135">인터페이스를 구현하는 기본 클래스를 상속했기 때문에 인터페이스가 상속되는 경우 기본 클래스는 인터페이스 멤버의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-135">If the interface is inherited because you inherited a base class that implements the interface, the base class provides the implementation of the members of the interface.</span></span> <span data-ttu-id="ab3dc-136">그러나 파생 클래스는 상속된 구현을 사용하는 대신 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-136">However, the derived class can reimplement the interface members instead of using the inherited implementation.</span></span>  
  
 <span data-ttu-id="ab3dc-137">또한 기본 클래스는 가상 멤버를 사용하여 인터페이스 멤버를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-137">A base class can also implement interface members by using virtual members.</span></span> <span data-ttu-id="ab3dc-138">이 경우 파생 클래스는 가상 멤버를 재정의하여 인터페이스 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-138">In that case, a derived class can change the interface behavior by overriding the virtual members.</span></span> <span data-ttu-id="ab3dc-139">가상 멤버에 대한 자세한 내용은 [다형성](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-139">For more information about virtual members, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="interfaces-summary"></a><span data-ttu-id="ab3dc-140">인터페이스 요약</span><span class="sxs-lookup"><span data-stu-id="ab3dc-140">Interfaces Summary</span></span>  
 <span data-ttu-id="ab3dc-141">인터페이스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-141">An interface has the following properties:</span></span>  
  
-   <span data-ttu-id="ab3dc-142">인터페이스는 추상 기본 클래스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-142">An interface is like an abstract base class.</span></span> <span data-ttu-id="ab3dc-143">인터페이스를 구현하는 모든 클래스 또는 구조체는 모든 멤버를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-143">Any class or struct that implements the interface must implement all its members.</span></span>  
  
-   <span data-ttu-id="ab3dc-144">인터페이스는 직접 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-144">An interface can't be instantiated directly.</span></span> <span data-ttu-id="ab3dc-145">해당 멤버는 인터페이스를 구현하는 클래스 또는 구조체에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-145">Its members are implemented by any class or struct that implements the interface.</span></span>  
  
-   <span data-ttu-id="ab3dc-146">인터페이스는 이벤트, 인덱서, 메서드 및 속성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-146">Interfaces can contain events, indexers, methods, and properties.</span></span>  
  
-   <span data-ttu-id="ab3dc-147">인터페이스에는 메서드의 구현이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-147">Interfaces contain no implementation of methods.</span></span>  
  
-   <span data-ttu-id="ab3dc-148">클래스 또는 구조체는 여러 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-148">A class or struct can implement multiple interfaces.</span></span> <span data-ttu-id="ab3dc-149">클래스는 기본 클래스를 상속할 수 있으며 하나 이상의 인터페이스를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-149">A class can inherit a base class and also implement one or more interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab3dc-150">단원 내용</span><span class="sxs-lookup"><span data-stu-id="ab3dc-150">In This Section</span></span>  
 [<span data-ttu-id="ab3dc-151">명시적 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="ab3dc-151">Explicit Interface Implementation</span></span>](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)  
 <span data-ttu-id="ab3dc-152">인터페이스와 관련된 클래스 멤버를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-152">Explains how to create a class member that’s specific to an interface.</span></span>  
  
 [<span data-ttu-id="ab3dc-153">방법: 인터페이스 멤버를 명시적으로 구현</span><span class="sxs-lookup"><span data-stu-id="ab3dc-153">How to: Explicitly Implement Interface Members</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)  
 <span data-ttu-id="ab3dc-154">인터페이스 멤버를 명시적으로 구현하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-154">Provides an example of how to explicitly implement members of interfaces.</span></span>  
  
 [<span data-ttu-id="ab3dc-155">방법: 두 인터페이스의 멤버를 명시적으로 구현</span><span class="sxs-lookup"><span data-stu-id="ab3dc-155">How to: Explicitly Implement Members of Two Interfaces</span></span>](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)  
 <span data-ttu-id="ab3dc-156">상속을 포함하는 인터페이스 멤버를 명시적으로 구현하는 방법에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab3dc-156">Provides an example of how to explicitly implement members of interfaces with inheritance.</span></span>  
  
##  <a name="BKMK_RelatedSections"></a><span data-ttu-id="ab3dc-157">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ab3dc-157">Related Sections</span></span>  
  
-   [<span data-ttu-id="ab3dc-158">인터페이스 속성</span><span class="sxs-lookup"><span data-stu-id="ab3dc-158">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="ab3dc-159">인터페이스의 인덱서</span><span class="sxs-lookup"><span data-stu-id="ab3dc-159">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="ab3dc-160">방법: 인터페이스 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="ab3dc-160">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="ab3dc-161">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="ab3dc-161">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
  
-   [<span data-ttu-id="ab3dc-162">상속</span><span class="sxs-lookup"><span data-stu-id="ab3dc-162">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
  
-   [<span data-ttu-id="ab3dc-163">메서드</span><span class="sxs-lookup"><span data-stu-id="ab3dc-163">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="ab3dc-164">다형성</span><span class="sxs-lookup"><span data-stu-id="ab3dc-164">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
  
-   [<span data-ttu-id="ab3dc-165">추상/봉인된 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="ab3dc-165">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
  
-   [<span data-ttu-id="ab3dc-166">속성</span><span class="sxs-lookup"><span data-stu-id="ab3dc-166">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
  
-   [<span data-ttu-id="ab3dc-167">이벤트</span><span class="sxs-lookup"><span data-stu-id="ab3dc-167">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
  
-   [<span data-ttu-id="ab3dc-168">인덱서</span><span class="sxs-lookup"><span data-stu-id="ab3dc-168">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="ab3dc-169">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="ab3dc-169">Featured Book Chapter</span></span>  
 <span data-ttu-id="ab3dc-170">[Interfaces](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="ab3dc-170">[Interfaces](http://msdn.microsoft.com/library/orm-9780596521066-01-13.aspx) in [Learning C# 3.0: Master the Fundamentals of C# 3.0](http://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab3dc-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab3dc-171">See Also</span></span>  
 [<span data-ttu-id="ab3dc-172">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ab3dc-172">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ab3dc-173">상속</span><span class="sxs-lookup"><span data-stu-id="ab3dc-173">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
