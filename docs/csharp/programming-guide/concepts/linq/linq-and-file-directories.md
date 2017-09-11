---
title: "LINQ 및 파일 디렉터리(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: b66c55e4-0f72-44e5-b086-519f9962335c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e7324e3b1d165bfe7ef477fa73bac5d3e7735dc5
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="linq-and-file-directories-c"></a><span data-ttu-id="d9962-102">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-102">LINQ and File Directories (C#)</span></span>
<span data-ttu-id="d9962-103">많은 파일 시스템 작업은 기본적으로 쿼리이므로 LINQ 접근 방식에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="d9962-104">이 섹션에서 쿼리는 비파괴적입니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="d9962-105">쿼리는 원본 파일이나 폴더의 내용을 변경하는 데 사용되지 않으며,</span><span class="sxs-lookup"><span data-stu-id="d9962-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="d9962-106">쿼리로 인해 의도하지 않은 결과가 발생하지 않아야 한다는 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="d9962-107">일반적으로 소스 데이터를 수정하는 모든 코드(만들기/업데이트/삭제 작업을 수행하는 쿼리 포함)는 데이터를 쿼리만하는 코드와 별도로 유지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="d9962-108">이 단원에는 다음 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="d9962-109">방법: 지정된 특성 또는 이름을 갖는 파일 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-109">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="d9962-110">하나 이상의 <xref:System.IO.FileInfo> 개체 속성을 검사하여 파일을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="d9962-111">방법: 확장명에 따라 파일 그룹화(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-111">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="d9962-112">파일 이름 확장명에 따라 <xref:System.IO.FileInfo> 개체의 그룹을 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="d9962-113">방법: 폴더 집합의 전체 바이트 수 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)  
 <span data-ttu-id="d9962-114">지정된 디렉터리 트리에 있는 모든 파일에서 전체 바이트 수를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="d9962-115">[방법: 두 폴더의 내용 비교(LINQ)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)</span><span class="sxs-lookup"><span data-stu-id="d9962-115">[How to: Compare the Contents of Two Folders (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="d9962-116">두 개의 지정된 폴더에 있는 모든 파일뿐만 아니라 특정 폴더에만 있는 모든 파일도 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="d9962-117">방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="d9962-118">디렉터리 트리에서 가장 크거나 가장 작은 파일 또는 지정한 파일 수를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="d9962-119">방법: 디렉터리 트리의 중복 파일 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="d9962-120">지정된 디렉터리 트리에서 둘 이상의 위치에 나타나는 모든 파일 이름을 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="d9962-121">또한 사용자 지정 비교자에 따라 보다 복잡한 비교를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="d9962-122">방법: 폴더의 파일 내용 쿼리(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-122">How to: Query the Contents of Files in a Folder (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-lin.md)  
 <span data-ttu-id="d9962-123">트리의 폴더를 반복하고, 각 파일을 열고, 파일의 내용을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="d9962-124">설명</span><span class="sxs-lookup"><span data-stu-id="d9962-124">Comments</span></span>  
 <span data-ttu-id="d9962-125">파일 시스템의 내용을 정확하게 나타내고 예외를 정상적으로 처리하는 데이터 소스 만들기와 관련하여 몇 가지 복잡한 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="d9962-126">이 섹션의 예제에서는 지정된 루트 폴더와 모든 하위 폴더에 있는 모든 파일을 나타내는 <xref:System.IO.FileInfo> 개체의 스냅숏 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="d9962-127">각 <xref:System.IO.FileInfo>의 실제 상태는 쿼리 실행을 시작하고 종료하는 시간 사이에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="d9962-128">예를 들어 <xref:System.IO.FileInfo> 개체 목록을 만들어 데이터 소스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="d9962-129">쿼리에서 `Length` 속성에 액세스하려고 하면 <xref:System.IO.FileInfo> 개체에서 파일 시스템에 액세스하여 `Length`의 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="d9962-130">파일이 더 이상 존재하지 않는 경우 파일 시스템을 직접 쿼리하지 않아도 쿼리에서 <xref:System.IO.FileNotFoundException>을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="d9962-131">이 섹션의 일부 쿼리는 특정한 경우에 이러한 특정 예외를 사용하는 별도의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="d9962-132">또 다른 옵션은 <xref:System.IO.FileSystemWatcher>를 사용하여 데이터 소스가 동적으로 업데이트되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9962-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9962-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9962-133">See Also</span></span>  
 [<span data-ttu-id="d9962-134">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="d9962-134">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)

