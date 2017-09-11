---
title: "방법: 지정된 단어 집합이 들어 있는 문장 쿼리(LINQ)(C#)"
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
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
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
ms.openlocfilehash: 8bc90e9919d620127c305c9a2c857968e2c799af
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a><span data-ttu-id="229d9-102">방법: 지정된 단어 집합이 들어 있는 문장 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="229d9-102">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (C#)</span></span>
<span data-ttu-id="229d9-103">이 예제에서는 지정된 각 단어 집합과 일치하는 항목이 포함된 문장을 텍스트 파일에서 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-103">This example shows how to find sentences in a text file that contain matches for each of a specified set of words.</span></span> <span data-ttu-id="229d9-104">이 예제에서는 검색어 배열이 하드 코드되어 있지만 런타임에 동적으로 채워질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-104">Although the array of search terms is hard-coded in this example, it could also be populated dynamically at runtime.</span></span> <span data-ttu-id="229d9-105">이 예제에서 쿼리는 "Historically", "data" 및 "integrated" 단어가 포함된 문장을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-105">In this example, the query returns the sentences that contain the words "Historically," "data," and "integrated."</span></span>  
  
## <a name="example"></a><span data-ttu-id="229d9-106">예제</span><span class="sxs-lookup"><span data-stu-id="229d9-106">Example</span></span>  
  
```csharp  
class FindSentences  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects " +  
        @"have not been well integrated. Programmers work in C# or Visual Basic " +  
        @"and also in SQL or XQuery. On the one side are concepts such as classes, " +  
        @"objects, fields, inheritance, and .NET Framework APIs. On the other side " +  
        @"are tables, columns, rows, nodes, and separate languages for dealing with " +  
        @"them. Data types often require translation between the two worlds; there are " +  
        @"different standard functions. Because the object world has no notion of query, a " +  
        @"query can only be represented as a string without compile-time type checking or " +  
        @"IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " +  
        @"objects in memory is often tedious and error-prone.";  
  
        // Split the text block into an array of sentences.  
        string[] sentences = text.Split(new char[] { '.', '?', '!' });  
  
        // Define the search terms. This list could also be dynamically populated at runtime.  
        string[] wordsToMatch = { "Historically", "data", "integrated" };  
  
        // Find sentences that contain all the terms in the wordsToMatch array.  
        // Note that the number of terms to match is not specified at compile time.  
        var sentenceQuery = from sentence in sentences  
                            let w = sentence.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' },  
                                                    StringSplitOptions.RemoveEmptyEntries)  
                            where w.Distinct().Intersect(wordsToMatch).Count() == wordsToMatch.Count()  
                            select sentence;  
  
        // Execute the query. Note that you can explicitly type  
        // the iteration variable here even though sentenceQuery  
        // was implicitly typed.   
        foreach (string str in sentenceQuery)  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
Historically, the world of data and the world of objects have not been well integrated  
*/  
```  
  
 <span data-ttu-id="229d9-107">쿼리에서는 먼저 텍스트를 문장으로 분할한 다음 문장을 각 단어가 포함된 문자열 배열로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-107">The query works by first splitting the text into sentences, and then splitting the sentences into an array of strings that hold each word.</span></span> <span data-ttu-id="229d9-108">각 배열에 대해 <xref:System.Linq.Enumerable.Distinct%2A> 메서드가 모든 중복 단어를 제거한 다음 쿼리가 단어 배열 및 `wordsToMatch` 배열에 대해 <xref:System.Linq.Enumerable.Intersect%2A> 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-108">For each of these arrays, the <xref:System.Linq.Enumerable.Distinct%2A> method removes all duplicate words, and then the query performs an <xref:System.Linq.Enumerable.Intersect%2A> operation on the word array and the `wordsToMatch` array.</span></span> <span data-ttu-id="229d9-109">교집합의 개수가 `wordsToMatch` 배열의 개수와 같으면 단어에서 모든 단어가 발견된 것이며 원래 문장이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-109">If the count of the intersection is the same as the count of the `wordsToMatch` array, all words were found in the words and the original sentence is returned.</span></span>  
  
 <span data-ttu-id="229d9-110"><xref:System.String.Split%2A> 호출에서는 문자열의 구분 기호를 제거하기 위해 문장 부호가 구분 기호로 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-110">In the call to <xref:System.String.Split%2A>, the punctuation marks are used as separators in order to remove them from the string.</span></span> <span data-ttu-id="229d9-111">이렇게 하지 않았다면, 예를 들어 `wordsToMatch` 배열의 "Historically"와 일치하지 않는 "Historically," 문자열이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-111">If you did not do this, for example you could have a string "Historically," that would not match "Historically" in the `wordsToMatch` array.</span></span> <span data-ttu-id="229d9-112">소스 텍스트에서 찾은 문장 부호 유형에 따라 추가 구분 기호를 사용해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-112">You may have to use additional separators, depending on the types of punctuation found in the source text.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="229d9-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="229d9-113">Compiling the Code</span></span>  
 <span data-ttu-id="229d9-114">System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="229d9-114">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="229d9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="229d9-115">See Also</span></span>  
 [<span data-ttu-id="229d9-116">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="229d9-116">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)

