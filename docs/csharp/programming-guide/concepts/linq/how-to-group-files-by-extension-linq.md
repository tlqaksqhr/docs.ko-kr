---
title: '방법: 확장명에 따라 파일 그룹화(LINQ)(C#)'
ms.date: 07/20/2015
ms.assetid: 21a98320-a5a1-4981-82d8-6a637e7d9018
ms.openlocfilehash: 4b2200799a7623bf9d47540f922798f5161be1bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319295"
---
# <a name="how-to-group-files-by-extension-linq-c"></a><span data-ttu-id="262e3-102">방법: 확장명에 따라 파일 그룹화(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="262e3-102">How to: Group Files by Extension (LINQ) (C#)</span></span>
<span data-ttu-id="262e3-103">이 예제에서는 LINQ를 사용하여 파일 또는 폴더 목록에 대해 고급 그룹화 및 정렬 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-103">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="262e3-104">또한 <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 콘솔 창에서 출력을 페이징하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-104">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="262e3-105">예</span><span class="sxs-lookup"><span data-stu-id="262e3-105">Example</span></span>  
 <span data-ttu-id="262e3-106">다음 쿼리는 지정된 디렉터리 트리의 내용을 파일 이름 확장명으로 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-106">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
```csharp  
class GroupByExtension  
{  
    // This query will sort all the files under the specified folder  
    //  and subfolder into groups keyed by the file extension.  
    private static void Main()  
    {  
        // Take a snapshot of the file system.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Used in WriteLine to trim output lines.  
        int trimLength = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Create the query.  
        var queryGroupByExt =  
            from file in fileList  
            group file by file.Extension.ToLower() into fileGroup  
            orderby fileGroup.Key  
            select fileGroup;  
  
        // Display one group at a time. If the number of   
        // entries is greater than the number of lines  
        // in the console window, then page the output.  
        PageOutput(trimLength, queryGroupByExt);  
    }  
  
    // This method specifically handles group queries of FileInfo objects with string keys.  
    // It can be modified to work for any long listings of data. Note that explicit typing  
    // must be used in method signatures. The groupbyExtList parameter is a query that produces  
    // groups of FileInfo objects with string keys.  
    private static void PageOutput(int rootLength,  
                                    IEnumerable<System.Linq.IGrouping<string, System.IO.FileInfo>> groupByExtList)  
    {  
        // Flag to break out of paging loop.  
        bool goAgain = true;  
  
        // "3" = 1 line for extension + 1 for "Press any key" + 1 for input cursor.  
        int numLines = Console.WindowHeight - 3;  
  
        // Iterate through the outer collection of groups.  
        foreach (var filegroup in groupByExtList)  
        {  
            // Start a new extension at the top of a page.  
            int currentLine = 0;  
  
            // Output only as many lines of the current group as will fit in the window.  
            do  
            {  
                Console.Clear();  
                Console.WriteLine(filegroup.Key == String.Empty ? "[none]" : filegroup.Key);  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var f in resultPage)  
                {  
                    Console.WriteLine("\t{0}", f.FullName.Substring(rootLength));  
                }  
  
                // Increment the line counter.  
                currentLine += numLines;  
  
                // Give the user a chance to escape.  
                Console.WriteLine("Press any key to continue or the 'End' key to break...");  
                ConsoleKey key = Console.ReadKey().Key;  
                if (key == ConsoleKey.End)  
                {  
                    goAgain = false;  
                    break;  
                }  
            } while (currentLine < filegroup.Count());  
  
            if (goAgain == false)  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="262e3-107">이 프로그램의 출력은 로컬 파일 시스템의 세부 정보 및 `startFolder`의 설정에 따라 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-107">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="262e3-108">모든 결과를 볼 수 있도록, 이 예제에서는 결과를 페이징하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-108">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="262e3-109">Windows 및 웹 응용 프로그램에 동일한 기법을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-109">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="262e3-110">코드에서 그룹의 항목을 페이징하기 때문에 중첩된 `foreach` 루프가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-110">Notice that because the code pages the items in a group, a nested `foreach` loop is required.</span></span> <span data-ttu-id="262e3-111">목록에서 현재 위치를 계산하며 사용자가 페이징을 중지하고 프로그램을 종료할 수 있도록 하는 몇 가지 추가 논리도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-111">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="262e3-112">이 특정 사례에서는 페이징 쿼리가 원래 쿼리에서 캐시된 결과에 대해 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-112">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="262e3-113">LINQ to SQL 등의 다른 컨텍스트에서는 이러한 캐싱이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-113">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="262e3-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="262e3-114">Compiling the Code</span></span>  
 <span data-ttu-id="262e3-115">System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="262e3-115">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262e3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="262e3-116">See Also</span></span>  
 [<span data-ttu-id="262e3-117">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="262e3-117">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="262e3-118">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="262e3-118">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
