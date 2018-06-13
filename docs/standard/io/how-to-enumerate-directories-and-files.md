---
title: '방법: 디렉터리 및 파일 열거'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cd7b7542e5cf9352e965717368399dcf4a9ecd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575852"
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="cff83-102">방법: 디렉터리 및 파일 열거</span><span class="sxs-lookup"><span data-stu-id="cff83-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="cff83-103">디렉터리 및 파일 이름의 문자열을 포함하는 열거 가능한 컬렉션을 반환하는 메서드를 사용하여 디렉터리 및 파일을 열거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="cff83-104">또한 <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo> 또는 <xref:System.IO.FileSystemInfo> 개체의 열거 가능한 컬렉션을 반환하는 메서드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="cff83-105">열거 가능한 컬렉션은 대규모의 디렉터리 및 파일 컬렉션으로 작업할 때 배열보다 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="cff83-106">또한 이러한 메서드에서 가져온 열거 가능한 컬렉션을 사용하여 <xref:System.Collections.Generic.List%601> 클래스와 같은 컬렉션 클래스의 생성자에 대한 <xref:System.Collections.Generic.IEnumerable%601> 매개 변수를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="cff83-107">디렉터리 또는 파일의 이름만 가져오려면 <xref:System.IO.Directory> 클래스의 열거 메서드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="cff83-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="cff83-108">디렉터리 또는 파일의 다른 속성을 가져오려면 <xref:System.IO.DirectoryInfo> 및 <xref:System.IO.FileSystemInfo> 클래스를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="cff83-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="cff83-109">다음 표는 열거 가능한 컬렉션을 반환하는 메서드에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="cff83-110">열거 대상</span><span class="sxs-lookup"><span data-stu-id="cff83-110">To enumerate</span></span>|<span data-ttu-id="cff83-111">반환할 열거 가능한 컬렉션</span><span class="sxs-lookup"><span data-stu-id="cff83-111">Enumerable collection to return</span></span>|<span data-ttu-id="cff83-112">사용할 메서드</span><span class="sxs-lookup"><span data-stu-id="cff83-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="cff83-113">디렉터리</span><span class="sxs-lookup"><span data-stu-id="cff83-113">Directories</span></span>|<span data-ttu-id="cff83-114">디렉터리 이름</span><span class="sxs-lookup"><span data-stu-id="cff83-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="cff83-115">디렉터리 정보(<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="cff83-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cff83-116">파일</span><span class="sxs-lookup"><span data-stu-id="cff83-116">Files</span></span>|<span data-ttu-id="cff83-117">파일 이름</span><span class="sxs-lookup"><span data-stu-id="cff83-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="cff83-118">파일 정보(<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="cff83-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="cff83-119">파일 시스템 정보</span><span class="sxs-lookup"><span data-stu-id="cff83-119">File system information</span></span>|<span data-ttu-id="cff83-120">파일 시스템 항목</span><span class="sxs-lookup"><span data-stu-id="cff83-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="cff83-121">파일 시스템 정보(<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="cff83-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="cff83-122"><xref:System.IO.SearchOption.AllDirectories> 열거형에서 제공된 <xref:System.IO.SearchOption> 검색 옵션을 사용하여 부모 디렉터리의 하위 디렉터리에 있는 모든 파일을 즉시 열거할 수 있지만, 이 경우 무단 액세스 예외(<xref:System.UnauthorizedAccessException>)로 인해 열거가 완료되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="cff83-123">이러한 예외가 발생할 경우 이를 catch하고 먼저 디렉터리를 열거한 다음, 파일을 열거하여 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="cff83-124">디렉터리 이름을 열거하려면</span><span class="sxs-lookup"><span data-stu-id="cff83-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="cff83-125">지정된 경로에서 최상위 디렉터리 이름의 목록을 가져오려면 <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="cff83-126">디렉터리 및 하위 디렉터리의 파일 이름을 열거하려면</span><span class="sxs-lookup"><span data-stu-id="cff83-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="cff83-127"><xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> 메서드를 사용해 디렉터리와 그 하위 디렉터리(선택 사항)를 검색하여 지정된 검색 패턴과 일치하는 파일 이름의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="cff83-128">DirectoryInfo 개체의 컬렉션을 열거하려면</span><span class="sxs-lookup"><span data-stu-id="cff83-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="cff83-129">최상위 디렉터리의 컬렉션을 가져오려면 <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="cff83-130">모든 디렉터리에서 FileInfo 개체의 컬렉션을 열거하려면</span><span class="sxs-lookup"><span data-stu-id="cff83-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="cff83-131">모든 디렉터리에서 지정된 검색 패턴과 일치하는 파일의 컬렉션을 가져오려면 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="cff83-132">이 예제는 먼저 최상위 디렉터리를 열거하여 가능한 권한 없는 액세스 예외를 catch하고 파일을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="cff83-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cff83-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cff83-133">See Also</span></span>  
 [<span data-ttu-id="cff83-134">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="cff83-134">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
