---
title: "방법: Visual Basic에서 디렉터리를 다른 디렉터리에 복사"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- I/O [Visual Basic], copying directories
- I/O [Visual Basic], copying folders
- folders [Visual Basic], copying
- directories [Visual Basic], copying
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 72f20ee767902395439f420f14fc2e352297ad31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-a-directory-to-another-directory-in-visual-basic"></a><span data-ttu-id="4726e-102">방법: Visual Basic에서 디렉터리를 다른 디렉터리에 복사</span><span class="sxs-lookup"><span data-stu-id="4726e-102">How to: Copy a Directory to Another Directory in Visual Basic</span></span>
<span data-ttu-id="4726e-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> 메서드를 사용하여 디렉터리를 다른 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-103">Use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> method to copy a directory to another directory.</span></span> <span data-ttu-id="4726e-104">이 메서드는 디렉터리 자체뿐만 아니라 디렉터리 내용을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-104">This method copies the contents of the directory as well as the directory itself.</span></span> <span data-ttu-id="4726e-105">대상 디렉터리가 없는 경우 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-105">If the target directory does not exist, it will be created.</span></span> <span data-ttu-id="4726e-106">같은 이름의 디렉터리가 대상 위치에 있고 `overwrite`가 `False`로 설정된 경우 두 디렉터리의 내용이 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-106">If a directory with the same name exists in the target location and `overwrite` is set to `False`, the contents of the two directories will be merged.</span></span> <span data-ttu-id="4726e-107">작업 중에 디렉터리의 새 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-107">You can specify a new name for the directory during the operation.</span></span>  
  
 <span data-ttu-id="4726e-108">디렉터리 내의 파일을 복사하는 경우 `overwrite`가 `False`로 설정된 동안 병합 중에 있는 파일 등의 특정 파일에서 발생하는 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-108">When copying files within a directory, exceptions may be thrown that are caused by specific file, such as a file existing during a merge while `overwrite` is set to `False`.</span></span> <span data-ttu-id="4726e-109">이러한 예외가 throw되면 `Data` 속성이 파일 또는 디렉터리 경로가 키이고 특정 예외 메시지가 해당 값에 포함된 항목을 저장하는 단일 예외에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-109">When such exceptions are thrown, they are consolidated into a single exception, whose `Data` property holds entries in which the file or directory path is the key and the specific exception message is contained in the corresponding value.</span></span>  
  
### <a name="to-copy-a-directory-to-another-directory"></a><span data-ttu-id="4726e-110">디렉터리를 다른 디렉터리에 복사하려면</span><span class="sxs-lookup"><span data-stu-id="4726e-110">To copy a directory to another directory</span></span>  
  
-   <span data-ttu-id="4726e-111">소스 및 대상 디렉터리 이름을 지정하여 `CopyDirectory` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-111">Use the `CopyDirectory` method, specifying source and destination directory names.</span></span> <span data-ttu-id="4726e-112">다음 예제에서는 `TestDirectory1`이라는 디렉터리를 `TestDirectory2`에 복사하고 기존 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-112">The following example copies the directory named `TestDirectory1` into `TestDirectory2`, overwriting existing files.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]  
  
     <span data-ttu-id="4726e-113">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-113">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="4726e-114">코드 조각 선택에서 **파일 시스템 - 드라이브, 폴더, 파일 처리**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-114">In the code snippet picker, it is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="4726e-115">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4726e-115">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4726e-116">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4726e-116">Robust Programming</span></span>  
 <span data-ttu-id="4726e-117">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4726e-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4726e-118">디렉터리에 대해 지정된 새 이름이 콜론(:) 또는 슬래시(\ 또는 /)를 포함하는 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-118">The new name specified for the directory contains a colon (:) or slash (\ or /) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4726e-119">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4726e-120">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="4726e-121">`destinationDirectoryName`이 `Nothing` 또는 빈 문자열인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-121">`destinationDirectoryName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="4726e-122">소스 디렉터리가 없는 경우(<xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-122">The source directory does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="4726e-123">소스 디렉터리가 루트 디렉터리인 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-123">The source directory is a root directory (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4726e-124">조합된 경로가 기존 파일을 가리키는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-124">The combined path points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4726e-125">소스 경로 및 대상 경로가 동일한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-125">The source path and target path are the same (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4726e-126">`ShowUI`가 `UIOption.AllDialogs`로 설정되었으며 사용자가 작업을 취소하거나 디렉터리에 있는 하나 이상의 파일을 복사할 수 없는 경우(<xref:System.OperationCanceledException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-126">`ShowUI` is set to `UIOption.AllDialogs` and the user cancels the operation, or one or more files in the directory cannot be copied (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="4726e-127">작업이 순환 방식인 경우(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-127">The operation is cyclic (<xref:System.InvalidOperationException>).</span></span>  
  
-   <span data-ttu-id="4726e-128">경로에 콜론(:)이 포함된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-128">The path contains a colon (:) (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="4726e-129">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-129">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="4726e-130">경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-130">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="4726e-131">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-131">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="4726e-132">대상 파일이 있지만 액세스할 수 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="4726e-132">A destination file exists but cannot be accessed (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4726e-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4726e-133">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>  
 [<span data-ttu-id="4726e-134">방법: 특정 패턴의 하위 디렉터리 찾기</span><span class="sxs-lookup"><span data-stu-id="4726e-134">How to: Find Subdirectories with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)  
 [<span data-ttu-id="4726e-135">방법: 디렉터리의 파일 컬렉션 가져오기</span><span class="sxs-lookup"><span data-stu-id="4726e-135">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
