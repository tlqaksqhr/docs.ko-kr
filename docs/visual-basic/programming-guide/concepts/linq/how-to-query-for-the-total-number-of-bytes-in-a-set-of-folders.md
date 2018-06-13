---
title: '방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리'
ms.date: 07/20/2015
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
ms.openlocfilehash: 6a6babaf019cdac2298aee6eff55581bf35b2e47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643551"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a><span data-ttu-id="3206c-102">방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="3206c-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="3206c-103">이 예제에서는 지정된 폴더 및 모든 하위 폴더의 모든 파일에서 사용된 총 바이트 수를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3206c-104">예제</span><span class="sxs-lookup"><span data-stu-id="3206c-104">Example</span></span>  
 <span data-ttu-id="3206c-105"><xref:System.Linq.Enumerable.Sum%2A> 메서드는 `select` 절에서 선택된 모든 항목의 값을 더합니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="3206c-106"><xref:System.Linq.Enumerable.Sum%2A> 대신 <xref:System.Linq.Enumerable.Min%2A> 또는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 호출하여 지정된 디렉터리 트리에서 가장 큰 파일이나 가장 작은 파일을 검색하도록 이 쿼리를 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="3206c-107">지정된 디렉터리 트리의 바이트 수만 계산하면 되는 경우 데이터 소스로 목록 컬렉션을 만드는 오버헤드를 유발하는 LINQ 쿼리를 만들지 않고 보다 효율적으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="3206c-108">LINQ 방식의 유용성은 쿼리가 더 복잡함에 따라 또는 동일한 데이터 소스에 대해 여러 쿼리를 실행해야 하는 경우에 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="3206c-109">쿼리는 파일 길이를 가져오기 위해 별도 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="3206c-110">`GetFiles` 호출에서 <xref:System.IO.FileInfo> 개체가 생성된 후 파일이 다른 스레드에서 삭제된 경우 발생할 수 있는 예외를 처리하기 위해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="3206c-111"><xref:System.IO.FileInfo> 개체가 이미 생성된 경우에도 <xref:System.IO.FileInfo> 개체는 속성에 처음 액세스할 때 최신 길이를 사용하여 해당 <xref:System.IO.FileInfo.Length%2A> 속성의 새로 고침을 시도하기 때문에 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="3206c-112">코드는 이 작업을 쿼리 외부의 try-catch 블록에 배치하여, 부작용을 일으킬 수 있는 작업을 쿼리에서 방지하는 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="3206c-113">일반적으로, 예외를 처리할 때는 응용 프로그램이 알 수 없는 상태로 남지 않도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3206c-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3206c-114">Compiling the Code</span></span>  
 <span data-ttu-id="3206c-115">대상.NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조는 프로젝트를 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3206c-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3206c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3206c-116">See Also</span></span>  
 [<span data-ttu-id="3206c-117">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3206c-117">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="3206c-118">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3206c-118">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
