---
title: "Variant 제네릭 인터페이스 만들기(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 122b56e34582fdd84424fd3f5d2fd5904b401775
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="creating-variant-generic-interfaces-c"></a><span data-ttu-id="6942e-102">Variant 제네릭 인터페이스 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="6942e-102">Creating Variant Generic Interfaces (C#)</span></span>
<span data-ttu-id="6942e-103">인터페이스에서 제네릭 형식 매개 변수를 공변(covariant) 또는 반공변(contravariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="6942e-104">*공변성(covariance)*은 인터페이스 메서드가 제네릭 형식 매개 변수에 정의된 것보다 더 많은 수의 파생된 반환 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="6942e-105">*반공변성(contravariance)*은 인터페이스 메서드가 제네릭 매개 변수에 지정된 것보다 더 적은 수의 파생된 형식의 인수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="6942e-106">공변(covariant) 또는 반공변(contravariant) 제네릭 형식 매개 변수가 포함된 제네릭 인터페이스를 *variant*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6942e-107">.NET Framework 4에서는 기존의 몇몇 제네릭 인터페이스에 대한 가변성 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="6942e-108">.NET Framework의 variant 인터페이스 목록은 [제네릭 인터페이스의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6942e-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="6942e-109">Variant 제네릭 인터페이스 선언</span><span class="sxs-lookup"><span data-stu-id="6942e-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="6942e-110">제네릭 형식 매개 변수에 `in` 및 `out` 키워드를 사용하여 Variant 제네릭 인터페이스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6942e-111">C#에서 `ref` 및 `out` 매개 변수는 variant일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-111">`ref` and `out` parameters in C# cannot be variant.</span></span> <span data-ttu-id="6942e-112">또한 값 형식은 가변성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="6942e-113">`out` 키워드를 사용하여 제네릭 형식 매개 변수를 공변(covariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="6942e-114">공변(covariant) 형식은 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="6942e-115">형식은 인터페이스 메서드의 반환 형식으로만 사용되고 메서드 인수의 형식으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="6942e-116">이 내용은 `R` 형식이 공변(covariant)으로 선언된 다음 예제에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```csharp  
    interface ICovariant<out R>  
    {  
        R GetSomething();  
        // The following statement generates a compiler error.  
        // void SetSometing(R sampleArg);  
  
    }  
    ```  
  
     <span data-ttu-id="6942e-117">그러나 이 규칙에는 한 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-117">There is one exception to this rule.</span></span> <span data-ttu-id="6942e-118">반공변(contravariant) 제네릭 대리자가 메서드 매개 변수로 있는 경우 형식을 이 대리자에 대한 제네릭 형식 매개 변수로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="6942e-119">다음 예제에서 `R` 형식을 통해 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="6942e-120">자세한 내용은 [대리자에서 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자에 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6942e-120">For more information, see [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```csharp  
    interface ICovariant<out R>  
    {  
        void DoSomething(Action<R> callback);  
    }  
    ```  
  
-   <span data-ttu-id="6942e-121">형식은 인터페이스 메서드에 대한 제네릭 제약 조건으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="6942e-122">이는 다음 코드에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-122">This is illustrated in the following code.</span></span>  
  
    ```csharp  
    interface ICovariant<out R>  
    {  
        // The following statement generates a compiler error  
        // because you can use only contravariant or invariant types  
        // in generic contstraints.  
        // void DoSomething<T>() where T : R;  
    }  
    ```  
  
 <span data-ttu-id="6942e-123">`in` 키워드를 사용하여 제네릭 형식 매개 변수를 반공변(contravariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="6942e-124">반공변(contravariant) 형식은 메서드 인수의 형식으로서만 사용할 수 있으며 인터페이스 메서드의 반환 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="6942e-125">반공변(contravariant) 형식은 제네릭 제약 조건에 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="6942e-126">다음 코드에서는 반공변(contravariant) 인터페이스를 선언하고 해당 메서드 중 하나에 제네릭 제약 조건을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```csharp  
interface IContravariant<in A>  
{  
    void SetSomething(A sampleArg);  
    void DoSomething<T>() where T : A;  
    // The following statement generates a compiler error.  
    // A GetSomething();              
}  
```  
  
 <span data-ttu-id="6942e-127">같은 인터페이스에서 그러나 서로 다른 형식 매개 변수에 대해 공변성(covariance) 및 반공변성(contravariance)을 모두 지원하는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```csharp  
interface IVariant<out R, in A>  
{  
    R GetSomething();  
    void SetSomething(A sampleArg);  
    R GetSetSometings(A sampleArg);  
}  
```  
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="6942e-128">Variant 제네릭 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="6942e-128">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="6942e-129">고정(invariant) 인터페이스에 사용되는 같은 구문을 사용하여 클래스에서 Variant 제네릭 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-129">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="6942e-130">다음 코드 예제에서는 제네릭 클래스에서 공변(covariant) 인터페이스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-130">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
```csharp  
interface ICovariant<out R>  
{  
    R GetSomething();  
}  
class SampleImplementation<R> : ICovariant<R>  
{  
    public R GetSomething()  
    {  
        // Some code.  
        return default(R);  
    }  
}  
```  
  
 <span data-ttu-id="6942e-131">Variant 인터페이스를 구현하는 클래스는 고정입니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-131">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="6942e-132">예를 들어, 다음과 같은 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-132">For example, consider the following code.</span></span>  
  
```csharp  
// The interface is covariant.  
ICovariant<Button> ibutton = new SampleImplementation<Button>();  
ICovariant<Object> iobj = ibutton;  
  
// The class is invariant.  
SampleImplementation<Button> button = new SampleImplementation<Button>();  
// The following statement generates a compiler error  
// because classes are invariant.  
// SampleImplementation<Object> obj = button;  
```  
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="6942e-133">Variant 제네릭 인터페이스 확장</span><span class="sxs-lookup"><span data-stu-id="6942e-133">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="6942e-134">Variant 제네릭 인터페이스를 확장할 경우 `in` 및 `out` 키워드를 사용하여 파생 인터페이스가 가변성을 지원하는지 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-134">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="6942e-135">컴파일러에서는 확장되고 있는 인터페이스에서 가변성을 유추하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-135">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="6942e-136">예를 들어 다음 인터페이스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-136">For example, consider the following interfaces.</span></span>  
  
```csharp  
interface ICovariant<out T> { }  
interface IInvariant<T> : ICovariant<T> { }  
interface IExtCovariant<out T> : ICovariant<T> { }  
```  
  
 <span data-ttu-id="6942e-137">두 인터페이스가 모두 같은 인터페이스를 확장하더라도 `IInvariant<T>` 인터페이스에서 제네릭 형식 매개 변수 `T`는 고정이지만, `IExtCovariant<out T>`에서 형식 매개 변수는 공변(covariant)입니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-137">In the `IInvariant<T>` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant<out T>` the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="6942e-138">반공변(contravariant) 제네릭 형식 매개 변수에는 같은 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-138">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="6942e-139">제네릭 형식 매개 변수 `T`가 공변(covariant)인 인터페이스 및 확장 인터페이스에서 제네릭 형식 매개 변수 `T`가 고정인 경우 반공변(contravariant)인 인터페이스를 둘 다 확장하는 인터페이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-139">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="6942e-140">다음 코드 예제에서 이 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-140">This is illustrated in the following code example.</span></span>  
  
```csharp  
interface ICovariant<out T> { }  
interface IContravariant<in T> { }  
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }  
```  
  
 <span data-ttu-id="6942e-141">그러나 한 인터페이스에서 제네릭 형식 매개 변수 `T`가 공변(covariant)으로 선언되면 확장 인터페이스에서는 이 매개 변수를 반공변(contravariant)으로 선언할 수 없고, 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-141">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="6942e-142">다음 코드 예제에서 이 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-142">This is illustrated in the following code example.</span></span>  
  
```csharp  
interface ICovariant<out T> { }  
// The following statement generates a compiler error.  
// interface ICoContraVariant<in T> : ICovariant<T> { }  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="6942e-143">모호성 방지</span><span class="sxs-lookup"><span data-stu-id="6942e-143">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="6942e-144">Variant 제네릭 인터페이스를 구현할 경우 가변성으로 인해 모호성이 나타나는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-144">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="6942e-145">이러한 경우가 발생해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-145">This should be avoided.</span></span>  
  
 <span data-ttu-id="6942e-146">예를 들어 서로 다른 제네릭 형식 매개 변수가 포함된 같은 Variant 제네릭 인터페이스를 한 클래스에서 명시적으로 구현하면 모호성이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-146">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="6942e-147">컴파일러에서는 이 경우 오류를 생성하지 않지만 런타임에 선택될 인터페이스 구현이 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-147">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="6942e-148">이로 인해 코드에서 미묘한 버그가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-148">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="6942e-149">다음 코드 예제를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-149">Consider the following code example.</span></span>  
  
```csharp  
// Simple class hierarchy.  
class Animal { }  
class Cat : Animal { }  
class Dog : Animal { }  
  
// This class introduces ambiguity  
// because IEnumerable<out T> is covariant.  
class Pets : IEnumerable<Cat>, IEnumerable<Dog>  
{  
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()  
    {  
        Console.WriteLine("Cat");  
        // Some code.  
        return null;  
    }  
  
    IEnumerator IEnumerable.GetEnumerator()  
    {  
        // Some code.  
        return null;  
    }  
  
    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()  
    {  
        Console.WriteLine("Dog");  
        // Some code.  
        return null;  
    }  
}  
class Program  
{  
    public static void Test()  
    {  
        IEnumerable<Animal> pets = new Pets();  
        pets.GetEnumerator();  
    }  
}  
```  
  
 <span data-ttu-id="6942e-150">이 예제에서는 `pets.GetEnumerator` 메서드가 `Cat` 및 `Dog` 중에 선택하는 방법이 지정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-150">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="6942e-151">이로 인해 코드에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6942e-151">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6942e-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6942e-152">See Also</span></span>  
 <span data-ttu-id="6942e-153">[제네릭 인터페이스의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="6942e-153">[Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
 [<span data-ttu-id="6942e-154">Func 및 Action 제네릭 대리자에 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="6942e-154">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)

