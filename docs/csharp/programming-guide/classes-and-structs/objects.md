---
title: "개체(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- objects [C#], about objects
- variables [C#]
ms.assetid: af4a5230-fbf3-4eea-95e1-8b883c2f845c
caps.latest.revision: 26
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
ms.openlocfilehash: a2a23d02e4ea95e908f97bc7264ee64d6899aee8
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="objects-c-programming-guide"></a><span data-ttu-id="f201b-102">개체(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f201b-102">Objects (C# Programming Guide)</span></span>
<span data-ttu-id="f201b-103">클래스 또는 구조체 정의는 형식이 수행할 수 있는 작업을 지정하는 청사진과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-103">A class or struct definition is like a blueprint that specifies what the type can do.</span></span> <span data-ttu-id="f201b-104">개체는 기본적으로 청사진에 따라 구성 및 할당된 메모리 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-104">An object is basically a block of memory that has been allocated and configured according to the blueprint.</span></span> <span data-ttu-id="f201b-105">프로그램에서 동일한 클래스의 많은 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-105">A program may create many objects of the same class.</span></span> <span data-ttu-id="f201b-106">개체를 인스턴스라고도 하며, 명명된 변수나 배열 또는 컬렉션에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-106">Objects are also called instances, and they can be stored in either a named variable or in an array or collection.</span></span> <span data-ttu-id="f201b-107">클라이언트 코드는 이러한 변수를 사용하여 메서드를 호출하고 개체의 공용 속성에 액세스하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-107">Client code is the code that uses these variables to call the methods and access the public properties of the object.</span></span> <span data-ttu-id="f201b-108">C#과 같은 개체 지향 언어에서 일반적인 프로그램은 동적으로 상호 작용하는 여러 개체로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-108">In an object-oriented language such as C#, a typical program consists of multiple objects interacting dynamically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f201b-109">정적 형식은 여기에 설명된 것과 다르게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-109">Static types behave differently than what is described here.</span></span> <span data-ttu-id="f201b-110">자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f201b-110">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
## <a name="struct-instances-vs-class-instances"></a><span data-ttu-id="f201b-111">구조체 인스턴스 및 클래스 인스턴스</span><span class="sxs-lookup"><span data-stu-id="f201b-111">Struct Instances vs. Class Instances</span></span>  
 <span data-ttu-id="f201b-112">클래스는 참조 형식이므로 클래스 개체의 변수는 관리되는 힙의 개체 주소에 대한 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-112">Because classes are reference types, a variable of a class object holds a reference to the address of the object on the managed heap.</span></span> <span data-ttu-id="f201b-113">동일한 형식의 두 번째 개체가 첫 번째 개체에 할당되면 두 변수가 모두 해당 주소의 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-113">If a second object of the same type is assigned to the first object, then both variables refer to the object at that address.</span></span> <span data-ttu-id="f201b-114">이 내용에 대해서는 이 항목의 뒷부분에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-114">This point is discussed in more detail later in this topic.</span></span>  
  
 <span data-ttu-id="f201b-115">클래스 인스턴스는 [new 연산자](../../../csharp/language-reference/keywords/new-operator.md)를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-115">Instances of classes are created by using the [new operator](../../../csharp/language-reference/keywords/new-operator.md).</span></span> <span data-ttu-id="f201b-116">다음 예제에서 `Person`은 형식이고 `person1` 및 `person 2`는 해당 형식의 인스턴스 또는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-116">In the following example, `Person` is the type and `person1` and `person 2` are instances, or objects, of that type.</span></span>  
  
 <span data-ttu-id="f201b-117">[!code-cs[csProgGuideStatements#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f201b-117">[!code-cs[csProgGuideStatements#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_1.cs)]</span></span>  
  
 <span data-ttu-id="f201b-118">구조체는 값 형식이므로 구조체 개체의 변수는 전체 개체의 복사본을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-118">Because structs are value types, a variable of a struct object holds a copy of the entire object.</span></span> <span data-ttu-id="f201b-119">다음 예제와 같이 `new` 연산자를 사용하여 구조체 인스턴스를 만들 수도 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-119">Instances of structs can also be created by using the `new` operator, but this is not required, as shown in the following example:</span></span>  
  
 <span data-ttu-id="f201b-120">[!code-cs[csProgGuideStatements#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f201b-120">[!code-cs[csProgGuideStatements#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_2.cs)]</span></span>  
  
 <span data-ttu-id="f201b-121">`p1` 및 `p2` 둘 다에 대한 메모리가 스레드 스택에서 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-121">The memory for both `p1` and `p2` is allocated on the thread stack.</span></span> <span data-ttu-id="f201b-122">해당 메모리가 선언된 형식 또는 메서드와 함께 회수됩니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-122">That memory is reclaimed along with the type or method in which it is declared.</span></span> <span data-ttu-id="f201b-123">이는 할당 시 구조체가 복사되는 이유 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-123">This is one reason why structs are copied on assignment.</span></span> <span data-ttu-id="f201b-124">반면, 클래스 인스턴스에 할당된 메모리는 개체에 대한 모든 참조가 범위를 벗어날 때 공용 언어 런타임에 의해 자동으로 회수(가비지 수집)됩니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-124">By contrast, the memory that is allocated for a class instance is automatically reclaimed (garbage collected) by the common language runtime when all references to the object have gone out of scope.</span></span> <span data-ttu-id="f201b-125">C++에서와 같이 클래스 개체를 자동으로 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-125">It is not possible to deterministically destroy a class object like you can in C++.</span></span> <span data-ttu-id="f201b-126">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 가비지 수집에 대한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f201b-126">For more information about garbage collection in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f201b-127">관리되는 힙의 메모리 할당 및 할당 취소는 공용 언어 런타임에서 고도로 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-127">The allocation and deallocation of memory on the managed heap is highly optimized in the common language runtime.</span></span> <span data-ttu-id="f201b-128">대부분의 경우 힙에서 클래스 인스턴스를 할당하는 경우와 스택에서 구조체 인스턴스를 할당하는 경우의 성능 차이는 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-128">In most cases there is no significant difference in the performance cost of allocating a class instance on the heap versus allocating a struct instance on the stack.</span></span>  
  
## <a name="object-identity-vs-value-equality"></a><span data-ttu-id="f201b-129">개체 ID와 값 같음 비교</span><span class="sxs-lookup"><span data-stu-id="f201b-129">Object Identity vs. Value Equality</span></span>  
 <span data-ttu-id="f201b-130">두 개체가 같은지를 비교하는 경우 먼저 두 변수가 메모리에서 동일한 개체를 나타내는지 또는 해당 필드 값이 하나 이상 같은지를 알고 싶은 것인지 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-130">When you compare two objects for equality, you must first distinguish whether you want to know whether the two variables represent the same object in memory, or whether the values of one or more of their fields are equivalent.</span></span> <span data-ttu-id="f201b-131">값을 비교하려는 경우 개체가 값 형식(구조체) 또는 참조 형식(클래스, 대리자, 배열)의 인스턴스인지 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-131">If you are intending to compare values, you must consider whether the objects are instances of value types (structs) or reference types (classes, delegates, arrays).</span></span>  
  
-   <span data-ttu-id="f201b-132">두 클래스 인스턴스가 메모리의 동일한 위치를 참조하는지 확인하려면(즉, *ID*가 같음) 정적 <xref:System.Object.Equals%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-132">To determine whether two class instances refer to the same location in memory (which means that they have the same *identity*), use the static <xref:System.Object.Equals%2A> method.</span></span> <span data-ttu-id="f201b-133"><xref:System.Object?displayProperty=fullName>은 사용자 정의 구조체 및 클래스를 포함하여 모든 값 형식 및 참조 형식에 대한 암시적 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-133">(<xref:System.Object?displayProperty=fullName> is the implicit base class for all value types and reference types, including user-defined structs and classes.)</span></span>  
  
-   <span data-ttu-id="f201b-134">두 구조체 인스턴스의 인스턴스 필드 값이 같은지 확인하려면 <xref:System.ValueType.Equals%2A?displayProperty=fullName> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-134">To determine whether the instance fields in two struct instances have the same values, use the <xref:System.ValueType.Equals%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="f201b-135">모든 구조체가 <xref:System.ValueType?displayProperty=fullName>에서 암시적으로 상속하기 때문에 다음 예제와 같이 개체에서 직접 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-135">Because all structs implicitly inherit from <xref:System.ValueType?displayProperty=fullName>, you call the method directly on your object as shown in the following example:</span></span>  
  
 <span data-ttu-id="f201b-136">[!code-cs[csProgGuideStatements#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f201b-136">[!code-cs[csProgGuideStatements#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/objects_3.cs)]</span></span>  
  
 <span data-ttu-id="f201b-137">`Equals`의 <xref:System.ValueType?displayProperty=fullName> 구현에서는 구조체의 필드를 확인할 수 있어야 하므로 리플렉션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-137">The <xref:System.ValueType?displayProperty=fullName> implementation of `Equals` uses reflection because it must be able to determine what the fields are in any struct.</span></span> <span data-ttu-id="f201b-138">고유한 구조체를 만드는 경우 `Equals` 메서드를 재정의하여 해당 형식과 관련된 효율적인 같음 알고리즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-138">When creating your own structs, override the `Equals` method to provide an efficient equality algorithm that is specific to your type.</span></span>  
  
-   <span data-ttu-id="f201b-139">두 클래스 인스턴스의 필드 값이 같은지 확인하기 위해 <xref:System.Object.Equals%2A> 메서드 또는 [== 연산자](../../../csharp/language-reference/operators/equality-comparison-operator.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-139">To determine whether the values of the fields in two class instances are equal, you might be able to use the <xref:System.Object.Equals%2A> method or the [== operator](../../../csharp/language-reference/operators/equality-comparison-operator.md).</span></span> <span data-ttu-id="f201b-140">그러나 클래스가 해당 형식의 개체에 대해 "같음"이 무엇을 의미하는지의 사용자 지정 정의를 제공하도록 재정의 또는 오버로드한 경우에만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-140">However, only use them if the class has overridden or overloaded them to provide a custom definition of what "equality" means for objects of that type.</span></span> <span data-ttu-id="f201b-141">클래스는 <xref:System.IEquatable%601> 인터페이스 또는 <xref:System.Collections.Generic.IEqualityComparer%601> 인터페이스도 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-141">The class might also implement the <xref:System.IEquatable%601> interface or the <xref:System.Collections.Generic.IEqualityComparer%601> interface.</span></span> <span data-ttu-id="f201b-142">두 인터페이스 모두 값이 같은지를 테스트하는 데 사용할 수 있는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-142">Both interfaces provide methods that can be used to test value equality.</span></span> <span data-ttu-id="f201b-143">`Equals`을 재정의하는 고유한 클래스를 디자인하는 경우 [방법: 형식의 값 일치 정의](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md) 및 <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>에 명시된 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f201b-143">When designing your own classes that override `Equals`, make sure to follow the guidelines stated in [How to: Define Value Equality for a Type](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md) and <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f201b-144">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f201b-144">Related Sections</span></span>  
 <span data-ttu-id="f201b-145">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f201b-145">For more information:</span></span>  
  
-   [<span data-ttu-id="f201b-146">클래스</span><span class="sxs-lookup"><span data-stu-id="f201b-146">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
  
-   [<span data-ttu-id="f201b-147">구조체</span><span class="sxs-lookup"><span data-stu-id="f201b-147">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
  
-   [<span data-ttu-id="f201b-148">생성자</span><span class="sxs-lookup"><span data-stu-id="f201b-148">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="f201b-149">종료자</span><span class="sxs-lookup"><span data-stu-id="f201b-149">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
  
-   [<span data-ttu-id="f201b-150">이벤트</span><span class="sxs-lookup"><span data-stu-id="f201b-150">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="f201b-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f201b-151">See Also</span></span>  
 <span data-ttu-id="f201b-152">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f201b-152">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f201b-153">[object](../../../csharp/language-reference/keywords/object.md) </span><span class="sxs-lookup"><span data-stu-id="f201b-153">[object](../../../csharp/language-reference/keywords/object.md) </span></span>  
 <span data-ttu-id="f201b-154">[상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="f201b-154">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="f201b-155">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="f201b-155">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="f201b-156">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="f201b-156">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 <span data-ttu-id="f201b-157">[new 연산자](../../../csharp/language-reference/keywords/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="f201b-157">[new Operator](../../../csharp/language-reference/keywords/new-operator.md) </span></span>  
 [<span data-ttu-id="f201b-158">공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="f201b-158">Common Type System</span></span>](../../../standard/base-types/common-type-system.md)

