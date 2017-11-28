---
title: "방법: Visual Basic에서 이진 파일 읽기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea6056f7d33b1137abb19b24246ce6874ff4d008
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a><span data-ttu-id="37ea9-102">방법: Visual Basic에서 이진 파일 읽기</span><span class="sxs-lookup"><span data-stu-id="37ea9-102">How to: Read From Binary Files in Visual Basic</span></span>
<span data-ttu-id="37ea9-103">`My.Computer.FileSystem` 개체는 이진 파일을 읽기 위한 `ReadAllBytes` 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-103">The `My.Computer.FileSystem` object provides the `ReadAllBytes` method for reading from binary files.</span></span>  
  
### <a name="to-read-from-a-binary-file"></a><span data-ttu-id="37ea9-104">이진 파일을 읽으려면</span><span class="sxs-lookup"><span data-stu-id="37ea9-104">To read from a binary file</span></span>  
  
-   <span data-ttu-id="37ea9-105">파일 내용을 바이트 배열로 반환하는 `ReadAllBytes` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-105">Use the `ReadAllBytes` method, which returns the contents of a file as a byte array.</span></span> <span data-ttu-id="37ea9-106">이 예제에서는 `C:/Documents and Settings/selfportrait.jpg` 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-106">This example reads from the file `C:/Documents and Settings/selfportrait.jpg`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]  
  
-   <span data-ttu-id="37ea9-107">큰 이진 파일의 경우 <xref:System.IO.FileStream> 개체의 <xref:System.IO.FileStream.Read%2A> 메서드를 사용하여 파일에서 한 번에 지정된 양만큼만 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-107">For large binary files, you can use the <xref:System.IO.FileStream.Read%2A> method of the <xref:System.IO.FileStream> object to read from the file only a specified amount at a time.</span></span> <span data-ttu-id="37ea9-108">그런 다음 각 읽기 작업에 대해 메모리에 로드되는 파일 크기를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-108">You can then limit how much of the file is loaded into memory for each read operation.</span></span> <span data-ttu-id="37ea9-109">다음 코드 예제에서는 파일을 복사하고, 호출자가 읽기 작업당 메모리로 읽어오는 파일 크기를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-109">The following code example copies a file and allows the caller to specify how much of the file is read into memory per read operation.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="37ea9-110">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="37ea9-110">Robust Programming</span></span>  
 <span data-ttu-id="37ea9-111">다음 조건에서는 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-111">The following conditions may cause an exception to be thrown:</span></span>  
  
-   <span data-ttu-id="37ea9-112">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="37ea9-113">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="37ea9-114">파일이 없는 경우(<xref:System.IO.FileNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-114">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="37ea9-115">다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-115">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="37ea9-116">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-116">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="37ea9-117">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-117">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="37ea9-118">문자열을 버퍼에 쓰기 위한 메모리가 부족한 경우(<xref:System.OutOfMemoryException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-118">There is not enough memory to write the string to buffer (<xref:System.OutOfMemoryException>).</span></span>  
  
-   <span data-ttu-id="37ea9-119">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="37ea9-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
 <span data-ttu-id="37ea9-120">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-120">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="37ea9-121">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-121">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="37ea9-122">응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-122">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="37ea9-123">파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ea9-123">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ea9-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37ea9-124">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>  
 [<span data-ttu-id="37ea9-125">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="37ea9-125">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [<span data-ttu-id="37ea9-126">방법: 여러 형식의 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="37ea9-126">How to: Read From Text Files with Multiple Formats</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)  
 [<span data-ttu-id="37ea9-127">데이터를 클립보드에 저장하고 클립보드에서 읽기</span><span class="sxs-lookup"><span data-stu-id="37ea9-127">Storing Data to and Reading from the Clipboard</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
