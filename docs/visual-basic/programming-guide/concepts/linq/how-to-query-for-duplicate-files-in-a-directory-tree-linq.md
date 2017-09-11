---
title: "방법: 쿼리 (LINQ) (Visual Basic) 디렉터리 트리의 중복 파일 | Microsoft 문서"
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
ms.assetid: 387d7c97-95dd-4a50-9761-7e9cf8ae9e6a
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f4ddab6129e7d05851553e544b9813951415a45
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="3c29c-102">방법: 디렉터리 트리 (LINQ) (Visual Basic)에서 중복 파일 쿼리</span><span class="sxs-lookup"><span data-stu-id="3c29c-102">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="3c29c-103">경우에 따라 동일한 이름을 가진 파일 한 개 이상의 폴더에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c29c-103">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="3c29c-104">예를 들어 Visual Studio 설치 폴더에서 여러 폴더는 readme.htm 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3c29c-104">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="3c29c-105">이 예제에는 이러한 중복 파일 이름 지정 된 루트 폴더에 대 한 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c29c-105">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="3c29c-106">생성 시간에도 일치 및 두 번째 예제에는 크기의 파일에 대 한 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c29c-106">The second example shows how to query for files whose size and creation times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c29c-107">예제</span><span class="sxs-lookup"><span data-stu-id="3c29c-107">Example</span></span>  
  
```vb  
Module QueryDuplicateFileNames  
  
    Public Sub Main()  
  
        Dim path As String = "C:\Program Files\Microsoft Visual Studio 9.0\Common7"  
        QueryDuplicates1(path)  
        ' Uncomment to run this query instead  
        ' QueryDuplicates2(path)  
  
    End Sub  
    Sub QueryDuplicates1(ByVal root As String)  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim duplicates = From aFile In dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
    End Sub  
    Sub QueryDuplicates2(ByVal root As String)  
  
        ' This time a composite key is used. This sub finds all files  
        ' that have been copied into multiple subfolders.  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim duplicates = From aFile In Dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name, aFile.CreationTime, aFile.Length Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
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
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the paths in the output.  
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
  
 <span data-ttu-id="3c29c-108">첫 번째 쿼리에서 간단한 키를 사용 하 여 일치 하는 항목을 확인 하려면 이 같은 이름이 같지만 내용이 다를 수 있는 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3c29c-108">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="3c29c-109">두 번째 쿼리에서 복합 키를 사용 하 여의 세 가지 속성에 대해 일치 하는 <xref:System.IO.FileInfo>개체.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="3c29c-109">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="3c29c-110">이 쿼리는 동일한 이름 및 동일 하거나 유사한 콘텐츠 파일을 찾을 가능성이 훨씬 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="3c29c-110">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c29c-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3c29c-111">Compiling the Code</span></span>  
 <span data-ttu-id="3c29c-112">.NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` 는 System.Linq 네임 스페이스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3c29c-112">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c29c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c29c-113">See Also</span></span>  
 <span data-ttu-id="3c29c-114">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="3c29c-114">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="3c29c-115"> [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="3c29c-115"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
