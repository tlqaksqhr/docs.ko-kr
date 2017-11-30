---
title: "방법: CSV 텍스트 파일 (LINQ) (Visual Basic)의 열 값 계산"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88b2b9f3-c82e-41f3-b1b4-26ede5973a02
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d57376ca2741801d6aee858688f00cba245a225d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compute-column-values-in-a-csv-text-file-linq-visual-basic"></a><span data-ttu-id="c3a43-102">방법: CSV 텍스트 파일 (LINQ) (Visual Basic)의 열 값 계산</span><span class="sxs-lookup"><span data-stu-id="c3a43-102">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="c3a43-103">이 예제에서는 .csv 파일의 열에 대해 Sum, Average, Min 및 Max 등의 집계 계산을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-103">This example shows how to perform aggregate computations such as Sum, Average, Min, and Max on the columns of a .csv file.</span></span> <span data-ttu-id="c3a43-104">여기 표시된 예제 원칙은 다른 형식의 구조화된 텍스트에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-104">The example principles that are shown here can be applied to other types of structured text.</span></span>  
  
### <a name="to-create-the-source-file"></a><span data-ttu-id="c3a43-105">소스 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c3a43-105">To create the source file</span></span>  
  
1.  <span data-ttu-id="c3a43-106">다음 줄을 scores.csv 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-106">Copy the following lines into a file that is named scores.csv and save it in your project folder.</span></span> <span data-ttu-id="c3a43-107">첫 번째 열은 학생 ID를 나타내고 후속 열은 4개 시험의 점수를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-107">Assume that the first column represents a student ID, and subsequent columns represent scores from four exams.</span></span>  
  
    ```  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
## <a name="example"></a><span data-ttu-id="c3a43-108">예제</span><span class="sxs-lookup"><span data-stu-id="c3a43-108">Example</span></span>  
  
```vb  
Class SumColumns  
  
    Public Shared Sub Main()  
  
        Dim lines As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' Specifies the column to compute  
        ' This value could be passed in at runtime.  
        Dim exam = 3  
  
        ' Spreadsheet format:  
        ' Student ID    Exam#1  Exam#2  Exam#3  Exam#4  
        ' 111,          97,     92,     81,     60  
        ' one is added to skip over the first column  
        ' which holds the student ID.  
        SumColumn(lines, exam + 1)  
        Console.WriteLine()  
        MultiColumns(lines)  
  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit...")  
        Console.ReadKey()  
  
    End Sub  
  
    Shared Sub SumColumn(ByVal lines As IEnumerable(Of String), ByVal col As Integer)  
  
        ' This query performs two steps:  
        ' split the string into a string array  
        ' convert the specified element to  
        ' integer and select it.  
        Dim columnQuery = From line In lines   
                           Let x = line.Split(",")   
                           Select Convert.ToInt32(x(col))  
  
        ' Execute and cache the results for performance.  
        ' Only needed with very large files.  
        Dim results = columnQuery.ToList()  
  
        ' Perform aggregate calculations   
        ' on the column specified by col.  
        Dim avgScore = Aggregate score In results Into Average(score)  
        Dim minScore = Aggregate score In results Into Min(score)  
        Dim maxScore = Aggregate score In results Into Max(score)  
  
        Console.WriteLine("Single Column Query:")  
        Console.WriteLine("Exam #{0}: Average:{1:##.##} High Score:{2} Low Score:{3}",   
                     col, avgScore, maxScore, minScore)  
  
    End Sub  
  
    Shared Sub MultiColumns(ByVal lines As IEnumerable(Of String))  
  
        Console.WriteLine("Multi Column Query:")  
  
        ' Create the query. It will produce nested sequences.   
        ' multiColQuery performs these steps:  
        ' 1) convert the string to a string array  
        ' 2) skip over the "Student ID" column and take the rest  
        ' 3) convert each field to an int and select that   
        '    entire sequence as one row in the results.  
        Dim multiColQuery = From line In lines   
                            Let fields = line.Split(",")   
                            Select From str In fields Skip 1   
                                        Select Convert.ToInt32(str)  
  
        Dim results = multiColQuery.ToList()  
  
        ' Find out how many columns we have.  
        Dim columnCount = results(0).Count()  
  
        ' Perform aggregate calculations on each column.              
        ' One loop for each score column in scores.  
        ' We can use a for loop because we have already  
        ' executed the multiColQuery in the call to ToList.  
  
        For j As Integer = 0 To columnCount - 1  
            Dim column = j  
            Dim res2 = From row In results   
                       Select row.ElementAt(column)  
  
            ' Perform aggregate calculations   
            ' on the column specified by col.  
            Dim avgScore = Aggregate score In res2 Into Average(score)  
            Dim minScore = Aggregate score In res2 Into Min(score)  
            Dim maxScore = Aggregate score In res2 Into Max(score)  
  
            ' Add 1 to column numbers because exams in this course start with #1  
            Console.WriteLine("Exam #{0} Average: {1:##.##} High Score: {2} Low Score: {3}",   
                              column + 1, avgScore, maxScore, minScore)  
  
        Next  
    End Sub  
  
End Class  
' Output:  
' Single Column Query:  
' Exam #4: Average:76.92 High Score:94 Low Score:39  
  
' Multi Column Query:  
' Exam #1 Average: 86.08 High Score: 99 Low Score: 35  
' Exam #2 Average: 86.42 High Score: 94 Low Score: 72  
' Exam #3 Average: 84.75 High Score: 91 Low Score: 65  
' Exam #4 Average: 76.92 High Score: 94 Low Score: 39  
```  
  
 <span data-ttu-id="c3a43-109">쿼리는 <xref:System.String.Split%2A> 메서드를 사용하여 텍스트의 각 줄을 배열로 변환하는 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-109">The query works by using the <xref:System.String.Split%2A> method to convert each line of text into an array.</span></span> <span data-ttu-id="c3a43-110">각 배열 요소는 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-110">Each array element represents a column.</span></span> <span data-ttu-id="c3a43-111">마지막으로 각 열의 텍스트가 숫자 표현으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-111">Finally, the text in each column is converted to its numeric representation.</span></span> <span data-ttu-id="c3a43-112">탭으로 구분된 파일인 경우 `Split` 메서드의 인수를 `\t`로 업데이트하세요.</span><span class="sxs-lookup"><span data-stu-id="c3a43-112">If your file is a tab-separated file, just update the argument in the `Split` method to `\t`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c3a43-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c3a43-113">Compiling the Code</span></span>  
 <span data-ttu-id="c3a43-114">System.Core.dll에 대한 참조와 System.Linq 네임스페이스에 대한 `Imports` 문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3a43-114">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a43-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3a43-115">See Also</span></span>  
 [<span data-ttu-id="c3a43-116">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3a43-116">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="c3a43-117">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3a43-117">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
