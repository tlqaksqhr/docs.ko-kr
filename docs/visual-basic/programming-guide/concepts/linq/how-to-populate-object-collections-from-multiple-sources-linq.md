---
title: "방법: 여러 소스로 (LINQ) (Visual Basic) 개체 컬렉션 채우기 | Microsoft 문서"
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
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
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
ms.openlocfilehash: 25f504d862ef2176dc90a31fbccf18777b9d3d0a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a>방법: 개체 컬렉션 (Visual Basic) (LINQ) 여러 소스에서 채우기
이 예제에는 새 형식의 시퀀스에 서로 다른 원본의 데이터를 병합 하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  아직 데이터베이스에에서 있는 데이터와 파일 시스템의 메모리 내 데이터 또는 데이터를 조인 하지 마십시오. 이러한 도메인 간 조인은 조인 작업 수 정의 되어 있는 데이터베이스 쿼리 및 다른 유형의 원본에 대 한 다양 한 방법으로 인해 정의 되지 않은 결과 얻을 수 있습니다. 또한 위험이 데이터베이스의 데이터 크기가 충분 하는 경우 이러한 작업이 메모리 부족 예외를 일으킬 수 있습니다. 메모리 내 데이터를 데이터베이스에서 데이터를 결합 하려면 먼저 호출 `ToList` 또는 `ToArray` 데이터베이스에서 쿼리하고 다음 반환된 된 컬렉션에서 조인을 수행 합니다.  
  
### <a name="to-create-the-data-file"></a>데이터 파일을 만들려면  
  
-   에 설명 된 대로 names.csv 및 scores.csv 파일을 프로젝트 폴더로 복사 [하는 방법: 콘텐츠 조인에서 서로 다른 파일 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 명명된 된 형식을 사용 하 여 `Student` .csv 형식으로 스프레드시트 데이터를 시뮬레이션 하는 문자열의 두 가지 메모리 내 컬렉션의 병합 된 데이터를 저장 합니다. 문자열의 첫 번째 컬렉션은 학생 이름과 Id를 나타내고 두 번째 컬렉션의 첫 번째 열에서 학생 ID와&4; 개의 시험 점수를 나타냅니다. ID는 외래 키로 사용 됩니다.  
  
```vb  
Class Student  
    Public FirstName As String  
    Public LastName As String  
    Public ID As Integer  
    Public ExamScores As List(Of Integer)  
End Class  
  
Class PopulateCollection  
  
    Shared Sub Main()  
  
        ' Merge content from spreadsheets into a list of Student objects.  
  
        ' These data files are defined in How to: Join Content from   
        ' Dissimilar Files (LINQ).  
  
        ' Each line of names.csv consists of a last name, a first name, and an  
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111  
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")  
  
        ' Each line of scores.csv consists of an ID number and four test   
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60  
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' The following query merges the content of two dissimilar spreadsheets   
        ' based on common ID values.  
        ' Multiple From clauses are used instead of a Join clause  
        ' in order to store the results of scoreLine.Split.  
        ' Note the dynamic creation of a list of integers for the  
        ' ExamScores member. We skip the first item in the split string   
        ' because it is the student ID, not an exam score.  
        Dim queryNamesScores = From nameLine In names  
                          Let splitName = nameLine.Split(New Char() {","})  
                          From scoreLine In scores  
                          Let splitScoreLine = scoreLine.Split(New Char() {","})  
                          Where splitName(2) = splitScoreLine(0)  
                          Select New Student() With {  
                               .FirstName = splitName(0), .LastName = splitName(1), .ID = splitName(2),  
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1  
                                             Select Convert.ToInt32(scoreAsText)).ToList()}  
  
        ' Optional. Store the query results for faster access in future  
        ' queries. This could be useful with very large data files.  
        Dim students As List(Of Student) = queryNamesScores.ToList()  
  
        ' Display each student's name and exam score average.  
        For Each s In students  
            Console.WriteLine("The average score of " & s.FirstName & " " &  
                              s.LastName & " is " & s.ExamScores.Average())  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
  
' Output:   
' The average score of Omelchenko Svetlana is 82.5  
' The average score of O'Donnell Claire is 72.25  
' The average score of Mortensen Sven is 84.5  
' The average score of Garcia Cesar is 88.25  
' The average score of Garcia Debra is 67  
' The average score of Fakhouri Fadi is 92.25  
' The average score of Feng Hanying is 88  
' The average score of Garcia Hugo is 85.75  
' The average score of Tucker Lance is 81.75  
' The average score of Adams Terry is 85.25  
' The average score of Zabokritski Eugene is 83  
' The average score of Tucker Michael is 92  
```  
  
 에 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md) 절, 개체 이니셜라이저는 인스턴스화하는 데 사용 각 새로운 `Student` 두 원본의 데이터를 사용 하 여 개체입니다.  
  
 쿼리 결과 저장 해야 하는 경우 익명 형식은 명명 된 형식 보다 더 편리할 수 있습니다. 쿼리가 실행 되는 메서드 외부에 쿼리 결과 전달 하는 경우에 명명 된 형식이 필요 합니다. 다음 예제에서는 앞의 예제와 같은 작업을 수행 하지만 명명 된 형식 대신 익명 형식을 사용 합니다.  
  
```vb  
' Merge the data by using an anonymous type.   
' Note the dynamic creation of a list of integers for the  
' ExamScores member. We skip 1 because the first string  
' in the array is the student ID, not an exam score.  
Dim queryNamesScores2 =  
    From nameLine In names  
    Let splitName = nameLine.Split(New Char() {","})  
    From scoreLine In scores  
    Let splitScoreLine = scoreLine.Split(New Char() {","})  
    Where splitName(2) = splitScoreLine(0)  
    Select New With  
           {.Last = splitName(0),  
            .First = splitName(1),  
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1  
                           Select Convert.ToInt32(scoreAsText)).ToList()}  
  
' Display each student's name and exam score average.  
For Each s In queryNamesScores2  
    Console.WriteLine("The average score of " & s.First & " " &  
                      s.Last & " is " & s.ExamScores.Average())  
Next  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
