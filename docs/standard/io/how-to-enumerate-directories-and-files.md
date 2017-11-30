---
title: "방법: 디렉터리 및 파일 열거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="cd304-102">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="cd304-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="cd304-103">디렉터리 및 파일 이름의 문자열을 포함하는 열거 가능한 컬렉션을 반환하는 메서드를 사용하여 디렉터리 및 파일을 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="cd304-104">열거 가능한 컬렉션을 반환 하는 메서드를 사용할 수도 있습니다 <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, 또는 <xref:System.IO.FileSystemInfo> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="cd304-105">열거 가능한 컬렉션은 대규모의 디렉터리 및 파일 컬렉션으로 작업할 때 배열보다 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="cd304-106">제공 하려면 이러한 방법 중에서 얻은 열거 가능한 컬렉션을 사용할 수도 있습니다는 <xref:System.Collections.Generic.IEnumerable%601> 와 같은 컬렉션의 생성자에 대 한 매개 변수 클래스는 <xref:System.Collections.Generic.List%601> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="cd304-107">디렉터리 또는 파일의 이름만 가져오려는 경우의 열거형 메서드를 사용는 <xref:System.IO.Directory> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="cd304-108">디렉터리 또는 파일의 다른 속성을 가져오는 경우 사용할는 <xref:System.IO.DirectoryInfo> 및 <xref:System.IO.FileSystemInfo> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="cd304-109">다음 표에서 열거 가능한 컬렉션을 반환 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="cd304-110">열거 하려면</span><span class="sxs-lookup"><span data-stu-id="cd304-110">To enumerate</span></span>|<span data-ttu-id="cd304-111">열거 가능한 컬렉션을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="cd304-111">Enumerable collection to return</span></span>|<span data-ttu-id="cd304-112">사용 하는 메서드</span><span class="sxs-lookup"><span data-stu-id="cd304-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="cd304-113">디렉터리</span><span class="sxs-lookup"><span data-stu-id="cd304-113">Directories</span></span>|<span data-ttu-id="cd304-114">디렉터리 이름</span><span class="sxs-lookup"><span data-stu-id="cd304-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="cd304-115">디렉터리 정보(<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="cd304-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cd304-116">파일</span><span class="sxs-lookup"><span data-stu-id="cd304-116">Files</span></span>|<span data-ttu-id="cd304-117">파일 이름</span><span class="sxs-lookup"><span data-stu-id="cd304-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="cd304-118">파일 정보(<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="cd304-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cd304-119">파일 시스템 정보</span><span class="sxs-lookup"><span data-stu-id="cd304-119">File system information</span></span>|<span data-ttu-id="cd304-120">파일 시스템 항목</span><span class="sxs-lookup"><span data-stu-id="cd304-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="cd304-121">파일 시스템 정보(<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="cd304-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="cd304-122"><xref:System.IO.SearchOption.AllDirectories> 열거형에서 제공된 <xref:System.IO.SearchOption> 검색 옵션을 사용하여 부모 디렉터리의 하위 디렉터리에 있는 모든 파일을 즉시 열거할 수 있지만, 이 경우 무단 액세스 예외(<xref:System.UnauthorizedAccessException>)로 인해 열거가 완료되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="cd304-123">이러한 예외를 가능한 경우에 catch 수 있으며 디렉터리를 먼저 열거 한 다음 파일을 열거 하 여 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="cd304-124">디렉터리 이름을 열거 하려면</span><span class="sxs-lookup"><span data-stu-id="cd304-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="cd304-125">사용 하 여는 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 메서드를 지정된 된 경로에서 최상위 디렉터리 이름의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="cd304-126">디렉터리 및 하위 디렉터리의 파일 이름을 열거하려면</span><span class="sxs-lookup"><span data-stu-id="cd304-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="cd304-127"><xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 메서드를 사용해 디렉터리와 그 하위 디렉터리(선택 사항)를 검색하여 지정된 검색 패턴과 일치하는 파일 이름의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="cd304-128">DirectoryInfo 개체의 컬렉션을 열거 하려면</span><span class="sxs-lookup"><span data-stu-id="cd304-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="cd304-129">사용 하 여 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 메서드 최상위 디렉터리의 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="cd304-130">모든 디렉터리의 FileInfo 개체의 컬렉션을 열거 하려면</span><span class="sxs-lookup"><span data-stu-id="cd304-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="cd304-131">사용 하 여 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 메서드 모든 디렉터리에서 지정 된 검색 패턴과 일치 하는 파일의 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="cd304-132">이 예에서는 먼저 가능한 무단된 액세스 예외를 catch 하는 최상위 디렉터리를 열거 하 고 파일을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd304-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cd304-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd304-133">See Also</span></span>  
 [<span data-ttu-id="cd304-134">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="cd304-134">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
