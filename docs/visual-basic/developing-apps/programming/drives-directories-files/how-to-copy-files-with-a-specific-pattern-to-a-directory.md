---
title: "방법: Visual Basic에서 특정 패턴의 파일을 디렉터리에 복사"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ead158a95d7f3ef4d0cd650b3b1a1db7042ccb29
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a><span data-ttu-id="ff973-102">방법: Visual Basic에서 특정 패턴의 파일을 디렉터리에 복사</span><span class="sxs-lookup"><span data-stu-id="ff973-102">How to: Copy Files with a Specific Pattern to a Directory in Visual Basic</span></span>
<span data-ttu-id="ff973-103"><xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> 메서드는 파일의 경로 이름을 나타내는 읽기 전용 문자열 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-103">The <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> method returns a read-only collection of strings representing the path names for the files.</span></span> <span data-ttu-id="ff973-104">`wildCards` 매개 변수를 사용하여 특정 패턴을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span>  
  
 <span data-ttu-id="ff973-105">일치하는 파일이 없으면 빈 컬렉션이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-105">An empty collection is returned if no matching files are found.</span></span>  
  
 <span data-ttu-id="ff973-106"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> 메서드를 사용하여 파일을 디렉터리로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-106">You can use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> method to copy the files to a directory.</span></span>  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a><span data-ttu-id="ff973-107">특정 패턴의 파일을 디렉터리로 복사하려면</span><span class="sxs-lookup"><span data-stu-id="ff973-107">To copy files with a specific pattern to a directory</span></span>  
  
1.  <span data-ttu-id="ff973-108">`GetFiles` 메서드를 사용하여 파일 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-108">Use the `GetFiles` method to return the list of files.</span></span> <span data-ttu-id="ff973-109">이 예제에서는 지정된 디렉터리에 있는 .rtf 파일을 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-109">This example returns all .rtf files in the specified directory.</span></span>  
  
     [!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]  
  
2.  <span data-ttu-id="ff973-110">`CopyFile` 메서드를 사용하여 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-110">Use the `CopyFile` method to copy the files.</span></span> <span data-ttu-id="ff973-111">이 예제에서는 `testdirectory`라는 디렉터리로 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-111">This example copies the files to the directory named `testdirectory`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]  
  
3.  <span data-ttu-id="ff973-112">`For` 문으로 `Next` 문을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-112">Close the `For` statement with a `Next` statement.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="ff973-113">예제</span><span class="sxs-lookup"><span data-stu-id="ff973-113">Example</span></span>  
 <span data-ttu-id="ff973-114">위 코드 조각의 완전한 형식인 다음 예제에서는 지정된 디렉터리의 모든 .rtf 파일을 `testdirectory`라는 이름의 디렉터리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-114">The following example, which presents the above snippets in complete form, copies all .rtf files in the specified directory to the directory named `testdirectory`.</span></span>  
  
 [!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="ff973-115">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ff973-115">.NET Framework Security</span></span>  
 <span data-ttu-id="ff973-116">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ff973-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ff973-117">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-117">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="ff973-118">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-118">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="ff973-119">디렉터리가 없는 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-119">The directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="ff973-120">디렉터리가 기존 파일을 가리키는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-120">The directory points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="ff973-121">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="ff973-122">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-122">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="ff973-123">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-123">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span> <span data-ttu-id="ff973-124">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="ff973-124">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff973-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff973-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>  
 [<span data-ttu-id="ff973-126">방법: 특정 패턴의 하위 디렉터리 찾기</span><span class="sxs-lookup"><span data-stu-id="ff973-126">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)  
 [<span data-ttu-id="ff973-127">문제 해결: 텍스트 파일 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="ff973-127">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)  
 [<span data-ttu-id="ff973-128">방법: 디렉터리의 파일 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="ff973-128">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
