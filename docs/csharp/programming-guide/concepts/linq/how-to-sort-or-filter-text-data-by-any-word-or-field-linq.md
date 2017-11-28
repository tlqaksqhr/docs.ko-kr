---
title: "방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ccc48745918081663317e746953be6e0f09cdd8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a><span data-ttu-id="7726e-102">방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="7726e-102">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>
<span data-ttu-id="7726e-103">다음 예제에서는 줄의 필드를 기준으로 쉼표로 구분된 값 등의 구조적 텍스트 줄을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7726e-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="7726e-104">필드가 런타임에 동적으로 지정될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7726e-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="7726e-105">scores.csv의 필드가 학생의 ID 번호와 일련의 시험 성적 4개를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7726e-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>  
  
### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="7726e-106">데이터가 포함된 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7726e-106">To create a file that contains data</span></span>  
  
1.  <span data-ttu-id="7726e-107">[방법: 서로 다른 파일의 콘텐츠 조인(LINQ)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) 항목에서 scores.csv 데이터를 복사하여 솔루션 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7726e-107">Copy the scores.csv data from the topic [How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7726e-108">예제</span><span class="sxs-lookup"><span data-stu-id="7726e-108">Example</span></span>  
  
```csharp  
public class SortLines  
{  
    static void Main()  
    {  
        // Create an IEnumerable data source  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Change this to any value from 0 to 4.  
        int sortField = 1;  
  
        Console.WriteLine("Sorted highest to lowest by field [{0}]:", sortField);  
  
        // Demonstrates how to return query from a method.  
        // The query is executed here.  
        foreach (string str in RunQuery(scores, sortField))  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Returns the query variable, not query results!  
    static IEnumerable<string> RunQuery(IEnumerable<string> source, int num)  
    {  
        // Split the string and sort on field[num]  
        var scoreQuery = from line in source  
                         let fields = line.Split(',')  
                         orderby fields[num] descending  
                         select line;  
  
        return scoreQuery;  
    }  
}  
/* Output (if sortField == 1):  
   Sorted highest to lowest by field [1]:  
    116, 99, 86, 90, 94  
    120, 99, 82, 81, 79  
    111, 97, 92, 81, 60  
    114, 97, 89, 85, 82  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    113, 88, 94, 65, 91  
    112, 75, 84, 91, 39  
    119, 68, 79, 88, 92  
    115, 35, 72, 91, 70  
 */  
```  
  
 <span data-ttu-id="7726e-109">이 예제에서는 메서드에서 쿼리 변수를 반환하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7726e-109">This example also demonstrates how to return a query variable from a method.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7726e-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7726e-110">Compiling the Code</span></span>  
 <span data-ttu-id="7726e-111">System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7726e-111">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7726e-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7726e-112">See Also</span></span>  
 [<span data-ttu-id="7726e-113">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="7726e-113">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
