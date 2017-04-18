---
title: "방법: 지정된 된 단어 (LINQ) (Visual Basic) 집합이 들어 있는 문장 쿼리 | Microsoft 문서"
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
ms.assetid: a5ae8ced-61fe-4c10-bb8a-95630e50f603
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31561d586c9c05f502002efdfc455acb55159fed
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-visual-basic"></a>방법: 지정된 단어 집합이 들어 있는 문장 쿼리(LINQ)(Visual Basic)
이 예제에는 각 단어의 지정된 된 집합에 대 한 일치 항목을 포함 하는 텍스트 파일에 문장을 찾는 방법을 보여 줍니다. 이 예에서 하드 코드 된 검색어의 배열 이지만 것 채울 수도 동적으로 런타임에 합니다. 이 예제에서는 쿼리에서 반환 문장을 "지금" 단어가 포함 된 "데이터" 및 "통합"입니다.  
  
## <a name="example"></a>예제  
  
```vb  
Class FindSentences  
  
    Shared Sub Main()  
        Dim text As String = "Historically, the world of data and the world of objects " &   
        "have not been well integrated. Programmers work in C# or Visual Basic " &   
        "and also in SQL or XQuery. On the one side are concepts such as classes, " &   
        "objects, fields, inheritance, and .NET Framework APIs. On the other side " &   
        "are tables, columns, rows, nodes, and separate languages for dealing with " &   
        "them. Data types often require translation between the two worlds; there are " &   
        "different standard functions. Because the object world has no notion of query, a " &   
        "query can only be represented as a string without compile-time type checking or " &   
        "IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " &   
        "objects in memory is often tedious and error-prone."  
  
        ' Split the text block into an array of sentences.  
        Dim sentences As String() = text.Split(New Char() {".", "?", "!"})  
  
        ' Define the search terms. This list could also be dynamically populated at runtime  
        Dim wordsToMatch As String() = {"Historically", "data", "integrated"}  
  
        ' Find sentences that contain all the terms in the wordsToMatch array  
        ' Note that the number of terms to match is not specified at compile time  
        Dim sentenceQuery = From sentence In sentences   
                            Let w = sentence.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                   StringSplitOptions.RemoveEmptyEntries)   
                            Where w.Distinct().Intersect(wordsToMatch).Count = wordsToMatch.Count()   
                            Select sentence  
  
        ' Execute the query  
        For Each str As String In sentenceQuery  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Class  
' Output:  
' Historically, the world of data and the world of objects have not been well integrated  
```  
  
 쿼리는 먼저 문장을 분할할 분할 한 다음 문장의 각 단어를 포함 하는 문자열의 배열에 의해 작동 합니다. 이러한 배열 각각에 대 한는 <xref:System.Linq.Enumerable.Distinct%2A>메서드는 모든 중복 단어를 제거 하 고 다음 쿼리를 수행는 <xref:System.Linq.Enumerable.Intersect%2A>단어 배열에서 작업 및 `wordsToMatch` 배열.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Distinct%2A> 경우 교차로의 개수는 수와 동일 하 게는 `wordsToMatch` 배열 하는 모든 단어는 단어에서 찾은 및 원래 문장이 반환 됩니다.  
  
 에 대 한 호출에서 <xref:System.String.Split%2A>, 문장 부호는 문자열에서 제거 하기 위해 구분 기호로 사용 됩니다.</xref:System.String.Split%2A> 예를 들어 문자열 "지금" 있을 수 있습니다이 수행 하지 않은 경우는 일치 하지 않습니다 "지금"에 `wordsToMatch` 배열입니다. 소스 텍스트에서 찾은 문장 부호의 유형에 따라 추가 구분 기호를 사용 해야 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
