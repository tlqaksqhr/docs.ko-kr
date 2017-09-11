---
title: "제네릭 컬렉션용 인터페이스의 가변성 사용(C#)"
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
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
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
ms.openlocfilehash: 5d505b566fe604afdedea583dc8c001f80c15d3c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a><span data-ttu-id="767b9-102">제네릭 컬렉션용 인터페이스의 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="767b9-102">Using Variance in Interfaces for Generic Collections (C#)</span></span>
<span data-ttu-id="767b9-103">공변(covariant) 인터페이스는 메서드가 인터페이스에 지정된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="767b9-104">반공변(contravariant) 인터페이스는 메서드가 인터페이스에 지정된 것보다 더 적은 파생된 형식의 매개 변수를 수락하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="767b9-105">.NET Framework 4에서는 몇 가지 기존 인터페이스가 공변(covariant) 및 반공변(contravariant)이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="767b9-106">여기에는 <xref:System.Collections.Generic.IEnumerable%601> 및 <xref:System.IComparable%601>이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="767b9-107">따라서 파생된 형식의 컬렉션에 대한 기본 형식의 제네릭 컬렉션과 함께 작동하는 메서드를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="767b9-108">.NET Framework의 variant 인터페이스 목록은 [제네릭 인터페이스의 가변성(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="767b9-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="767b9-109">제네릭 컬렉션 변환</span><span class="sxs-lookup"><span data-stu-id="767b9-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="767b9-110">다음 예제에서는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 공변성(Covariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="767b9-111">`PrintFullName` 메서드는 `IEnumerable<Person>` 형식의 컬렉션을 매개 변수로 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-111">The `PrintFullName` method accepts a collection of the `IEnumerable<Person>` type as a parameter.</span></span> <span data-ttu-id="767b9-112">그러나 `Employee`는 `Person`을 상속하므로 `IEnumerable<Employee>` 형식의 컬렉션에 대해 이를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-112">However, you can reuse it for a collection of the `IEnumerable<Employee>` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,   
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a><span data-ttu-id="767b9-113">제네릭 컬렉션 비교</span><span class="sxs-lookup"><span data-stu-id="767b9-113">Comparing Generic Collections</span></span>  
 <span data-ttu-id="767b9-114">다음 예제에서는 <xref:System.Collections.Generic.IComparer%601> 인터페이스에서 반공변성(Contravariance) 지원의 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-114">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="767b9-115">`PersonComparer` 클래스는 `IComparer<Person>` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-115">The `PersonComparer` class implements the `IComparer<Person>` interface.</span></span> <span data-ttu-id="767b9-116">그러나 `Employee`는 `Person`을 상속하므로 `Employee` 형식 개체의 시퀀스를 비교하기 위해 이 클래스를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="767b9-116">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {              
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;              
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,   
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="767b9-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="767b9-117">See Also</span></span>  
 [<span data-ttu-id="767b9-118">제네릭 인터페이스의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="767b9-118">Variance in Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)

