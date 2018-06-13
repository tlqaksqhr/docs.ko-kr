---
title: '방법: Visual Basic에서 파일 다운로드'
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: b0dc95674e17a7aba9b04a8b7e0b82c9c97c4180
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590732"
---
# <a name="how-to-download-a-file-in-visual-basic"></a><span data-ttu-id="b04cd-102">방법: Visual Basic에서 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="b04cd-102">How to: Download a File in Visual Basic</span></span>
<span data-ttu-id="b04cd-103"><xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> 메서드를 사용하여 원격 파일을 다운로드한 다음 특정 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-103">The <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> method can be used to download a remote file and store it to a specific location.</span></span> <span data-ttu-id="b04cd-104">`ShowUI` 매개 변수가 `True`로 설정된 경우 다운로드 진행률을 표시하고 사용자가 작업을 취소할 수 있도록 하는 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed showing the progress of the download and allowing users to cancel the operation.</span></span> <span data-ttu-id="b04cd-105">기본적으로 동일한 이름의 기존 파일을 덮어쓰지 않습니다. 기존 파일을 덮어쓰려는 경우 `overwrite` 매개 변수를 `True`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-105">By default, existing files having the same name are not overwritten; if you want to overwrite existing files, set the `overwrite` parameter to `True`.</span></span>  
  
 <span data-ttu-id="b04cd-106">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-106">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b04cd-107">드라이브 이름이 잘못된 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="b04cd-107">Drive name is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="b04cd-108">필요한 인증이 제공되지 않은 경우(<xref:System.UnauthorizedAccessException> 또는 <xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="b04cd-108">Necessary authentication has not been supplied (<xref:System.UnauthorizedAccessException> or <xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="b04cd-109">서버가 지정된 `connectionTimeout` 내에 응답하지 않는 경우(<xref:System.TimeoutException>)</span><span class="sxs-lookup"><span data-stu-id="b04cd-109">The server does not respond within the specified `connectionTimeout` (<xref:System.TimeoutException>).</span></span>  
  
-   <span data-ttu-id="b04cd-110">웹 사이트에서 요청을 거부하는 경우(<xref:System.Net.WebException>)</span><span class="sxs-lookup"><span data-stu-id="b04cd-110">The request is denied by the Web site (<xref:System.Net.WebException>).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
> [!IMPORTANT]
>  <span data-ttu-id="b04cd-111">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-111">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="b04cd-112">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-112">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="b04cd-113">응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-113">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="b04cd-114">파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-114">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
### <a name="to-download-a-file"></a><span data-ttu-id="b04cd-115">파일을 다운로드하려면</span><span class="sxs-lookup"><span data-stu-id="b04cd-115">To download a file</span></span>  
  
-   <span data-ttu-id="b04cd-116">대상 파일의 위치를 문자열 또는 URI로 지정하고 파일을 저장할 위치를 지정하여 `DownloadFile` 메서드를 통해 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-116">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file.</span></span> <span data-ttu-id="b04cd-117">이 예제에서는 `http://www.cohowinery.com/downloads`에서 `WineList.txt` 파일을 다운로드하고 `C:\Documents and Settings\All Users\Documents`에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-117">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`:</span></span>  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### <a name="to-download-a-file-specifying-a-time-out-interval"></a><span data-ttu-id="b04cd-118">시간 제한 간격을 지정하여 파일을 다운로드하려면</span><span class="sxs-lookup"><span data-stu-id="b04cd-118">To download a file, specifying a time-out interval</span></span>  
  
-   <span data-ttu-id="b04cd-119">대상 파일의 위치를 문자열 또는 URI로 지정하고, 파일을 저장할 위치를 지정하고, 시간 제한 간격을 밀리초 단위로 지정(기본값은 1000)하여 `DownloadFile` 메서드를 통해 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-119">Use the `DownloadFile` method to download the file, specifying the target file's location as a string or URI, specifying the location at which to store the file, and specifying the time-out interval in milliseconds (the default is 1000).</span></span> <span data-ttu-id="b04cd-120">이 예제에서는 시간 제한 간격을 500밀리초로 지정하여 `http://www.cohowinery.com/downloads`에서 `WineList.txt` 파일을 다운로드하고 `C:\Documents and Settings\All Users\Documents`에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-120">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, specifying a time-out interval of 500 milliseconds:</span></span>  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### <a name="to-download-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="b04cd-121">사용자 이름 및 암호를 제공하여 파일을 다운로드하려면</span><span class="sxs-lookup"><span data-stu-id="b04cd-121">To download a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="b04cd-122">대상 파일의 위치를 문자열 또는 URI로 지정하고 파일을 저장할 위치, 사용자 이름 및 암호를 지정하여 `DownLoadFile` 메서드를 통해 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-122">Use the `DownLoadFile` method to download the file, specifying the target file's location as a string or URI and specifying the location at which to store the file, the user name, and the password.</span></span> <span data-ttu-id="b04cd-123">이 예제에서는 사용자 이름 `anonymous` 및 빈 암호를 사용하여 `http://www.cohowinery.com/downloads`에서 `WineList.txt` 파일을 다운로드하고 `C:\Documents and Settings\All Users\Documents`에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-123">This example downloads the file `WineList.txt` from `http://www.cohowinery.com/downloads` and saves it to `C:\Documents and Settings\All Users\Documents`, with the user name `anonymous` and a blank password.</span></span>  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b04cd-124">`DownLoadFile` 메서드에서 사용되는 FTP 프로토콜은 암호 등의 정보를 일반 텍스트로 보내므로 중요한 정보 전송에 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b04cd-124">The FTP protocol used by the `DownLoadFile` method sends information, including passwords, in plain text and should not be used for transmitting sensitive information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04cd-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b04cd-125">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network>  
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>  
 [<span data-ttu-id="b04cd-126">방법: 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="b04cd-126">How to: Upload a File</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)  
 [<span data-ttu-id="b04cd-127">방법: 파일 경로의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="b04cd-127">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
