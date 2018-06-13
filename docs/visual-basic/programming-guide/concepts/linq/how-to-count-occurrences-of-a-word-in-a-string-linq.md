---
title: '방법: LINQ () (Visual Basic) 문자열에서 단어의 개수'
ms.date: 07/20/2015
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
ms.openlocfilehash: a2e7b59ee1d289fe794fb83705d42ac0e48fb4a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642001"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a>방법: LINQ () (Visual Basic) 문자열에서 단어의 개수
이 예제에서는 LINQ 쿼리를 사용하여 문자열에서 지정된 단어의 발생 수를 계산하는 방법을 보여 줍니다. 계산을 수행하려면 먼저 <xref:System.String.Split%2A> 메서드를 호출하여 단어 배열을 만듭니다. <xref:System.String.Split%2A> 메서드를 사용하는 경우 성능이 저하됩니다. 문자열의 유일한 작업이 단어 개수 계산인 경우 <xref:System.Text.RegularExpressions.Regex.Matches%2A> 또는 <xref:System.String.IndexOf%2A> 메서드를 대신 사용하는 것이 좋습니다. 그러나 성능이 중요한 문제가 아니거나 다른 유형의 쿼리를 수행하기 위해 이미 문장을 분할한 경우 LINQ를 사용하여 단어 또는 구도 계산하는 것이 좋습니다.  
  
## <a name="example"></a>예제  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
 System.Core.dll에 대한 참조와 System.Linq 네임스페이스에 대한 `Imports` 문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
