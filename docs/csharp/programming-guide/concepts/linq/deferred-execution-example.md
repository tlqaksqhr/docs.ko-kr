---
title: 지연된 실행 예제(C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 8613f2335e5b3cb2a012f5309307e081b9400709
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335928"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="fc20c-102">지연된 실행 예제(C#)</span><span class="sxs-lookup"><span data-stu-id="fc20c-102">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="fc20c-103">이 항목에서는 지연된 실행과 지연 계산이 LINQ to XML 쿼리의 실행에 미치는 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc20c-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc20c-104">예</span><span class="sxs-lookup"><span data-stu-id="fc20c-104">Example</span></span>  
 <span data-ttu-id="fc20c-105">다음 예제에서는 지연된 실행을 사용하는 확장 메서드를 사용하는 경우의 실행 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc20c-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="fc20c-106">이 예제에서는 세 문자열의 배열을 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="fc20c-106">The example declares an array of three strings.</span></span> <span data-ttu-id="fc20c-107">`ConvertCollectionToUpperCase`에서 반환하는 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fc20c-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="fc20c-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fc20c-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="fc20c-109">`ConvertCollectionToUpperCase`에서 반환하는 컬렉션을 반복할 때 각 항목이 소스 문자열 배열에서 검색되어 대문자로 변환된 후 다음 항목이 소스 문자열 배열에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc20c-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="fc20c-110">반환된 컬렉션의 각 항목이 `foreach`의 `Main` 루프에서 처리되기 전에는 문자열의 전체 배열이 대문자로 변환되지 않는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc20c-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="fc20c-111">이 자습서의 다음 항목에서는 쿼리를 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc20c-111">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
-   [<span data-ttu-id="fc20c-112">연결 쿼리 예제(C#)</span><span class="sxs-lookup"><span data-stu-id="fc20c-112">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc20c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc20c-113">See Also</span></span>  
 [<span data-ttu-id="fc20c-114">자습서: 여러 쿼리 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="fc20c-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
