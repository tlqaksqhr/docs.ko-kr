---
title: "개체 지향 프로그래밍 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d5491b3bd5a25908194d02063f688a319509bb77
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="object-oriented-programming-visual-basic"></a><span data-ttu-id="1d758-102">개체 지향 프로그래밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d758-102">Object-Oriented Programming (Visual Basic)</span></span>
<span data-ttu-id="1d758-103">Visual Basic 캡슐화, 상속, 다형성 등 개체 지향 프로그래밍에 대 한 모든 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-103">Visual Basic provides full support for object-oriented programming including encapsulation, inheritance, and polymorphism.</span></span>  
  
 <span data-ttu-id="1d758-104">*캡슐화* 관련된 속성, 메서드 및 기타 멤버의 그룹을 하나의 단위나 개체로 취급 하는 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-104">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>  
  
 <span data-ttu-id="1d758-105">*상속* 기존 클래스를 기반으로 새 클래스를 만들 수 있는 능력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-105">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>  
  
 <span data-ttu-id="1d758-106">*다형성* 동일한 속성 또는 메서드를 각각 다른 방식에서으로 구현 하는 경우에를 서로 바꾸어 사용할 수 있는 여러 클래스를 포함할 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-106">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>  
  
 <span data-ttu-id="1d758-107">이 단원에서는 다음과 같은 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-107">This section describes the following concepts:</span></span>  
  
