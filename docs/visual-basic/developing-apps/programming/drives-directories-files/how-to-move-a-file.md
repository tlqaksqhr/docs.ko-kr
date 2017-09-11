---
title: "방법: Visual Basic에서 파일 이동"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, moving
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5a2623ec7e440e8fdf85138cd0b3de9ab18b773c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-move-a-file-in-visual-basic"></a><span data-ttu-id="f0318-102">방법: Visual Basic에서 파일 이동</span><span class="sxs-lookup"><span data-stu-id="f0318-102">How to: Move a File in Visual Basic</span></span>
<span data-ttu-id="f0318-103">`My.Computer.FileSystem.MoveFile` 메서드를 사용하여 파일을 다른 폴더로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-103">The `My.Computer.FileSystem.MoveFile` method can be used to move a file to another folder.</span></span> <span data-ttu-id="f0318-104">대상 구조체가 없는 경우 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-104">If the target structure does not exist, it will be created.</span></span>  
  
### <a name="to-move-a-file"></a><span data-ttu-id="f0318-105">파일을 이동하려면</span><span class="sxs-lookup"><span data-stu-id="f0318-105">To move a file</span></span>  
  
-   <span data-ttu-id="f0318-106">`MoveFile` 메서드를 사용하여 소스 파일과 대상 파일의 위치 및 파일 이름을 지정하여 파일을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-106">Use the `MoveFile` method to move the file, specifying the file name and location for both the source file and the target file.</span></span> <span data-ttu-id="f0318-107">이 예제에서는 이름이 `test.txt` 인 파일을 `TestDir1` 에서 `TestDir2`로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-107">This example moves the file named `test.txt` from `TestDir1` to `TestDir2`.</span></span> <span data-ttu-id="f0318-108">여기서는 대상 파일 이름이 소스 파일 이름과 동일하더라도 대상 파일 이름을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-108">Note that the target file name is specified even though it is the same as the source file name.</span></span>  
  
     <span data-ttu-id="f0318-109">[!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0318-109">[!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_1.vb)]</span></span>  
  
### <a name="to-move-a-file-and-rename-it"></a><span data-ttu-id="f0318-110">파일을 이동하고 이름을 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="f0318-110">To move a file and rename it</span></span>  
  
-   <span data-ttu-id="f0318-111">`MoveFile` 메서드를 사용하여 소스 파일 이름과 위치, 대상 위치 및 대상 위치에서의 새 이름을 지정하여 파일을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-111">Use the `MoveFile` method to move the file, specifying the source file name and location, the target location, and the new name at the target location.</span></span> <span data-ttu-id="f0318-112">이 예제에서는 이름이 `test.txt` 인 파일을 `TestDir1` 에서 `TestDir2` 로 이동하고 이름을 `nexttest.txt`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-112">This example moves the file named `test.txt` from `TestDir1` to `TestDir2` and renames it `nexttest.txt`.</span></span>  
  
     <span data-ttu-id="f0318-113">[!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f0318-113">[!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-move-a-file_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f0318-114">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f0318-114">Robust Programming</span></span>  
 <span data-ttu-id="f0318-115">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f0318-115">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f0318-116">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-116">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="f0318-117">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-117">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="f0318-118">`destinationFileName` 이 `Nothing` 이거나 빈 문자열인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-118">`destinationFileName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="f0318-119">소스 파일이 잘못되었거나 존재하지 않는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-119">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="f0318-120">조합된 경로가 기존 디렉터리를 가리키거나, 대상 파일이 이미 있고 `overwrite` 가 `False`로 설정되었거나, 대상 디렉터리에 있는 동일한 이름의 파일이 사용 중이거나, 사용자에게 파일에 액세스할 권한이 없는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-120">The combined path points to an existing directory, the destination file exists and `overwrite` is set to `False`, a file in the target directory with the same name is in use, or the user does not have sufficient permissions to access the file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="f0318-121">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-121">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="f0318-122">`showUI` 가 `True`로 설정되고, `onUserCancel` 이 `ThrowException`으로 설정되고, 사용자가 작업을 취소했거나 지정되지 않은 I/O 오류가 발생한 경우(<xref:System.OperationCanceledException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-122">`showUI` is set to `True`, `onUserCancel` is set to `ThrowException`, and either the user has cancelled the operation or an unspecified I/O error occurs (<xref:System.OperationCanceledException>).</span></span>  
  
-   <span data-ttu-id="f0318-123">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-123">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="f0318-124">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="f0318-125">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="f0318-125">The user does not have required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0318-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0318-126">See Also</span></span>  
 <span data-ttu-id="f0318-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A></span><span class="sxs-lookup"><span data-stu-id="f0318-127"><xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A></span></span>   
 <span data-ttu-id="f0318-128">[방법: 파일 이름 바꾸기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="f0318-128">[How to: Rename a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md) </span></span>  
 <span data-ttu-id="f0318-129">[방법: 다른 디렉터리에 파일의 복사본 만들기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md) </span><span class="sxs-lookup"><span data-stu-id="f0318-129">[How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md) </span></span>  
 [<span data-ttu-id="f0318-130">방법: 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="f0318-130">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

