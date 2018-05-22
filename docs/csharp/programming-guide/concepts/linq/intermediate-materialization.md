---
title: 중간 구체화(C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: b98f9765f5c54a49f26a9d1a3ac351f3eebcf9c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="7f5b5-102">중간 구체화(C#)</span><span class="sxs-lookup"><span data-stu-id="7f5b5-102">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="7f5b5-103">주의하지 않으면 특정한 경우에 쿼리에서 컬렉션을 미리 구체화하여 응용 프로그램의 메모리와 성능 프로필을 크게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-103">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="7f5b5-104">일부 표준 쿼리 연산자는 단일 요소를 생성하기 전에 소스 컬렉션을 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-104">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="7f5b5-105">예를 들어, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType>는 먼저 전체 소스 컬렉션을 반복한 다음 모든 항목을 정렬하고 마지막으로 첫 번째 항목을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-105">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="7f5b5-106">즉, 정렬된 컬렉션의 첫 번째 항목을 가져오는 것은 비용이 많이 들며 그 다음에 나오는 각 항목에는 비용이 많이 들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-106">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="7f5b5-107">해당 쿼리 연산자가 다른 방식으로 작업하는 것은 불가능할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-107">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f5b5-108">예</span><span class="sxs-lookup"><span data-stu-id="7f5b5-108">Example</span></span>  
 <span data-ttu-id="7f5b5-109">이 예제에서는 이전 예제를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-109">This example alters the previous example.</span></span> <span data-ttu-id="7f5b5-110">`AppendString` 메서드는 소스를 반복하기 전에 <xref:System.Linq.Enumerable.ToList%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-110">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="7f5b5-111">이로 인해 구체화가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-111">This causes materialization.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="7f5b5-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-112">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="7f5b5-113">이 예제에서 <xref:System.Linq.Enumerable.ToList%2A>을 호출하면 `AppendString`이 첫 번째 항목을 생성하기 전에 전체 소스를 열거하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-113">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="7f5b5-114">소스가 큰 배열인 경우에는 응용 프로그램의 메모리 프로필이 크게 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-114">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="7f5b5-115">표준 쿼리 연산자도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-115">Standard query operators can also be chained together.</span></span> <span data-ttu-id="7f5b5-116">이 자습서의 최종 항목에서 이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f5b5-116">The final topic in this tutorial illustrates this.</span></span>  
  
-   [<span data-ttu-id="7f5b5-117">여러 표준 쿼리 연산자 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="7f5b5-117">Chaining Standard Query Operators Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="7f5b5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f5b5-118">See Also</span></span>  
 [<span data-ttu-id="7f5b5-119">자습서: 여러 쿼리 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="7f5b5-119">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
