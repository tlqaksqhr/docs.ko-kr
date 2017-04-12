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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5ec6bb31fa095786f7c507a66e831a90fd1c6e92
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a>방법: 문자열 (LINQ) (Visual Basic)에서 단어 수 계산
이 예제에서는 LINQ 쿼리는 문자열에서 지정 된 단어의 개수를 사용 하는 방법을 보여 줍니다. 먼저 계산을 수행 하는 <xref:System.String.Split%2A>메서드는 단어의 배열을 만듭니다.</xref:System.String.Split%2A> 에 성능 비용이 <xref:System.String.Split%2A>메서드.</xref:System.String.Split%2A> 사용을 고려해 야 작업만 문자열에서 단어 수를 계산 하려는 경우는 <xref:System.Text.RegularExpressions.Regex.Matches%2A>또는 <xref:System.String.IndexOf%2A>메서드 대신.</xref:System.String.IndexOf%2A> </xref:System.Text.RegularExpressions.Regex.Matches%2A> 그러나 성능이 중요 한 문제가 없거나 문장 위로 다른 유형의 쿼리를 수행 하기 위해 이미 분할 하는 경우 다음 편이 LINQ를 사용 하 여 단어 또는 구를 계산 합니다.  
  
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
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` 는 System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
