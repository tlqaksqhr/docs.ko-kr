---
title: "개체 지향 프로그래밍(C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a7f30293bb2d50981353badfb7e373b60dcfeec
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="9c309-102">개체 지향 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="9c309-102">Object-Oriented Programming (C#)</span></span>
<span data-ttu-id="9c309-103">C#은 캡슐화, 상속, 다형성 등 개체 지향 프로그래밍에 대한 모든 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-103">C# provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>  
  
 <span data-ttu-id="9c309-104">*캡슐화*는 서로 관련된 속성, 메서드 및 기타 멤버의 그룹을 하나의 단위나 개체로 취급하는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>  
  
 <span data-ttu-id="9c309-105">*상속*은 기존 클래스를 기반으로 새로운 클래스를 만들 수 있는 능력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>  
  
 <span data-ttu-id="9c309-106">*다형성*은 동일한 속성 또는 메서드를 각각 다른 방식으로 구현하는 여러 클래스를 서로 교체하여 사용할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>  
  
 <span data-ttu-id="9c309-107">이 단원에서는 다음과 같은 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-107">This section describes the following concepts:</span></span>  
  
-   [<span data-ttu-id="9c309-108">클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="9c309-108">Classes and Objects</span></span>](#Classes)  
  
    -   [<span data-ttu-id="9c309-109">클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="9c309-109">Class Members</span></span>](#Members)  
  
         [<span data-ttu-id="9c309-110">속성 및 필드</span><span class="sxs-lookup"><span data-stu-id="9c309-110">Properties and Fields</span></span>](#Properties)  
  
         [<span data-ttu-id="9c309-111">메서드</span><span class="sxs-lookup"><span data-stu-id="9c309-111">Methods</span></span>](#Methods)  
  
         [<span data-ttu-id="9c309-112">생성자</span><span class="sxs-lookup"><span data-stu-id="9c309-112">Constructors</span></span>](#Constructors)  
  
         [<span data-ttu-id="9c309-113">종료자</span><span class="sxs-lookup"><span data-stu-id="9c309-113">Finalizers</span></span>](#Finalizers)  
  
         [<span data-ttu-id="9c309-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="9c309-114">Events</span></span>](#Events)  
  
         [<span data-ttu-id="9c309-115">중첩 클래스</span><span class="sxs-lookup"><span data-stu-id="9c309-115">Nested Classes</span></span>](#NestedClasses)  
  
    -   [<span data-ttu-id="9c309-116">액세스 한정자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="9c309-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)  
  
    -   [<span data-ttu-id="9c309-117">클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="9c309-117">Instantiating Classes</span></span>](#InstantiatingClasses)  
  
    -   [<span data-ttu-id="9c309-118">정적 클래스 및 멤버</span><span class="sxs-lookup"><span data-stu-id="9c309-118">Static Classes and Members</span></span>](#Static)  
  
    -   [<span data-ttu-id="9c309-119">익명 형식</span><span class="sxs-lookup"><span data-stu-id="9c309-119">Anonymous Types</span></span>](#AnonymousTypes)  
  
-   [<span data-ttu-id="9c309-120">상속</span><span class="sxs-lookup"><span data-stu-id="9c309-120">Inheritance</span></span>](#Inheritance)  
  
    -   [<span data-ttu-id="9c309-121">멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="9c309-121">Overriding Members</span></span>](#Overriding)  
  
-   [<span data-ttu-id="9c309-122">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c309-122">Interfaces</span></span>](#Interfaces)  
  
-   [<span data-ttu-id="9c309-123">제네릭</span><span class="sxs-lookup"><span data-stu-id="9c309-123">Generics</span></span>](#Generics)  
  
-   [<span data-ttu-id="9c309-124">대리자</span><span class="sxs-lookup"><span data-stu-id="9c309-124">Delegates</span></span>](#Delegates)  
  
##  <a name="Classes"></a> <span data-ttu-id="9c309-125">클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="9c309-125">Classes and Objects</span></span>  
 <span data-ttu-id="9c309-126">*클래스*와 *개체*를 혼용하는 경우가 있지만 클래스는 개체의 *형식*을 나타내고 개체는 사용 가능한 클래스의 *인스턴스*를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="9c309-127">따라서 개체를 만드는 작업을 *인스턴스화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="9c309-128">청사진에 비유한다면 클래스는 청사진이고 개체는 해당 청사진을 사용하여 만든 빌딩입니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>  
  
 <span data-ttu-id="9c309-129">클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-129">To define a class:</span></span>  
  
```csharp  
class SampleClass  
{  
}  
```  
  
 <span data-ttu-id="9c309-130">C#에서는 큰 개체 배열을 만들어야 하는데 메모리는 많이 사용하지 않으려는 경우에 유용한 라이브 버전의 클래스를 제공합니다. 이를 *구조체*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-130">C# also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>  
  
 <span data-ttu-id="9c309-131">구조체를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-131">To define a structure:</span></span>  
  
```csharp  
struct SampleStruct  
{  
}  
```  
  
 <span data-ttu-id="9c309-132">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-132">For more information, see:</span></span>  
  
-   [<span data-ttu-id="9c309-133">class</span><span class="sxs-lookup"><span data-stu-id="9c309-133">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="9c309-134">truct</span><span class="sxs-lookup"><span data-stu-id="9c309-134">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
###  <a name="Members"></a> <span data-ttu-id="9c309-135">클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="9c309-135">Class Members</span></span>  
 <span data-ttu-id="9c309-136">각 클래스에는 클래스 데이터를 설명하는 속성, 클래스 동작을 정의하는 메서드 및 서로 다른 클래스와 개체 간의 통신을 제공하는 이벤트가 포함된 다양한 *클래스 멤버*가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>  
  
####  <a name="Properties"></a> <span data-ttu-id="9c309-137">속성 및 필드</span><span class="sxs-lookup"><span data-stu-id="9c309-137">Properties and Fields</span></span>  
 <span data-ttu-id="9c309-138">필드 및 속성은 개체가 포함하는 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="9c309-139">필드는 직접 읽거나 설정할 수 있기 때문에 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-139">Fields are like variables because they can be read or set directly.</span></span>  
  
 <span data-ttu-id="9c309-140">필드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-140">To define a field:</span></span>  
  
```csharp  
Class SampleClass  
{  
    public string sampleField;  
}  
```  
  
 <span data-ttu-id="9c309-141">속성에는 값을 설정하고 가져오는 방법을 보다 세밀하게 제어할 수 있는 get 및 set 프로시저가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>  
  
 <span data-ttu-id="9c309-142">C#에서는 속성 값을 저장하기 위한 전용 필드를 만들거나 이 필드를 내부적으로 자동으로 만들고 속성 프로시저에 대한 기본 논리를 제공하는 자동 구현 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-142">C# allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>  
  
 <span data-ttu-id="9c309-143">자동 구현 속성을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-143">To define an auto-implemented property:</span></span>  
  
```csharp  
class SampleClass  
{  
    public int SampleProperty { get; set; }  
}  
```  
  
 <span data-ttu-id="9c309-144">속성 값을 읽고 쓰기 위해 몇 가지 추가 작업을 수행해야 하는 경우 다음과 같이 속성 값을 저장하기 위한 필드를 정의하고, 속성 값을 저장 및 검색하기 위한 기본 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>  
  
```csharp  
class SampleClass  
{  
    private int _sample;  
    public int Sample  
    {  
        // Return the value stored in a field.  
        get { return _sample; }  
        // Store the value in the field.  
        set { _sample = value; }  
    }  
}  
```  
  
 <span data-ttu-id="9c309-145">대부분의 속성에는 속성 값을 설정하고 가져오는 메서드나 프로시저가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="9c309-146">그러나 읽기 전용 또는 쓰기 전용 속성을 만들어 속성을 수정하거나 읽지 못하도록 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="9c309-147">C#에서는 `get` 또는 `set` 속성 메서드를 생략하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-147">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="9c309-148">하지만 자동 구현 속성은 읽기 전용 또는 쓰기 전용일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>  
  
 <span data-ttu-id="9c309-149">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-149">For more information, see:</span></span>  
  
-   [<span data-ttu-id="9c309-150">get</span><span class="sxs-lookup"><span data-stu-id="9c309-150">get</span></span>](../../../csharp/language-reference/keywords/get.md)  
  
-   [<span data-ttu-id="9c309-151">set</span><span class="sxs-lookup"><span data-stu-id="9c309-151">set</span></span>](../../../csharp/language-reference/keywords/set.md)  
  
####  <a name="Methods"></a> <span data-ttu-id="9c309-152">메서드</span><span class="sxs-lookup"><span data-stu-id="9c309-152">Methods</span></span>  
 <span data-ttu-id="9c309-153">*메서드*는 개체에서 수행할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-153">A *method* is an action that an object can perform.</span></span>  
  
 <span data-ttu-id="9c309-154">클래스의 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-154">To define a method of a class:</span></span>  
  
```csharp  
class SampleClass  
{  
    public int sampleMethod(string sampleParam)  
    {  
        // Insert code here  
    }  
}  
```  
  
 <span data-ttu-id="9c309-155">클래스에는 매개 변수 개수나 매개 변수 형식이 다른 동일한 메서드의 구현 또는 *오버로드*가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-155">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>  
  
 <span data-ttu-id="9c309-156">메서드를 오버로드하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-156">To overload a method:</span></span>  
  
```csharp  
public int sampleMethod(string sampleParam) {};  
public int sampleMethod(int sampleParam) {}  
```  
  
 <span data-ttu-id="9c309-157">대부분의 경우 클래스 정의 내에서 메서드를 선언하지만</span><span class="sxs-lookup"><span data-stu-id="9c309-157">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="9c309-158">C#에서는 클래스의 실제 정의 밖에 있는 기존 클래스에 메서드를 추가할 수 있는 *확장 메서드*도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-158">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>  
  
 <span data-ttu-id="9c309-159">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-159">For more information, see:</span></span>  
  
-   [<span data-ttu-id="9c309-160">메서드</span><span class="sxs-lookup"><span data-stu-id="9c309-160">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="9c309-161">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="9c309-161">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
  
####  <a name="Constructors"></a> <span data-ttu-id="9c309-162">생성자</span><span class="sxs-lookup"><span data-stu-id="9c309-162">Constructors</span></span>  
 <span data-ttu-id="9c309-163">생성자는 지정된 형식의 개체를 만들 때 자동으로 실행되는 클래스 메서드로,</span><span class="sxs-lookup"><span data-stu-id="9c309-163">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="9c309-164">일반적으로 새 개체의 데이터 멤버를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-164">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="9c309-165">생성자는 클래스를 만들 때 한 번만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-165">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="9c309-166">또한 생성자의 코드는 항상 클래스의 다른 코드보다 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-166">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="9c309-167">그러나 다른 메서드를 만들 때와 동일한 방법으로 여러 생성자 오버로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-167">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>  
  
 <span data-ttu-id="9c309-168">클래스의 생성자를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-168">To define a constructor for a class:</span></span>  
  
```csharp  
public class SampleClass  
{  
    public SampleClass()  
    {  
        // Add code here  
    }  
}  
```  
  
 <span data-ttu-id="9c309-169">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-169">For more information, see:</span></span>  
  
 <span data-ttu-id="9c309-170">[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="9c309-170">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md).</span></span>  
  
####  <a name="Finalizers"></a> <span data-ttu-id="9c309-171">종료자</span><span class="sxs-lookup"><span data-stu-id="9c309-171">Finalizers</span></span>  
 <span data-ttu-id="9c309-172">종료자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-172">Finalizers are used to destruct instances of classes.</span></span> <span data-ttu-id="9c309-173">.NET Framework에서는 응용 프로그램의 관리되는 개체에 대해 가비지 수집기가 자동으로 메모리를 할당하고 해제하지만</span><span class="sxs-lookup"><span data-stu-id="9c309-173">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="9c309-174">응용 프로그램이 만드는 관리되지 않는 리소스를 정리하려면 여전히 종료자가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-174">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="9c309-175">각 클래스에는 종료자가 하나씩만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-175">There can be only one finalizers for a class.</span></span>  
  
 <span data-ttu-id="9c309-176">.NET Framework의 종료자 및 가비지 수집에 대한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-176">For more information about finalizers and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
####  <a name="Events"></a> <span data-ttu-id="9c309-177">이벤트</span><span class="sxs-lookup"><span data-stu-id="9c309-177">Events</span></span>  
 <span data-ttu-id="9c309-178">클래스나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-178">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="9c309-179">이벤트를 보내거나 발생시키는 클래스를 *게시자*라고 하며 이벤트를 받거나 처리하는 클래스를 *구독자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-179">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="9c309-180">이벤트를 발생시키고 처리하는 방법에 대한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-180">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>  
  
-   <span data-ttu-id="9c309-181">클래스에서 이벤트를 선언하려면 [event](../../../csharp/language-reference/keywords/event.md) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-181">To declare an event in a class, use the [event](../../../csharp/language-reference/keywords/event.md) keyword.</span></span>  
  
-   <span data-ttu-id="9c309-182">이벤트를 발생시키려면 이벤트 대리자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-182">To raise an event, invoke the event delegate.</span></span>  
  
-   <span data-ttu-id="9c309-183">이벤트를 구독하려면 `+=` 연산자를 사용하고 이벤트를 구독 취소하려면 `-=` 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-183">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>  
  
####  <a name="NestedClasses"></a> <span data-ttu-id="9c309-184">중첩 클래스</span><span class="sxs-lookup"><span data-stu-id="9c309-184">Nested Classes</span></span>  
 <span data-ttu-id="9c309-185">다른 클래스 내에 정의된 클래스를 *중첩 클래스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-185">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="9c309-186">기본적으로 중첩 클래스는 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-186">By default, the nested class is private.</span></span>  
  
```csharp  
class Container  
{  
    class Nested  
    {  
        // Add code here.  
    }  
}  
```  
  
 <span data-ttu-id="9c309-187">중첩 클래스의 인스턴스를 만들려면 다음과 같이 컨테이너 클래스의 이름, 점, 중첩 클래스의 이름을 차례로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-187">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>  
  
```csharp  
Container.Nested nestedInstance = new Container.Nested()  
```  
  
###  <a name="AccessModifiers"></a> <span data-ttu-id="9c309-188">액세스 한정자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="9c309-188">Access Modifiers and Access Levels</span></span>  
 <span data-ttu-id="9c309-189">모든 클래스 및 클래스 멤버는 *액세스 한정자*를 사용하여 다른 클래스에 제공할 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-189">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>  
  
 <span data-ttu-id="9c309-190">다음과 같은 액세스 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-190">The following access modifiers are available:</span></span>  
  
|<span data-ttu-id="9c309-191">C# 한정자</span><span class="sxs-lookup"><span data-stu-id="9c309-191">C# Modifier</span></span>|<span data-ttu-id="9c309-192">정의</span><span class="sxs-lookup"><span data-stu-id="9c309-192">Definition</span></span>|  
|------------------|----------------|  
|[<span data-ttu-id="9c309-193">public</span><span class="sxs-lookup"><span data-stu-id="9c309-193">public</span></span>](../../../csharp/language-reference/keywords/public.md)|<span data-ttu-id="9c309-194">동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-194">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|  
|[<span data-ttu-id="9c309-195">private</span><span class="sxs-lookup"><span data-stu-id="9c309-195">private</span></span>](../../../csharp/language-reference/keywords/private.md)|<span data-ttu-id="9c309-196">동일한 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-196">The type or member can only be accessed by code in the same class.</span></span>|  
|[<span data-ttu-id="9c309-197">protected</span><span class="sxs-lookup"><span data-stu-id="9c309-197">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)|<span data-ttu-id="9c309-198">동일한 클래스의 코드나 파생 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-198">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|  
|[<span data-ttu-id="9c309-199">internal</span><span class="sxs-lookup"><span data-stu-id="9c309-199">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)|<span data-ttu-id="9c309-200">동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-200">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|  
|[<span data-ttu-id="9c309-201">내부 보호</span><span class="sxs-lookup"><span data-stu-id="9c309-201">protected internal</span></span>](../../../csharp/language-reference/keywords/protected-internal.md)|<span data-ttu-id="9c309-202">동일한 어셈블리의 코드 또는 다른 어셈블리의 파생 클래스에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-202">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|  
|[<span data-ttu-id="9c309-203">보호 된 개인</span><span class="sxs-lookup"><span data-stu-id="9c309-203">private protected</span></span>](../../../csharp/language-reference/keywords/private-protected.md)|<span data-ttu-id="9c309-204">형식 또는 멤버는 동일한 클래스 또는 기본 클래스 어셈블리 내에서 파생된 클래스에서 코드를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-204">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span>|  
  
 <span data-ttu-id="9c309-205">자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-205">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
###  <a name="InstantiatingClasses"></a> <span data-ttu-id="9c309-206">클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="9c309-206">Instantiating Classes</span></span>  
 <span data-ttu-id="9c309-207">개체를 만들려면 클래스를 인스턴스화하거나 클래스 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-207">To create an object, you need to instantiate a class, or create a class instance.</span></span>  
  
```csharp  
SampleClass sampleObject = new SampleClass();  
```  
  
 <span data-ttu-id="9c309-208">클래스를 인스턴스화한 후에는 인스턴스의 속성과 필드에 값을 할당하고 클래스 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-208">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>  
  
```csharp  
// Set a property value.  
sampleObject.sampleProperty = "Sample String";  
// Call a method.  
sampleObject.sampleMethod();  
```  
  
 <span data-ttu-id="9c309-209">클래스를 인스턴스화하는 동안 속성에 값을 할당하려면 다음과 같이 개체 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-209">To assign values to properties during the class instantiation process, use object initializers:</span></span>  
  
```csharp  
// Set a property value.  
SampleClass sampleObject = new SampleClass   
    { FirstProperty = "A", SecondProperty = "B" };  
```  
  
 <span data-ttu-id="9c309-210">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-210">For more information, see:</span></span>  
  
-   [<span data-ttu-id="9c309-211">new 연산자</span><span class="sxs-lookup"><span data-stu-id="9c309-211">new Operator</span></span>](../../../csharp/language-reference/keywords/new-operator.md)  
  
-   [<span data-ttu-id="9c309-212">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="9c309-212">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
  
###  <a name="Static"></a> <span data-ttu-id="9c309-213">정적 클래스 및 멤버</span><span class="sxs-lookup"><span data-stu-id="9c309-213">Static Classes and Members</span></span>  
 <span data-ttu-id="9c309-214">클래스의 정적 멤버는 클래스의 모든 인스턴스에서 공유하는 속성, 프로시저 또는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-214">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>  
  
 <span data-ttu-id="9c309-215">정적 멤버를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-215">To define a static member:</span></span>  
  
```csharp  
static class SampleClass  
{  
    public static string SampleString = "Sample String";  
}  
```  
  
 <span data-ttu-id="9c309-216">정적 멤버에 액세스하려면 다음과 같이 이 클래스의 개체를 만들지 않고 클래스 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-216">To access the static member, use the name of the class without creating an object of this class:</span></span>  
  
```csharp  
Console.WriteLine(SampleClass.SampleString);  
```  
  
 <span data-ttu-id="9c309-217">C#의 정적 클래스는 정적 멤버만 포함하며 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-217">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="9c309-218">또한 정적 멤버는 비정적 속성, 필드 또는 메서드에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-218">Static members also cannot access non-static  properties, fields or methods</span></span>  
  
 <span data-ttu-id="9c309-219">자세한 내용은 [static](../../../csharp/language-reference/keywords/static.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-219">For more information, see: [static](../../../csharp/language-reference/keywords/static.md).</span></span>  
  
###  <a name="AnonymousTypes"></a> <span data-ttu-id="9c309-220">무명 형식</span><span class="sxs-lookup"><span data-stu-id="9c309-220">Anonymous Types</span></span>  
 <span data-ttu-id="9c309-221">익명 형식을 사용하면 데이터 형식에 대한 클래스 정의를 작성하지 않고 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-221">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="9c309-222">대신 컴파일러가 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-222">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="9c309-223">이 클래스는 사용할 수 있는 이름이 없고 개체를 선언할 때 지정하는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-223">The class has no usable name and contains the properties you specify in declaring the object.</span></span>  
  
 <span data-ttu-id="9c309-224">익명 형식의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9c309-224">To create an instance of an anonymous type:</span></span>  
  
```csharp  
// sampleObject is an instance of a simple anonymous type.  
var sampleObject =   
    new { FirstProperty = "A", SecondProperty = "B" };  
```  
  
 <span data-ttu-id="9c309-225">자세한 내용은 [무명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-225">For more information, see: [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
##  <a name="Inheritance"></a> <span data-ttu-id="9c309-226">상속</span><span class="sxs-lookup"><span data-stu-id="9c309-226">Inheritance</span></span>  
 <span data-ttu-id="9c309-227">상속을 사용하면 다른 클래스에 정의된 동작을 다시 사용, 확장 및 수정하는 새 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-227">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="9c309-228">멤버가 상속되는 클래스를 *기본 클래스*라고 하고 해당 멤버를 상속하는 클래스를 *파생 클래스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-228">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="9c309-229">그러나 C#의 모든 클래스는 .NET 클래스 계층 구조를 지원하고 모든 클래스에 하위 수준 서비스를 제공하는 <xref:System.Object> 클래스에서 암시적으로 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-229">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c309-230">C#은 다중 상속을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-230">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="9c309-231">즉, 파생된 클래스에 대해 하나의 기본 클래스만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-231">That is, you can specify only one base class for a derived class.</span></span>  
  
 <span data-ttu-id="9c309-232">기본 클래스에서 상속하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-232">To inherit from a base class:</span></span>  
  
```csharp  
class DerivedClass:BaseClass{}  
```  
  
 <span data-ttu-id="9c309-233">기본적으로 모든 클래스는 상속될 수 있지만</span><span class="sxs-lookup"><span data-stu-id="9c309-233">By default all classes can be inherited.</span></span> <span data-ttu-id="9c309-234">클래스가 기본 클래스로 사용되지 않아야 하는지 여부를 지정하거나 기본 클래스로만 사용될 수 있는 클래스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-234">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>  
  
 <span data-ttu-id="9c309-235">클래스가 기본 클래스로 사용될 수 없도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-235">To specify that a class cannot be used as a base class:</span></span>  
  
```csharp  
public sealed class A { }  
```  
  
 <span data-ttu-id="9c309-236">클래스가 기본 클래스로만 사용되고 인스턴스화되지 않도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-236">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>  
  
```csharp  
public abstract class B { }  
```  
  
 <span data-ttu-id="9c309-237">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-237">For more information, see:</span></span>  
  
-   [<span data-ttu-id="9c309-238">sealed</span><span class="sxs-lookup"><span data-stu-id="9c309-238">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)  
  
-   [<span data-ttu-id="9c309-239">abstract</span><span class="sxs-lookup"><span data-stu-id="9c309-239">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
  
###  <a name="Overriding"></a> <span data-ttu-id="9c309-240">멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="9c309-240">Overriding Members</span></span>  
 <span data-ttu-id="9c309-241">기본적으로 파생 클래스는 해당 기본 클래스에서 모든 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-241">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="9c309-242">상속된 멤버의 동작을 변경하려면 해당 멤버를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-242">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="9c309-243">즉, 파생 클래스에 해당 메서드, 속성 또는 이벤트의 새로운 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-243">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>  
  
 <span data-ttu-id="9c309-244">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-244">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
|<span data-ttu-id="9c309-245">C# 한정자</span><span class="sxs-lookup"><span data-stu-id="9c309-245">C# Modifier</span></span>|<span data-ttu-id="9c309-246">정의</span><span class="sxs-lookup"><span data-stu-id="9c309-246">Definition</span></span>|  
|------------------|----------------|  
|[<span data-ttu-id="9c309-247">virtual</span><span class="sxs-lookup"><span data-stu-id="9c309-247">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)|<span data-ttu-id="9c309-248">파생 클래스에서 클래스 멤버를 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-248">Allows a class member to be overridden in a derived class.</span></span>|  
|[<span data-ttu-id="9c309-249">override</span><span class="sxs-lookup"><span data-stu-id="9c309-249">override</span></span>](../../../csharp/language-reference/keywords/override.md)|<span data-ttu-id="9c309-250">기본 클래스에 정의된 가상(재정의 가능) 멤버를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-250">Overrides a virtual (overridable) member defined in the base class.</span></span>|  
|[<span data-ttu-id="9c309-251">abstract</span><span class="sxs-lookup"><span data-stu-id="9c309-251">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)|<span data-ttu-id="9c309-252">파생 클래스에서 클래스 멤버가 재정의되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-252">Requires that a class member to be overridden in the derived class.</span></span>|  
|[<span data-ttu-id="9c309-253">new 한정자</span><span class="sxs-lookup"><span data-stu-id="9c309-253">new Modifier</span></span>](../../../csharp/language-reference/keywords/new-modifier.md)|<span data-ttu-id="9c309-254">기본 클래스에서 상속된 멤버를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-254">Hides a member inherited from a base class</span></span>|  
  
##  <a name="Interfaces"></a> <span data-ttu-id="9c309-255">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c309-255">Interfaces</span></span>  
 <span data-ttu-id="9c309-256">인터페이스는 클래스와 마찬가지로 속성, 메서드 및 이벤트를 정의하지만</span><span class="sxs-lookup"><span data-stu-id="9c309-256">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="9c309-257">클래스와는 달리 구현을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-257">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="9c309-258">인터페이스는 클래스에 의해 구현되며 클래스와는 별개의 엔터티로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-258">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="9c309-259">인터페이스는 계약을 나타내므로 인터페이스를 구현하는 클래스에서는 해당 인터페이스의 모든 부분을 정의된 그대로 정확하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-259">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>  
  
 <span data-ttu-id="9c309-260">인터페이스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-260">To define an interface:</span></span>  
  
```csharp  
interface ISampleInterface  
{  
    void doSomething();  
}  
```  
  
 <span data-ttu-id="9c309-261">클래스에서 인터페이스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-261">To implement an interface in a class:</span></span>  
  
```csharp  
class SampleClass : ISampleInterface  
{  
    void ISampleInterface.doSomething()  
    {  
        // Method implementation.  
    }  
}  
```  
  
 <span data-ttu-id="9c309-262">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-262">For more information, see:</span></span>  
  
 [<span data-ttu-id="9c309-263">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c309-263">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
  
 [<span data-ttu-id="9c309-264">interface</span><span class="sxs-lookup"><span data-stu-id="9c309-264">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
##  <a name="Generics"></a> <span data-ttu-id="9c309-265">제네릭</span><span class="sxs-lookup"><span data-stu-id="9c309-265">Generics</span></span>  
 <span data-ttu-id="9c309-266">.NET Framework의 클래스, 구조체, 인터페이스 및 메서드는 저장하거나 사용할 수 있는 개체의 형식을 정의하는 *형식 매개 변수*를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-266">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="9c309-267">제네릭의 가장 일반적인 예는 컬렉션에 저장할 개체의 형식을 지정할 수 있는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-267">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>  
  
 <span data-ttu-id="9c309-268">제네릭 클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9c309-268">To define a generic class:</span></span>  
  
```csharp  
Public class SampleGeneric<T>   
{  
    public T Field;  
}  
```  
  
 <span data-ttu-id="9c309-269">제네릭 클래스의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9c309-269">To create an instance of a generic class:</span></span>  
  
```csharp  
SampleGeneric<string> sampleObject = new SampleGeneric<string>();  
sampleObject.Field = "Sample string";  
```  
  
 <span data-ttu-id="9c309-270">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-270">For more information, see:</span></span>  
  
-   [<span data-ttu-id="9c309-271">제네릭</span><span class="sxs-lookup"><span data-stu-id="9c309-271">Generics</span></span>](~/docs/standard/generics/index.md)  
  
-   [<span data-ttu-id="9c309-272">제네릭</span><span class="sxs-lookup"><span data-stu-id="9c309-272">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
  
##  <a name="Delegates"></a> <span data-ttu-id="9c309-273">대리자</span><span class="sxs-lookup"><span data-stu-id="9c309-273">Delegates</span></span>  
 <span data-ttu-id="9c309-274">*대리자*는 메서드 시그니처를 정의하는 형식으로, 호환되는 시그니처가 있는 모든 메서드에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-274">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="9c309-275">대리자를 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-275">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="9c309-276">대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-276">Delegates are used to pass methods as arguments to other methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c309-277">이벤트 처리기는 대리자를 통해 호출되는 메서드라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c309-277">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="9c309-278">이벤트를 처리할 때 대리자를 사용하는 방법에 대한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-278">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>  
  
 <span data-ttu-id="9c309-279">대리자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9c309-279">To create a delegate:</span></span>  
  
```csharp  
public delegate void SampleDelegate(string str);  
```  
  
 <span data-ttu-id="9c309-280">대리자가 지정한 시그니처와 일치하는 메서드에 대한 참조를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9c309-280">To create a reference to a method that matches the signature specified by the delegate:</span></span>  
  
```csharp  
class SampleClass  
{  
    // Method that matches the SampleDelegate signature.  
    public static void sampleMethod(string message)  
    {  
        // Add code here.  
    }  
    // Method that instantiates the delegate.  
    void SampleDelegate()  
    {  
        SampleDelegate sd = sampleMethod;  
        sd("Sample string");  
    }  
}  
```  
  
 <span data-ttu-id="9c309-281">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c309-281">For more information, see:</span></span>  
  
-   [<span data-ttu-id="9c309-282">대리자</span><span class="sxs-lookup"><span data-stu-id="9c309-282">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
  
-   [<span data-ttu-id="9c309-283">delegate</span><span class="sxs-lookup"><span data-stu-id="9c309-283">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c309-284">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c309-284">See Also</span></span>  
 [<span data-ttu-id="9c309-285">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9c309-285">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
