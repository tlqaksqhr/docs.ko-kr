---
title: '방법: Visual Basic에서 파일 업로드'
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: 769c04430f8323dfde680fca45cfcd67809bdab0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="8ed4c-102">방법: Visual Basic에서 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="8ed4c-102">How to: Upload a File in Visual Basic</span></span>
<span data-ttu-id="8ed4c-103"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> 메서드는 파일을 업로드하고 원격 위치에 저장하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="8ed4c-104">`ShowUI` 매개 변수를 `True`로 설정하면 업로드 진행률을 표시하고 사용자가 작업을 취소할 수 있도록 하는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="8ed4c-105">파일을 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="8ed4c-105">To upload a file</span></span>  
  
-   <span data-ttu-id="8ed4c-106">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI(Uniform Resource Identifier)로 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다. 이 예제에서는 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     [!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="8ed4c-107">파일을 업로드하고 작업 진행률을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="8ed4c-107">To upload a file and show the progress of the operation</span></span>  
  
-   <span data-ttu-id="8ed4c-108">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-108">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="8ed4c-109">이 예제에서는 사용자 이름 또는 암호를 제공하지 않고 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드하며, 업로드 진행률을 표시하고, 시간 제한 간격으로 500밀리초가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-109">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     [!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="8ed4c-110">사용자 이름 및 암호를 제공하여 파일을 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="8ed4c-110">To upload a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="8ed4c-111">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하고 사용자 이름 및 암호를 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-111">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="8ed4c-112">이 예제에서는 사용자 이름 `anonymous` 및 빈 암호를 제공하여 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-112">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     [!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8ed4c-113">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8ed4c-113">Robust Programming</span></span>  
 <span data-ttu-id="8ed4c-114">다음 조건에서는 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed4c-114">The following conditions may throw an exception:</span></span>  
  
-   <span data-ttu-id="8ed4c-115">로컬 파일 경로가 잘못된 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="8ed4c-115">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="8ed4c-116">인증에 실패한 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="8ed4c-116">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="8ed4c-117">연결 시간이 초과된 경우(<xref:System.TimeoutException>)</span><span class="sxs-lookup"><span data-stu-id="8ed4c-117">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed4c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ed4c-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>  
 [<span data-ttu-id="8ed4c-119">방법: 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="8ed4c-119">How to: Download a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)  
 [<span data-ttu-id="8ed4c-120">방법: 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="8ed4c-120">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
