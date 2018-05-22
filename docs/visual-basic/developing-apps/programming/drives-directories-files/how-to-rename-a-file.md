---
title: '방법: Visual Basic에서 파일 이름 바꾸기'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], renaming files
- files [Visual Basic], renaming
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
ms.openlocfilehash: ef024f90567d8d69bdd432499db96e4f67578ce5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-rename-a-file-in-visual-basic"></a><span data-ttu-id="700eb-102">방법: Visual Basic에서 파일 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="700eb-102">How to: Rename a File in Visual Basic</span></span>
<span data-ttu-id="700eb-103">`My.Computer.FileSystem` 개체의 `RenameFile` 메서드를 사용하면 현재 위치, 파일 이름 및 새 파일 이름을 제공하여 파일 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="700eb-103">Use the `RenameFile` method of the `My.Computer.FileSystem` object to rename a file by supplying the current location, file name, and the new file name.</span></span> <span data-ttu-id="700eb-104">이 메서드를 사용하여 파일을 이동할 수는 없습니다. 파일을 이동하고 파일 이름을 바꾸려면 `MoveFile` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="700eb-104">This method cannot be used to move a file; use the `MoveFile` method to move and rename the file.</span></span>  
  
### <a name="to-rename-a-file"></a><span data-ttu-id="700eb-105">파일 이름을 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="700eb-105">To rename a file</span></span>  
  
-   <span data-ttu-id="700eb-106">`My.Computer.FileSystem.RenameFile` 메서드를 사용하여 파일 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="700eb-106">Use the `My.Computer.FileSystem.RenameFile` method to rename a file.</span></span> <span data-ttu-id="700eb-107">이 예제에서는 `Test.txt` 파일의 이름을 `SecondTest.txt`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="700eb-107">This example renames the file named `Test.txt` to `SecondTest.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-rename-a-file_1.vb)]  
  
 <span data-ttu-id="700eb-108">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="700eb-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="700eb-109">코드 조각 선택에서 코드 조각은 **파일 시스템 - 드라이브, 폴더, 파일 처리**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="700eb-109">In the code snippet picker, the snippet is located in **File system - Processing Drives, Folders, and Files**.</span></span> <span data-ttu-id="700eb-110">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="700eb-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="700eb-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="700eb-111">Robust Programming</span></span>  
 <span data-ttu-id="700eb-112">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="700eb-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="700eb-113">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-113">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="700eb-114">`newName`에 경로 정보가 포함된 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-114">`newName` contains path information (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="700eb-115">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-115">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="700eb-116">`newName` 이 `Nothing` 이거나 빈 문자열인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-116">`newName` is `Nothing` or an empty string (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="700eb-117">소스 파일이 잘못되었거나 없는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-117">The source file is not valid or does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="700eb-118">`newName`에 지정된 이름의 기존 파일 또는 디렉터리가 있는 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-118">There is an existing file or directory with the name specified in `newName` (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="700eb-119">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-119">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="700eb-120">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-120">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="700eb-121">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="700eb-122">사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="700eb-122">The user does not have the required permission (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700eb-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="700eb-123">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>  
 [<span data-ttu-id="700eb-124">방법: 파일 이동</span><span class="sxs-lookup"><span data-stu-id="700eb-124">How to: Move a File</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)  
 [<span data-ttu-id="700eb-125">파일/디렉터리 만들기, 삭제 및 이동</span><span class="sxs-lookup"><span data-stu-id="700eb-125">Creating, Deleting, and Moving Files and Directories</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)  
 [<span data-ttu-id="700eb-126">방법: 동일한 디렉터리에 파일의 복사본 만들기</span><span class="sxs-lookup"><span data-stu-id="700eb-126">How to: Create a Copy of a File in the Same Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)  
 [<span data-ttu-id="700eb-127">방법: 다른 디렉터리에 파일의 복사본 만들기</span><span class="sxs-lookup"><span data-stu-id="700eb-127">How to: Create a Copy of a File in a Different Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)
