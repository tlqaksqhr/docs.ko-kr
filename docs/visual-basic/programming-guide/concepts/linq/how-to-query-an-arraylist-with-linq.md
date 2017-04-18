---
title: "방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리 | Microsoft 문서"
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
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
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
ms.openlocfilehash: f48b06c23b1e28fccb953638954a8d9afefe574e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a>방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리
제네릭이 아닌 쿼리를 LINQ를 사용 하는 경우 <xref:System.Collections.IEnumerable>와 같은 컬렉션 <xref:System.Collections.ArrayList>, 컬렉션에 있는 개체의 특정 유형을 반영 하도록 범위 변수의 형식을 명시적으로 선언 해야 합니다.</xref:System.Collections.ArrayList> </xref:System.Collections.IEnumerable> 예를 들어 한 <xref:System.Collections.ArrayList>의 `Student` 개체를 프로그램 [From 절이](../../../../visual-basic/language-reference/queries/from-clause.md) 다음과 같아야 합니다:</xref:System.Collections.ArrayList>  
  
```  
  
Dim query = From student As Student In arrList   
...  
  
```  
  
 범위 변수의 종류를 지정 하 여 각 항목에 캐스팅할는 <xref:System.Collections.ArrayList>에 `Student`.</xref:System.Collections.ArrayList>  
  
 쿼리 식에 명시적으로 형식화 된 범위 변수의 사용 하는 것은 <xref:System.Linq.Enumerable.Cast%2A>메서드.</xref:System.Linq.Enumerable.Cast%2A> <xref:System.Linq.Enumerable.Cast%2A>지정된 된 캐스트를 수행할 수 없는 경우 예외를 throw 합니다.</xref:System.Linq.Enumerable.Cast%2A> <xref:System.Linq.Enumerable.Cast%2A>및 <xref:System.Linq.Enumerable.OfType%2A>제네릭이 아닌에서 작동 하는 두 개의 표준 쿼리 연산자 메서드가 <xref:System.Collections.IEnumerable>형식.</xref:System.Collections.IEnumerable> </xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.Cast%2A> Visual Basic의 경우 명시적으로 호출 해야는 <xref:System.Linq.Enumerable.Cast%2A>특정 범위 변수 형식을 확인 하는 데이터 원본에 대해 메서드.</xref:System.Linq.Enumerable.Cast%2A> 자세한 내용은 참조[쿼리 작업 (Visual Basic)의 형식 관계](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Collections.ArrayList>.</xref:System.Collections.ArrayList> 따라 간단한 쿼리를 보여 줍니다. 참고 코드를 호출 하는 경우이 예제에서는 개체 이니셜라이저를 사용 하 여 <xref:System.Collections.ArrayList.Add%2A>방법 이지만이 필요는 없습니다.</xref:System.Collections.ArrayList.Add%2A>  
  
```vb  
Imports System.Collections  
Imports System.Linq  
  
Module Module1  
  
    Public Class Student  
        Public Property FirstName As String  
        Public Property LastName As String  
        Public Property Scores As Integer()  
    End Class  
  
    Sub Main()  
  
        Dim student1 As New Student With {.FirstName = "Svetlana",   
                                     .LastName = "Omelchenko",   
                                     .Scores = New Integer() {98, 92, 81, 60}}  
        Dim student2 As New Student With {.FirstName = "Claire",   
                                    .LastName = "O'Donnell",   
                                    .Scores = New Integer() {75, 84, 91, 39}}  
        Dim student3 As New Student With {.FirstName = "Cesar",   
                                    .LastName = "Garcia",   
                                    .Scores = New Integer() {97, 89, 85, 82}}  
        Dim student4 As New Student With {.FirstName = "Sven",   
                                    .LastName = "Mortensen",   
                                    .Scores = New Integer() {88, 94, 65, 91}}  
  
        Dim arrList As New ArrayList()  
        arrList.Add(student1)  
        arrList.Add(student2)  
        arrList.Add(student3)  
        arrList.Add(student4)  
  
        ' Use an explicit type for non-generic collections  
        Dim query = From student As Student In arrList   
                    Where student.Scores(0) > 95   
                    Select student  
  
        For Each student As Student In query  
            Console.WriteLine(student.LastName & ": " & student.Scores(0))  
        Next  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Module  
' Output:  
'   Omelchenko: 98  
'   Garcia: 97  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
