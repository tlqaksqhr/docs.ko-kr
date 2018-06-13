---
title: 제네릭 클래스(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
ms.openlocfilehash: 65c5f376bce44e6120c17638076d2edfc38c734e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338288"
---
# <a name="generic-classes-c-programming-guide"></a><span data-ttu-id="7679f-102">제네릭 클래스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7679f-102">Generic Classes (C# Programming Guide)</span></span>
<span data-ttu-id="7679f-103">제네릭 클래스는 특정 데이터 형식과 관련이 없는 작업을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-103">Generic classes encapsulate operations that are not specific to a particular data type.</span></span> <span data-ttu-id="7679f-104">제네릭 클래스는 연결된 목록, 해시 테이블, 스택, 큐, 트리 등의 컬렉션에 가장 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-104">The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on.</span></span> <span data-ttu-id="7679f-105">컬렉션에서 항목을 추가하고 제거하는 등의 작업은 저장되는 데이터의 형식과 관계없이 기본적으로 동일한 방식으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-105">Operations such as adding and removing items from the collection are performed in basically the same way regardless of the type of data being stored.</span></span>  
  
 <span data-ttu-id="7679f-106">컬렉션 클래스를 필요로 하는 대부분의 시나리오에서는 .NET 클래스 라이브러리에서 제공하는 컬렉션 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-106">For most scenarios that require collection classes, the recommended approach is to use the ones provided in the .NET class library.</span></span> <span data-ttu-id="7679f-107">이러한 클래스 사용에 대한 자세한 내용은 [.NET의 제네릭 컬렉션](../../../standard/generics/collections.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7679f-107">For more information about using these classes, see [Generic Collections in .NET](../../../standard/generics/collections.md).</span></span>  
  
 <span data-ttu-id="7679f-108">일반적으로 기존의 구체적인 클래스로 시작하여 일반성과 편의성의 균형이 맞을 때까지 형식을 하나씩 형식 매개 변수로 변경하여 제네릭 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-108">Typically, you create generic classes by starting with an existing concrete class, and changing types into type parameters one at a time until you reach the optimal balance of generalization and usability.</span></span> <span data-ttu-id="7679f-109">고유한 제네릭 클래스를 만들 때 중요한 고려 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-109">When creating your own generic classes, important considerations include the following:</span></span>  
  
-   <span data-ttu-id="7679f-110">형식 매개 변수로 일반화할 형식</span><span class="sxs-lookup"><span data-stu-id="7679f-110">Which types to generalize into type parameters.</span></span>  
  
     <span data-ttu-id="7679f-111">일반적으로 매개 변수화할 수 있는 형식이 많을수록 코드의 유용성과 재사용 가능성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-111">As a rule, the more types you can parameterize, the more flexible and reusable your code becomes.</span></span> <span data-ttu-id="7679f-112">그러나 지나친 일반화는 다른 개발자가 읽거나 이해하기 어려운 코드를 만들어낼 소지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-112">However, too much generalization can create code that is difficult for other developers to read or understand.</span></span>  
  
-   <span data-ttu-id="7679f-113">형식 매개 변수에 적용할 제약 조건([형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md) 참조)</span><span class="sxs-lookup"><span data-stu-id="7679f-113">What constraints, if any, to apply to the type parameters (See [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span></span>  
  
     <span data-ttu-id="7679f-114">필요한 형식을 처리할 수 있는 범위 내에서 최대한 많은 제약 조건을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-114">A good rule is to apply the maximum constraints possible that will still let you handle the types you must handle.</span></span> <span data-ttu-id="7679f-115">예를 들어 제네릭 클래스를 참조 형식으로만 사용하려는 경우에는 클래스 제약 조건을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-115">For example, if you know that your generic class is intended for use only with reference types, apply the class constraint.</span></span> <span data-ttu-id="7679f-116">이렇게 하면 클래스를 값 형식으로 잘못 사용하는 것을 막을 수 있고, `as` 연산자를 `T`에 적용하여 null 값 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-116">That will prevent unintended use of your class with value types, and will enable you to use the `as` operator on `T`, and check for null values.</span></span>  
  
-   <span data-ttu-id="7679f-117">제네릭 동작을 기본 클래스와 서브클래스로 분할할지 여부</span><span class="sxs-lookup"><span data-stu-id="7679f-117">Whether to factor generic behavior into base classes and subclasses.</span></span>  
  
     <span data-ttu-id="7679f-118">제네릭 클래스는 기본 클래스가 될 수 있으므로 제네릭이 아닌 클래스에 적용되는 디자인 고려 사항이 동일하게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-118">Because generic classes can serve as base classes, the same design considerations apply here as with non-generic classes.</span></span> <span data-ttu-id="7679f-119">자세한 내용은 이 항목의 뒷부분에서 설명하는 제네릭 기본 클래스에서 상속하는 데 대한 규칙을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7679f-119">See the rules about inheriting from generic base classes later in this topic.</span></span>  
  
-   <span data-ttu-id="7679f-120">제네릭 인터페이스를 하나 이상 구현할지 여부</span><span class="sxs-lookup"><span data-stu-id="7679f-120">Whether to implement one or more generic interfaces.</span></span>  
  
     <span data-ttu-id="7679f-121">예를 들어 제네릭 기반 컬렉션에 항목을 만드는 데 사용될 클래스를 디자인할 경우 클래스 형식이 `T`인 <xref:System.IComparable%601>와 같은 인터페이스를 구현해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-121">For example, if you are designing a class that will be used to create items in a generics-based collection, you may have to implement an interface such as <xref:System.IComparable%601> where `T` is the type of your class.</span></span>  
  
 <span data-ttu-id="7679f-122">간단한 제네릭 클래스의 예제를 보려면 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7679f-122">For an example of a simple generic class, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span>  
  
 <span data-ttu-id="7679f-123">형식 매개 변수와 제약 조건에 대한 규칙은 제네릭 클래스 동작, 특히 상속과 멤버 접근성에 몇 가지 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-123">The rules for type parameters and constraints have several implications for generic class behavior, especially regarding inheritance and member accessibility.</span></span> <span data-ttu-id="7679f-124">계속하려면 몇 가지 용어를 이해하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-124">Before proceeding, you should understand some terms.</span></span> <span data-ttu-id="7679f-125">제네릭 클래스 `Node<T>,`의 경우 클라이언트 코드는 형식 인수를 지정하여 폐쇄형 생성 형식(`Node<int>`)을 만들어 클래스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-125">For a generic class `Node<T>,` client code can reference the class either by specifying a type argument, to create a closed constructed type (`Node<int>`).</span></span> <span data-ttu-id="7679f-126">또는 제네릭 기본 클래스를 지정하는 경우와 같이 형식 매개 변수를 지정하지 않고 개방형 생성 형식(`Node<T>`)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-126">Alternatively, it can leave the type parameter unspecified, for example when you specify a generic base class, to create an open constructed type (`Node<T>`).</span></span> <span data-ttu-id="7679f-127">제네릭 클래스는 구체적인 클래스, 폐쇄형 생성 클래스 또는 개방형 생성 기본 클래스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-127">Generic classes can inherit from concrete, closed constructed, or open constructed base classes:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]  
  
 <span data-ttu-id="7679f-128">제네릭이 아닌 구체적인 클래스는 폐쇄형 생성 기본 클래스에서는 상속할 수 있지만 개방형 생성 클래스 또는 형식 매개 변수에서는 상속할 수 없습니다. 이는 런타임에 클라이언트 코드에서 기본 클래스를 인스턴스화할 때 필요한 형식 인수를 제공할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-128">Non-generic, in other words, concrete, classes can inherit from closed constructed base classes, but not from open constructed classes or from type parameters because there is no way at run time for client code to supply the type argument required to instantiate the base class.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]  
  
 <span data-ttu-id="7679f-129">개방형 생성 형식에서 상속하는 제네릭 클래스에서는 다음 코드와 같이 상속하는 클래스에서 공유하지 않는 모든 기본 클래스 형식 매개 변수에 대해 형식 인수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-129">Generic classes that inherit from open constructed types must supply type arguments for any base class type parameters that are not shared by the inheriting class, as demonstrated in the following code:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]  
  
 <span data-ttu-id="7679f-130">개방형 생성 형식에서 상속하는 제네릭 클래스에서는 기본 형식에 대한 제약 조건을 포함하거나 암시하는 제약 조건을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-130">Generic classes that inherit from open constructed types must specify constraints that are a superset of, or imply, the constraints on the base type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]  
  
 <span data-ttu-id="7679f-131">제네릭 형식은 다음과 같이 여러 형식 매개 변수와 제약 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-131">Generic types can use multiple type parameters and constraints, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]  
  
 <span data-ttu-id="7679f-132">개방형 생성 형식 및 폐쇄형 생성 형식은 메서드 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-132">Open constructed and closed constructed types can be used as method parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]  
  
 <span data-ttu-id="7679f-133">제네릭 클래스에서 인터페이스를 구현하면 이 클래스의 모든 인스턴스를 해당 인터페이스에 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-133">If a generic class implements an interface, all instances of that class can be cast to that interface.</span></span>  
  
 <span data-ttu-id="7679f-134">제네릭 클래스는 고정적입니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-134">Generic classes are invariant.</span></span> <span data-ttu-id="7679f-135">즉, 입력 매개 변수에서 `List<BaseClass>`를 지정하면 `List<DerivedClass>`를 제공하려고 할 때 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7679f-135">In other words, if an input parameter specifies a `List<BaseClass>`, you will get a compile-time error if you try to provide a `List<DerivedClass>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7679f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7679f-136">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="7679f-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7679f-137">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7679f-138">제네릭</span><span class="sxs-lookup"><span data-stu-id="7679f-138">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
 [<span data-ttu-id="7679f-139">열거자의 상태 저장</span><span class="sxs-lookup"><span data-stu-id="7679f-139">Saving the State of Enumerators</span></span>](https://blogs.msdn.microsoft.com/wesdyer/2006/01/13/saving-the-state-of-enumerators/)  
 [<span data-ttu-id="7679f-140">상속 퍼즐, 1부</span><span class="sxs-lookup"><span data-stu-id="7679f-140">An Inheritance Puzzle, Part One</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/07/27/an-inheritance-puzzle-part-one/)
