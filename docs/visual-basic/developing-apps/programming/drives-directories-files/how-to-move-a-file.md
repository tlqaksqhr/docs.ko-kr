---
title: "방법: Visual Basic에서 파일 이동"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: files [Visual Basic], moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 96c6d1d89c0dfe4720637202b42414047e96f146
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-a-file-in-visual-basic"></a><span data-ttu-id="2f15b-102">방법: Visual Basic에서 파일 이동</span><span class="sxs-lookup"><span data-stu-id="2f15b-102">How to: Move a File in Visual Basic</span></span>
<span data-ttu-id="2f15b-103">`My.Computer.FileSystem.MoveFile` 메서드를 사용하여 파일을 다른 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-103">The `My.Computer.FileSystem.MoveFile` method can be used to move a file to another folder.</span></span> <span data-ttu-id="2f15b-104">대상 구조체가 없는 경우 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-104">If the target structure does not exist, it will be created.</span></span>  
  
### <a name="to-move-a-file"></a><span data-ttu-id="2f15b-105">파일을 이동하려면</span><span class="sxs-lookup"><span data-stu-id="2f15b-105">To move a file</span></span>  
  
-   <span data-ttu-id="2f15b-106">`MoveFile` 메서드를 사용하여 소스 파일과 대상 파일의 위치 및 파일 이름을 지정하여 파일을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-106">Use the `MoveFile` method to move the file, specifying the file name and location for both the source file and the target file.</span></span> <span data-ttu-id="2f15b-107">이 예제에서는 이름이 `test.txt` 인 파일을 `TestDir1` 에서 `TestDir2`로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-107">This example moves the file named `test.txt` from `TestDir1` to `TestDir2`.</span></span> <span data-ttu-id="2f15b-108">여기서는 대상 파일 이름이 소스 파일 이름과 동일하더라도 대상 파일 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-108">Note that the target file name is specified even though it is the same as the source file name.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_1.vb)]  
  
### <a name="to-move-a-file-and-rename-it"></a><span data-ttu-id="2f15b-109">파일을 이동하고 이름을 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="2f15b-109">To move a file and rename it</span></span>  
  
-   <span data-ttu-id="2f15b-110">`MoveFile` 메서드를 사용하여 소스 파일 이름과 위치, 대상 위치 및 대상 위치에서의 새 이름을 지정하여 파일을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-110">Use the `MoveFile` method to move the file, specifying the source file name and location, the target location, and the new name at the target location.</span></span> <span data-ttu-id="2f15b-111">이 예제에서는 이름이 `test.txt` 인 파일을 `TestDir1` 에서 `TestDir2` 로 이동하고 이름을 `nexttest.txt`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-111">This example moves the file named `test.txt` from `TestDir1` to `TestDir2` and renames it `nexttest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_2.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="2f15b-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2f15b-112">Robust Programming</span></span>  
 <span data-ttu-id="2f15b-113">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2f15b-113">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="2f15b-114">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-114">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="2f15b-115">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="2f15b-116">`destinationFileName` 이 `Nothing` 이거나 빈 문자열인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-116">`destinationFileName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="2f15b-117">소스 파일이 잘못되었거나 존재하지 않는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-117">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="2f15b-118">조합된 경로가 기존 디렉터리를 가리키거나, 대상 파일이 이미 있고 `overwrite` 가 `False`로 설정되었거나, 대상 디렉터리에 있는 동일한 이름의 파일이 사용 중이거나, 사용자에게 파일에 액세스할 권한이 없는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-118">The combined path points to an existing directory, the destination file exists and `overwrite` is set to `False`, a file in the target directory with the same name is in use, or the user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="2f15b-119">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-119">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="2f15b-120">`showUI` 가 `True`로 설정되고, `onUserCancel` 이 `ThrowException`으로 설정되고, 사용자가 작업을 취소했거나 지정되지 않은 I/O 오류가 발생한 경우(<xref:System.OperationCanceledException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-120">`showUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and either the user has cancelled the operation or an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="2f15b-121">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="2f15b-122">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-122">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="2f15b-123">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="2f15b-123">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f15b-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f15b-124">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>  
 [<span data-ttu-id="2f15b-125">방법: 파일 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="2f15b-125">How to: Rename a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 [<span data-ttu-id="2f15b-126">방법: 다른 디렉터리에 파일의 복사본 만들기</span><span class="sxs-lookup"><span data-stu-id="2f15b-126">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)  
 [<span data-ttu-id="2f15b-127">방법: 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="2f15b-127">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
