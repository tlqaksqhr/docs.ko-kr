---
title: '방법: 문자열의 문자 쿼리(LINQ)(C#)'
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: db535f55822fa40d8589ddf95f9f78adfa1b6f1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="04f12-102">방법: 문자열의 문자 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="04f12-102">How to: Query for Characters in a String (LINQ) (C#)</span></span>
<span data-ttu-id="04f12-103"><xref:System.String> 클래스는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하기 때문에 모든 문자열을 문자 시퀀스로 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04f12-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="04f12-104">그러나 LINQ는 일반적으로 이 용도로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04f12-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="04f12-105">복잡한 패턴 일치 작업의 경우 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04f12-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04f12-106">예</span><span class="sxs-lookup"><span data-stu-id="04f12-106">Example</span></span>  
 <span data-ttu-id="04f12-107">다음 예제에서는 문자열을 쿼리하여 문자열에 포함된 숫자 자릿수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="04f12-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="04f12-108">쿼리가 처음 실행된 후 "다시 사용"됩니다.</span><span class="sxs-lookup"><span data-stu-id="04f12-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="04f12-109">이 작업은 쿼리 자체가 실제 결과를 저장하지 않기 때문에 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="04f12-109">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="04f12-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="04f12-110">Compiling the Code</span></span>  
 <span data-ttu-id="04f12-111">System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04f12-111">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f12-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04f12-112">See Also</span></span>  
 [<span data-ttu-id="04f12-113">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="04f12-113">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="04f12-114">방법: LINQ 쿼리와 정규식 결합(C#)</span><span class="sxs-lookup"><span data-stu-id="04f12-114">How to: Combine LINQ Queries with Regular Expressions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
