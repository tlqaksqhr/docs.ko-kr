---
title: 추상 및 봉인 클래스와 클래스 멤버(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: aa7c951acadd2e7b60f6da17cd7bf357fbd02d95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313916"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="1557e-102">추상 및 봉인 클래스와 클래스 멤버(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1557e-102">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="1557e-103">[abstract](../../../csharp/language-reference/keywords/abstract.md) 키워드를 사용하면, 불완전하여 파생 클래스에서 구현해야 하는 클래스 및 [클래스](../../../csharp/language-reference/keywords/class.md) 멤버를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-103">The [abstract](../../../csharp/language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../../csharp/language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="1557e-104">[sealed](../../../csharp/language-reference/keywords/sealed.md) 키워드를 사용하면, 이전에 [virtual](../../../csharp/language-reference/keywords/virtual.md)로 표시되었던 클래스나 특정 클래스 멤버의 상속을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-104">The [sealed](../../../csharp/language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="1557e-105">추상 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="1557e-105">Abstract Classes and Class Members</span></span>  
 <span data-ttu-id="1557e-106">클래스 정의 앞에 `abstract` 키워드를 배치하여 클래스를 추상으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-106">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="1557e-107">예:</span><span class="sxs-lookup"><span data-stu-id="1557e-107">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]  
  
 <span data-ttu-id="1557e-108">추상 클래스는 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-108">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="1557e-109">추상 클래스의 목적은 여러 파생 클래스에서 공유할 수 있는 기본 클래스의 공통적인 정의를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-109">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="1557e-110">예를 들어 클래스 라이브러리에서 여러 자체 함수에 매개 변수로 사용되는 추상 클래스를 정의한 다음 해당 라이브러리를 사용하는 프로그래머가 파생 클래스를 만들어 클래스의 고유 구현을 제공하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-110">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="1557e-111">추상 클래스에서는 추상 메서드도 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-111">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="1557e-112">메서드의 반환 형식 앞에 `abstract` 키워드를 추가하면 추상 메서드가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-112">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="1557e-113">예:</span><span class="sxs-lookup"><span data-stu-id="1557e-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]  
  
 <span data-ttu-id="1557e-114">추상 메서드에는 구현이 없으므로 메서드 정의 다음에는 일반적인 메서드 블록 대신 세미콜론이 옵니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-114">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="1557e-115">추상 클래스의 파생 클래스에서는 모든 추상 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-115">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="1557e-116">추상 클래스에서 기본 클래스의 가상 메서드를 상속하는 경우 추상 클래스에서는 추상 메서드를 사용하여 가상 메서드를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-116">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="1557e-117">예:</span><span class="sxs-lookup"><span data-stu-id="1557e-117">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]  
  
 <span data-ttu-id="1557e-118">`virtual` 메서드는 `abstract`로 선언되어도 추상 클래스에서 상속된 모든 클래스에 대해 여전히 가상입니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-118">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="1557e-119">추상 메서드를 상속하는 클래스에서는 메서드의 원본 구현에 액세스할 수 없습니다. 앞의 예제에서 F 클래스의 `DoWork`에서는 D 클래스의 `DoWork`를 호출할 수 없습니다. 따라서 추상 클래스는 파생 클래스에서 가상 메서드에 대한 새 메서드 구현을 반드시 제공하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-119">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="1557e-120">봉인 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="1557e-120">Sealed Classes and Class Members</span></span>  
 <span data-ttu-id="1557e-121">클래스 정의 앞에 `sealed` 키워드를 배치하여 클래스를 [sealed](../../../csharp/language-reference/keywords/sealed.md)로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-121">Classes can be declared as [sealed](../../../csharp/language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="1557e-122">예:</span><span class="sxs-lookup"><span data-stu-id="1557e-122">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]  
  
 <span data-ttu-id="1557e-123">봉인 클래스는 기본 클래스로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-123">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="1557e-124">그러므로 추상 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-124">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="1557e-125">봉인 클래스는 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-125">Sealed classes prevent derivation.</span></span> <span data-ttu-id="1557e-126">봉인 클래스는 기본 클래스로 사용될 수 없으므로 일부 런타임 최적화에서는 봉인 클래스 멤버 호출이 약간 더 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-126">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="1557e-127">기본 클래스의 가상 멤버를 재정의하는 파생 클래스의 메서드, 인덱서, 속성 또는 이벤트는 해당 멤버를 봉인으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-127">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="1557e-128">이렇게 하면 이후에 파생되는 클래스에서는 해당 멤버가 가상이 아니게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-128">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="1557e-129">클래스 멤버 선언에서 [override](../../../csharp/language-reference/keywords/override.md) 키워드 앞에 `sealed` 키워드를 배치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1557e-129">This is accomplished by putting the `sealed` keyword before the [override](../../../csharp/language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="1557e-130">예:</span><span class="sxs-lookup"><span data-stu-id="1557e-130">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1557e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1557e-131">See Also</span></span>  
 [<span data-ttu-id="1557e-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1557e-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1557e-133">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="1557e-133">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="1557e-134">상속</span><span class="sxs-lookup"><span data-stu-id="1557e-134">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [<span data-ttu-id="1557e-135">메서드</span><span class="sxs-lookup"><span data-stu-id="1557e-135">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="1557e-136">필드</span><span class="sxs-lookup"><span data-stu-id="1557e-136">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)  
 [<span data-ttu-id="1557e-137">방법: 추상 속성 정의</span><span class="sxs-lookup"><span data-stu-id="1557e-137">How to: Define Abstract Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)
