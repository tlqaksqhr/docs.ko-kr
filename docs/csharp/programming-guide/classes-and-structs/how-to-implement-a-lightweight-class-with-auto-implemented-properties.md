---
title: '방법: 자동으로 구현된 속성을 사용하여 간단한 클래스 구현(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: 9612ec916481776691e85a84503ce5063c20b099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321524"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="4b17d-102">방법: 자동으로 구현된 속성을 사용하여 간단한 클래스 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4b17d-102">How to: Implement a Lightweight Class with Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="4b17d-103">이 예제에서는 자동 구현 속성 집합을 캡슐화하는 데만 사용되는 변경할 수 없는 간단한 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-103">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="4b17d-104">참조 형식 의미 체계를 사용해야 하는 경우 구조체 대신 이러한 종류의 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-104">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>  
  
 <span data-ttu-id="4b17d-105">변경할 수 없는 속성은 두 가지 방법으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-105">You can make an immutable property in two ways.</span></span>  <span data-ttu-id="4b17d-106">[set](../../../csharp/language-reference/keywords/set.md) 접근자를 [private](../../../csharp/language-reference/keywords/private.md)로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-106">You can declare the [set](../../../csharp/language-reference/keywords/set.md) accessor.to be [private](../../../csharp/language-reference/keywords/private.md).</span></span>  <span data-ttu-id="4b17d-107">속성은 형식 내에서만 설정할 수 있고 소비자는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-107">The property is only settable within the type, but it is immutable to consumers.</span></span>  <span data-ttu-id="4b17d-108">또는 [get](../../../csharp/language-reference/keywords/get.md) 접근자만 선언하여 형식의 생성자를 제외한 어떤 위치에서도 속성을 변경할 수 없도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-108">You can instead declare only the [get](../../../csharp/language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type’s constructor.</span></span>  
  
 <span data-ttu-id="4b17d-109">private `set` 접근자를 선언하는 경우 개체 이니셜라이저를 사용하여 속성을 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-109">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="4b17d-110">생성자나 팩터리 메서드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-110">You must use a constructor or a factory method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b17d-111">예</span><span class="sxs-lookup"><span data-stu-id="4b17d-111">Example</span></span>  
 <span data-ttu-id="4b17d-112">다음 예제에서는 자동 구현 속성을 갖는 변경할 수 없는 클래스를 구현하는 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-112">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="4b17d-113">각 방법에서 속성 중 하나는 private `set`으로 선언하고 다른 하나는 `get`으로만 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-113">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="4b17d-114">첫 번째 클래스는 생성자만 사용하여 속성을 초기화하고 두 번째 클래스는 생성자를 호출하는 정적 팩터리 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-114">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>  
  
```csharp  
// This class is immutable. After an object is created,   
    // it cannot be modified from outside the class. It uses a   
    // constructor to initialize its properties.   
    class Contact  
    {  
        // Read-only properties.   
        public string Name { get; }  
        public string Address { get; private set; }  
  
        // Public constructor.   
        public Contact(string contactName, string contactAddress)  
        {  
            Name = contactName;  
            Address = contactAddress;                 
        }  
    }  
  
    // This class is immutable. After an object is created,   
    // it cannot be modified from outside the class. It uses a   
    // static method and private constructor to initialize its properties.      
    public class Contact2  
    {  
        // Read-only properties.   
        public string Name { get; private set; }  
        public string Address { get; }  
  
        // Private constructor.   
        private Contact2(string contactName, string contactAddress)  
        {  
            Name = contactName;  
            Address = contactAddress;                 
        }  
  
        // Public factory method.   
        public static Contact2 CreateContact(string name, string address)  
        {  
            return new Contact2(name, address);  
        }  
    }  
  
    public class Program  
    {   
        static void Main()  
        {  
            // Some simple data sources.   
            string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",   
                              "Cesar Garcia", "Debra Garcia"};  
            string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",  
                                  "12 108th St.", "89 E. 42nd St."};  
  
            // Simple query to demonstrate object creation in select clause.   
            // Create Contact objects by using a constructor.   
            var query1 = from i in Enumerable.Range(0, 5)  
                        select new Contact(names[i], addresses[i]);  
  
            // List elements cannot be modified by client code.   
            var list = query1.ToList();  
            foreach (var contact in list)  
            {  
                Console.WriteLine("{0}, {1}", contact.Name, contact.Address);  
            }  
  
            // Create Contact2 objects by using a static factory method.   
            var query2 = from i in Enumerable.Range(0, 5)  
                         select Contact2.CreateContact(names[i], addresses[i]);  
  
            // Console output is identical to query1.   
            var list2 = query2.ToList();  
  
            // List elements cannot be modified by client code.   
            // CS0272:   
            // list2[0].Name = "Eugene Zabokritski";   
  
            // Keep the console open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();                  
        }  
    }  
  
/* Output:  
    Terry Adams, 123 Main St.  
    Fadi Fakhouri, 345 Cypress Ave.  
    Hanying Feng, 678 1st Ave  
    Cesar Garcia, 12 108th St.  
    Debra Garcia, 89 E. 42nd St.  
*/  
```  
  
 <span data-ttu-id="4b17d-115">컴파일러는 각 자동 구현 속성에 대해 지원 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-115">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="4b17d-116">이 필드는 소스 코드에서 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b17d-116">The fields are not accessible directly from source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b17d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b17d-117">See Also</span></span>  
 [<span data-ttu-id="4b17d-118">속성</span><span class="sxs-lookup"><span data-stu-id="4b17d-118">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="4b17d-119">struct</span><span class="sxs-lookup"><span data-stu-id="4b17d-119">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
 [<span data-ttu-id="4b17d-120">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="4b17d-120">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
