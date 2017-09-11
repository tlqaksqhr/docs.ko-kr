---
title: "방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리 | Microsoft 문서"
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
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
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
ms.openlocfilehash: bda25acd3065898eeb61dce83d46d7526e825add
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a><span data-ttu-id="dfcc9-102">방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="dfcc9-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="dfcc9-103">이 예제에서는 지정된 된 폴더에 있는 모든 파일 및 모든 하위 폴더에 사용 된 바이트의 총 수를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfcc9-104">예제</span><span class="sxs-lookup"><span data-stu-id="dfcc9-104">Example</span></span>  
 <span data-ttu-id="dfcc9-105"><xref:System.Linq.Enumerable.Sum%2A>에서 선택한 모든 항목의 값을 추가 하는 메서드는 `select` 절.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="dfcc9-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="dfcc9-106"><xref:System.Linq.Enumerable.Min%2A>또는 <xref:System.Linq.Enumerable.Max%2A> <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> 대신 메서드</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> 를 호출 하 여 지정 된 디렉터리 트리에서 가장 큰 크거나 작은 파일을 검색 하려면 다음이 쿼리를 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
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
  
 <span data-ttu-id="dfcc9-107">지정된 된 디렉터리 트리에서의 바이트 수를 계산 해야 하는 경우 이렇게 하려면 보다 효율적으로 데이터 원본으로 목록 컬렉션을 만드는 오버 헤드를 유발 하는 LINQ 쿼리를 만들지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="dfcc9-108">LINQ 사용 하는 조건의 유용성에는 쿼리가 더 복잡 하거나 동일한 데이터 원본에 대해 여러 쿼리를 실행 해야 할 때 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="dfcc9-109">쿼리 파일 길이를 가져오는 별도 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="dfcc9-110">이후 다른 스레드에서 파일이 삭제 된 경우 발생할 수 있는 예외를 처리 하기 위해이 위해는 <xref:System.IO.FileInfo>개체에 대 한 호출에서 만든 `GetFiles`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="dfcc9-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="dfcc9-111">경우에는 <xref:System.IO.FileInfo>개체에 이미 생성 되어 예외가 발생할 수 있으므로 한 <xref:System.IO.FileInfo>개체는 새로 고침 하려고 해당 <xref:System.IO.FileInfo.Length%2A>최신 길이 처음으로 속성에 액세스를 사용 하 여 속성.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="dfcc9-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="dfcc9-112">쿼리 외부에 try catch 블록에서이 작업을 배치 하 여 코드의 의도 일으킬 수 있는 쿼리에서 연산을 회피 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="dfcc9-113">일반적으로 매우 주의 해야 응용 프로그램 하지 알 수 없는 상태에 남아 있는 있는지 확인 하는 예외를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dfcc9-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dfcc9-114">Compiling the Code</span></span>  
 <span data-ttu-id="dfcc9-115">.NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcc9-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcc9-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfcc9-116">See Also</span></span>  
 <span data-ttu-id="dfcc9-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="dfcc9-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="dfcc9-118"> [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="dfcc9-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
