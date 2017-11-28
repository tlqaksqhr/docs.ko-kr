---
title: "방법: LINQ를 사용하여 ArrayList 쿼리(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2bfb471c-6e9a-4e60-bd83-4a1778abde11
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fe1426bb77f4e958abda83814632e61ee9ce415c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-query-an-arraylist-with-linq-c"></a><span data-ttu-id="fcd5b-102">방법: LINQ를 사용하여 ArrayList 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="fcd5b-102">How to: Query an ArrayList with LINQ (C#)</span></span>
<span data-ttu-id="fcd5b-103">LINQ를 사용하여 <xref:System.Collections.ArrayList> 등의 제네릭이 아닌 <xref:System.Collections.IEnumerable> 컬렉션을 쿼리하는 경우 컬렉션에 있는 개체의 특정 형식을 반영하도록 범위 변수의 형식을 명시적으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-103">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="fcd5b-104">예를 들어 `Student` 개체의 <xref:System.Collections.ArrayList>가 있는 경우 [from 절](../../../../csharp/language-reference/keywords/from-clause.md)은 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-104">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [from clause](../../../../csharp/language-reference/keywords/from-clause.md) should look like this:</span></span>  
  
```  
var query = from Student s in arrList  
...  
```  
  
 <span data-ttu-id="fcd5b-105">범위 변수의 형식을 지정하여 <xref:System.Collections.ArrayList>의 각 항목을 `Student`로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-105">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="fcd5b-106">명시적 형식 범위 변수를 쿼리 식에 사용하는 것은 <xref:System.Linq.Enumerable.Cast%2A> 메서드 호출과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-106">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="fcd5b-107">지정된 캐스트를 수행할 수 없는 경우 <xref:System.Linq.Enumerable.Cast%2A>에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-107"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="fcd5b-108"><xref:System.Linq.Enumerable.Cast%2A> 및 <xref:System.Linq.Enumerable.OfType%2A>은 제네릭이 아닌 <xref:System.Collections.IEnumerable> 형식에서 작동하는 두 가지 표준 쿼리 연산자 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-108"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="fcd5b-109">자세한 내용은 [LINQ 쿼리 작업의 형식 관계](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-109">For more information, see[Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcd5b-110">예제</span><span class="sxs-lookup"><span data-stu-id="fcd5b-110">Example</span></span>  
 <span data-ttu-id="fcd5b-111">다음 예제에서는 <xref:System.Collections.ArrayList>에 대한 단순 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-111">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="fcd5b-112">이 예제에서는 코드가 <xref:System.Collections.ArrayList.Add%2A> 메서드를 호출할 때 개체 이니셜라이저를 사용하지만 요구 사항은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fcd5b-112">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Linq;  
  
namespace NonGenericLINQ  
{  
    public class Student  
    {  
        public string FirstName { get; set; }  
        public string LastName { get; set; }  
        public int[] Scores { get; set; }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ArrayList arrList = new ArrayList();  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Svetlana", LastName = "Omelchenko", Scores = new int[] { 98, 92, 81, 60 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Claire", LastName = "O’Donnell", Scores = new int[] { 75, 84, 91, 39 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Sven", LastName = "Mortensen", Scores = new int[] { 88, 94, 65, 91 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Cesar", LastName = "Garcia", Scores = new int[] { 97, 89, 85, 82 }  
                    });  
  
            var query = from Student student in arrList  
                        where student.Scores[0] > 95  
                        select student;  
  
            foreach (Student s in query)  
                Console.WriteLine(s.LastName + ": " + s.Scores[0]);  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
}  
/* Output:   
    Omelchenko: 98  
    Garcia: 97  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcd5b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcd5b-113">See Also</span></span>  
 [<span data-ttu-id="fcd5b-114">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="fcd5b-114">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
