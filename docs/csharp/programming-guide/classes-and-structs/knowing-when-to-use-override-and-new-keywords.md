---
title: "Override 및 New 키워드를 사용해야 하는 경우(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- override keyword [C#]
- new keyword [C#]
- polymorphism [C#], using override and new [C#]
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b4d53f16f046839d56bc1dc37f7b2d8816c5956f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="knowing-when-to-use-override-and-new-keywords-c-programming-guide"></a><span data-ttu-id="05673-102">Override 및 New 키워드를 사용해야 하는 경우(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="05673-102">Knowing When to Use Override and New Keywords (C# Programming Guide)</span></span>
<span data-ttu-id="05673-103">C#에서는 파생 클래스의 메서드가 기본 클래스의 메서드와 동일한 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-103">In C#, a method in a derived class can have the same name as a method in the base class.</span></span> <span data-ttu-id="05673-104">[new](../../../csharp/language-reference/keywords/new.md) 및 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 메서드가 상호 작용하는 방식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-104">You can specify how the methods interact by using the [new](../../../csharp/language-reference/keywords/new.md) and [override](../../../csharp/language-reference/keywords/override.md) keywords.</span></span> <span data-ttu-id="05673-105">`override` 한정자는 기본 클래스 메서드를 *확장*하고, `new` 한정자는 기본 클래스 메서드를 *숨깁니다*.</span><span class="sxs-lookup"><span data-stu-id="05673-105">The `override` modifier *extends* the base class method, and the `new` modifier *hides* it.</span></span> <span data-ttu-id="05673-106">이 항목의 예제에서는 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05673-106">The difference is illustrated in the examples in this topic.</span></span>  
  
 <span data-ttu-id="05673-107">콘솔 응용 프로그램에서 `BaseClass` 및 `DerivedClass`라는 두 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-107">In a console application, declare the following two classes, `BaseClass` and `DerivedClass`.</span></span> <span data-ttu-id="05673-108">`DerivedClass`는 `BaseClass`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-108">`DerivedClass` inherits from `BaseClass`.</span></span>  
  
```csharp  
class BaseClass  
{  
    public void Method1()  
    {  
        Console.WriteLine("Base - Method1");  
    }  
}  
  
class DerivedClass : BaseClass  
{  
    public void Method2()  
    {  
        Console.WriteLine("Derived - Method2");  
    }  
}  
```  
  
 <span data-ttu-id="05673-109">`Main` 메서드에서 `bc`, `dc` 및 `bcdc` 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-109">In the `Main` method, declare variables `bc`, `dc`, and `bcdc`.</span></span>  
  
-   <span data-ttu-id="05673-110">`bc`는 `BaseClass` 형식이고, 해당 값은 `BaseClass` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05673-110">`bc` is of type `BaseClass`, and its value is of type `BaseClass`.</span></span>  
  
-   <span data-ttu-id="05673-111">`dc`는 `DerivedClass` 형식이고, 해당 값은 `DerivedClass` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05673-111">`dc` is of type `DerivedClass`, and its value is of type `DerivedClass`.</span></span>  
  
-   <span data-ttu-id="05673-112">`bcdc`는 `BaseClass` 형식이고, 해당 값은 `DerivedClass` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05673-112">`bcdc` is of type `BaseClass`, and its value is of type `DerivedClass`.</span></span> <span data-ttu-id="05673-113">이 변수에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-113">This is the variable to pay attention to.</span></span>  
  
 <span data-ttu-id="05673-114">`bc` 및 `bcdc`는 `BaseClass` 형식이기 때문에 캐스팅을 사용하지 않는 경우 `Method1`에 직접 액세스할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-114">Because `bc` and `bcdc` have type `BaseClass`, they can only directly access `Method1`, unless you use casting.</span></span> <span data-ttu-id="05673-115">`dc` 변수는 `Method1` 및 `Method2` 둘 다에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-115">Variable `dc` can access both `Method1` and `Method2`.</span></span> <span data-ttu-id="05673-116">이러한 관계는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-116">These relationships are shown in the following code.</span></span>  
  
```csharp  
class Program  
{  
    static void Main(string[] args)  
    {  
        BaseClass bc = new BaseClass();  
        DerivedClass dc = new DerivedClass();  
        BaseClass bcdc = new DerivedClass();  
  
        bc.Method1();  
        dc.Method1();  
        dc.Method2();  
        bcdc.Method1();  
    }  
    // Output:  
    // Base - Method1  
    // Base - Method1  
    // Derived - Method2  
    // Base - Method1  
}  
```  
  
 <span data-ttu-id="05673-117">다음 `Method2` 메서드를 `BaseClass`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-117">Next, add the following `Method2` method to `BaseClass`.</span></span> <span data-ttu-id="05673-118">이 메서드의 시그니처는 `DerivedClass`에 있는 `Method2` 메서드의 시그니처와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-118">The signature of this method matches the signature of the `Method2` method in `DerivedClass`.</span></span>  
  
```csharp  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
```  
  
 <span data-ttu-id="05673-119">이제 `BaseClass`에 `Method2` 메서드가 있으므로 다음 코드와 같이 `BaseClass` 변수 `bc` 및 `bcdc`에 대해 두 번째 호출 문을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-119">Because `BaseClass` now has a `Method2` method, a second calling statement can be added for `BaseClass` variables `bc` and `bcdc`, as shown in the following code.</span></span>  
  
```csharp  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
```  
  
 <span data-ttu-id="05673-120">프로젝트를 빌드할 때 `BaseClass`에 `Method2` 메서드를 추가하면 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-120">When you build the project, you see that the addition of the `Method2` method in `BaseClass` causes a warning.</span></span> <span data-ttu-id="05673-121">`DerivedClass`의 `Method2` 메서드가 `BaseClass`의 `Method2` 메서드를 숨긴다는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-121">The warning says that the `Method2` method in `DerivedClass` hides the `Method2` method in `BaseClass`.</span></span> <span data-ttu-id="05673-122">이러한 결과를 원한다면 `Method2` 정의에 `new` 키워드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-122">You are advised to use the `new` keyword in the `Method2` definition if you intend to cause that result.</span></span> <span data-ttu-id="05673-123">또는 `Method2` 메서드 중 하나의 이름을 바꿔 경고를 해결할 수 있지만 이 방법이 항상 실현 가능한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="05673-123">Alternatively, you could rename one of the `Method2` methods to resolve the warning, but that is not always practical.</span></span>  
  
 <span data-ttu-id="05673-124">`new`를 추가하기 전에 프로그램을 실행하여 추가 호출 문에서 생성되는 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-124">Before adding `new`, run the program to see the output produced by the additional calling statements.</span></span> <span data-ttu-id="05673-125">다음과 같은 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-125">The following results are displayed.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="05673-126">`new` 키워드는 해당 출력을 생성하는 관계를 유지하지만 경고는 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-126">The `new` keyword preserves the relationships that produce that output, but it suppresses the warning.</span></span> <span data-ttu-id="05673-127">`BaseClass` 형식인 변수는 계속해서 `BaseClass`의 멤버에 액세스하고, `DerivedClass` 형식인 변수는 계속해서 `DerivedClass`의 멤버에 먼저 액세스한 다음 `BaseClass`에서 상속된 멤버를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-127">The variables that have type `BaseClass` continue to access the members of `BaseClass`, and the variable that has type `DerivedClass` continues to access members in `DerivedClass` first, and then to consider members inherited from `BaseClass`.</span></span>  
  
 <span data-ttu-id="05673-128">경고를 표시하지 않으려면 다음 코드와 같이 `DerivedClass`에 있는 `Method2`의 정의에 `new` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-128">To suppress the warning, add the `new` modifier to the definition of `Method2` in `DerivedClass`, as shown in the following code.</span></span> <span data-ttu-id="05673-129">`public` 앞이나 뒤에 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-129">The modifier can be added before or after `public`.</span></span>  
  
```csharp  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
```  
  
 <span data-ttu-id="05673-130">프로그램을 다시 실행하여 출력이 변경되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-130">Run the program again to verify that the output has not changed.</span></span> <span data-ttu-id="05673-131">또한 경고가 더 이상 나타나지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-131">Also verify that the warning no longer appears.</span></span> <span data-ttu-id="05673-132">`new`를 사용하면 수정하는 멤버가 기본 클래스에서 상속된 멤버를 숨김을 인식하고 있다고 어설션하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="05673-132">By using `new`, you are asserting that you are aware that the member that it modifies hides a member that is inherited from the base class.</span></span> <span data-ttu-id="05673-133">상속을 통한 이름 숨기기에 대한 자세한 내용은 [new 한정자](../../../csharp/language-reference/keywords/new-modifier.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05673-133">For more information about name hiding through inheritance, see [new Modifier](../../../csharp/language-reference/keywords/new-modifier.md).</span></span>  
  
 <span data-ttu-id="05673-134">이 동작을 `override`를 사용할 경우의 효과와 비교하려면 다음 메서드를 `DerivedClass`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-134">To contrast this behavior to the effects of using `override`, add the following method to `DerivedClass`.</span></span> <span data-ttu-id="05673-135">`public` 앞이나 뒤에 `override` 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-135">The `override` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
```  
  
 <span data-ttu-id="05673-136">`BaseClass`에 있는 `Method1`의 정의에 `virtual` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-136">Add the `virtual` modifier to the definition of `Method1` in `BaseClass`.</span></span> <span data-ttu-id="05673-137">`public` 앞이나 뒤에 `virtual` 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-137">The `virtual` modifier can be added before or after `public`.</span></span>  
  
```csharp  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
```  
  
 <span data-ttu-id="05673-138">프로젝트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-138">Run the project again.</span></span> <span data-ttu-id="05673-139">특히 다음 출력의 마지막 두 줄을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-139">Notice especially the last two lines of the following output.</span></span>  
  
```csharp  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
```  
  
 <span data-ttu-id="05673-140">`override` 한정자를 사용하면 `bcdc`가 `DerivedClass`에 정의된 `Method1` 메서드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-140">The use of the `override` modifier enables `bcdc` to access the `Method1` method that is defined in `DerivedClass`.</span></span> <span data-ttu-id="05673-141">일반적으로 이는 상속 계층 구조에서 원하는 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="05673-141">Typically, that is the desired behavior in inheritance hierarchies.</span></span> <span data-ttu-id="05673-142">파생 클래스에서 생성된 값을 가진 개체에 파생 클래스에서 정의된 메서드를 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-142">You want objects that have values that are created from the derived class to use the methods that are defined in the derived class.</span></span> <span data-ttu-id="05673-143">이 동작을 위해 `override`를 사용하여 기본 클래스 메서드를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-143">You achieve that behavior by using `override` to extend the base class method.</span></span>  
  
 <span data-ttu-id="05673-144">다음 코드에는 전체 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-144">The following code contains the full example.</span></span>  
  
```csharp  
using System;  
using System.Text;  
  
namespace OverrideAndNew  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            BaseClass bc = new BaseClass();  
            DerivedClass dc = new DerivedClass();  
            BaseClass bcdc = new DerivedClass();  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in BaseClass.  
            bc.Method1();  
            bc.Method2();  
            // Output:  
            // Base - Method1  
            // Base - Method2  
  
            // The following two calls do what you would expect. They call  
            // the methods that are defined in DerivedClass.  
            dc.Method1();  
            dc.Method2();  
            // Output:  
            // Derived - Method1  
            // Derived - Method2  
  
            // The following two calls produce different results, depending   
            // on whether override (Method1) or new (Method2) is used.  
            bcdc.Method1();  
            bcdc.Method2();  
            // Output:  
            // Derived - Method1  
            // Base - Method2  
        }  
    }  
  
    class BaseClass  
    {  
        public virtual void Method1()  
        {  
            Console.WriteLine("Base - Method1");  
        }  
  
        public virtual void Method2()  
        {  
            Console.WriteLine("Base - Method2");  
        }  
    }  
  
    class DerivedClass : BaseClass  
    {  
        public override void Method1()  
        {  
            Console.WriteLine("Derived - Method1");  
        }  
  
        public new void Method2()  
        {  
            Console.WriteLine("Derived - Method2");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="05673-145">다음 예제에서는 다른 컨텍스트의 비슷한 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05673-145">The following example illustrates similar behavior in a different context.</span></span> <span data-ttu-id="05673-146">이 예제에서는 `Car`라는 기본 클래스 하나와 이 클래스에서 파생된 두 클래스 `ConvertibleCar` 및 `Minivan`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-146">The example defines three classes: a base class named `Car` and two classes that are derived from it, `ConvertibleCar` and `Minivan`.</span></span> <span data-ttu-id="05673-147">기본 클래스에는 `DescribeCar` 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-147">The base class contains a `DescribeCar` method.</span></span> <span data-ttu-id="05673-148">이 메서드는 자동차에 대한 기본 설명을 표시한 다음 `ShowDetails`를 호출하여 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-148">The method displays a basic description of a car, and then calls `ShowDetails` to provide additional information.</span></span> <span data-ttu-id="05673-149">세 클래스는 각각 `ShowDetails` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-149">Each of the three classes defines a `ShowDetails` method.</span></span> <span data-ttu-id="05673-150">`new` 한정자는 `ConvertibleCar` 클래스의 `ShowDetails`를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-150">The `new` modifier is used to define `ShowDetails` in the `ConvertibleCar` class.</span></span> <span data-ttu-id="05673-151">`override` 한정자는 `Minivan` 클래스의 `ShowDetails`를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-151">The `override` modifier is used to define `ShowDetails` in the `Minivan` class.</span></span>  
  
```csharp  
// Define the base class, Car. The class defines two methods,  
// DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
// class also defines a ShowDetails method. The example tests which version of  
// ShowDetails is selected, the base class method or the derived class method.  
class Car  
{  
    public void DescribeCar()  
    {  
        System.Console.WriteLine("Four wheels and an engine.");  
        ShowDetails();  
    }  
  
    public virtual void ShowDetails()  
    {  
        System.Console.WriteLine("Standard transportation.");  
    }  
}  
  
// Define the derived classes.  
  
// Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
// hides the base class method.  
class ConvertibleCar : Car  
{  
    public new void ShowDetails()  
    {  
        System.Console.WriteLine("A roof that opens up.");  
    }  
}  
  
// Class Minivan uses the override modifier to specify that ShowDetails  
// extends the base class method.  
class Minivan : Car  
{  
    public override void ShowDetails()  
    {  
        System.Console.WriteLine("Carries seven people.");  
    }  
}  
```  
  
 <span data-ttu-id="05673-152">예제에서는 호출되는 `ShowDetails` 버전을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-152">The example tests which version of `ShowDetails` is called.</span></span> <span data-ttu-id="05673-153">다음 메서드 `TestCars1`은 각 클래스의 인스턴스를 선언한 다음 각 인스턴스에서 `DescribeCar`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-153">The following method, `TestCars1`, declares an instance of each class, and then calls `DescribeCar` on each instance.</span></span>  
  
```csharp  
public static void TestCars1()  
{  
    System.Console.WriteLine("\nTestCars1");  
    System.Console.WriteLine("----------");  
  
    Car car1 = new Car();  
    car1.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    // Notice the output from this test case. The new modifier is  
    // used in the definition of ShowDetails in the ConvertibleCar  
    // class.    
  
    ConvertibleCar car2 = new ConvertibleCar();  
    car2.DescribeCar();  
    System.Console.WriteLine("----------");  
  
    Minivan car3 = new Minivan();  
    car3.DescribeCar();  
    System.Console.WriteLine("----------");  
}  
```  
  
 <span data-ttu-id="05673-154">`TestCars1`은 다음 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-154">`TestCars1` produces the following output.</span></span> <span data-ttu-id="05673-155">특히 예상과 다를 수 있는 `car2`의 결과를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-155">Notice especially the results for `car2`, which probably are not what you expected.</span></span> <span data-ttu-id="05673-156">개체 형식은 `ConvertibleCar`이지만 `DescribeCar`는 `ConvertibleCar` 클래스에 정의된 `ShowDetails` 버전에 액세스하지 않습니다. 해당 메서드는 `override` 한정자가 아니라 `new` 한정자로 선언되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="05673-156">The type of the object is `ConvertibleCar`, but `DescribeCar` does not access the version of `ShowDetails` that is defined in the `ConvertibleCar` class because that method is declared with the `new` modifier, not the `override` modifier.</span></span> <span data-ttu-id="05673-157">결과적으로 `ConvertibleCar` 개체는 `Car` 개체와 동일한 설명을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-157">As a result, a `ConvertibleCar` object displays the same description as a `Car` object.</span></span> <span data-ttu-id="05673-158">`Minivan` 개체인 `car3`의 결과와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-158">Contrast the results for `car3`, which is a `Minivan` object.</span></span> <span data-ttu-id="05673-159">이 경우 `Minivan` 클래스에서 선언된 `ShowDetails` 메서드가 `Car` 클래스에서 선언된 `ShowDetails` 메서드를 재정의하고, 표시되는 설명은 미니밴에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-159">In this case, the `ShowDetails` method that is declared in the `Minivan` class overrides the `ShowDetails` method that is declared in the `Car` class, and the description that is displayed describes a minivan.</span></span>  
  
```csharp  
// TestCars1  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="05673-160">`TestCars2`는 `Car` 형식인 개체 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05673-160">`TestCars2` creates a list of objects that have type `Car`.</span></span> <span data-ttu-id="05673-161">개체의 값은 `Car`, `ConvertibleCar` 및 `Minivan` 클래스에서 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-161">The values of the objects are instantiated from the `Car`, `ConvertibleCar`, and `Minivan` classes.</span></span> <span data-ttu-id="05673-162">목록의 각 요소에 대해 `DescribeCar`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-162">`DescribeCar` is called on each element of the list.</span></span> <span data-ttu-id="05673-163">다음 코드에서는 `TestCars2`의 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05673-163">The following code shows the definition of `TestCars2`.</span></span>  
  
```csharp  
public static void TestCars2()  
{  
    System.Console.WriteLine("\nTestCars2");  
    System.Console.WriteLine("----------");  
  
    var cars = new List<Car> { new Car(), new ConvertibleCar(),   
        new Minivan() };  
  
    foreach (var car in cars)  
    {  
        car.DescribeCar();  
        System.Console.WriteLine("----------");  
    }  
}  
```  
  
 <span data-ttu-id="05673-164">다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05673-164">The following output is displayed.</span></span> <span data-ttu-id="05673-165">이 출력은 `TestCars1`이 표시하는 출력과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-165">Notice that it is the same as the output that is displayed by `TestCars1`.</span></span> <span data-ttu-id="05673-166">개체의 형식이 `ConvertibleCar`(`TestCars1`) 또는 `Car`(`TestCars2`)이든 관계없이 `ConvertibleCar` 클래스의 `ShowDetails` 메서드는 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05673-166">The `ShowDetails` method of the `ConvertibleCar` class is not called, regardless of whether the type of the object is `ConvertibleCar`, as in `TestCars1`, or `Car`, as in `TestCars2`.</span></span> <span data-ttu-id="05673-167">한편, `car3`은 `Minivan` 형식 또는 `Car` 형식이든 관계없이 두 경우 모두 `Minivan` 클래스에서 `ShowDetails` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-167">Conversely, `car3` calls the `ShowDetails` method from the `Minivan` class in both cases, whether it has type `Minivan` or type `Car`.</span></span>  
  
```csharp  
// TestCars2  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Standard transportation.  
// ----------  
// Four wheels and an engine.  
// Carries seven people.  
// ----------  
```  
  
 <span data-ttu-id="05673-168">`TestCars3` 및 `TestCars4` 메서드가 예제를 완성합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-168">Methods `TestCars3` and `TestCars4` complete the example.</span></span> <span data-ttu-id="05673-169">이러한 메서드는 `ConvertibleCar` 및 `Minivan`(`TestCars3`) 형식으로 선언된 개체와 `Car`(`TestCars4`) 형식으로 선언된 개체에서 차례로 `ShowDetails`를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-169">These methods call `ShowDetails` directly, first from objects declared to have type `ConvertibleCar` and `Minivan` (`TestCars3`), then from objects declared to have type `Car` (`TestCars4`).</span></span> <span data-ttu-id="05673-170">다음 코드에서는 이러한 두 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-170">The following code defines these two methods.</span></span>  
  
```csharp  
public static void TestCars3()  
{  
    System.Console.WriteLine("\nTestCars3");  
    System.Console.WriteLine("----------");  
    ConvertibleCar car2 = new ConvertibleCar();  
    Minivan car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
  
public static void TestCars4()  
{  
    System.Console.WriteLine("\nTestCars4");  
    System.Console.WriteLine("----------");  
    Car car2 = new ConvertibleCar();  
    Car car3 = new Minivan();  
    car2.ShowDetails();  
    car3.ShowDetails();  
}  
```  
  
 <span data-ttu-id="05673-171">메서드는 이 항목에 있는 첫 번째 예제의 결과에 해당하는 다음 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="05673-171">The methods produce the following output, which corresponds to the results from the first example in this topic.</span></span>  
  
```csharp  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
```  
  
 <span data-ttu-id="05673-172">다음 코드에서는 전체 프로젝트와 해당 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05673-172">The following code shows the complete project and its output.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
namespace OverrideAndNew2  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Declare objects of the derived classes and test which version  
            // of ShowDetails is run, base or derived.  
            TestCars1();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars2();  
  
            // Declare objects of the derived classes and call ShowDetails  
            // directly.  
            TestCars3();  
  
            // Declare objects of the base class, instantiated with the  
            // derived classes, and repeat the tests.  
            TestCars4();  
        }  
  
        public static void TestCars1()  
        {  
            System.Console.WriteLine("\nTestCars1");  
            System.Console.WriteLine("----------");  
  
            Car car1 = new Car();  
            car1.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            // Notice the output from this test case. The new modifier is  
            // used in the definition of ShowDetails in the ConvertibleCar  
            // class.    
            ConvertibleCar car2 = new ConvertibleCar();  
            car2.DescribeCar();  
            System.Console.WriteLine("----------");  
  
            Minivan car3 = new Minivan();  
            car3.DescribeCar();  
            System.Console.WriteLine("----------");  
        }  
        // Output:  
        // TestCars1  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars2()  
        {  
            System.Console.WriteLine("\nTestCars2");  
            System.Console.WriteLine("----------");  
  
            var cars = new List<Car> { new Car(), new ConvertibleCar(),   
                new Minivan() };  
  
            foreach (var car in cars)  
            {  
                car.DescribeCar();  
                System.Console.WriteLine("----------");  
            }  
        }  
        // Output:  
        // TestCars2  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Standard transportation.  
        // ----------  
        // Four wheels and an engine.  
        // Carries seven people.  
        // ----------  
  
        public static void TestCars3()  
        {  
            System.Console.WriteLine("\nTestCars3");  
            System.Console.WriteLine("----------");  
            ConvertibleCar car2 = new ConvertibleCar();  
            Minivan car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars3  
        // ----------  
        // A roof that opens up.  
        // Carries seven people.  
  
        public static void TestCars4()  
        {  
            System.Console.WriteLine("\nTestCars4");  
            System.Console.WriteLine("----------");  
            Car car2 = new ConvertibleCar();  
            Car car3 = new Minivan();  
            car2.ShowDetails();  
            car3.ShowDetails();  
        }  
        // Output:  
        // TestCars4  
        // ----------  
        // Standard transportation.  
        // Carries seven people.  
    }  
  
    // Define the base class, Car. The class defines two virtual methods,  
    // DescribeCar and ShowDetails. DescribeCar calls ShowDetails, and each derived  
    // class also defines a ShowDetails method. The example tests which version of  
    // ShowDetails is used, the base class method or the derived class method.  
    class Car  
    {  
        public virtual void DescribeCar()  
        {  
            System.Console.WriteLine("Four wheels and an engine.");  
            ShowDetails();  
        }  
  
        public virtual void ShowDetails()  
        {  
            System.Console.WriteLine("Standard transportation.");  
        }  
    }  
  
    // Define the derived classes.  
  
    // Class ConvertibleCar uses the new modifier to acknowledge that ShowDetails  
    // hides the base class method.  
    class ConvertibleCar : Car  
    {  
        public new void ShowDetails()  
        {  
            System.Console.WriteLine("A roof that opens up.");  
        }  
    }  
  
    // Class Minivan uses the override modifier to specify that ShowDetails  
    // extends the base class method.  
    class Minivan : Car  
    {  
        public override void ShowDetails()  
        {  
            System.Console.WriteLine("Carries seven people.");  
        }  
    }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="05673-173">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05673-173">See Also</span></span>  
 [<span data-ttu-id="05673-174">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="05673-174">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="05673-175">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="05673-175">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="05673-176">Override 및 New 키워드를 사용하여 버전 관리</span><span class="sxs-lookup"><span data-stu-id="05673-176">Versioning with the Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)  
 [<span data-ttu-id="05673-177">base</span><span class="sxs-lookup"><span data-stu-id="05673-177">base</span></span>](../../../csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="05673-178">abstract</span><span class="sxs-lookup"><span data-stu-id="05673-178">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)
