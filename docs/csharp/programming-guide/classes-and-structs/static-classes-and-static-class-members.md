---
title: "정적 클래스 및 정적 클래스 멤버(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: "49"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b1e7366d8d82ca99a8d779dda1e194dcc8c2ab6e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a><span data-ttu-id="ba410-102">정적 클래스 및 정적 클래스 멤버(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ba410-102">Static Classes and Static Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="ba410-103">[정적](../../../csharp/language-reference/keywords/static.md) 클래스는 기본적으로 비정적 클래스와 동일하지만, 정적 클래스는 인스턴스화할 수 없다는 한 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-103">A [static](../../../csharp/language-reference/keywords/static.md) class is basically the same as a non-static class, but there is one difference: a static class cannot be instantiated.</span></span> <span data-ttu-id="ba410-104">즉, [new](../../../csharp/language-reference/keywords/new.md) 키워드를 사용하여 클래스 형식의 변수를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-104">In other words, you cannot use the [new](../../../csharp/language-reference/keywords/new.md) keyword to create a variable of the class type.</span></span> <span data-ttu-id="ba410-105">인스턴스 변수가 없기 때문에 클래스 이름 자체를 사용하여 정적 클래스의 멤버에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-105">Because there is no instance variable, you access the members of a static class by using the class name itself.</span></span> <span data-ttu-id="ba410-106">예를 들어 public 메서드 `MethodA`를 포함하는 `UtilityClass`라는 정적 클래스가 있는 경우 다음 예제와 같이 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-106">For example, if you have a static class that is named `UtilityClass` that has a public method named `MethodA`, you call the method as shown in the following example:</span></span>  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 <span data-ttu-id="ba410-107">정적 클래스는 입력 매개 변수에 대해서만 작동하고 내부 인스턴스 필드를 가져오거나 설정할 필요가 없는 메서드 집합에 대한 편리한 컨테이너로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-107">A static class can be used as a convenient container for sets of methods that just operate on input parameters and do not have to get or set any internal instance fields.</span></span> <span data-ttu-id="ba410-108">예를 들어 .NET Framework 클래스 라이브러리의 정적 <xref:System.Math?displayProperty=nameWithType> 클래스에는 <xref:System.Math> 클래스의 특정 인스턴스에 고유한 데이터를 저장하거나 검색할 필요 없이 수학 연산을 수행하는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-108">For example, in the .NET Framework Class Library, the static <xref:System.Math?displayProperty=nameWithType> class contains methods that perform mathematical operations, without any requirement to store or retrieve data that is unique to a particular instance of the <xref:System.Math> class.</span></span> <span data-ttu-id="ba410-109">즉, 다음 예제와 같이 클래스 이름과 메서드 이름을 지정하여 클래스의 멤버를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-109">That is, you apply the members of the class by specifying the class name and the method name, as shown in the following example.</span></span>  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 <span data-ttu-id="ba410-110">모든 클래스 형식과 마찬가지로, 정적 클래스에 대한 형식 정보는 클래스를 참조하는 프로그램이 로드될 때 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] CLR(공용 언어 런타임)에 의해 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-110">As is the case with all class types, the type information for a static class is loaded by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] common language runtime (CLR) when the program that references the class is loaded.</span></span> <span data-ttu-id="ba410-111">프로그램에서 클래스가 로드되는 시기를 정확하게 지정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-111">The program cannot specify exactly when the class is loaded.</span></span> <span data-ttu-id="ba410-112">그러나 클래스가 로드되도록 하고, 프로그램에서 클래스를 처음으로 참조하기 전에 해당 필드가 초기화되고 정적 생성자가 호출되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-112">However, it is guaranteed to be loaded and to have its fields initialized and its static constructor called before the class is referenced for the first time in your program.</span></span> <span data-ttu-id="ba410-113">정적 생성자는 한 번만 호출되며, 프로그램이 있는 응용 프로그램 도메인의 수명 동안 정적 클래스가 메모리에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-113">A static constructor is only called one time, and a static class remains in memory for the lifetime of the application domain in which your program resides.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba410-114">자체 인스턴스 하나만 생성될 수 있도록 하는 비정적 클래스를 만들려면 [C#에서 Singleton 구현](https://msdn.microsoft.com/library/ms998558.aspx)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba410-114">To create a non-static class that allows only one instance of itself to be created, see [Implementing Singleton in C#](https://msdn.microsoft.com/library/ms998558.aspx).</span></span>  
  
 <span data-ttu-id="ba410-115">다음 목록은 정적 클래스의 주요 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-115">The following list provides the main features of a static class:</span></span>  
  
-   <span data-ttu-id="ba410-116">정적 멤버만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-116">Contains only static members.</span></span>  
  
-   <span data-ttu-id="ba410-117">인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-117">Cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="ba410-118">봉인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-118">Is sealed.</span></span>  
  
-   <span data-ttu-id="ba410-119">[인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-119">Cannot contain [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="ba410-120">따라서 정적 클래스를 만드는 것은 기본적으로 정적 멤버와 private 생성자만 포함된 클래스를 만드는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-120">Creating a static class is therefore basically the same as creating a class that contains only static members and a private constructor.</span></span> <span data-ttu-id="ba410-121">private 생성자는 클래스가 인스턴스화되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-121">A private constructor prevents the class from being instantiated.</span></span> <span data-ttu-id="ba410-122">정적 클래스를 사용하면 컴파일러에서 인스턴스 멤버가 실수로 추가되지 않도록 확인할 수 있다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-122">The advantage of using a static class is that the compiler can check to make sure that no instance members are accidentally added.</span></span> <span data-ttu-id="ba410-123">컴파일러는 이 클래스의 인스턴스를 만들 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-123">The compiler will guarantee that instances of this class cannot be created.</span></span>  
  
 <span data-ttu-id="ba410-124">정적 클래스는 봉인되므로 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-124">Static classes are sealed and therefore cannot be inherited.</span></span> <span data-ttu-id="ba410-125"><xref:System.Object>를 제외하고 어떤 클래스에서도 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-125">They cannot inherit from any class except <xref:System.Object>.</span></span> <span data-ttu-id="ba410-126">정적 클래스는 인스턴스 생성자를 포함할 수 없지만 정적 생성자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-126">Static classes cannot contain an instance constructor; however, they can contain a static constructor.</span></span> <span data-ttu-id="ba410-127">또한 클래스에 특수한 초기화가 필요한 정적 멤버가 포함된 경우 비정적 클래스에서 정적 생성자도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-127">Non-static classes should also define a static constructor if the class contains static members that require non-trivial initialization.</span></span> <span data-ttu-id="ba410-128">자세한 내용은 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba410-128">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba410-129">예</span><span class="sxs-lookup"><span data-stu-id="ba410-129">Example</span></span>  
 <span data-ttu-id="ba410-130">온도를 섭씨에서 화씨로, 화씨에서 섭씨로 변환하는 두 메서드를 포함하는 정적 클래스의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-130">Here is an example of a static class that contains two methods that convert temperature from Celsius to Fahrenheit and from Fahrenheit to Celsius:</span></span>  
  
 [!code-csharp[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## <a name="static-members"></a><span data-ttu-id="ba410-131">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="ba410-131">Static Members</span></span>  
 <span data-ttu-id="ba410-132">비정적 클래스는 정적 메서드, 필드, 속성 또는 이벤트를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-132">A non-static class can contain static methods, fields, properties, or events.</span></span> <span data-ttu-id="ba410-133">정적 멤버는 클래스 인스턴스가 생성되지 않은 경우에도 클래스에 대해 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-133">The static member is callable on a class even when no instance of the class has been created.</span></span> <span data-ttu-id="ba410-134">정적 멤버는 항상 인스턴스 이름이 아니라 클래스 이름으로 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-134">The static member is always accessed by the class name, not the instance name.</span></span> <span data-ttu-id="ba410-135">생성된 클래스 인스턴스 개수에 관계없이 정적 멤버의 복사본 한 개만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-135">Only one copy of a static member exists, regardless of how many instances of the class are created.</span></span> <span data-ttu-id="ba410-136">정적 메서드 및 속성은 포함하는 형식의 비정적 필드 및 이벤트에 액세스할 수 없으며, 메서드 매개 변수에 명시적으로 전달되지 않은 경우 개체의 인스턴스 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-136">Static methods and properties cannot access non-static fields and events in their containing type, and they cannot access an instance variable of any object unless it is explicitly passed in a method parameter.</span></span>  
  
 <span data-ttu-id="ba410-137">전체 클래스를 static으로 선언하는 것보다 일부 정적 멤버가 포함된 비정적 클래스를 선언하는 것이 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-137">It is more typical to declare a non-static class with some static members, than to declare an entire class as static.</span></span> <span data-ttu-id="ba410-138">정적 필드의 두 가지 일반적인 사용은 인스턴스화된 개체 개수를 유지하거나 모든 인스턴스 간에 공유해야 하는 값을 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-138">Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.</span></span>  
  
 <span data-ttu-id="ba410-139">정적 메서드는 클래스 인스턴스가 아니라 클래스에 속해 있으므로 오버로드할 수 있지만 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-139">Static methods can be overloaded but not overridden, because they belong to the class, and not to any instance of the class.</span></span>  
  
 <span data-ttu-id="ba410-140">필드를 `static const`로 선언할 수는 없지만, [const](../../../csharp/language-reference/keywords/const.md) 필드는 기본적으로 정적으로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-140">Although a field cannot be declared as `static const`, a [const](../../../csharp/language-reference/keywords/const.md) field is essentially static in its behavior.</span></span> <span data-ttu-id="ba410-141">형식의 인스턴스가 아니라 형식에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-141">It belongs to the type, not to instances of the type.</span></span> <span data-ttu-id="ba410-142">따라서 정적 필드에 사용되는 것과 동일한 `ClassName.MemberName` 표기법을 사용하여 const 필드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-142">Therefore, const fields can be accessed by using the same `ClassName.MemberName` notation that is used for static fields.</span></span> <span data-ttu-id="ba410-143">개체 인스턴스는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-143">No object instance is required.</span></span>  
  
 <span data-ttu-id="ba410-144">C#은 정적 지역 변수(메서드 범위 내에서 선언된 변수)를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-144">C# does not support static local variables (variables that are declared in method scope).</span></span>  
  
 <span data-ttu-id="ba410-145">다음 예제와 같이 멤버의 반환 형식 앞에 `static` 키워드를 사용하여 정적 클래스 멤버를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-145">You declare static class members by using the `static` keyword before the return type of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 <span data-ttu-id="ba410-146">정적 멤버는 정적 멤버를 처음으로 액세스하기 전, 정적 생성자가 있을 경우 호출되기 전에 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-146">Static members are initialized before the static member is accessed for the first time and before the static constructor, if there is one, is called.</span></span> <span data-ttu-id="ba410-147">정적 클래스 멤버에 액세스하려면 다음 예제와 같이 변수 이름 대신 클래스 이름을 사용하여 멤버의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-147">To access a static class member, use the name of the class instead of a variable name to specify the location of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 <span data-ttu-id="ba410-148">클래스에 정적 필드가 포함된 경우 클래스가 로드될 때 정적 필드를 초기화하는 정적 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-148">If your class contains static fields, provide a static constructor that initializes them when the class is loaded.</span></span>  
  
 <span data-ttu-id="ba410-149">정적 메서드를 호출하면 MSIL(Microsoft Intermediate Language)로 호출 명령이 생성되는 반면, 인스턴스 메서드를 호출하면 null 개체 참조도 확인하는 `callvirt` 명령이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-149">A call to a static method generates a call instruction in Microsoft intermediate language (MSIL), whereas a call to an instance method generates a `callvirt` instruction, which also checks for a null object references.</span></span> <span data-ttu-id="ba410-150">그러나 대부분의 경우 둘 간의 성능 차이는 크지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba410-150">However, most of the time the performance difference between the two is not significant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ba410-151">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ba410-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ba410-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba410-152">See Also</span></span>  
 [<span data-ttu-id="ba410-153">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ba410-153">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ba410-154">static</span><span class="sxs-lookup"><span data-stu-id="ba410-154">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
 [<span data-ttu-id="ba410-155">클래스</span><span class="sxs-lookup"><span data-stu-id="ba410-155">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [<span data-ttu-id="ba410-156">class</span><span class="sxs-lookup"><span data-stu-id="ba410-156">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="ba410-157">정적 생성자</span><span class="sxs-lookup"><span data-stu-id="ba410-157">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
 [<span data-ttu-id="ba410-158">인스턴스 생성자</span><span class="sxs-lookup"><span data-stu-id="ba410-158">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)
