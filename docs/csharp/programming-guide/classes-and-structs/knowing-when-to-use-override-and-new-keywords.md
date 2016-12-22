---
title: "Override 및 New 키워드를 사용해야 하는 경우(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new 키워드[C#]"
  - "override 키워드[C#]"
  - "다형성[C#], override 및 new 사용[C#]"
ms.assetid: 323db184-b136-46fc-8839-007886e7e8b0
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Override 및 New 키워드를 사용해야 하는 경우(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

C\#에서 파생 클래스의 메서드는 기본 클래스의 메서드와 같은 이름을 가질 수 있습니다.  [new](../../../csharp/language-reference/keywords/new.md) 및 [override](../../../csharp/language-reference/keywords/override.md) 키워드를 사용하여 메서드가 상호 작용하는 방법을 지정할 수 있습니다.  `override` 한정자는 기본 클래스 메서드를 *확장*하며, `new` 한정자는 그것을 *숨깁니다*.  차이는 이 항목의 예제에 설명되어 있습니다.  
  
 콘솔 응용 프로그램에서 `BaseClass` 및 `DerivedClass`, 두 클래스를 선언합니다.  `DerivedClass`는 `BaseClass`에서 상속됩니다.  
  
```c#  
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
  
 `Main` 메서드에서 `bc`, `dc` 및 `bcdc` 변수를 선언합니다.  
  
-   `bc`가 `BaseClass` 형식이고 그 값이 `BaseClass`인 경우  
  
-   `dc`가 `DerivedClass` 형식이고 그 값이 `DerivedClass`인 경우  
  
-   `bcdc`가 `BaseClass` 형식이고 그 값이 `DerivedClass`인 경우  이것은 주목해야 하는 변수입니다.  
  
 `bc` 및 `bcdc`에 `BaseClass` 형식이 있으므로 캐스팅을 사용하지 않는 한 `Method1`에만 직접 액세스할 수 있습니다.   `dc` 변수는 `Method1` 및 `Method2`에 액세스할 수 있습니다.  이러한 관계는 다음 코드에서 볼 수 있습니다.  
  
```c#  
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
  
 그런 후에, 다음 `Method2` 메서드를 `BaseClass`에 추가합니다.  이 메서드의 서명이 `DerivedClass`의 `Method2` 메서드의 서명과 일치합니다.  
  
```c#  
public void Method2()  
{  
    Console.WriteLine("Base - Method2");  
}  
  
```  
  
 `BaseClass`에는 이제 `Method2` 메서드가 있기 때문에 두 번째 호출 문은 다음 코드에 표시된 것처럼 `BaseClass` 변수 `bc` 및 `bcdc`에 추가할 수 있습니다.  
  
```c#  
bc.Method1();  
bc.Method2();  
dc.Method1();  
dc.Method2();  
bcdc.Method1();  
bcdc.Method2();  
  
```  
  
 프로젝트를 빌드할 때 볼의 추가 `BaseClass`에 `Method2` 메서드를 추가하면 경고가 발생하는 것을 확인하게 됩니다.  경고에 `DerivedClass`의 `Method2` 메서드가 `BaseClass`의 `Method2` 메서드를 숨긴다고 나와 있습니다.  그러한 결과를 얻으려면 `Method2` 정의에서 `new` 키워드를 사용하는 것이 좋습니다.  또한 `Method2` 메서드 중 하나를 이름 변경하여 경고를 해결하지만 항상 실용적인 것은 아닙니다.  
  
 `new`를 추가하기 전에 추가 호출 문에서 생성되는 출력을 볼 수 있는 프로그램을 실행합니다.  다음과 같은 결과가 표시됩니다.  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Base - Method1  
// Derived - Method2  
// Base - Method1  
// Base - Method2  
  
```  
  
 `new` 키워드는 해당 출력을 만드는 관계를 유지하지만 경고를 억제합니다.  `BaseClass` 형식의 변수는 `BaseClass`의 멤버에 지속적으로 액세스하며 `DerivedClass` 형식의 변수는 우선 `DerivedClass`의 멤버에 액세스한 후 `BaseClass`에서 상속된 멤버를 고려합니다.  
  
 경고를 표시하지 않으려면 다음 코드에 표시된 대로 `new` 한정자를 `DerivedClass`에서 `Method2`의 정의로 추가합니다.  `public` 앞 또는 뒤에 한정자를 추가할 수 있습니다.  
  
```c#  
public new void Method2()  
{  
    Console.WriteLine("Derived - Method2");  
}  
  
```  
  
 출력이 변경되지 않은 것을 확인하기 위해 프로그램을 다시 실행합니다.  경고가 더 이상 나타나는지 않는지도 확인합니다.  `new`를 사용함으로써 수정하는 구성원이 기본 클래스에서 상속된 구성원을 숨기는 것을 인식하고 있음을 어설션하는 것입니다.  상속을 통한 이름 숨기기에 대한 자세한 내용은 [new 한정자](../../../csharp/language-reference/keywords/new-modifier.md)를 참조하십시오.  
  
 이 동작을 `override`를 사용하는 경우의 효과와 비교하려면 다음 메서드를 `DerivedClass`에 추가합니다.  `public` 전에 또는 후에 `override` 한정자를 추가할 수 있습니다.  
  
```c#  
public override void Method1()  
{  
    Console.WriteLine("Derived - Method1");  
}  
  
```  
  
 `BaseClass`의 `Method1` 정의에 `virtual` 한정자를 추가합니다.  `public` 전에 또는 후에 `virtual` 한정자를 추가할 수 있습니다.  
  
```c#  
public virtual void Method1()  
{  
    Console.WriteLine("Base - Method1");  
}  
  
```  
  
 프로젝트를 다시 실행합니다.  특히 다음 출력의 마지막 두 줄을 주목하십시오.  
  
```c#  
// Output:  
// Base - Method1  
// Base - Method2  
// Derived - Method1  
// Derived - Method2  
// Derived - Method1  
// Base - Method2  
  
```  
  
 `override` 한정자는 `bcdc`를 통해 `DerivedClass`에 정의되어 있는 `Method1` 메서드에 액세스할 수 있습니다.  일반적으로 상속 계층 구조에서 원하는 동작입니다.  파생 클래스에서 정의되는 메서드를 사용하도록 파생 클래스에서 생성되는 값을 가진 개체를 사용합니다.  `override`를 사용하여 기본 클래스 메서드를 확장하는 동작을 달성합니다.  
  
 다음 코드에는 전체 예제가 포함되어 있습니다.  
  
```c#  
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
  
 다음 예제는 다른 컨텍스트에서의 비슷한 동작을 보여 줍니다.  다음 예제에서는 `Car`라는 기본 클래스 하나와 `ConvertibleCar` 및 `Minivan`에서 파생되는 두 개의 클래스를 정의합니다.  기본 클래스에는 `DescribeCar` 메서드가 포함되어 있습니다.  메서드가 자동차에 대한 기본적 설명을 표시한 다음 `ShowDetails`를 호출하여 추가 정보를 제공합니다.  각 클래스 3개는 `ShowDetails` 메서드를 정의합니다.  `ConvertibleCar` 클래스에 `ShowDetails`을 정의하는 데 `new` 한정자가 사용되었습니다.  `Minivan` 클래스에 `ShowDetails`을 정의하는 데 `override` 한정자가 사용되었습니다.  
  
```c#  
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
  
 이 예제는 어느 버전의 `ShowDetails`가 호출되었는지를 테스트합니다.  다음 메서드 `TestCars1`은 각 클래스의 인스턴스를 선언한 다음 각 인스턴스에 `DescribeCar`를 호출합니다.  
  
```c#  
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
  
 `TestCars1`은 다음과 같은 출력을 생성합니다.  특히 `car2`에 대해 예상과 다르게 나타난 결과에 주목하십시오.  개체의 형식은 `ConvertibleCar`이나 `DescribeCar`는 해당 메서드가 `override` 한정자가 아닌 `new` 한정자와 함께 선언되므로  `ConvertibleCar` 클래스에 정의되어 있는 `ShowDetails` 버전에 액세스할 수 없습니다.  그 결과 `ConvertibleCar` 개체에는 `Car` 개체와 동일한 설명이 표시됩니다.  `Minivan` 개체인 `car3`의 결과와 반대되는 개념입니다.  이 경우 `Minivan` 클래스에 선언된 `ShowDetails` 메서드는 `Car` 클래스에 선언된 `ShowDetails` 메서드를 재정의하고 표시되는 설명에서는 minivan을 설명합니다.  
  
```c#  
  
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
  
 `TestCars2`는 `Car` 형식을 가진 개체 목록을 만듭니다.  개체의 값은 `Car`, `ConvertibleCar` 및 `Minivan` 클래스에서 인스턴스화됩니다.  `DescribeCar`는 목록의 각 요소에서 호출됩니다.  다음 코드에서는 `TestCars2`의 정의를 보여 줍니다.  
  
```c#  
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
  
 다음과 같은 출력이 표시됩니다.  이는 `TestCars1`에서 표시한 결과와 동일하다는 점에 주목하십시오.  `ConvertibleCar` 클래스의 `ShowDetails` 메서드는 개체 형식이 `TestCars1`에서와 같이 `ConvertibleCar`인지, `TestCars2`에서와 같이 `Car`인지 여부에 관계 없이 호출되지 않습니다.  이와는 반대로, `car3`는 형식이 `Minivan` 또는 `Car`인지에 관계 없이 두 경우 모두 `Minivan` 클래스에서 `ShowDetails` 메서드를 호출합니다.  
  
```c#  
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
  
 `TestCars3` 및 `TestCars4` 메서드로 예제를 완료합니다.  이러한 메서드는 먼저 `ConvertibleCar` 및 `Minivan`\(`TestCars3`\) 형식을 가지도록 선언되는 개체에서 시작하여 `Car`\(`TestCars4`\) 형식을 가지도록 선언되는 개체로 `ShowDetails`를 직접 호출합니다.  다음 코드는 이 두 메서드를 정의합니다.  
  
```c#  
  
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
  
 메서드에서 이 항목의 첫 번째 예제의 결과에 해당하는 출력을 생성합니다.  
  
```c#  
// TestCars3  
// ----------  
// A roof that opens up.  
// Carries seven people.  
  
// TestCars4  
// ----------  
// Standard transportation.  
// Carries seven people.  
  
```  
  
 다음 코드에서는 완전한 프로젝트와 그 출력을 보여 줍니다.  
  
```c#  
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
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)   
 [base](../../../csharp/language-reference/keywords/base.md)   
 [abstract](../../../csharp/language-reference/keywords/abstract.md)