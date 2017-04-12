---
title: "방법: 그룹화 (LINQ) (Visual Basic) 확장 하 여 파일 | Microsoft 문서"
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
ms.assetid: 904dc6d7-7162-4655-a7f4-5785d669bc5a
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
ms.openlocfilehash: f78785b4da3ae3b362603eea34d81207ed48a657
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-group-files-by-extension-linq-visual-basic"></a>방법: 파일 확장명 (LINQ) (Visual Basic)으로 그룹화
이 예제에서는 고급 그룹화 및 정렬 파일 또는 폴더의 목록에 대 한 작업 수행 하 고 LINQ를 사용할 수 있는 방법을 보여 줍니다. 콘솔 창의 출력을에서 사용 하 여 페이징 하는 방법을 보여 줍니다는 <xref:System.Linq.Enumerable.Skip%2A>및 <xref:System.Linq.Enumerable.Take%2A>메서드.</xref:System.Linq.Enumerable.Take%2A> </xref:System.Linq.Enumerable.Skip%2A>  
  
## <a name="example"></a>예제  
 다음 쿼리는 내용이 지정된 된 디렉터리 트리에서의 파일 이름 확장명으로 그룹화 하는 방법을 보여 줍니다.  
  
```vb  
Module GroupByExtension  
    Public Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        Dim startFolder As String = "C:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        ' Used in WriteLine() to skip over startfolder in output lines.  
        Dim rootLength As Integer = startFolder.Length  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Create the query.  
        Dim queryGroupByExt = From file In fileList _  
                          Group By file.Extension.ToLower() Into fileGroup = Group _  
                          Order By ToLower _  
                          Select fileGroup  
  
        ' Execute the query. By storing the result we can  
        ' page the display with good performance.  
        Dim groupByExtList = queryGroupByExt.ToList()  
  
        ' Display one group at a time. If the number of   
        ' entries is greater than the number of lines  
        ' in the console window, then page the output.  
        Dim trimLength = startFolder.Length  
        PageOutput(groupByExtList, trimLength)  
  
    End Sub  
  
    ' Pages console diplay for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to diplay  
        Dim goAgain As Boolean = True  
  
        For Each fg As IEnumerable(Of System.IO.FileInfo) In groupQuery  
            ' Start a new extension at the top of a page.  
            Dim currentLine As Integer = 0  
  
            Do While (currentLine < fg.Count())  
                Console.Clear()  
                Console.WriteLine(fg(0).Extension)  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the display output.  
                For Each line In resultPage  
                    Console.WriteLine(vbTab & line.FullName.Substring(charsToSkip))  
                Next  
  
                ' Advance the current position  
                currentLine = numLines + currentLine  
  
                ' Give the user a chance to break out of the loop  
                Console.WriteLine("Press any key for next page or the 'End' key to exit.")  
                Dim key As ConsoleKey = Console.ReadKey().Key  
                If key = ConsoleKey.End Then  
                    goAgain = False  
                    Exit For  
                End If  
            Loop  
        Next  
    End Sub  
End Module  
```  
  
 이 프로그램의 출력을에서 로컬 파일 시스템 및 기능에 대 한 세부 정보에 따라 길 수는 `startFolder` 로 설정 됩니다. 모든 결과 볼 수 있도록,이 예제에는 결과를 페이징 하는 방법을 보여 줍니다. Windows 및 웹 응용 프로그램에 동일한 기법을 적용할 수 있습니다. 코드에는 중첩 된 그룹에서 항목을 페이징 하기 때문에 `For Each` 루프가 필요 합니다. 목록에서 현재 위치를 계산 하 고 페이징을 중지 하 고 프로그램을 종료할 수 있도록 몇 가지 추가 논리가 이기도 합니다. 이 특정 예제의 원래 쿼리에서 페이징 쿼리는 캐시 된 결과 대해 실행 됩니다. LINQ to SQL에서와 같은 다른 컨텍스트에서 같은 캐싱이 필요 하지 않습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
