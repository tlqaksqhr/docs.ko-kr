---
title: "방법: 폴더 집합의 전체 바이트 수 쿼리(LINQ)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 342ab9e23b733051679483172a1da6027f6e6f3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a><span data-ttu-id="59292-102">방법: 폴더 집합의 전체 바이트 수 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="59292-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>
<span data-ttu-id="59292-103">이 예제에서는 지정된 폴더 및 모든 하위 폴더의 모든 파일에서 사용된 총 바이트 수를 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59292-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59292-104">예제</span><span class="sxs-lookup"><span data-stu-id="59292-104">Example</span></span>  
 <span data-ttu-id="59292-105"><xref:System.Linq.Enumerable.Sum%2A> 메서드는 `select` 절에서 선택된 모든 항목의 값을 더합니다.</span><span class="sxs-lookup"><span data-stu-id="59292-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="59292-106"><xref:System.Linq.Enumerable.Sum%2A> 대신 <xref:System.Linq.Enumerable.Min%2A> 또는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 호출하여 지정된 디렉터리 트리에서 가장 큰 파일이나 가장 작은 파일을 검색하도록 이 쿼리를 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59292-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```csharp  
class QuerySize  
{  
    public static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\VC#";  
  
        // Take a snapshot of the file system.  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<string> fileList = System.IO.Directory.GetFiles(startFolder, "*.*", System.IO.SearchOption.AllDirectories);  
  
        var fileQuery = from file in fileList  
                        select GetFileLength(file);  
  
        // Cache the results to avoid multiple trips to the file system.  
        long[] fileLengths = fileQuery.ToArray();  
  
        // Return the size of the largest file  
        long largestFile = fileLengths.Max();  
  
        // Return the total number of bytes in all the files under the specified folder.  
        long totalBytes = fileLengths.Sum();  
  
        Console.WriteLine("There are {0} bytes in {1} files under {2}",  
            totalBytes, fileList.Count(), startFolder);  
        Console.WriteLine("The largest files is {0} bytes.", largestFile);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the System.IO.FileInfo.Length property.  
    static long GetFileLength(string filename)  
    {  
        long retval;  
        try  
        {  
            System.IO.FileInfo fi = new System.IO.FileInfo(filename);  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
}  
```  
  
 <span data-ttu-id="59292-107">지정된 디렉터리 트리의 바이트 수만 계산하면 되는 경우 데이터 소스로 목록 컬렉션을 만드는 오버헤드를 유발하는 LINQ 쿼리를 만들지 않고 보다 효율적으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59292-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="59292-108">LINQ 방식의 유용성은 쿼리가 더 복잡함에 따라 또는 동일한 데이터 소스에 대해 여러 쿼리를 실행해야 하는 경우에 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="59292-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="59292-109">쿼리는 파일 길이를 가져오기 위해 별도 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="59292-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="59292-110">`GetFiles` 호출에서 <xref:System.IO.FileInfo> 개체가 생성된 후 파일이 다른 스레드에서 삭제된 경우 발생할 수 있는 예외를 처리하기 위해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="59292-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="59292-111"><xref:System.IO.FileInfo> 개체가 이미 생성된 경우에도 <xref:System.IO.FileInfo> 개체는 속성에 처음 액세스할 때 최신 길이를 사용하여 해당 <xref:System.IO.FileInfo.Length%2A> 속성의 새로 고침을 시도하기 때문에 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59292-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="59292-112">코드는 이 작업을 쿼리 외부의 try-catch 블록에 배치하여, 부작용을 일으킬 수 있는 작업을 쿼리에서 방지하는 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="59292-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="59292-113">일반적으로, 예외를 처리할 때는 응용 프로그램이 알 수 없는 상태로 남지 않도록 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59292-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="59292-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="59292-114">Compiling the Code</span></span>  
 <span data-ttu-id="59292-115">System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59292-115">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59292-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59292-116">See Also</span></span>  
 [<span data-ttu-id="59292-117">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="59292-117">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="59292-118">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="59292-118">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
