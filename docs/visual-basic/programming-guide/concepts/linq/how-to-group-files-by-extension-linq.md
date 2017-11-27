---
title: "방법: 파일 확장명 (LINQ) (Visual Basic)으로 그룹화"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 904dc6d7-7162-4655-a7f4-5785d669bc5a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e2d81f88371e63f64567422e87ed5b185e7a633
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-files-by-extension-linq-visual-basic"></a><span data-ttu-id="31f6c-102">방법: 파일 확장명 (LINQ) (Visual Basic)으로 그룹화</span><span class="sxs-lookup"><span data-stu-id="31f6c-102">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="31f6c-103">이 예제에서는 LINQ를 사용하여 파일 또는 폴더 목록에 대해 고급 그룹화 및 정렬 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-103">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="31f6c-104">또한 <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 콘솔 창에서 출력을 페이징하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-104">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31f6c-105">예제</span><span class="sxs-lookup"><span data-stu-id="31f6c-105">Example</span></span>  
 <span data-ttu-id="31f6c-106">다음 쿼리는 지정된 디렉터리 트리의 내용을 파일 이름 확장명으로 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-106">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
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
  
 <span data-ttu-id="31f6c-107">이 프로그램의 출력은 로컬 파일 시스템의 세부 정보 및 `startFolder`의 설정에 따라 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-107">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="31f6c-108">모든 결과를 볼 수 있도록, 이 예제에서는 결과를 페이징하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-108">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="31f6c-109">Windows 및 웹 응용 프로그램에 동일한 기법을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-109">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="31f6c-110">코드에서 그룹의 항목을 페이징하기 때문에 중첩된 `For Each` 루프가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-110">Notice that because the code pages the items in a group, a nested `For Each` loop is required.</span></span> <span data-ttu-id="31f6c-111">목록에서 현재 위치를 계산하며 사용자가 페이징을 중지하고 프로그램을 종료할 수 있도록 하는 몇 가지 추가 논리도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-111">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="31f6c-112">이 특정 사례에서는 페이징 쿼리가 원래 쿼리에서 캐시된 결과에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-112">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="31f6c-113">LINQ to SQL 등의 다른 컨텍스트에서는 이러한 캐싱이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-113">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31f6c-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="31f6c-114">Compiling the Code</span></span>  
 <span data-ttu-id="31f6c-115">대상.NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조는 프로젝트를 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="31f6c-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f6c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31f6c-116">See Also</span></span>  
 [<span data-ttu-id="31f6c-117">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31f6c-117">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="31f6c-118">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31f6c-118">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
