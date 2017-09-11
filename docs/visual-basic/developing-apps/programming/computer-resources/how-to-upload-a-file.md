---
title: "방법: Visual Basic에서 파일 업로드"
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
- networks, uploading files
- files, uploading
- uploading files
- UploadFile method
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 29baf1f420cece6e0b05f9638b30a326178a013d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="e93b0-102">방법: Visual Basic에서 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="e93b0-102">How to: Upload a File in Visual Basic</span></span>
<span data-ttu-id="e93b0-103"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> 메서드는 파일을 업로드하고 원격 위치에 저장하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="e93b0-104">`ShowUI` 매개 변수를 `True`로 설정하면 업로드 진행률을 표시하고 사용자가 작업을 취소할 수 있도록 하는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="e93b0-105">파일을 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="e93b0-105">To upload a file</span></span>  
  
-   <span data-ttu-id="e93b0-106">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI(Uniform Resource Identifier)로 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다. 이 예제에서는 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     <span data-ttu-id="e93b0-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e93b0-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span></span>  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="e93b0-108">파일을 업로드하고 작업 진행률을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="e93b0-108">To upload a file and show the progress of the operation</span></span>  
  
-   <span data-ttu-id="e93b0-109">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-109">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="e93b0-110">이 예제에서는 사용자 이름 또는 암호를 제공하지 않고 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드하며, 업로드 진행률을 표시하고, 시간 제한 간격으로 500밀리초가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-110">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     <span data-ttu-id="e93b0-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e93b0-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span></span>  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="e93b0-112">사용자 이름 및 암호를 제공하여 파일을 업로드하려면</span><span class="sxs-lookup"><span data-stu-id="e93b0-112">To upload a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="e93b0-113">소스 파일 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하고 사용자 이름 및 암호를 지정하여 `UploadFile` 메서드를 통해 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-113">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="e93b0-114">이 예제에서는 사용자 이름 `anonymous` 및 빈 암호를 제공하여 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-114">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     <span data-ttu-id="e93b0-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e93b0-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e93b0-116">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e93b0-116">Robust Programming</span></span>  
 <span data-ttu-id="e93b0-117">다음 조건에서는 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e93b0-117">The following conditions may throw an exception:</span></span>  
  
-   <span data-ttu-id="e93b0-118">로컬 파일 경로가 잘못된 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="e93b0-118">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="e93b0-119">인증에 실패한 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="e93b0-119">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="e93b0-120">연결 시간이 초과된 경우(<xref:System.TimeoutException>)</span><span class="sxs-lookup"><span data-stu-id="e93b0-120">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e93b0-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e93b0-121">See Also</span></span>  
 <span data-ttu-id="e93b0-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e93b0-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span></span>   
 <span data-ttu-id="e93b0-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span><span class="sxs-lookup"><span data-stu-id="e93b0-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span></span>   
 <span data-ttu-id="e93b0-124">[방법: 파일 다운로드](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="e93b0-124">[How to: Download a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span></span>  
 [<span data-ttu-id="e93b0-125">방법: 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="e93b0-125">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

