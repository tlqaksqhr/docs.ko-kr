---
title: "방법: Visual Basic에서 특정 패턴의 파일 찾기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], finding
- pattern matching
- patterns, matching
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce37e7241eb33c3d4f18355d3b5375e0de95b28f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-files-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="71335-102">방법: Visual Basic에서 특정 패턴의 파일 찾기</span><span class="sxs-lookup"><span data-stu-id="71335-102">How to: Find Files with a Specific Pattern in Visual Basic</span></span>
<span data-ttu-id="71335-103"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> 메서드는 파일의 경로 이름을 나타내는 읽기 전용 문자열 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71335-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="71335-104">`wildCards` 매개 변수를 사용하여 특정 패턴을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71335-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="71335-105">하위 디렉터리를 검색에 포함하려면 `searchType` 매개 변수를 `SearchOption.SearchAllSubDirectories`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="71335-105">If you would like to include subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="71335-106">지정한 패턴과 일치하는 파일이 없으면 빈 컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="71335-106">An empty collection is returned if no files matching the specified pattern are found.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71335-107">`System.IO` 네임스페이스의 `DirectoryInfo` 클래스를 사용하여 파일 목록을 반환하는 방법에 대한 자세한 내용은 <xref:System.IO.DirectoryInfo.GetFiles%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71335-107">For information about returning a file list by using the `DirectoryInfo` class of the `System.IO` namespace, see <xref:System.IO.DirectoryInfo.GetFiles%2A>.</span></span>  
  
### <a name="to-find-files-with-a-specified-pattern"></a><span data-ttu-id="71335-108">지정된 패턴의 파일을 찾으려면</span><span class="sxs-lookup"><span data-stu-id="71335-108">To find files with a specified pattern</span></span>  
  
-   <span data-ttu-id="71335-109">검색하려는 디렉터리의 이름 및 경로를 제공하고 패턴을 지정하여 `GetFiles` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="71335-109">Use the `GetFiles` method, supplying the name and path of the directory you want to search and specifying the pattern.</span></span> <span data-ttu-id="71335-110">다음 예제에서는 디렉터리에서 `.dll` 확장명을 가진 모든 파일을 반환하고 `ListBox1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="71335-110">The following example returns all files with the extension `.dll` in the directory and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="71335-111">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="71335-111">.NET Framework Security</span></span>  
 <span data-ttu-id="71335-112">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="71335-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="71335-113">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="71335-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="71335-114">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="71335-114">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="71335-115">`directory`가 없는 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="71335-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="71335-116">`directory`가 기존 파일을 가리키는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="71335-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="71335-117">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="71335-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="71335-118">경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="71335-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="71335-119">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="71335-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="71335-120">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="71335-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71335-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71335-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>  
 [<span data-ttu-id="71335-122">방법: 특정 패턴의 하위 디렉터리 찾기</span><span class="sxs-lookup"><span data-stu-id="71335-122">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)  
 [<span data-ttu-id="71335-123">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="71335-123">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 [<span data-ttu-id="71335-124">방법: 디렉터리의 파일 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="71335-124">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
