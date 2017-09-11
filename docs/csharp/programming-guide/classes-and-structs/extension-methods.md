---
title: "확장명 메서드(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- methods [C#], adding to existing types
- extension methods [C#]
- methods [C#], extension
ms.assetid: 175ce3ff-9bbf-4e64-8421-faeb81a0bb51
caps.latest.revision: 35
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
ms.sourcegitcommit: d74c1d0760d4e776c2cf4c7dea1dac060c85a83c
ms.openlocfilehash: 657f9ebfba5d6f49d3a88cb1cf790e4a0134a007
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="extension-methods-c-programming-guide"></a><span data-ttu-id="71985-102">확장명 메서드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="71985-102">Extension Methods (C# Programming Guide)</span></span>
<span data-ttu-id="71985-103">확장명 메서드를 사용하면 새 파생 형식을 만들거나 다시 컴파일하거나 원래 형식을 수정하지 않고도 기존 형식에 메서드를 "추가"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-103">Extension methods enable you to "add" methods to existing types without creating a new derived type, recompiling, or otherwise modifying the original type.</span></span> <span data-ttu-id="71985-104">확장 메서드는 특수한 종류의 정적 메서드이지만 확장 형식의 인스턴스 메서드인 것처럼 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="71985-104">Extension methods are a special kind of static method, but they are called as if they were instance methods on the extended type.</span></span> <span data-ttu-id="71985-105">C#, F# 및 Visual Basic에서 작성된 클라이언트 코드의 경우 확장명 메서드를 호출하는 것과 형식에 실제로 정의된 메서드를 호출하는 데는 명백한 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-105">For client code written in C#, F# and Visual Basic, there is no apparent difference between calling an extension method and the methods that are actually defined in a type.</span></span>  
  
 <span data-ttu-id="71985-106">가장 일반적인 확장명 메서드는 쿼리 기능을 기존 <xref:System.Collections.IEnumerable?displayProperty=fullName> 및 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 형식에 추가하는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 표준 쿼리 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="71985-106">The most common extension methods are the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] standard query operators that add query functionality to the existing <xref:System.Collections.IEnumerable?displayProperty=fullName> and <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> types.</span></span> <span data-ttu-id="71985-107">표준 쿼리 연산자를 사용하려면 `using System.Linq` 지시문을 사용해서 먼저 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-107">To use the standard query operators, first bring them into scope with a `using System.Linq` directive.</span></span> <span data-ttu-id="71985-108">그러면 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 모든 형식에 <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A> 등의 인스턴스 메서드가 있는 것처럼 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="71985-108">Then any type that implements <xref:System.Collections.Generic.IEnumerable%601> appears to have instance methods such as <xref:System.Linq.Enumerable.GroupBy%2A>, <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="71985-109"><xref:System.Collections.Generic.List%601> 또는 <xref:System.Array>와 같은 <xref:System.Collections.Generic.IEnumerable%601> 형식의 인스턴스 뒤에 "dot"를 입력하면 IntelliSense 문 완성에서 이러한 추가 메서드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-109">You can see these additional methods in IntelliSense statement completion when you type "dot" after an instance of an <xref:System.Collections.Generic.IEnumerable%601> type such as <xref:System.Collections.Generic.List%601> or <xref:System.Array>.</span></span>  
  
 <span data-ttu-id="71985-110">다음 예제에서는 정수 배열에서 표준 쿼리 연산자 `OrderBy`를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71985-110">The following example shows how to call the standard query operator `OrderBy` method on an array of integers.</span></span> <span data-ttu-id="71985-111">괄호 안의 식은 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="71985-111">The expression in parentheses is a lambda expression.</span></span> <span data-ttu-id="71985-112">많은 표준 쿼리 연산자가 람다 식을 매개 변수로 사용하지만 확장명 메서드에 대한 요구 사항은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="71985-112">Many standard query operators take lambda expressions as parameters, but this is not a requirement for extension methods.</span></span> <span data-ttu-id="71985-113">자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71985-113">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="71985-114">[!code-cs[csProgGuideExtensionMethods#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="71985-114">[!code-cs[csProgGuideExtensionMethods#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="71985-115">확장명 메서드는 정적 메서드로 정의되지만 인스턴스 메서드 구문을 사용하여 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="71985-115">Extension methods are defined as static methods but are called by using instance method syntax.</span></span> <span data-ttu-id="71985-116">확장 메서드의 첫 번째 매개 변수는 메서드가 작동하는 형식을 지정하며 매개 변수 앞에 [this](../../../csharp/language-reference/keywords/this.md) 한정자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-116">Their first parameter specifies which type the method operates on, and the parameter is preceded by the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span> <span data-ttu-id="71985-117">확장 메서드는 `using` 지시문을 사용하여 명시적으로 네임스페이스를 소스 코드로 가져오는 경우에만 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-117">Extension methods are only in scope when you explicitly import the namespace into your source code with a `using` directive.</span></span>  
  
 <span data-ttu-id="71985-118">다음 예제에서는 <xref:System.String?displayProperty=fullName> 클래스에 대해 정의된 확장 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71985-118">The following example shows an extension method defined for the <xref:System.String?displayProperty=fullName> class.</span></span> <span data-ttu-id="71985-119">이 확장 메서드는 제네릭이 아닌 비중첩 정적 클래스 내부에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="71985-119">Note that it is defined inside a non-nested, non-generic static class:</span></span>  
  
 <span data-ttu-id="71985-120">[!code-cs[csProgGuideExtensionMethods#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="71985-120">[!code-cs[csProgGuideExtensionMethods#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="71985-121">`WordCount` 지시문을 사용하여 `using` 확장 메서드를 범위로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-121">The `WordCount` extension method can be brought into scope with this `using` directive:</span></span>  
  
```  
using ExtensionMethods;  
```  
  
 <span data-ttu-id="71985-122">또한 다음 구문을 사용하여 응용 프로그램에서 확장 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-122">And it can be called from an application by using this syntax:</span></span>  
  
```  
string s = "Hello Extension Methods";  
int i = s.WordCount();  
```  
  
 <span data-ttu-id="71985-123">코드에서 인스턴스 메서드 구문을 사용하여 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-123">In your code you invoke the extension method with instance method syntax.</span></span> <span data-ttu-id="71985-124">그러나 컴파일러에서 생성된 IL(중간 언어)이 코드를 정적 메서드 호출로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-124">However, the intermediate language (IL) generated by the compiler translates your code into a call on the static method.</span></span> <span data-ttu-id="71985-125">따라서 실제로 캡슐화의 원칙을 위반하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-125">Therefore, the principle of encapsulation is not really being violated.</span></span> <span data-ttu-id="71985-126">사실상 확장명 메서드는 확장하는 형식의 private 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-126">In fact, extension methods cannot access private variables in the type they are extending.</span></span>  
  
 <span data-ttu-id="71985-127">자세한 내용은 [방법: 사용자 지정 확장 메서드 구현 및 호출](../../../csharp/programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71985-127">For more information, see [How to: Implement and Call a Custom  Extension Method](../../../csharp/programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).</span></span>  
  
 <span data-ttu-id="71985-128">일반적으로 확장명 메서드를 직접 구현하는 것보다 호출하는 경우가 훨씬 많습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-128">In general, you will probably be calling extension methods far more often than implementing your own.</span></span> <span data-ttu-id="71985-129">확장 메서드는 인스턴스 메서드 구문을 사용하여 호출되므로 특별한 지식이 없어도 클라이언트 코드에서 확장 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-129">Because extension methods are called by using instance method syntax, no special knowledge is required to use them from client code.</span></span> <span data-ttu-id="71985-130">특정 형식의 확장 메서드를 사용하려면 해당 메서드가 정의된 네임스페이스에 대해 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-130">To enable extension methods for a particular type, just add a `using` directive for the namespace in which the methods are defined.</span></span> <span data-ttu-id="71985-131">예를 들어 표준 쿼리 연산자를 사용하려면 다음 `using` 지시문을 코드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-131">For example, to use the standard query operators, add this `using` directive to your code:</span></span>  
  
```  
using System.Linq;  
```  
  
 <span data-ttu-id="71985-132">System.Core.dll에 대한 참조를 추가해야 할 수도 있습니다. 이제 표준 쿼리 연산자가 대부분의 <xref:System.Collections.Generic.IEnumerable%601> 형식에 사용할 수 있는 추가 메서드로 IntelliSense에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="71985-132">(You may also have to add a reference to System.Core.dll.) You will notice that the standard query operators now appear in IntelliSense as additional methods available for most <xref:System.Collections.Generic.IEnumerable%601> types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71985-133"><xref:System.String>에 대한 표준 쿼리 연산자는 IntelliSense에는 표시되지 않지만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-133">Although standard query operators do not appear in IntelliSense for <xref:System.String>, they are still available.</span></span>  
  
## <a name="binding-extension-methods-at-compile-time"></a><span data-ttu-id="71985-134">컴파일 타임에 확장 메서드 바인딩</span><span class="sxs-lookup"><span data-stu-id="71985-134">Binding Extension Methods at Compile Time</span></span>  
 <span data-ttu-id="71985-135">확장 메서드를 사용하여 클래스 또는 인터페이스를 확장할 수 있지만 재정의할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-135">You can use extension methods to extend a class or interface, but not to override them.</span></span> <span data-ttu-id="71985-136">이름과 시그니처가 인터페이스 또는 클래스 메서드와 동일한 확장 메서드는 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-136">An extension method with the same name and signature as an interface or class method will never be called.</span></span> <span data-ttu-id="71985-137">컴파일 시간에 확장 메서드는 항상 형식 자체에서 정의된 인스턴스 메서드보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-137">At compile time, extension methods always have lower priority than instance methods defined in the type itself.</span></span> <span data-ttu-id="71985-138">즉, 형식에 `Process(int i)`라는 메서드가 있고 동일한 시그니처를 가진 확장 메서드가 있는 경우 컴파일러는 항상 인스턴스 메서드에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-138">In other words, if a type has a method named `Process(int i)`, and you have an extension method with the same signature, the compiler will always bind to the instance method.</span></span> <span data-ttu-id="71985-139">컴파일러는 메서드 호출을 발견할 경우 먼저 형식의 인스턴스 메서드에서 일치 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-139">When the compiler encounters a method invocation, it first looks for a match in the type's instance methods.</span></span> <span data-ttu-id="71985-140">일치 항목이 없으면 형식에 대해 정의된 확장 메서드를 검색하고 찾은 첫 번째 확장 메서드에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-140">If no match is found, it will search for any extension methods that are defined for the type, and bind to the first extension method that it finds.</span></span> <span data-ttu-id="71985-141">다음 예제에서는 컴파일러가 바인딩할 확장명 메서드 또는 인스턴스 메서드를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71985-141">The following example demonstrates how the compiler determines which extension method or instance method to bind to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71985-142">예제</span><span class="sxs-lookup"><span data-stu-id="71985-142">Example</span></span>  
 <span data-ttu-id="71985-143">다음 예제에서는 C# 컴파일러가 메서드 호출을 형식의 인스턴스 메서드 또는 확장명 메서드에 바인딩할 것인지 결정할 때 따르는 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71985-143">The following example demonstrates the rules that the C# compiler follows in determining whether to bind a method call to an instance method on the type, or to an extension method.</span></span> <span data-ttu-id="71985-144">정적 클래스 `Extensions`는 `IMyInterface`를 구현하는 모든 형식에 대해 정의된 확장 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-144">The static class `Extensions` contains extension methods defined for any type that implements `IMyInterface`.</span></span> <span data-ttu-id="71985-145">`A`, `B` 및 `C` 클래스는 모두 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-145">Classes `A`, `B`, and `C` all implement the interface.</span></span>  
  
 <span data-ttu-id="71985-146">`MethodB` 확장 메서드는 이름과 시그니처가 클래스에서 이미 구현된 메서드와 정확하게 일치하므로 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-146">The `MethodB` extension method is never called because its name and signature exactly match methods already implemented by the classes.</span></span>  
  
 <span data-ttu-id="71985-147">일치하는 시그니처를 가진 인스턴스 메서드를 찾을 수 없으면 컴파일러는 일치하는 확장명 메서드(있는 경우)에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-147">When the compiler cannot find an instance method with a matching signature, it will bind to a matching extension method if one exists.</span></span>  
  
 <span data-ttu-id="71985-148">[!code-cs[csProgGuideExtensionMethods#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="71985-148">[!code-cs[csProgGuideExtensionMethods#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/extension-methods_3.cs)]</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="71985-149">일반 지침</span><span class="sxs-lookup"><span data-stu-id="71985-149">General Guidelines</span></span>  
 <span data-ttu-id="71985-150">일반적으로 반드시 필요한 경우에만 드물게 확장 메서드를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-150">In general, we recommend that you implement extension methods sparingly and only when you have to.</span></span> <span data-ttu-id="71985-151">가능하면 기존 형식을 확장해야 하는 클라이언트 코드는 기존 형식에서 파생된 새 형식을 만들어 이 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-151">Whenever possible, client code that must extend an existing type should do so by creating a new type derived from the existing type.</span></span> <span data-ttu-id="71985-152">자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71985-152">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="71985-153">기존 메서드를 사용하여 소스 코드를 변경할 수 없는 형식을 확장하는 경우 형식의 구현이 변경되어 확장명 메서드가 손상될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-153">When using an extension method to extend a type whose source code you cannot change, you run the risk that a change in the implementation of the type will cause your extension method to break.</span></span>  
  
 <span data-ttu-id="71985-154">지정된 형식에 대해 확장 메서드를 구현하는 경우 다음 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="71985-154">If you do implement extension methods for a given type, remember the following points:</span></span>  
  
-   <span data-ttu-id="71985-155">시그니처가 형식에 정의된 메서드와 동일한 확장 메서드는 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71985-155">An extension method will never be called if it has the same signature as a method defined in the type.</span></span>  
  
-   <span data-ttu-id="71985-156">확장 메서드는 네임스페이스 수준에서 범위로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71985-156">Extension methods are brought into scope at the namespace level.</span></span> <span data-ttu-id="71985-157">예를 들어 `Extensions`라는 단일 네임스페이스에 확장 메서드를 포함하는 여러 개의 정적 클래스가 있는 경우 `using Extensions;` 지시문을 통해 모두 범위로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="71985-157">For example, if you have multiple static classes that contain extension methods in a single namespace named `Extensions`, they will all be brought into scope by the `using Extensions;` directive.</span></span>  
  
 <span data-ttu-id="71985-158">구현된 클래스 라이브러리의 경우 어셈블리의 버전 번호가 증가되는 것을 방지하기 위해 확장 메서드를 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71985-158">For a class library that you implemented, you shouldn't use extension methods to avoid incrementing the version number of an assembly.</span></span> <span data-ttu-id="71985-159">소스 코드를 소유하고 있는 라이브러리에 중요 기능을 추가하려는 경우 어셈블리 버전 관리를 위한 표준 .NET Framework 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71985-159">If you want to add significant functionality to a library for which you own the source code, you should follow the standard .NET Framework guidelines for assembly versioning.</span></span> <span data-ttu-id="71985-160">자세한 내용은 [어셈블리 버전 관리](https://msdn.microsoft.com/library/51ket42z)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71985-160">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71985-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71985-161">See Also</span></span>  
 <span data-ttu-id="71985-162">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="71985-162">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="71985-163">[병렬 프로그래밍 샘플(많은 예제 확장 메서드 포함)](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364) </span><span class="sxs-lookup"><span data-stu-id="71985-163">[Parallel Programming Samples (these include many example extension methods)](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364) </span></span>  
 <span data-ttu-id="71985-164">[람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="71985-164">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 <span data-ttu-id="71985-165">[표준 쿼리 연산자 개요](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2) </span><span class="sxs-lookup"><span data-stu-id="71985-165">[Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2) </span></span>  
 <span data-ttu-id="71985-166">[인스턴스 매개 변수의 변환 규칙 및 그에 따른 영향](http://go.microsoft.com/fwlink/?LinkId=112385) </span><span class="sxs-lookup"><span data-stu-id="71985-166">[Conversion rules for Instance parameters and their impact](http://go.microsoft.com/fwlink/?LinkId=112385) </span></span>  
 <span data-ttu-id="71985-167">[언어 간 확장 메서드 상호 운용성](http://go.microsoft.com/fwlink/?LinkId=112386) </span><span class="sxs-lookup"><span data-stu-id="71985-167">[Extension methods Interoperability between languages](http://go.microsoft.com/fwlink/?LinkId=112386) </span></span>  
 <span data-ttu-id="71985-168">[확장 메서드 및 대리자 변환](http://go.microsoft.com/fwlink/?LinkId=112387) </span><span class="sxs-lookup"><span data-stu-id="71985-168">[Extension methods and Curried Delegates](http://go.microsoft.com/fwlink/?LinkId=112387) </span></span>  
 [<span data-ttu-id="71985-169">확장 메서드 바인딩 및 오류 보고</span><span class="sxs-lookup"><span data-stu-id="71985-169">Extension method Binding and Error reporting</span></span>](http://go.microsoft.com/fwlink/?LinkId=112388)

