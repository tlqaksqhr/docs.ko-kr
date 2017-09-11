---
title: "생성자 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
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
ms.openlocfilehash: 75b55fde2fbd1697aed7eb0665a571c63b9b0b42
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="bb33e-102">생성자 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="bb33e-102">Using Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="bb33e-103">[class](../../../csharp/language-reference/keywords/class.md) 또는 [struct](../../../csharp/language-reference/keywords/struct.md)가 만들어지면 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-103">When a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="bb33e-104">생성자는 클래스 또는 구조체와 이름이 같으며 일반적으로 새 개체의 데이터 멤버를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="bb33e-105">다음 예제에서는 간단한 생성자를 사용하여 `Taxi`란 이름의 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="bb33e-106">그런 다음 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 이 클래스를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-106">This class is then instantiated with the [new](../../../csharp/language-reference/keywords/new.md) operator.</span></span> <span data-ttu-id="bb33e-107">새 개체에 메모리가 할당된 직후 `new` 연산자가 `Taxi` 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 <span data-ttu-id="bb33e-108">[!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-108">[!code-cs[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-109">매개 변수가 없는 생성자를 *기본 생성자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-109">A constructor that takes no parameters is called a *default constructor*.</span></span> <span data-ttu-id="bb33e-110">`new` 연산자를 사용하여 개체가 인스턴스화되고 `new`에 제공된 인수가 없을 때마다 기본 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-110">Default constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="bb33e-111">자세한 내용은 [인스턴스 생성자](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb33e-111">For more information, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="bb33e-112">클래스가 [정적](../../../csharp/language-reference/keywords/static.md)이 아닌 경우 생성자가 없는 클래스에는 클래스 인스턴스화를 사용할 수 있도록 C# 컴파일러에서 공용 기본 생성자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-112">Unless the class is [static](../../../csharp/language-reference/keywords/static.md), classes without constructors are given a public default constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="bb33e-113">자세한 내용은 [정적 클래스 및 정적 클래스 멤버](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb33e-113">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="bb33e-114">다음과 같이 생성자를 비공개로 설정하여 클래스의 인스턴스화를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-114">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 <span data-ttu-id="bb33e-115">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-115">[!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-116">자세한 내용은 [전용 생성자](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb33e-116">For more information, see [Private Constructors](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).</span></span>  
  
 <span data-ttu-id="bb33e-117">[struct](../../../csharp/language-reference/keywords/struct.md) 형식의 생성자는 class 생성자와 비슷하지만, `structs`는 컴파일러에서 자동으로 제공되므로 명시적 기본 생성자를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-117">Constructors for [struct](../../../csharp/language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit default constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="bb33e-118">이 생성자는 `struct`의 각 필드를 기본값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-118">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="bb33e-119">자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb33e-119">For more information, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="bb33e-120">그러나 이 기본 생성자는 `struct`가 `new`로 인스턴스화될 경우에만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-120">However, this default constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="bb33e-121">예를 들어, 이 코드는 <xref:System.Int32>에 기본 생성자를 사용하므로 정수가 초기화되었음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-121">For example, this code uses the default constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="bb33e-122">그러나 다음 코드는 `new`를 사용하지 않으므로, 그리고 초기화되지 않은 개체를 사용하려고 하므로 컴파일러 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-122">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="bb33e-123">또는 `structs` 기반의 개체(모든 기본 제공 숫자 형식 포함)를 초기화하거나 할당한 후 다음 예제와 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-123">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="bb33e-124">따라서 값 형식에 대한 기본 생성자를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-124">So calling the default constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="bb33e-125">클래스와 `structs` 모두 매개 변수를 사용하는 생성자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-125">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="bb33e-126">매개 변수를 사용하는 생성자는 `new` 문 또는 [base](../../../csharp/language-reference/keywords/base.md) 문을 통해 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-126">Constructors that take parameters must be called through a `new` statement or a [base](../../../csharp/language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="bb33e-127">클래스 및 `structs`는 여러 생성자를 정의할 수 있으며, 기본 생성자를 정의하는 데에는 둘 다 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-127">Classes and `structs` can also define multiple constructors, and neither is required to define a default constructor.</span></span> <span data-ttu-id="bb33e-128">예:</span><span class="sxs-lookup"><span data-stu-id="bb33e-128">For example:</span></span>  
  
 <span data-ttu-id="bb33e-129">[!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-129">[!code-cs[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-130">다음 문 중 하나를 사용하여 이 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-130">This class can be created by using either of the following statements:</span></span>  
  
 <span data-ttu-id="bb33e-131">[!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-131">[!code-cs[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-132">생성자는 `base` 키워드를 사용하여 기본 클래스의 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-132">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="bb33e-133">예:</span><span class="sxs-lookup"><span data-stu-id="bb33e-133">For example:</span></span>  
  
 <span data-ttu-id="bb33e-134">[!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-134">[!code-cs[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-135">이 예제에서는 생성자의 블록이 실행되기 전에 기본 클래스의 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-135">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="bb33e-136">`base` 키워드는 매개 변수와 함께 또는 매개 변수 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-136">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="bb33e-137">생성자에 대한 매개 변수는 `base`에 대한 매개 변수로 또는 식의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-137">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="bb33e-138">자세한 내용은 [base](../../../csharp/language-reference/keywords/base.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb33e-138">For more information, see [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="bb33e-139">파생 클래스에서는 `base` 키워드를 사용해 기본 클래스 생성자를 명시적으로 호출하지 않으면, 기본 생성자(있는 경우)가 암시적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-139">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the default constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="bb33e-140">즉, 다음과 같은 생성자 선언은 실제로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-140">This means that the following constructor declarations are effectively the same:</span></span>  
  
 <span data-ttu-id="bb33e-141">[!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-141">[!code-cs[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-142">[!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-142">[!code-cs[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-143">기본 클래스가 기본 생성자를 제공하지 않으면 파생 클래스는 `base`를 사용해 기본 생성자를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-143">If a base class does not offer a default constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="bb33e-144">생성자는 [this](../../../csharp/language-reference/keywords/this.md) 키워드를 사용해 동일한 개체의 다른 생성자를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-144">A constructor can invoke another constructor in the same object by using the [this](../../../csharp/language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="bb33e-145">`base`와 마찬가지로 `this`도 매개 변수 유무와 상관없이 사용할 수 있으며, 생성자에 대한 매개 변수는 `this`에 대한 매개 변수로 또는 식의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-145">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="bb33e-146">예를 들어, 이전 예제의 두 번째 생성자는 `this`를 사용해 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-146">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 <span data-ttu-id="bb33e-147">[!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-147">[!code-cs[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-148">이전 예제에서 `this` 키워드를 사용하면 이 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-148">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 <span data-ttu-id="bb33e-149">[!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb33e-149">[!code-cs[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]</span></span>  
  
 <span data-ttu-id="bb33e-150">생성자는 [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) 또는 `protected internal`로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-150">Constructors can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="bb33e-151">이러한 액세스 한정자는 클래스의 사용자가 클래스를 생성하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-151">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="bb33e-152">자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb33e-152">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="bb33e-153">[static](../../../csharp/language-reference/keywords/static.md) 키워드를 사용하여 생성자를 정적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-153">A constructor can be declared static by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="bb33e-154">정적 생성자는 정적 필드에 액세스하기 직전에 자동으로 호출되며 일반적으로 정적 클래스 멤버를 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb33e-154">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="bb33e-155">자세한 내용은 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb33e-155">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bb33e-156">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="bb33e-156">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb33e-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb33e-157">See Also</span></span>  
 <span data-ttu-id="bb33e-158">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb33e-158">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bb33e-159">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb33e-159">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="bb33e-160">[생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="bb33e-160">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="bb33e-161">종료자</span><span class="sxs-lookup"><span data-stu-id="bb33e-161">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