-   [<span data-ttu-id="1d758-108">클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="1d758-108">Classes and Objects</span></span>](#Classes)  
  
    -   [<span data-ttu-id="1d758-109">클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="1d758-109">Class Members</span></span>](#Members)  
  
         [<span data-ttu-id="1d758-110">속성 및 필드</span><span class="sxs-lookup"><span data-stu-id="1d758-110">Properties and Fields</span></span>](#Properties)  
  
         [<span data-ttu-id="1d758-111">메서드</span><span class="sxs-lookup"><span data-stu-id="1d758-111">Methods</span></span>](#Methods)  
  
         [<span data-ttu-id="1d758-112">생성자</span><span class="sxs-lookup"><span data-stu-id="1d758-112">Constructors</span></span>](#Constructors)  
  
         [<span data-ttu-id="1d758-113">소멸자</span><span class="sxs-lookup"><span data-stu-id="1d758-113">Destructors</span></span>](#Destructors)  
  
         [<span data-ttu-id="1d758-114">이벤트</span><span class="sxs-lookup"><span data-stu-id="1d758-114">Events</span></span>](#Events)  
  
         [<span data-ttu-id="1d758-115">중첩된 클래스</span><span class="sxs-lookup"><span data-stu-id="1d758-115">Nested Classes</span></span>](#NestedClasses)  
  
    -   [<span data-ttu-id="1d758-116">액세스 한정자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="1d758-116">Access Modifiers and Access Levels</span></span>](#AccessModifiers)  
  
    -   [<span data-ttu-id="1d758-117">클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="1d758-117">Instantiating Classes</span></span>](#InstantiatingClasses)  
  
    -   [<span data-ttu-id="1d758-118">공유 클래스 및 멤버</span><span class="sxs-lookup"><span data-stu-id="1d758-118">Shared Classes and Members</span></span>](#Static)  
  
    -   [<span data-ttu-id="1d758-119">익명 형식</span><span class="sxs-lookup"><span data-stu-id="1d758-119">Anonymous Types</span></span>](#AnonymousTypes)  
  
-   [<span data-ttu-id="1d758-120">상속</span><span class="sxs-lookup"><span data-stu-id="1d758-120">Inheritance</span></span>](#Inheritance)  
  
    -   [<span data-ttu-id="1d758-121">멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="1d758-121">Overriding Members</span></span>](#Overriding)  
  
-   [<span data-ttu-id="1d758-122">인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d758-122">Interfaces</span></span>](#Interfaces)  
  
-   [<span data-ttu-id="1d758-123">제네릭</span><span class="sxs-lookup"><span data-stu-id="1d758-123">Generics</span></span>](#Generics)  
  
-   [<span data-ttu-id="1d758-124">대리자</span><span class="sxs-lookup"><span data-stu-id="1d758-124">Delegates</span></span>](#Delegates)  
  
##  <span data-ttu-id="1d758-125"><a name="Classes"></a>클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="1d758-125"><a name="Classes"></a> Classes and Objects</span></span>  
 <span data-ttu-id="1d758-126">용어 *클래스* 및 *개체* 사용 되는 경우가 실제로 하지만 서로 교체 하 여 클래스를 설명는 *형식* 나타내고 개체는 사용 가능한 개체의 *인스턴스* 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-126">The terms *class* and *object* are sometimes used interchangeably, but in fact, classes describe the *type* of objects, while objects are usable *instances* of classes.</span></span> <span data-ttu-id="1d758-127">따라서, 개체를 만드는 작업 라고 *인스턴스화*합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-127">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="1d758-128">청사진에 비유한다면 클래스는 청사진이고 개체는 해당 청사진을 사용하여 만든 빌딩입니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-128">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>  
  
 <span data-ttu-id="1d758-129">클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-129">To define a class:</span></span>  
  
```vb  
Class SampleClass  
End Class  
```  
  
 <span data-ttu-id="1d758-130">Visual Basic에서 밝은 버전의 클래스도 제공 *구조* 큰 개체 배열을 만들어야 하 고 실행 해야 할 때 유용 하는 메모리를 너무 많이 사용 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-130">Visual Basic also provides a light version of classes called *structures* that are useful when you need to create large array of objects and do not want to consume too much memory for that.</span></span>  
  
 <span data-ttu-id="1d758-131">구조체를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-131">To define a structure:</span></span>  
  
```vb  
Structure SampleStructure  
End Structure  
```  
  
 <span data-ttu-id="1d758-132">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-132">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-133">Class 문</span><span class="sxs-lookup"><span data-stu-id="1d758-133">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="1d758-134">Structure 문</span><span class="sxs-lookup"><span data-stu-id="1d758-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
###  <span data-ttu-id="1d758-135"><a name="Members"></a>클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="1d758-135"><a name="Members"></a> Class Members</span></span>  
 <span data-ttu-id="1d758-136">각 클래스는 서로 다른 점이 *클래스 멤버* 클래스 데이터, 클래스 동작을 정의 하는 메서드 및 서로 다른 클래스와 개체 간의 통신을 제공 하는 이벤트를 설명 하는 속성을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-136">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>  
  
####  <span data-ttu-id="1d758-137"><a name="Properties"></a>속성 및 필드</span><span class="sxs-lookup"><span data-stu-id="1d758-137"><a name="Properties"></a> Properties and Fields</span></span>  
 <span data-ttu-id="1d758-138">필드 및 속성은 개체가 포함하는 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-138">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="1d758-139">필드는 직접 읽거나 설정할 수 있기 때문에 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-139">Fields are like variables because they can be read or set directly.</span></span>  
  
 <span data-ttu-id="1d758-140">필드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-140">To define a field:</span></span>  
  
```vb  
Class SampleClass  
    Public SampleField As String  
End Class  
```  
  
 <span data-ttu-id="1d758-141">속성에는 값을 설정하고 가져오는 방법을 보다 세밀하게 제어할 수 있는 get 및 set 프로시저가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-141">Properties have get and set procedures, which provide more control on how values are set or returned.</span></span>  
  
 <span data-ttu-id="1d758-142">Visual Basic을 사용 하면 속성 값을 저장 하기 위한 전용 필드를 만들거나이 필드는 내부적으로 자동으로 만들고 속성 프로시저에 대 한 기본 논리를 제공 하는 소위 자동 구현 속성을 사용 하 여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-142">Visual Basic allows you either to create a private field for storing the property value or use so-called auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>  
  
 <span data-ttu-id="1d758-143">자동 구현 속성을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-143">To define an auto-implemented property:</span></span>  
  
```vb  
Class SampleClass  
    Public Property SampleProperty as String  
End Class  
```  
  
 <span data-ttu-id="1d758-144">속성 값을 읽고 쓰기 위해 몇 가지 추가 작업을 수행해야 하는 경우 다음과 같이 속성 값을 저장하기 위한 필드를 정의하고, 속성 값을 저장 및 검색하기 위한 기본 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-144">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>  
  
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
  
 <span data-ttu-id="1d758-145">대부분의 속성에는 속성 값을 설정하고 가져오는 메서드나 프로시저가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-145">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="1d758-146">그러나 읽기 전용 또는 쓰기 전용 속성을 만들어 속성을 수정하거나 읽지 못하도록 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-146">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="1d758-147">이렇게 하려면 Visual Basic에서는 `ReadOnly` 및 `WriteOnly` 키워드를 사용하면 되고</span><span class="sxs-lookup"><span data-stu-id="1d758-147">In Visual Basic you can use `ReadOnly` and `WriteOnly` keywords.</span></span> <span data-ttu-id="1d758-148">그러나 자동 구현 속성 읽기 전용 또는 쓰기 전용일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-148">However, auto-implemented properties cannot be read-only or write-only.</span></span>  
  
 <span data-ttu-id="1d758-149">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-149">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-150">Property 문</span><span class="sxs-lookup"><span data-stu-id="1d758-150">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="1d758-151">Get 문</span><span class="sxs-lookup"><span data-stu-id="1d758-151">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
  
-   [<span data-ttu-id="1d758-152">Set 문</span><span class="sxs-lookup"><span data-stu-id="1d758-152">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
  
-   [<span data-ttu-id="1d758-153">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="1d758-153">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
-   [<span data-ttu-id="1d758-154">WriteOnly</span><span class="sxs-lookup"><span data-stu-id="1d758-154">WriteOnly</span></span>](../../../visual-basic/language-reference/modifiers/writeonly.md)  
  
####  <span data-ttu-id="1d758-155"><a name="Methods"></a>메서드</span><span class="sxs-lookup"><span data-stu-id="1d758-155"><a name="Methods"></a> Methods</span></span>  
 <span data-ttu-id="1d758-156">A *메서드* 개체에서 수행할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-156">A *method* is an action that an object can perform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d758-157">Visual Basic에서는 두 가지 방법으로 메서드를 만들 수 있습니다. 메서드가 값을 반환하지 않으면 `Sub` 문을 사용하고 메서드가 값을 반환하면 `Function` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-157">In Visual Basic, there are two ways to create a method: the `Sub` statement is used if the method does not return a value; the `Function` statement is used if a method returns a value.</span></span>  
  
 <span data-ttu-id="1d758-158">클래스의 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-158">To define a method of a class:</span></span>  
  
```vb  
Class SampleClass  
    Public Function SampleFunc(ByVal SampleParam As String)  
        ' Add code here  
    End Function  
End Class  
```  
  
 <span data-ttu-id="1d758-159">클래스가 여러 구현 소유할 수 또는 *오버 로드*, 매개 변수 또는 매개 변수 형식이 다른 동일한 메서드의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-159">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>  
  
 <span data-ttu-id="1d758-160">메서드를 오버로드하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-160">To overload a method:</span></span>  
  
```vb  
Overloads Sub Display(ByVal theChar As Char)  
    ' Add code that displays Char data.  
End Sub  
Overloads Sub Display(ByVal theInteger As Integer)  
    ' Add code that displays Integer data.  
End Sub  
```  
  
 <span data-ttu-id="1d758-161">대부분의 경우 클래스 정의 내에서 메서드를 선언하지만</span><span class="sxs-lookup"><span data-stu-id="1d758-161">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="1d758-162">그러나 Visual Basic에서는 *확장 메서드* 클래스의 실제 정의 밖에 있는 기존 클래스에 메서드를 추가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-162">However, Visual Basic also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>  
  
 <span data-ttu-id="1d758-163">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-163">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-164">Function 문</span><span class="sxs-lookup"><span data-stu-id="1d758-164">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="1d758-165">Sub 문</span><span class="sxs-lookup"><span data-stu-id="1d758-165">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="1d758-166">오버로드</span><span class="sxs-lookup"><span data-stu-id="1d758-166">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
-   [<span data-ttu-id="1d758-167">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="1d758-167">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
  
####  <span data-ttu-id="1d758-168"><a name="Constructors"></a>생성자</span><span class="sxs-lookup"><span data-stu-id="1d758-168"><a name="Constructors"></a> Constructors</span></span>  
 <span data-ttu-id="1d758-169">생성자는 지정된 형식의 개체를 만들 때 자동으로 실행되는 클래스 메서드로,</span><span class="sxs-lookup"><span data-stu-id="1d758-169">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="1d758-170">일반적으로 새 개체의 데이터 멤버를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-170">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="1d758-171">생성자는 클래스를 만들 때 한 번만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-171">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="1d758-172">또한 생성자의 코드는 항상 클래스의 다른 코드보다 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-172">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="1d758-173">그러나 다른 메서드를 만들 때와 동일한 방법으로 여러 생성자 오버로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-173">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>  
  
 <span data-ttu-id="1d758-174">클래스의 생성자를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-174">To define a constructor for a class:</span></span>  
  
```vb  
Class SampleClass  
    Sub New(ByVal s As String)  
        // Add code here.  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1d758-175">자세한 내용은 참조: [개체 수명: 개체가 만들어지고 소멸 되는 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-175">For more information, see: [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
####  <span data-ttu-id="1d758-176"><a name="Destructors"></a>소멸자</span><span class="sxs-lookup"><span data-stu-id="1d758-176"><a name="Destructors"></a> Destructors</span></span>  
 <span data-ttu-id="1d758-177">소멸자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-177">Destructors are used to destruct instances of classes.</span></span> <span data-ttu-id="1d758-178">.NET Framework에서는 응용 프로그램의 관리되는 개체에 대해 가비지 수집기가 자동으로 메모리를 할당하고 해제하지만</span><span class="sxs-lookup"><span data-stu-id="1d758-178">In the .NET Framework, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="1d758-179">응용 프로그램에서 만들어지는 관리되지 않는 개체를 정리하려면 여전히 소멸자가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-179">However, you may still need destructors to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="1d758-180">각 클래스에는 소멸자가 하나씩만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-180">There can be only one destructor for a class.</span></span>  
  
 <span data-ttu-id="1d758-181">소멸자 및.NET Framework의 가비지 수집에 대 한 자세한 내용은 참조 [가비지 수집](../../../standard/garbagecollection/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-181">For more information about destructors and garbage collection in the .NET Framework, see [Garbage Collection](../../../standard/garbagecollection/index.md).</span></span>  
  
####  <span data-ttu-id="1d758-182"><a name="Events"></a>이벤트</span><span class="sxs-lookup"><span data-stu-id="1d758-182"><a name="Events"></a> Events</span></span>  
 <span data-ttu-id="1d758-183">클래스나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-183">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="1d758-184">이벤트를 보냅니다 (또는 발생) 하는 클래스 라고는 *게시자* 되는 이벤트를 수신 (또는 처리) 클래스 라고 하 고 *구독자*합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-184">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="1d758-185">이벤트에 대 한 자세한 내용은 어떻게 발생 하 고 참조를 처리 된 [이벤트](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-185">For more information about events, how they are raised and handled, see [Events](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span></span>  
  
-   <span data-ttu-id="1d758-186">이벤트를 선언 하려면 사용 된 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-186">To declare events, use the [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
-   <span data-ttu-id="1d758-187">이벤트를 발생 시키기 위해 사용 하 여는 [RaiseEvent 문](../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-187">To raise events, use the [RaiseEvent Statement](../../../visual-basic/language-reference/statements/raiseevent-statement.md).</span></span>  
  
-   <span data-ttu-id="1d758-188">선언적 방식으로 이벤트 처리기를 지정 하려면는 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) 문 및 [처리](../../../visual-basic/language-reference/statements/handles-clause.md) 절.</span><span class="sxs-lookup"><span data-stu-id="1d758-188">To specify event handlers using a declarative way, use the [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) statement and the [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) clause.</span></span>  
  
-   <span data-ttu-id="1d758-189">수 동적으로 추가, 제거 및 변경 이벤트와 연결 된 이벤트 처리기를 사용 하 여는 [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md) 및 [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md) 와 함께 [AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-189">To be able to dynamically add, remove, and change the event handler associated with an event, use the [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) and [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) together with the [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).</span></span>  
  
####  <span data-ttu-id="1d758-190"><a name="NestedClasses"></a>중첩된 클래스</span><span class="sxs-lookup"><span data-stu-id="1d758-190"><a name="NestedClasses"></a> Nested Classes</span></span>  
 <span data-ttu-id="1d758-191">다른 클래스 내에 정의 된 클래스 라고 *중첩*합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-191">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="1d758-192">기본적으로 중첩 클래스는 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-192">By default, the nested class is private.</span></span>  
  
```vb  
Class Container  
    Class Nested  
    ' Add code here.  
    End Class  
End Class  
```  
  
 <span data-ttu-id="1d758-193">중첩 클래스의 인스턴스를 만들려면 다음과 같이 컨테이너 클래스의 이름, 점, 중첩 클래스의 이름을 차례로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-193">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>  
  
```vb  
Dim nestedInstance As Container.Nested = New Container.Nested()  
```  
  
###  <span data-ttu-id="1d758-194"><a name="AccessModifiers"></a>액세스 한정자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="1d758-194"><a name="AccessModifiers"></a> Access Modifiers and Access Levels</span></span>  
 <span data-ttu-id="1d758-195">모든 클래스 및 클래스 멤버를 사용 하 여 다른 클래스에 제공할 액세스 수준을 지정할 수 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-195">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>  
  
 <span data-ttu-id="1d758-196">다음과 같은 액세스 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-196">The following access modifiers are available:</span></span>  
  
|<span data-ttu-id="1d758-197">Visual Basic 한정자</span><span class="sxs-lookup"><span data-stu-id="1d758-197">Visual Basic Modifier</span></span>|<span data-ttu-id="1d758-198">정의</span><span class="sxs-lookup"><span data-stu-id="1d758-198">Definition</span></span>|  
|---------------------------|----------------|  
|[<span data-ttu-id="1d758-199">공용</span><span class="sxs-lookup"><span data-stu-id="1d758-199">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)|<span data-ttu-id="1d758-200">동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-200">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span>|  
|[<span data-ttu-id="1d758-201">전용</span><span class="sxs-lookup"><span data-stu-id="1d758-201">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)|<span data-ttu-id="1d758-202">동일한 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-202">The type or member can only be accessed by code in the same class.</span></span>|  
|[<span data-ttu-id="1d758-203">보호됨</span><span class="sxs-lookup"><span data-stu-id="1d758-203">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)|<span data-ttu-id="1d758-204">동일한 클래스의 코드나 파생 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-204">The type or member can only be accessed by code in the same class or in a derived class.</span></span>|  
|[<span data-ttu-id="1d758-205">Friend</span><span class="sxs-lookup"><span data-stu-id="1d758-205">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)|<span data-ttu-id="1d758-206">동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-206">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span>|  
|`Protected Friend`|<span data-ttu-id="1d758-207">동일한 어셈블리의 코드 또는 다른 어셈블리의 파생 클래스에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-207">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span>|  
  
 <span data-ttu-id="1d758-208">자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-208">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
###  <span data-ttu-id="1d758-209"><a name="InstantiatingClasses"></a>클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="1d758-209"><a name="InstantiatingClasses"></a> Instantiating Classes</span></span>  
 <span data-ttu-id="1d758-210">개체를 만들려면 클래스를 인스턴스화하거나 클래스 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-210">To create an object, you need to instantiate a class, or create a class instance.</span></span>  
  
```vb  
Dim sampleObject as New SampleClass()  
```  
  
 <span data-ttu-id="1d758-211">클래스를 인스턴스화한 후에는 인스턴스의 속성과 필드에 값을 할당하고 클래스 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-211">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>  
  
```vb  
' Set a property value.  
sampleObject.SampleProperty = "Sample String"  
' Call a method.  
sampleObject.SampleMethod()  
```  
  
 <span data-ttu-id="1d758-212">클래스를 인스턴스화하는 동안 속성에 값을 할당하려면 다음과 같이 개체 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-212">To assign values to properties during the class instantiation process, use object initializers:</span></span>  
  
```vb  
Dim sampleObject = New SampleClass With   
    {.FirstProperty = "A", .SecondProperty = "B"}  
```  
  
 <span data-ttu-id="1d758-213">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-213">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-214">New 연산자</span><span class="sxs-lookup"><span data-stu-id="1d758-214">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
  
-   [<span data-ttu-id="1d758-215">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="1d758-215">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
  
###  <span data-ttu-id="1d758-216"><a name="Static"></a>공유 클래스 및 멤버</span><span class="sxs-lookup"><span data-stu-id="1d758-216"><a name="Static"></a> Shared Classes and Members</span></span>  
 <span data-ttu-id="1d758-217">클래스의 공유 멤버 속성, 프로시저 또는 클래스의 모든 인스턴스에서 공유 되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-217">A shared member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>  
  
 <span data-ttu-id="1d758-218">정의 하려면 공유 멤버:</span><span class="sxs-lookup"><span data-stu-id="1d758-218">To define a shared member:</span></span>  
  
```vb  
Class SampleClass  
    Public Shared SampleString As String = "Sample String"  
End Class  
```  
  
 <span data-ttu-id="1d758-219">공유 멤버에 액세스 하려면이 클래스의 개체를 만들지 않고 클래스의 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-219">To access the shared member, use the name of the class without creating an object of this class:</span></span>  
  
```vb  
MsgBox(SampleClass.SampleString)  
```  
  
 <span data-ttu-id="1d758-220">Visual Basic의 모듈은 공유 멤버에만 공유 있으며 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-220">Shared modules in Visual Basic have shared members only and cannot be instantiated.</span></span> <span data-ttu-id="1d758-221">공유 멤버 또한 액세스할 수 없습니다 공유 되지 않는 속성, 필드 또는 메서드</span><span class="sxs-lookup"><span data-stu-id="1d758-221">Shared members also cannot access non-shared properties, fields or methods</span></span>  
  
 <span data-ttu-id="1d758-222">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-222">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-223">공유</span><span class="sxs-lookup"><span data-stu-id="1d758-223">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
  
-   [<span data-ttu-id="1d758-224">Module 문</span><span class="sxs-lookup"><span data-stu-id="1d758-224">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
###  <span data-ttu-id="1d758-225"><a name="AnonymousTypes"></a>익명 형식</span><span class="sxs-lookup"><span data-stu-id="1d758-225"><a name="AnonymousTypes"></a> Anonymous Types</span></span>  
 <span data-ttu-id="1d758-226">익명 형식을 사용하면 데이터 형식에 대한 클래스 정의를 작성하지 않고 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-226">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="1d758-227">대신 컴파일러가 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-227">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="1d758-228">이 클래스는 사용할 수 있는 이름이 없고 개체를 선언할 때 지정하는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-228">The class has no usable name and contains the properties you specify in declaring the object.</span></span>  
  
 <span data-ttu-id="1d758-229">익명 형식의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1d758-229">To create an instance of an anonymous type:</span></span>  
  
```vb  
' sampleObject is an instance of a simple anonymous type.  
Dim sampleObject =   
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}  
```  
  
 <span data-ttu-id="1d758-230">자세한 내용은 참조: [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-230">For more information, see: [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
##  <span data-ttu-id="1d758-231"><a name="Inheritance"></a>상속</span><span class="sxs-lookup"><span data-stu-id="1d758-231"><a name="Inheritance"></a> Inheritance</span></span>  
 <span data-ttu-id="1d758-232">상속을 사용하면 다른 클래스에 정의된 동작을 다시 사용, 확장 및 수정하는 새 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-232">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="1d758-233">멤버가 상속 되는 클래스 라고는 *기본 클래스*, 해당 멤버를 상속 하는 클래스 라고 하 고는 *파생 클래스*합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-233">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="1d758-234">하지만 Visual Basic의 모든 클래스에서 암시적으로 상속는 <xref:System.Object>.NET 클래스 계층 구조를 지원 하 고 모든 클래스에 하위 수준 서비스를 제공 하는 클래스입니다.</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="1d758-234">However, all classes in Visual Basic implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d758-235">Visual Basic 다중 상속을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-235">Visual Basic doesn't support multiple inheritance.</span></span> <span data-ttu-id="1d758-236">즉, 파생된 클래스에 대 한 기본 클래스가 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-236">That is, you can specify only one base class for a derived class.</span></span>  
  
 <span data-ttu-id="1d758-237">기본 클래스에서 상속하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-237">To inherit from a base class:</span></span>  
  
```vb  
Class DerivedClass  
    Inherits BaseClass  
End Class  
```  
  
 <span data-ttu-id="1d758-238">기본적으로 모든 클래스는 상속될 수 있지만</span><span class="sxs-lookup"><span data-stu-id="1d758-238">By default all classes can be inherited.</span></span> <span data-ttu-id="1d758-239">클래스가 기본 클래스로 사용되지 않아야 하는지 여부를 지정하거나 기본 클래스로만 사용될 수 있는 클래스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-239">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>  
  
 <span data-ttu-id="1d758-240">클래스가 기본 클래스로 사용될 수 없도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-240">To specify that a class cannot be used as a base class:</span></span>  
  
```vb  
NotInheritable Class SampleClass  
End Class  
```  
  
 <span data-ttu-id="1d758-241">클래스가 기본 클래스로만 사용되고 인스턴스화되지 않도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-241">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>  
  
```vb  
MustInherit Class BaseClass  
End Class  
```  
  
 <span data-ttu-id="1d758-242">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-242">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-243">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="1d758-243">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
  
-   [<span data-ttu-id="1d758-244">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="1d758-244">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
  
-   [<span data-ttu-id="1d758-245">MustInherit</span><span class="sxs-lookup"><span data-stu-id="1d758-245">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
  
###  <span data-ttu-id="1d758-246"><a name="Overriding"></a>멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="1d758-246"><a name="Overriding"></a> Overriding Members</span></span>  
 <span data-ttu-id="1d758-247">기본적으로 파생 클래스는 해당 기본 클래스에서 모든 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-247">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="1d758-248">상속된 멤버의 동작을 변경하려면 해당 멤버를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-248">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="1d758-249">즉, 파생 클래스에 해당 메서드, 속성 또는 이벤트의 새로운 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-249">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>  
  
 <span data-ttu-id="1d758-250">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-250">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
|<span data-ttu-id="1d758-251">Visual Basic 한정자</span><span class="sxs-lookup"><span data-stu-id="1d758-251">Visual Basic Modifier</span></span>|<span data-ttu-id="1d758-252">정의</span><span class="sxs-lookup"><span data-stu-id="1d758-252">Definition</span></span>|  
|---------------------------|----------------|  
|[<span data-ttu-id="1d758-253">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="1d758-253">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)|<span data-ttu-id="1d758-254">파생 클래스에서 클래스 멤버를 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-254">Allows a class member to be overridden in a derived class.</span></span>|  
|[<span data-ttu-id="1d758-255">재정의</span><span class="sxs-lookup"><span data-stu-id="1d758-255">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)|<span data-ttu-id="1d758-256">기본 클래스에 정의된 가상(재정의 가능) 멤버를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-256">Overrides a virtual (overridable) member defined in the base class.</span></span>|  
|[<span data-ttu-id="1d758-257">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="1d758-257">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)|<span data-ttu-id="1d758-258">멤버가 상속 클래스에서 재정의되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-258">Prevents a member from being overridden in an inheriting class.</span></span>|  
|[<span data-ttu-id="1d758-259">MustOverride</span><span class="sxs-lookup"><span data-stu-id="1d758-259">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)|<span data-ttu-id="1d758-260">파생 클래스에서 클래스 멤버가 재정의되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-260">Requires that a class member to be overridden in the derived class.</span></span>|  
|[<span data-ttu-id="1d758-261">Shadows</span><span class="sxs-lookup"><span data-stu-id="1d758-261">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)|<span data-ttu-id="1d758-262">기본 클래스에서 상속된 멤버를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-262">Hides a member inherited from a base class</span></span>|  
  
##  <span data-ttu-id="1d758-263"><a name="Interfaces"></a>인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d758-263"><a name="Interfaces"></a> Interfaces</span></span>  
 <span data-ttu-id="1d758-264">인터페이스는 클래스와 마찬가지로 속성, 메서드 및 이벤트를 정의하지만</span><span class="sxs-lookup"><span data-stu-id="1d758-264">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="1d758-265">클래스와는 달리 구현을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-265">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="1d758-266">인터페이스는 클래스에 의해 구현되며 클래스와는 별개의 엔터티로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-266">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="1d758-267">인터페이스는 계약을 나타내므로 인터페이스를 구현하는 클래스에서는 해당 인터페이스의 모든 부분을 정의된 그대로 정확하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-267">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>  
  
 <span data-ttu-id="1d758-268">인터페이스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-268">To define an interface:</span></span>  
  
```vb  
Public Interface ISampleInterface  
    Sub DoSomething()  
End Interface  
```  
  
 <span data-ttu-id="1d758-269">클래스에서 인터페이스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-269">To implement an interface in a class:</span></span>  
  
```vb  
Class SampleClass  
    Implements ISampleInterface  
    Sub DoSomething  
        ' Method implementation.  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1d758-270">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-270">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-271">인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d758-271">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
  
-   [<span data-ttu-id="1d758-272">Interface 문</span><span class="sxs-lookup"><span data-stu-id="1d758-272">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   [<span data-ttu-id="1d758-273">Implements 문</span><span class="sxs-lookup"><span data-stu-id="1d758-273">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)  
  
##  <span data-ttu-id="1d758-274"><a name="Generics"></a>제네릭</span><span class="sxs-lookup"><span data-stu-id="1d758-274"><a name="Generics"></a> Generics</span></span>  
 <span data-ttu-id="1d758-275">클래스, 구조체, 인터페이스 및 메서드는.NET Framework에 포함 될 수 있습니다 *형식 매개 변수* 저장 하거나 사용할 수 있는 개체의 형식을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-275">Classes, structures, interfaces and methods in the .NET Framework can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="1d758-276">제네릭의 가장 일반적인 예는 컬렉션에 저장할 개체의 형식을 지정할 수 있는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-276">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>  
  
 <span data-ttu-id="1d758-277">제네릭 클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="1d758-277">To define a generic class:</span></span>  
  
```vb  
Class SampleGeneric(Of T)  
    Public Field As T  
End Class  
```  
  
 <span data-ttu-id="1d758-278">제네릭 클래스의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1d758-278">To create an instance of a generic class:</span></span>  
  
```vb  
Dim sampleObject As New SampleGeneric(Of String)  
sampleObject.Field = "Sample string"  
```  
  
 <span data-ttu-id="1d758-279">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-279">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-280">제네릭</span><span class="sxs-lookup"><span data-stu-id="1d758-280">Generics</span></span>](https://msdn.microsoft.com/library/ms172192)  
  
-   [<span data-ttu-id="1d758-281">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="1d758-281">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
  
##  <span data-ttu-id="1d758-282"><a name="Delegates"></a>대리자</span><span class="sxs-lookup"><span data-stu-id="1d758-282"><a name="Delegates"></a> Delegates</span></span>  
 <span data-ttu-id="1d758-283">A *위임* 메서드 시그니처를 정의 하는 형식이 고 호환 되는 시그니처가 있는 메서드에 대 한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-283">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="1d758-284">대리자를 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-284">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="1d758-285">대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-285">Delegates are used to pass methods as arguments to other methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d758-286">이벤트 처리기는 대리자를 통해 호출되는 메서드라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-286">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="1d758-287">대리자를 사용 하 여 이벤트 처리에서 하는 방법에 대 한 자세한 내용은 참조 [이벤트](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d758-287">For more information about using delegates in event handling, see [Events](http://msdn.microsoft.com/library/b6f65241-e0ad-4590-a99f-200ce741bb1f).</span></span>  
  
 <span data-ttu-id="1d758-288">대리자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1d758-288">To create a delegate:</span></span>  
  
```vb  
Delegate Sub SampleDelegate(ByVal str As String)  
```  
  
 <span data-ttu-id="1d758-289">대리자가 지정한 시그니처와 일치하는 메서드에 대한 참조를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1d758-289">To create a reference to a method that matches the signature specified by the delegate:</span></span>  
  
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
  
 <span data-ttu-id="1d758-290">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d758-290">For more information, see:</span></span>  
  
-   [<span data-ttu-id="1d758-291">대리자</span><span class="sxs-lookup"><span data-stu-id="1d758-291">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
  
-   [<span data-ttu-id="1d758-292">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="1d758-292">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
-   [<span data-ttu-id="1d758-293">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="1d758-293">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d758-294">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d758-294">See Also</span></span>  
 [<span data-ttu-id="1d758-295">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1d758-295">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
