---
title: "방법: (LINQ) (Visual Basic) 문자열에서 단어가 나오는 횟수 세기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5697e52729287a09f1afe993c7b1c1d0c9a6507b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a><span data-ttu-id="6082d-102">방법: 문자열 (LINQ) (Visual Basic)에서 단어 수 계산</span><span class="sxs-lookup"><span data-stu-id="6082d-102">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="6082d-103">이 예제에서는 LINQ 쿼리는 문자열에서 지정 된 단어의 개수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6082d-103">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="6082d-104">먼저 계산을 수행 하는 <xref:System.String.Split%2A>메서드는 단어의 배열을 만듭니다.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="6082d-104">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="6082d-105">에 성능 비용이 <xref:System.String.Split%2A>메서드.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="6082d-105">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="6082d-106">사용을 고려해 야 작업만 문자열에서 단어 수를 계산 하려는 경우는 <xref:System.Text.RegularExpressions.Regex.Matches%2A>또는 <xref:System.String.IndexOf%2A>메서드 대신.</xref:System.String.IndexOf%2A> </xref:System.Text.RegularExpressions.Regex.Matches%2A></span><span class="sxs-lookup"><span data-stu-id="6082d-106">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="6082d-107">그러나 성능이 중요 한 문제가 없거나 문장 위로 다른 유형의 쿼리를 수행 하기 위해 이미 분할 하는 경우 다음 편이 LINQ를 사용 하 여 단어 또는 구를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="6082d-107">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6082d-108">예제</span><span class="sxs-lookup"><span data-stu-id="6082d-108">Example</span></span>  
  
```vb  
Class CountWords  
  
    Shared Sub Main()  
  
        Dim text As String = "Historically, the world of data and the world of objects" &   
                  " have not been well integrated. Programmers work in C# or Visual Basic" &   
                  " and also in SQL or XQuery. On the one side are concepts such as classes," &   
                  " objects, fields, inheritance, and .NET Framework APIs. On the other side" &   
                  " are tables, columns, rows, nodes, and separate languages for dealing with" &   
                  " them. Data types often require translation between the two worlds; there are" &   
                  " different standard functions. Because the object world has no notion of query, a" &   
                  " query can only be represented as a string without compile-time type checking or" &   
                  " IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" &   
                  " objects in memory is often tedious and error-prone."  
  
        Dim searchTerm As String = "data"  
  
        ' Convert the string into an array of words.  
        Dim dataSource As String() = text.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                 StringSplitOptions.RemoveEmptyEntries)  
  
        ' Create and execute the query. It executes immediately   
        ' because a singleton value is produced.  
        ' Use ToLower to match "data" and "Data"   
        Dim matchQuery = From word In dataSource   
                      Where word.ToLowerInvariant() = searchTerm.ToLowerInvariant()   
                      Select word  
  
        ' Count the matches.  
        Dim count As Integer = matchQuery.Count()  
        Console.WriteLine(count & " occurrence(s) of the search term """ &   
                          searchTerm & """ were found.")  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' 3 occurrence(s) of the search term "data" were found.  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6082d-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6082d-109">Compiling the Code</span></span>  
 <span data-ttu-id="6082d-110">.NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` 는 System.Linq 네임 스페이스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="6082d-110">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6082d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6082d-111">See Also</span></span>  
 [<span data-ttu-id="6082d-112">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6082d-112">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
