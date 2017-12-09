---
title: "개체 지향 프로그래밍 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 950f080949dce0fc1a2834825d2f7c945007fb7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="8e96a-102">개체 지향 프로그래밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e96a-102">Object-Oriented Programming (Visual Basic)</span></span>
<span data-ttu-id="8e96a-103">Visual Basic 캡슐화, 상속, 다형성 등 개체 지향 프로그래밍에 대 한 완벽 하 게 지원에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>  
  
 <span data-ttu-id="8e96a-104">*캡슐화*는 서로 관련된 속성, 메서드 및 기타 멤버의 그룹을 하나의 단위나 개체로 취급하는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>  
  
 <span data-ttu-id="8e96a-105">*상속*은 기존 클래스를 기반으로 새로운 클래스를 만들 수 있는 능력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>  
  
 <span data-ttu-id="8e96a-106">*다형성*은 동일한 속성 또는 메서드를 각각 다른 방식으로 구현하는 여러 클래스를 서로 교체하여 사용할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>  
  
 <span data-ttu-id="8e96a-107">이 단원에서는 다음과 같은 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-107">This section describes the following concepts:</span></span>  
  
-   [<span data-ttu-id="8e96a-108">클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="8e96a-108">Classes and objects</span></span>](#classes-and-objects)  
  
    -   [<span data-ttu-id="8e96a-109">클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="8e96a-109">Class members</span></span>](#members)  
  
         [<span data-ttu-id="8e96a-110">속성 및 필드</span><span class="sxs-lookup"><span data-stu-id="8e96a-110">Properties and fields</span></span>](#properties-and-fields)  
  
         [<span data-ttu-id="8e96a-111">메서드</span><span class="sxs-lookup"><span data-stu-id="8e96a-111">Methods</span></span>](#methods)  
  
         [<span data-ttu-id="8e96a-112">생성자</span><span class="sxs-lookup"><span data-stu-id="8e96a-112">Constructors</span></span>](#constructors)  
  
         [<span data-ttu-id="8e96a-113">소멸자</span><span class="sxs-lookup"><span data-stu-id="8e96a-113">Destructors</span></span>](#destructors)  
  
         [<span data-ttu-id="8e96a-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="8e96a-114">Events</span></span>](#events)  
  
         [<span data-ttu-id="8e96a-115">중첩된 클래스</span><span class="sxs-lookup"><span data-stu-id="8e96a-115">Nested classes</span></span>](#nested-classes)  
  
    -   [<span data-ttu-id="8e96a-116">액세스 한정자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="8e96a-116">Access modifiers and access levels</span></span>](#access-modifiers-and-access-levels)  
  
    -   [<span data-ttu-id="8e96a-117">클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="8e96a-117">Instantiating classes</span></span>](#instantiating-classes)  
  
    -   [<span data-ttu-id="8e96a-118">공유 클래스 및 멤버</span><span class="sxs-lookup"><span data-stu-id="8e96a-118">Shared classes and members</span></span>](#shared-classes-and-members)  
  
    -   [<span data-ttu-id="8e96a-119">무명 형식</span><span class="sxs-lookup"><span data-stu-id="8e96a-119">Anonymous types</span></span>](#anonymous-types)  
  
-   [<span data-ttu-id="8e96a-120">상속</span><span class="sxs-lookup"><span data-stu-id="8e96a-120">Inheritance</span></span>](#inheritance)  
  
    -   [<span data-ttu-id="8e96a-121">멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="8e96a-121">Overriding members</span></span>](#overriding-members)  
  
-   [<span data-ttu-id="8e96a-122">인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e96a-122">Interfaces</span></span>](#interfaces)  
  
-   [<span data-ttu-id="8e96a-123">제네릭</span><span class="sxs-lookup"><span data-stu-id="8e96a-123">Generics</span></span>](#generics)  
  
-   [<span data-ttu-id="8e96a-124">대리자</span><span class="sxs-lookup"><span data-stu-id="8e96a-124">Delegates</span></span>](#delegates)  
  
## <a name="classes-and-objects"></a><span data-ttu-id="8e96a-125">클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="8e96a-125">Classes and objects</span></span>  
<span data-ttu-id="8e96a-126">*클래스*와 *개체*를 혼용하는 경우가 있지만 클래스는 개체의 *형식*을 나타내고 개체는 사용 가능한 클래스의 *인스턴스*를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="8e96a-127">따라서 개체를 만드는 작업을 *인스턴스화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="8e96a-128">청사진에 비유한다면 클래스는 청사진이고 개체는 해당 청사진을 사용하여 만든 빌딩입니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="8e96a-129">클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-129">To define a class:</span></span>

```vb  
Class SampleClass
End Class
```

<span data-ttu-id="8e96a-130">Visual Basic에서 간단한 버전의 클래스도 제공 *구조* 하는 큰 개체 배열을 만들 수 있고 필요한 경우 유용 원하지는 메모리를 너무 많이 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>

<span data-ttu-id="8e96a-131">구조체를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-131">To define a structure:</span></span>  

```vb
Structure SampleStructure
End Structure
```

<span data-ttu-id="8e96a-132">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-132">For more information, see:</span></span>

- [<span data-ttu-id="8e96a-133">Class 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="8e96a-134">Structure 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a><span data-ttu-id="8e96a-135">클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="8e96a-135">Class members</span></span>
<span data-ttu-id="8e96a-136">각 클래스에는 클래스 데이터를 설명하는 속성, 클래스 동작을 정의하는 메서드 및 서로 다른 클래스와 개체 간의 통신을 제공하는 이벤트가 포함된 다양한 *클래스 멤버*가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="8e96a-137">속성 및 필드</span><span class="sxs-lookup"><span data-stu-id="8e96a-137">Properties and fields</span></span>
<span data-ttu-id="8e96a-138">필드 및 속성은 개체가 포함하는 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="8e96a-139">필드는 직접 읽거나 설정할 수 있기 때문에 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-139">Fields are like variables because they can be read or set directly.</span></span>

<span data-ttu-id="8e96a-140">필드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-140">To define a field:</span></span>

```vb
Class SampleClass
    Public SampleField As String
End Class
```

<span data-ttu-id="8e96a-141">속성에는 값을 설정하고 가져오는 방법을 보다 세밀하게 제어할 수 있는 get 및 set 프로시저가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="8e96a-142">Visual Basic을 사용 하면 자동으로 백그라운드에서이 필드를 만들고 속성 프로시저에 대 한 기본 논리를 제공 하는 소위 자동 구현 속성을 사용 하거나 속성 값을 저장 하기 위한 전용 필드를 만들가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="8e96a-143">자동 구현 속성을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-143">To define an auto-implemented property:</span></span>

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

<span data-ttu-id="8e96a-144">속성 값을 읽고 쓰기 위해 몇 가지 추가 작업을 수행해야 하는 경우 다음과 같이 속성 값을 저장하기 위한 필드를 정의하고, 속성 값을 저장 및 검색하기 위한 기본 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

<span data-ttu-id="8e96a-145">대부분의 속성에는 속성 값을 설정하고 가져오는 메서드나 프로시저가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="8e96a-146">그러나 읽기 전용 또는 쓰기 전용 속성을 만들어 속성을 수정하거나 읽지 못하도록 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="8e96a-147">이렇게 하려면 Visual Basic에서는 `ReadOnly` 및 `WriteOnly` 키워드를 사용하면 되고</span><span class="sxs-lookup"><span data-stu-id="8e96a-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="8e96a-148">하지만 자동 구현 속성은 읽기 전용 또는 쓰기 전용일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>

<span data-ttu-id="8e96a-149">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-149">For more information, see:</span></span>
  
-   [<span data-ttu-id="8e96a-150">Property 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="8e96a-151">Get 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
  
-   [<span data-ttu-id="8e96a-152">Set 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
  
-   [<span data-ttu-id="8e96a-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="8e96a-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
-   [<span data-ttu-id="8e96a-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="8e96a-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
  
#### <a name="methods"></a><span data-ttu-id="8e96a-155">메서드</span><span class="sxs-lookup"><span data-stu-id="8e96a-155">Methods</span></span>  
 <span data-ttu-id="8e96a-156">*메서드*는 개체에서 수행할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-156">A *method* is an action that an object can perform.</span></span>  

> [!NOTE]
>  <span data-ttu-id="8e96a-157">Visual Basic에서는 두 가지 방법으로 메서드를 만들 수 있습니다. 메서드가 값을 반환하지 않으면 `Sub` 문을 사용하고 메서드가 값을 반환하면 `Function` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>

<span data-ttu-id="8e96a-158">클래스의 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-158">To define a method of a class:</span></span>

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

<span data-ttu-id="8e96a-159">클래스에는 매개 변수 개수나 매개 변수 형식이 다른 동일한 메서드의 구현 또는 *오버로드*가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="8e96a-160">메서드를 오버로드하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-160">To overload a method:</span></span>

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

<span data-ttu-id="8e96a-161">대부분의 경우 클래스 정의 내에서 메서드를 선언하지만</span><span class="sxs-lookup"><span data-stu-id="8e96a-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="8e96a-162">하지만 Visual Basic도 지원 *확장 메서드* 클래스의 실제 정의 밖에 있는 기존 클래스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="8e96a-163">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-163">For more information, see:</span></span>

- [<span data-ttu-id="8e96a-164">Function 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  

- [<span data-ttu-id="8e96a-165">Sub 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  

- [<span data-ttu-id="8e96a-166">오버로드</span><span class="sxs-lookup"><span data-stu-id="8e96a-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  

- [<span data-ttu-id="8e96a-167">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="8e96a-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  

#### <a name="constructors"></a><span data-ttu-id="8e96a-168">생성자</span><span class="sxs-lookup"><span data-stu-id="8e96a-168">Constructors</span></span>  
<span data-ttu-id="8e96a-169">생성자는 지정된 형식의 개체를 만들 때 자동으로 실행되는 클래스 메서드로,</span><span class="sxs-lookup"><span data-stu-id="8e96a-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="8e96a-170">일반적으로 새 개체의 데이터 멤버를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="8e96a-171">생성자는 클래스를 만들 때 한 번만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="8e96a-172">또한 생성자의 코드는 항상 클래스의 다른 코드보다 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="8e96a-173">그러나 다른 메서드를 만들 때와 동일한 방법으로 여러 생성자 오버로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="8e96a-174">클래스의 생성자를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-174">To define a constructor for a class:</span></span>

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class 
```

<span data-ttu-id="8e96a-175">자세한 내용은 참조: [개체 수명: 개체가 만들어지고 소멸 되는 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

#### <a name="destructors"></a><span data-ttu-id="8e96a-176">소멸자</span><span class="sxs-lookup"><span data-stu-id="8e96a-176">Destructors</span></span>
<span data-ttu-id="8e96a-177">소멸자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="8e96a-178">.NET Framework에서는 응용 프로그램의 관리되는 개체에 대해 가비지 수집기가 자동으로 메모리를 할당하고 해제하지만</span><span class="sxs-lookup"><span data-stu-id="8e96a-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="8e96a-179">응용 프로그램에서 만들어지는 관리되지 않는 개체를 정리하려면 여전히 소멸자가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="8e96a-180">각 클래스에는 소멸자가 하나씩만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-180">There can be only one destructor for a class.</span></span>

<span data-ttu-id="8e96a-181">.NET Framework의 소멸자 및 가비지 수집에 대한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="8e96a-182">이벤트</span><span class="sxs-lookup"><span data-stu-id="8e96a-182">Events</span></span>
<span data-ttu-id="8e96a-183">클래스나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="8e96a-184">이벤트를 보내거나 발생시키는 클래스를 *게시자*라고 하며 이벤트를 받거나 처리하는 클래스를 *구독자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="8e96a-185">이벤트를 발생시키고 처리하는 방법에 대한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-185">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="8e96a-186">이벤트를 선언 하려면 사용 된 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>

- <span data-ttu-id="8e96a-187">이벤트를 발생 시키기 위해 사용 하 여는 [RaiseEvent 문](../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>

- <span data-ttu-id="8e96a-188">작업을 선언적으로 사용 하 여 이벤트 처리기를 지정 하려면는 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) 문 및 [처리](../../../visual-basic/language-reference/statements/handles-clause.md) 절.</span><span class="sxs-lookup"><span data-stu-id="8e96a-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>

- <span data-ttu-id="8e96a-189">동적으로 추가, 제거 및 변경 이벤트와 연결 된 이벤트 처리기를 사용 하 여는 [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md) 및 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md) 와 함께 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="8e96a-190">중첩된 클래스</span><span class="sxs-lookup"><span data-stu-id="8e96a-190">Nested classes</span></span>  
<span data-ttu-id="8e96a-191">다른 클래스 내에 정의된 클래스를 *중첩 클래스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="8e96a-192">기본적으로 중첩 클래스는 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-192">By default, the nested class is private.</span></span>

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

<span data-ttu-id="8e96a-193">중첩 클래스의 인스턴스를 만들려면 다음과 같이 컨테이너 클래스의 이름, 점, 중첩 클래스의 이름을 차례로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="8e96a-194">액세스 한정자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="8e96a-194">Access modifiers and access levels</span></span>  
<span data-ttu-id="8e96a-195">모든 클래스 및 클래스 멤버는 *액세스 한정자*를 사용하여 다른 클래스에 제공할 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="8e96a-196">다음과 같은 액세스 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-196">The following access modifiers are available:</span></span>

|<span data-ttu-id="8e96a-197">Visual Basic 한정자</span><span class="sxs-lookup"><span data-stu-id="8e96a-197">Visual Basic Modifier</span></span>|<span data-ttu-id="8e96a-198">정의</span><span class="sxs-lookup"><span data-stu-id="8e96a-198">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="8e96a-199">공용</span><span class="sxs-lookup"><span data-stu-id="8e96a-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="8e96a-200">동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|
|[<span data-ttu-id="8e96a-201">전용</span><span class="sxs-lookup"><span data-stu-id="8e96a-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="8e96a-202">동일한 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-202">The type or member can only be accessed by code in the same class.</span></span>|
|[<span data-ttu-id="8e96a-203">보호됨</span><span class="sxs-lookup"><span data-stu-id="8e96a-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="8e96a-204">동일한 클래스의 코드나 파생 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|
|[<span data-ttu-id="8e96a-205">Friend</span><span class="sxs-lookup"><span data-stu-id="8e96a-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="8e96a-206">동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|
|`Protected Friend`|<span data-ttu-id="8e96a-207">동일한 어셈블리의 코드 또는 다른 어셈블리의 파생 클래스에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|

<span data-ttu-id="8e96a-208">자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-208">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="8e96a-209">클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="8e96a-209">Instantiating classes</span></span>  
<span data-ttu-id="8e96a-210">개체를 만들려면 클래스를 인스턴스화하거나 클래스 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```vb
Dim sampleObject as New SampleClass()
```

<span data-ttu-id="8e96a-211">클래스를 인스턴스화한 후에는 인스턴스의 속성과 필드에 값을 할당하고 클래스 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

<span data-ttu-id="8e96a-212">클래스를 인스턴스화하는 동안 속성에 값을 할당하려면 다음과 같이 개체 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="8e96a-213">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-213">For more information, see:</span></span>

- [<span data-ttu-id="8e96a-214">New 연산자</span><span class="sxs-lookup"><span data-stu-id="8e96a-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)

- [<span data-ttu-id="8e96a-215">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="8e96a-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

###  <a name="Static"></a><span data-ttu-id="8e96a-216">공유 클래스 및 멤버</span><span class="sxs-lookup"><span data-stu-id="8e96a-216">Shared Classes and Members</span></span>  
 <span data-ttu-id="8e96a-217">클래스의 공유 멤버에는 속성, 프로시저 또는 클래스의 모든 인스턴스에서 공유 되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>  
  
 <span data-ttu-id="8e96a-218">정의 하려면 공유 멤버:</span><span class="sxs-lookup"><span data-stu-id="8e96a-218">To define a shared member:</span></span>  
  
```vb  
Class SampleClass  
    Public Shared SampleString As String = "Sample String"  
End Class  
```  
  
 <span data-ttu-id="8e96a-219">공유 멤버에 액세스 하려면이 클래스의 개체를 만들지 않고 클래스의 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>  
  
```vb  
MsgBox(SampleClass.SampleString)  
```  
  
 <span data-ttu-id="8e96a-220">Visual Basic의 공유 모듈 멤버에만 공유 이어서 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="8e96a-221">공유 멤버도 액세스할 수 없습니다 공유 되지 않는 속성, 필드 또는 메서드</span><span class="sxs-lookup"><span data-stu-id="8e96a-221">Shared members also cannot access non-shared properties, fields or methods</span></span>  
  
 <span data-ttu-id="8e96a-222">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-222">For more information, see:</span></span>  
  
-   [<span data-ttu-id="8e96a-223">공유</span><span class="sxs-lookup"><span data-stu-id="8e96a-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
  
-   [<span data-ttu-id="8e96a-224">Module 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
### <a name="anonymous-types"></a><span data-ttu-id="8e96a-225">익명 형식</span><span class="sxs-lookup"><span data-stu-id="8e96a-225">Anonymous types</span></span>  
<span data-ttu-id="8e96a-226">익명 형식을 사용하면 데이터 형식에 대한 클래스 정의를 작성하지 않고 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="8e96a-227">대신 컴파일러가 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="8e96a-228">이 클래스는 사용할 수 있는 이름이 없고 개체를 선언할 때 지정하는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="8e96a-229">익명 형식의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-229">To create an instance of an anonymous type:</span></span>

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

<span data-ttu-id="8e96a-230">자세한 내용은 [무명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="8e96a-231">상속</span><span class="sxs-lookup"><span data-stu-id="8e96a-231">Inheritance</span></span>
<span data-ttu-id="8e96a-232">상속을 사용하면 다른 클래스에 정의된 동작을 다시 사용, 확장 및 수정하는 새 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="8e96a-233">멤버가 상속되는 클래스를 *기본 클래스*라고 하고 해당 멤버를 상속하는 클래스를 *파생 클래스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="8e96a-234">하지만 Visual Basic의 모든 클래스에서 암시적으로 상속는 <xref:System.Object> 클래스.NET 클래스 계층 구조를 지원 하 고 모든 클래스에 하위 수준 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
>  <span data-ttu-id="8e96a-235">Visual Basic 다중 상속을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="8e96a-236">즉, 파생된 클래스에 대해 하나의 기본 클래스만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-236">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="8e96a-237">기본 클래스에서 상속하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-237">To inherit from a base class:</span></span>

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

<span data-ttu-id="8e96a-238">기본적으로 모든 클래스는 상속될 수 있지만</span><span class="sxs-lookup"><span data-stu-id="8e96a-238">By default all classes can be inherited.</span></span> <span data-ttu-id="8e96a-239">클래스가 기본 클래스로 사용되지 않아야 하는지 여부를 지정하거나 기본 클래스로만 사용될 수 있는 클래스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="8e96a-240">클래스가 기본 클래스로 사용될 수 없도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-240">To specify that a class cannot be used as a base class:</span></span>

```vb
NotInheritable Class SampleClass
End Class
```

<span data-ttu-id="8e96a-241">클래스가 기본 클래스로만 사용되고 인스턴스화되지 않도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```vb
MustInherit Class BaseClass
End Class
```

<span data-ttu-id="8e96a-242">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-242">For more information, see:</span></span>

- [<span data-ttu-id="8e96a-243">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)

- [<span data-ttu-id="8e96a-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="8e96a-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)

- [<span data-ttu-id="8e96a-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="8e96a-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a><span data-ttu-id="8e96a-246">멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="8e96a-246">Overriding members</span></span>
<span data-ttu-id="8e96a-247">기본적으로 파생 클래스는 해당 기본 클래스에서 모든 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="8e96a-248">상속된 멤버의 동작을 변경하려면 해당 멤버를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="8e96a-249">즉, 파생 클래스에 해당 메서드, 속성 또는 이벤트의 새로운 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="8e96a-250">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-250">The following modifiers are used to control how properties and methods are overridden:</span></span>

|<span data-ttu-id="8e96a-251">Visual Basic 한정자</span><span class="sxs-lookup"><span data-stu-id="8e96a-251">Visual Basic Modifier</span></span>|<span data-ttu-id="8e96a-252">정의</span><span class="sxs-lookup"><span data-stu-id="8e96a-252">Definition</span></span>|
|---------------------------|----------------|
|[<span data-ttu-id="8e96a-253">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="8e96a-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="8e96a-254">파생 클래스에서 클래스 멤버를 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-254">Allows a class member to be overridden in a derived class.</span></span>|
|[<span data-ttu-id="8e96a-255">재정의</span><span class="sxs-lookup"><span data-stu-id="8e96a-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="8e96a-256">기본 클래스에 정의된 가상(재정의 가능) 멤버를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|
|[<span data-ttu-id="8e96a-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="8e96a-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="8e96a-258">멤버가 상속 클래스에서 재정의되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-258">Prevents a member from being overridden in an inheriting class.</span></span>|
|[<span data-ttu-id="8e96a-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="8e96a-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="8e96a-260">파생 클래스에서 클래스 멤버가 재정의되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-260">Requires that a class member to be overridden in the derived class.</span></span>|
|[<span data-ttu-id="8e96a-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="8e96a-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="8e96a-262">기본 클래스에서 상속된 멤버를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-262">Hides a member inherited from a base class</span></span>|

## <a name="interfaces"></a><span data-ttu-id="8e96a-263">인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e96a-263">Interfaces</span></span>
<span data-ttu-id="8e96a-264">인터페이스는 클래스와 마찬가지로 속성, 메서드 및 이벤트를 정의하지만</span><span class="sxs-lookup"><span data-stu-id="8e96a-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="8e96a-265">클래스와는 달리 구현을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="8e96a-266">인터페이스는 클래스에 의해 구현되며 클래스와는 별개의 엔터티로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="8e96a-267">인터페이스는 계약을 나타내므로 인터페이스를 구현하는 클래스에서는 해당 인터페이스의 모든 부분을 정의된 그대로 정확하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="8e96a-268">인터페이스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-268">To define an interface:</span></span>

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

<span data-ttu-id="8e96a-269">클래스에서 인터페이스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-269">To implement an interface in a class:</span></span>

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

<span data-ttu-id="8e96a-270">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-270">For more information, see:</span></span>

- [<span data-ttu-id="8e96a-271">인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e96a-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  

- [<span data-ttu-id="8e96a-272">Interface 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  

- [<span data-ttu-id="8e96a-273">Implements 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  

## <a name="generics"></a><span data-ttu-id="8e96a-274">제네릭</span><span class="sxs-lookup"><span data-stu-id="8e96a-274">Generics</span></span>
<span data-ttu-id="8e96a-275">클래스, 구조체, 인터페이스 및.net에서 메서드를 포함할 수 *형식 매개 변수* 저장 하거나 사용할 수 있는 개체의 형식을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-275">Classes, structures, interfaces and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="8e96a-276">제네릭의 가장 일반적인 예는 컬렉션에 저장할 개체의 형식을 지정할 수 있는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>  

<span data-ttu-id="8e96a-277">제네릭 클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-277">To define a generic class:</span></span>

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

<span data-ttu-id="8e96a-278">제네릭 클래스의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-278">To create an instance of a generic class:</span></span>

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

<span data-ttu-id="8e96a-279">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-279">For more information, see:</span></span>

- [<span data-ttu-id="8e96a-280">제네릭</span><span class="sxs-lookup"><span data-stu-id="8e96a-280">Generics</span></span>](~/docs/standard/generics/index.md)

- [<span data-ttu-id="8e96a-281">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="8e96a-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a><span data-ttu-id="8e96a-282">대리자</span><span class="sxs-lookup"><span data-stu-id="8e96a-282">Delegates</span></span>
 <span data-ttu-id="8e96a-283">*대리자*는 메서드 시그니처를 정의하는 형식으로, 호환되는 시그니처가 있는 모든 메서드에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="8e96a-284">대리자를 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="8e96a-285">대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-285">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
>  <span data-ttu-id="8e96a-286">이벤트 처리기는 대리자를 통해 호출되는 메서드라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e96a-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="8e96a-287">이벤트를 처리할 때 대리자를 사용하는 방법에 대한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-287">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="8e96a-288">대리자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-288">To create a delegate:</span></span>

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

<span data-ttu-id="8e96a-289">대리자가 지정한 시그니처와 일치하는 메서드에 대한 참조를 만들려면</span><span class="sxs-lookup"><span data-stu-id="8e96a-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

<span data-ttu-id="8e96a-290">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e96a-290">For more information, see:</span></span>

- [<span data-ttu-id="8e96a-291">대리자</span><span class="sxs-lookup"><span data-stu-id="8e96a-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)

- [<span data-ttu-id="8e96a-292">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="8e96a-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="8e96a-293">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="8e96a-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a><span data-ttu-id="8e96a-294">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e96a-294">See also</span></span>
 [<span data-ttu-id="8e96a-295">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8e96a-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
