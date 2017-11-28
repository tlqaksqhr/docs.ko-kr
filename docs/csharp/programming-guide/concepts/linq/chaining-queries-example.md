---
title: "연결 쿼리 예제(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 74d3dcaca686487d79a90f28faf4d9c00218f6a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="45a36-102">연결 쿼리 예제(C#)</span><span class="sxs-lookup"><span data-stu-id="45a36-102">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="45a36-103">이 예제에서는 이전 예제를 기반으로 하며 지연된 실행과 지연 계산을 모두 사용하는 두 쿼리를 연결할 때 발생하는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-103">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45a36-104">예제</span><span class="sxs-lookup"><span data-stu-id="45a36-104">Example</span></span>  
 <span data-ttu-id="45a36-105">이 예제에는 지정된 문자열을 소스 컬렉션의 모든 문자열에 추가한 다음 새 문자열을 생성하는 `AppendString` 확장 메서드가 추가로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-105">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
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
        foreach (string str in source)  
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
  
 <span data-ttu-id="45a36-106">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-106">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="45a36-107">이 예제에서 각 확장 메서드가 소스 컬렉션의 항목마다 한 번씩 작동하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-107">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="45a36-108">이 예제에서 알아 두어야 할 점은 컬렉션을 생성하는 쿼리를 연결했지만 중간 컬렉션이 구체화되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-108">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="45a36-109">대신 각 항목이 한 지연 메서드에서 다음 지연 메서드로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-109">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="45a36-110">이렇게 하면 먼저 문자열 배열을 하나 가져온 다음 대문자로 변환된 두 번째 문자열 배열을 만들고 마지막으로 각 문자열 끝에 느낌표가 추가된 세 번째 문자열 배열을 만드는 방법보다 훨씬 적은 메모리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-110">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="45a36-111">이 자습서의 다음 항목에서는 중간 구체화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45a36-111">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
-   [<span data-ttu-id="45a36-112">중간 구체화(C#)</span><span class="sxs-lookup"><span data-stu-id="45a36-112">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="45a36-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45a36-113">See Also</span></span>  
 [<span data-ttu-id="45a36-114">자습서: 여러 쿼리 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="45a36-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
