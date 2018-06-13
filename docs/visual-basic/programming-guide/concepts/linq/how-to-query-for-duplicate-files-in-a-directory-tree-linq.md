---
title: '방법: (LINQ) (Visual Basic) 디렉터리 트리의 중복 파일 쿼리'
ms.date: 07/20/2015
ms.assetid: 387d7c97-95dd-4a50-9761-7e9cf8ae9e6a
ms.openlocfilehash: c9243d98c73571fcde009cddb2d5435365f20760
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643182"
---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="22bbc-102">방법: (LINQ) (Visual Basic) 디렉터리 트리의 중복 파일 쿼리</span><span class="sxs-lookup"><span data-stu-id="22bbc-102">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="22bbc-103">동일한 이름을 가진 파일이 둘 이상의 폴더에 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-103">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="22bbc-104">예를 들어 Visual Studio 설치 폴더 아래의 여러 폴더에 readme.htm 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-104">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="22bbc-105">이 예제에서는 지정된 루트 폴더 아래에서 이러한 중복 파일 이름을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-105">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="22bbc-106">두 번째 예제에서는 크기 및 생성 시간도 일치하는 파일을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-106">The second example shows how to query for files whose size and creation times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22bbc-107">예제</span><span class="sxs-lookup"><span data-stu-id="22bbc-107">Example</span></span>  
  
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
  
 <span data-ttu-id="22bbc-108">첫 번째 쿼리는 단순 키를 사용하여 일치하는 항목을 확인합니다. 이름은 같지만 내용이 다를 수 있는 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-108">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="22bbc-109">두 번째 쿼리는 복합 키를 사용하여 <xref:System.IO.FileInfo> 개체의 세 가지 속성과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-109">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="22bbc-110">이 쿼리가 이름이 같고 내용이 비슷하거나 동일한 파일을 찾을 가능성이 훨씬 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-110">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22bbc-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="22bbc-111">Compiling the Code</span></span>  
 <span data-ttu-id="22bbc-112">System.Core.dll에 대한 참조와 System.Linq 네임스페이스에 대한 `Imports` 문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22bbc-112">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22bbc-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22bbc-113">See Also</span></span>  
 [<span data-ttu-id="22bbc-114">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22bbc-114">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="22bbc-115">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22bbc-115">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
