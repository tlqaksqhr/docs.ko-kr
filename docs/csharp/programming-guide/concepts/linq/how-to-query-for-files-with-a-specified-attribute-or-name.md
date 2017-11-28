---
title: "방법: 지정된 특성 또는 이름을 갖는 파일 쿼리(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8e5ad9f6ea5d6d8ff97389fc6535dc34acca7d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a><span data-ttu-id="a4d7c-102">방법: 지정된 특성 또는 이름을 갖는 파일 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="a4d7c-102">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>
<span data-ttu-id="a4d7c-103">이 예제에서는 지정된 디렉터리 트리에서 지정된 파일 이름 확장명(예: ".txt")을 가진 파일을 모두 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="a4d7c-104">또한 생성 시간을 기준으로 트리에서 가장 최신 파일이나 가장 오래된 파일을 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4d7c-105">예제</span><span class="sxs-lookup"><span data-stu-id="a4d7c-105">Example</span></span>  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous   
        // query as a starting point. fileQuery is not   
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a4d7c-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a4d7c-106">Compiling the Code</span></span>  
 <span data-ttu-id="a4d7c-107">System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4d7c-107">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d7c-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4d7c-108">See Also</span></span>  
 [<span data-ttu-id="a4d7c-109">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="a4d7c-109">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="a4d7c-110">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="a4d7c-110">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
