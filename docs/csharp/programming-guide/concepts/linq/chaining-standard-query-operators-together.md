---
title: "여러 표준 쿼리 연산자 연결(C#)"
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
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40c65c80c08caa310cb72a194534ad63fcea890a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="9d1d4-102">여러 표준 쿼리 연산자 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="9d1d4-102">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="9d1d4-103">이 항목은 [자습서: 쿼리 연결(C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) 자습서의 마지막 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-103">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) tutorial.</span></span>  
  
 <span data-ttu-id="9d1d4-104">표준 쿼리 연산자도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-104">The standard query operators can also be chained together.</span></span> <span data-ttu-id="9d1d4-105">예를 들어, <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> 연산자를 삽입할 수 있으며 이 연산자는 지연 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-105">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="9d1d4-106">이 연산자는 중간 결과를 유형화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-106">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d1d4-107">예제</span><span class="sxs-lookup"><span data-stu-id="9d1d4-107">Example</span></span>  
 <span data-ttu-id="9d1d4-108">이 예제에서 <xref:System.Linq.Enumerable.Where%2A> 메서드는 `ConvertCollectionToUpperCase`를 호출하기 전에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-108">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="9d1d4-109"><xref:System.Linq.Enumerable.Where%2A> 메서드는 이 자습서의 이전 예제에서 사용되는 지연 메서드인 `ConvertCollectionToUpperCase` 및 `AppendString`과 거의 똑같은 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-109">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="9d1d4-110">한 가지 차이점은 이 경우에 <xref:System.Linq.Enumerable.Where%2A> 메서드는 소스 컬렉션을 반복하고 첫 번째 항목이 조건자를 통과하지 않는 것을 확인한 다음 조건자를 통과하는 다음 항목을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-110">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="9d1d4-111">그런 다음 두 번째 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-111">It then yields the second item.</span></span>  
  
 <span data-ttu-id="9d1d4-112">그러나 기본 개념은 동일합니다. 중간 컬렉션이 유형화될 필요가 없으면 유형화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-112">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="9d1d4-113">쿼리 식이 사용되는 경우 쿼리 식은 표준 쿼리 연산자에 대한 호출로 변환되고 동일한 원칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-113">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="9d1d4-114">Office Open XML 문서를 쿼리하는 이 단원의 모든 예제에서는 동일한 원칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-114">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="9d1d4-115">지연된 실행과 지연 계산은 LINQ와 LINQ to XML을 효과적으로 사용하기 위해 이해해야 하는 기본 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-115">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
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
            where s.CompareTo("D") >= 0  
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
  
 <span data-ttu-id="9d1d4-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9d1d4-116">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d1d4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d1d4-117">See Also</span></span>  
 [<span data-ttu-id="9d1d4-118">자습서: 여러 쿼리 연결(C#)</span><span class="sxs-lookup"><span data-stu-id="9d1d4-118">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)

