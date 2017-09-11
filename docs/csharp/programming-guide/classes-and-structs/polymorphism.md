---
title: "다형성(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
caps.latest.revision: 31
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
ms.openlocfilehash: c278a6a931154af97cab5b1ff33124dd31a3fa2e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="polymorphism-c-programming-guide"></a><span data-ttu-id="55448-102">다형성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="55448-102">Polymorphism (C# Programming Guide)</span></span>
<span data-ttu-id="55448-103">다형성은 흔히 캡슐화와 상속의 뒤를 이어 개체 지향 프로그래밍의 세 번째 특징으로 일컬어집니다.</span><span class="sxs-lookup"><span data-stu-id="55448-103">Polymorphism is often referred to as the third pillar of object-oriented programming, after encapsulation and inheritance.</span></span> <span data-ttu-id="55448-104">다형성은 "여러 형태"를 의미하는 그리스어 단어이며 다음과 같은 두 가지 고유한 측면을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="55448-104">Polymorphism is a Greek word that means "many-shaped" and it has two distinct aspects:</span></span>  
  
-   <span data-ttu-id="55448-105">런타임에 파생 클래스의 개체가 메서드 매개 변수 및 컬렉션 또는 배열과 같은 위치에서 기본 클래스의 개체로 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-105">At run time, objects of a derived class may be treated as objects of a base class in places such as method parameters and collections or arrays.</span></span> <span data-ttu-id="55448-106">이 경우 개체의 선언된 형식이 더 이상 해당 런타임 형식과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-106">When this occurs, the object's declared type is no longer identical to its run-time type.</span></span>  
  
-   <span data-ttu-id="55448-107">기본 클래스는 [가상](../../../csharp/language-reference/keywords/virtual.md) *메서드*를 정의 및 구현할 수 있으며, 파생 클래스는 이러한 가상 메서드를 [재정의](../../../csharp/language-reference/keywords/override.md)할 수 있습니다. 즉, 파생 클래스는 고유한 정의 및 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-107">Base classes may define and implement [virtual](../../../csharp/language-reference/keywords/virtual.md) *methods*, and derived classes can [override](../../../csharp/language-reference/keywords/override.md) them, which means they provide their own definition and implementation.</span></span> <span data-ttu-id="55448-108">런타임에 클라이언트 코드에서 메서드를 호출하면 CLR은 개체의 런타임 형식을 조회하고 가상 메서드의 해당 재정의를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-108">At run-time, when client code calls the method, the CLR looks up the run-time type of the object, and invokes that override of the virtual method.</span></span> <span data-ttu-id="55448-109">따라서 소스 코드에서 기본 클래스에 대한 메서드를 호출하여 메서드의 파생 클래스 버전이 실행되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-109">Thus in your source code you can call a method on a base class, and cause a derived class's version of the method to be executed.</span></span>  
  
 <span data-ttu-id="55448-110">가상 메서드를 사용하면 동일한 방식으로 관련 개체 그룹에 대한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-110">Virtual methods enable you to work with groups of related objects in a uniform way.</span></span> <span data-ttu-id="55448-111">예를 들어, 사용자가 그리기 화면에서 다양한 종류의 도형을 만들 수 있는 그리기 응용 프로그램이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-111">For example, suppose you have a drawing application that enables a user to create various kinds of shapes on a drawing surface.</span></span> <span data-ttu-id="55448-112">컴파일 타임에는 사용자가 어떤 특정 형식의 도형을 만들지 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-112">You do not know at compile time which specific types of shapes the user will create.</span></span> <span data-ttu-id="55448-113">그러나 응용 프로그램은 만들어지는 다양한 모든 형식의 도형을 추적해야 하며, 사용자의 마우스 작업에 따라 이러한 도형을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-113">However, the application has to keep track of all the various types of shapes that are created, and it has to update them in response to user mouse actions.</span></span> <span data-ttu-id="55448-114">다음과 같은 기본 두 단계로 다형성을 사용하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-114">You can use polymorphism to solve this problem in two basic steps:</span></span>  
  
1.  <span data-ttu-id="55448-115">각 특정 도형 클래스가 공통 기본 클래스에서 파생되는 클래스 계층 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55448-115">Create a class hierarchy in which each specific shape class derives from a common base class.</span></span>  
  
2.  <span data-ttu-id="55448-116">가상 메서드를 사용하여 기본 클래스 메서드에 대한 단일 호출을 통해 모든 파생 클래스에 대해 적절한 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-116">Use a virtual method to invoke the appropriate method on any derived class through a single call to the base class method.</span></span>  
  
 <span data-ttu-id="55448-117">먼저, `Shape`라는 기본 클래스를 만들고 `Rectangle`, `Circle` 및 `Triangle`과 같은 파생 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55448-117">First, create a base class called `Shape`, and derived classes such as `Rectangle`, `Circle`, and `Triangle`.</span></span> <span data-ttu-id="55448-118">`Shape` 클래스에 `Draw`라는 가상 메서드를 제공하고, 각 파생 클래스에서 이를 재정의하여 클래스가 나타내는 특정 도형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="55448-118">Give the `Shape` class a virtual method called `Draw`, and override it in each derived class to draw the particular shape that the class represents.</span></span> <span data-ttu-id="55448-119">`List<Shape>` 개체를 만들고 이 개체에 Circle, Triangle 및 Rectangle을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-119">Create a `List<Shape>` object and add a Circle, Triangle and Rectangle to it.</span></span> <span data-ttu-id="55448-120">그리기 화면을 업데이트하려면 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 루프를 사용하여 목록을 반복하고 목록의 각 `Shape` 개체에 대해 `Draw` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-120">To update the drawing surface, use a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loop to iterate through the list and call the `Draw` method on each `Shape` object in the list.</span></span> <span data-ttu-id="55448-121">목록의 각 개체에 선언된 형식 `Shape`가 있더라도 이는 호출될 런타임 형식(각 파생 클래스에 있는 메서드의 재정의된 버전)입니다.</span><span class="sxs-lookup"><span data-stu-id="55448-121">Even though each object in the list has a declared type of `Shape`, it is the run-time type (the overridden version of the method in each derived class) that will be invoked.</span></span>  
  
 <span data-ttu-id="55448-122">[!code-cs[csProgGuideInheritance#50](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-122">[!code-cs[csProgGuideInheritance#50](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_1.cs)]</span></span>  
  
 <span data-ttu-id="55448-123">C#에서 모든 형식은 사용자 정의 형식을 포함한 모든 형식이 <xref:System.Object>에서 파생되므로 다형 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55448-123">In C#, every type is polymorphic because all types, including user-defined types, inherit from <xref:System.Object>.</span></span>  
  
## <a name="polymorphism-overview"></a><span data-ttu-id="55448-124">다형성 개요</span><span class="sxs-lookup"><span data-stu-id="55448-124">Polymorphism Overview</span></span>  
  
### <a name="virtual-members"></a><span data-ttu-id="55448-125">가상 멤버</span><span class="sxs-lookup"><span data-stu-id="55448-125">Virtual Members</span></span>  
 <span data-ttu-id="55448-126">기본 클래스에서 파생 클래스가 상속되면 파생 클래스는 기본 클래스의 모든 메서드, 필드, 속성 및 이벤트를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-126">When a derived class inherits from a base class, it gains all the methods, fields, properties and events of the base class.</span></span> <span data-ttu-id="55448-127">파생 클래스의 디자이너는 다음의 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-127">The designer of the derived class can choose whether to</span></span>  
  
-   <span data-ttu-id="55448-128">기본 클래스의 가상 멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="55448-128">override virtual members in the base class,</span></span>  
  
-   <span data-ttu-id="55448-129">가장 가까운 기본 클래스 메서드를 재정의하지 않고 상속</span><span class="sxs-lookup"><span data-stu-id="55448-129">inherit the closest base class method without overriding it</span></span>  
  
-   <span data-ttu-id="55448-130">기본 클래스 구현을 숨기는 해당 멤버의 새 비가상 구현 정의</span><span class="sxs-lookup"><span data-stu-id="55448-130">define new non-virtual implementation of those members that hide the base class implementations</span></span>  
  
 <span data-ttu-id="55448-131">파생 클래스는 기본 클래스 멤버가 [virtual](../../../csharp/language-reference/keywords/virtual.md) 또는 [abstract](../../../csharp/language-reference/keywords/abstract.md)로 선언된 경우에만 기본 클래스 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-131">A derived class can override a base class member only if the base class member is declared as [virtual](../../../csharp/language-reference/keywords/virtual.md) or [abstract](../../../csharp/language-reference/keywords/abstract.md).</span></span> <span data-ttu-id="55448-132">파생 멤버는 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 메서드가 가상 호출에 참여하도록 되어 있음을 명시적으로 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-132">The derived member must use the [override](../../../csharp/language-reference/keywords/override.md) keyword to explicitly indicate that the method is intended to participate in virtual invocation.</span></span> <span data-ttu-id="55448-133">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-133">The following code provides an example:</span></span>  
  
 <span data-ttu-id="55448-134">[!code-cs[csProgGuideInheritance#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-134">[!code-cs[csProgGuideInheritance#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_2.cs)]</span></span>  
  
 <span data-ttu-id="55448-135">필드는 가상일 수 없습니다. 메서드, 속성, 이벤트 및 인덱서만 가상일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-135">Fields cannot be virtual; only methods, properties, events and indexers can be virtual.</span></span> <span data-ttu-id="55448-136">파생 클래스가 가상 멤버를 재정의하면 해당 멤버는 해당 클래스의 인스턴스가 기본 클래스의 인스턴스로 액세스되는 경우에도 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="55448-136">When a derived class overrides a virtual member, that member is called even when an instance of that class is being accessed as an instance of the base class.</span></span> <span data-ttu-id="55448-137">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-137">The following code provides an example:</span></span>  
  
 <span data-ttu-id="55448-138">[!code-cs[csProgGuideInheritance#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-138">[!code-cs[csProgGuideInheritance#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_3.cs)]</span></span>  
  
 <span data-ttu-id="55448-139">가상 메서드 및 속성을 통해 파생 클래스는 메서드의 기본 클래스 구현을 사용할 필요 없이 기본 클래스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-139">Virtual methods and properties enable derived classes to extend a base class without needing to use the base class implementation of a method.</span></span> <span data-ttu-id="55448-140">자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55448-140">For more information, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md).</span></span> <span data-ttu-id="55448-141">인터페이스는 구현이 파생 클래스에 남겨진 메서드 또는 메서드 집합을 정의하는 또 다른 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-141">An interface provides another way to define a method or set of methods whose implementation is left to derived classes.</span></span> <span data-ttu-id="55448-142">자세한 내용은 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55448-142">For more information, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
### <a name="hiding-base-class-members-with-new-members"></a><span data-ttu-id="55448-143">새 멤버로 기본 클래스 멤버 숨기기</span><span class="sxs-lookup"><span data-stu-id="55448-143">Hiding Base Class Members with New Members</span></span>  
 <span data-ttu-id="55448-144">파생 멤버가 기본 클래스의 멤버와 동일한 이름을 갖되 가상 호출에는 참여하지 않도록 하려면 [new](../../../csharp/language-reference/keywords/new.md) 키워드를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55448-144">If you want your derived member to have the same name as a member in a base class, but you do not want it to participate in virtual invocation, you can use the [new](../../../csharp/language-reference/keywords/new.md) keyword.</span></span> <span data-ttu-id="55448-145">`new` 키워드는 바꿀 클래스 멤버의 반환 형식 앞에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="55448-145">The `new` keyword is put before the return type of a class member that is being replaced.</span></span> <span data-ttu-id="55448-146">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-146">The following code provides an example:</span></span>  
  
 <span data-ttu-id="55448-147">[!code-cs[csProgGuideInheritance#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-147">[!code-cs[csProgGuideInheritance#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_4.cs)]</span></span>  
  
 <span data-ttu-id="55448-148">숨겨진 기본 클래스 멤버는 파생 클래스의 인스턴스를 기본 클래스의 인스턴스로 캐스팅하여 클라이언트 코드에서 계속 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-148">Hidden base class members can still be accessed from client code by casting the instance of the derived class to an instance of the base class.</span></span> <span data-ttu-id="55448-149">예:</span><span class="sxs-lookup"><span data-stu-id="55448-149">For example:</span></span>  
  
 <span data-ttu-id="55448-150">[!code-cs[csProgGuideInheritance#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-150">[!code-cs[csProgGuideInheritance#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_5.cs)]</span></span>  
  
### <a name="preventing-derived-classes-from-overriding-virtual-members"></a><span data-ttu-id="55448-151">파생 클래스가 가상 멤버를 재정의하지 못하도록 설정</span><span class="sxs-lookup"><span data-stu-id="55448-151">Preventing Derived Classes from Overriding Virtual Members</span></span>  
 <span data-ttu-id="55448-152">가상 멤버는 가상 멤버와 원래 가상 멤버를 선언한 클래스 간에 선언된 클래스 수와 관계없이 무기한 가상으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="55448-152">Virtual members remain virtual indefinitely, regardless of how many classes have been declared between the virtual member and the class that originally declared it.</span></span> <span data-ttu-id="55448-153">클래스 A가 가상 멤버를 선언하고, 클래스 B가 A에서 파생되며, 클래스 C가 B에서 파생되면 클래스 C는 클래스 B가 해당 멤버에 대한 재정의를 선언했는지 여부와 관계없이 가상 멤버를 상속하며, 가상 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-153">If class A declares a virtual member, and class B derives from A, and class C derives from B, class C inherits the virtual member, and has the option to override it, regardless of whether class B declared an override for that member.</span></span> <span data-ttu-id="55448-154">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-154">The following code provides an example:</span></span>  
  
 <span data-ttu-id="55448-155">[!code-cs[csProgGuideInheritance#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-155">[!code-cs[csProgGuideInheritance#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_6.cs)]</span></span>  
  
 <span data-ttu-id="55448-156">파생 클래스는 재정의를 [sealed](../../../csharp/language-reference/keywords/sealed.md)로 선언하여 가상 상속을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-156">A derived class can stop virtual inheritance by declaring an override as [sealed](../../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="55448-157">이렇게 하려면 클래스 멤버 선언에서 `sealed` 키워드 앞에 `override` 키워드를 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-157">This requires putting the `sealed` keyword before the `override` keyword in the class member declaration.</span></span> <span data-ttu-id="55448-158">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-158">The following code provides an example:</span></span>  
  
 <span data-ttu-id="55448-159">[!code-cs[csProgGuideInheritance#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-159">[!code-cs[csProgGuideInheritance#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_7.cs)]</span></span>  
  
 <span data-ttu-id="55448-160">앞의 예제에서 `DoWork` 메서드는 C에서 파생된 모든 클래스에 대해 더 이상 가상이 아닙니다. 그러나 이 메서드는 C의 인스턴스가 형식 B 또는 형식 A로 캐스팅되더라도 여전히 C의 인스턴스에 대해서는 가상입니다. 다음 예제와 같이 `new` 키워드를 사용하여 sealed 메서드를 파생 클래스로 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-160">In the previous example, the method `DoWork` is no longer virtual to any class derived from C. It is still virtual for instances of C, even if they are cast to type B or type A. Sealed methods can be replaced by derived classes by using the `new` keyword, as the following example shows:</span></span>  
  
 <span data-ttu-id="55448-161">[!code-cs[csProgGuideInheritance#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-161">[!code-cs[csProgGuideInheritance#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_8.cs)]</span></span>  
  
 <span data-ttu-id="55448-162">이 경우 형식 D 변수를 사용하여 D에 대해 `DoWork`을 호출하면 새 `DoWork`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="55448-162">In this case, if `DoWork` is called on D using a variable of type D, the new `DoWork` is called.</span></span> <span data-ttu-id="55448-163">형식 C, B 또는 A 변수를 사용하여 D의 인스턴스에 액세스하면 `DoWork`에 대한 호출에서 가상 상속의 규칙을 따라 해당 호출을 클래스 C에 대한 `DoWork`의 구현으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-163">If a variable of type C, B, or A is used to access an instance of D, a call to `DoWork` will follow the rules of virtual inheritance, routing those calls to the implementation of `DoWork` on class C.</span></span>  
  
### <a name="accessing-base-class-virtual-members-from-derived-classes"></a><span data-ttu-id="55448-164">파생 클래스에서 기본 클래스 가상 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="55448-164">Accessing Base Class Virtual Members from Derived Classes</span></span>  
 <span data-ttu-id="55448-165">메서드 또는 속성을 바꾸었거나 재정의한 파생 클래스는 계속해서 base 키워드를 사용하여 기본 클래스에 대한 메서드 또는 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-165">A derived class that has replaced or overridden a method or property can still access the method or property on the base class using the base keyword.</span></span> <span data-ttu-id="55448-166">다음 코드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="55448-166">The following code provides an example:</span></span>  
  
 <span data-ttu-id="55448-167">[!code-cs[csProgGuideInheritance#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="55448-167">[!code-cs[csProgGuideInheritance#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/polymorphism_9.cs)]</span></span>  
  
 <span data-ttu-id="55448-168">자세한 내용은 [base](../../../csharp/language-reference/keywords/base.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55448-168">For more information, see [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55448-169">가상 멤버는 `base`를 사용하여 자체 구현에서 해당 멤버의 기본 클래스 구현을 호출하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-169">It is recommended that virtual members use `base` to call the base class implementation of that member in their own implementation.</span></span> <span data-ttu-id="55448-170">기본 클래스 동작이 발생하도록 하면 파생 클래스가 파생 클래스에 대한 동작 구현에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55448-170">Letting the base class behavior occur enables the derived class to concentrate on implementing behavior specific to the derived class.</span></span> <span data-ttu-id="55448-171">기본 클래스 구현이 호출되지 않는 경우 해당 동작이 기본 클래스의 동작과 호환되도록 하는 것은 파생 클래스의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="55448-171">If the base class implementation is not called, it is up to the derived class to make their behavior compatible with the behavior of the base class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55448-172">단원 내용</span><span class="sxs-lookup"><span data-stu-id="55448-172">In This Section</span></span>  
  
-   [<span data-ttu-id="55448-173">Override 및 New 키워드를 사용하여 버전 관리</span><span class="sxs-lookup"><span data-stu-id="55448-173">Versioning with the Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)  
  
-   [<span data-ttu-id="55448-174">Override 및 New 키워드를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="55448-174">Knowing When to Use Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)  
  
-   [<span data-ttu-id="55448-175">방법: ToString 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="55448-175">How to: Override the ToString Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-override-the-tostring-method.md)  
  
## <a name="see-also"></a><span data-ttu-id="55448-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55448-176">See Also</span></span>  
 <span data-ttu-id="55448-177">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="55448-177">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="55448-178">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="55448-178">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="55448-179">[상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="55448-179">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="55448-180">[추상 및 봉인 클래스와 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="55448-180">[Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span></span>  
 <span data-ttu-id="55448-181">[메서드](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="55448-181">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="55448-182">[이벤트](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="55448-182">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="55448-183">[속성](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="55448-183">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="55448-184">[인덱서](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="55448-184">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 [<span data-ttu-id="55448-185">유형</span><span class="sxs-lookup"><span data-stu-id="55448-185">Types</span></span>](../../../csharp/programming-guide/types/index.md)

