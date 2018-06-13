---
title: '방법: Visual Basic에서 텍스트 파일에 추가'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [Visual Basic], appending to files
- I/O [Visual Basic], My.Computer.FileSystem.WriteAllText method
- I/O [Visual Basic], WriteAllText method
ms.assetid: bbbd7fb5-f169-41a9-b53f-520ea9613913
ms.openlocfilehash: 78d98dcf098966de435254926af21db76b7bccfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585738"
---
# <a name="how-to-append-to-text-files-in-visual-basic"></a><span data-ttu-id="b5386-102">방법: Visual Basic에서 텍스트 파일에 추가</span><span class="sxs-lookup"><span data-stu-id="b5386-102">How to: Append to Text Files in Visual Basic</span></span>
<span data-ttu-id="b5386-103"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드는 `append` 매개 변수가 `True`로 설정되도록 지정하여 텍스트 파일에 추가하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5386-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method can be used to append to a text file by specifying that the `append` parameter is set to `True`.</span></span>  
  
### <a name="to-append-to-a-text-file"></a><span data-ttu-id="b5386-104">텍스트 파일에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="b5386-104">To append to a text file</span></span>  
  
-   <span data-ttu-id="b5386-105">대상 파일 및 추가할 문자열을 지정하고 `append` 매개 변수를 `True`로 설정하여 `WriteAllText` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5386-105">Use the `WriteAllText` method, specifying the target file and string to be appended and setting the `append` parameter to `True`.</span></span>  
  
     <span data-ttu-id="b5386-106">이 예제에서는 `Testfile.txt`라는 파일에 `"This is a test string."` 문자열을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="b5386-106">This example writes the string `"This is a test string."` to the file named `Testfile.txt`.</span></span>  
  
     [!code-vb[VbFileIOWrite#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-append-to-text-files_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b5386-107">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b5386-107">Robust Programming</span></span>  
 <span data-ttu-id="b5386-108">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b5386-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b5386-109">길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="b5386-109">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="b5386-110">경로가 `Nothing`이기 때문에 올바르지 않은 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="b5386-110">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="b5386-111">`File`이 존재하지 않는 경로를 가리키는 경우(<xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.DirectoryNotFoundException>)</span><span class="sxs-lookup"><span data-stu-id="b5386-111">`File` points to a path that does not exist (<xref:System.IO.FileNotFoundException> or <xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="b5386-112">다른 프로세스에서 파일을 사용 중이거나 I/O 오류가 발생한 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="b5386-112">The file is in use by another process, or an I/O error occurs (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="b5386-113">경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)</span><span class="sxs-lookup"><span data-stu-id="b5386-113">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="b5386-114">경로의 파일 이름이나 디렉터리 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="b5386-114">A file or directory name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="b5386-115">경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="b5386-115">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5386-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5386-116">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 [<span data-ttu-id="b5386-117">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="b5386-117">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
