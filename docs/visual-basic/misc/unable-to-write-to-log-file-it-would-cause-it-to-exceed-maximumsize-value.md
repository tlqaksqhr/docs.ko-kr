---
title: "MaximumSize 값을 초과할 수 있기 때문에 로그 파일에 쓸 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4004dca2a3b9f13583cfdfe43f89bc4bff5dd6d6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="9e4c7-102">MaximumSize 값을 초과할 수 있기 때문에 로그 파일에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e4c7-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>
<span data-ttu-id="9e4c7-103"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스가 다음 이유로 로그 파일에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e4c7-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
-   <span data-ttu-id="9e4c7-104">로그 파일 크기(바이트)가 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 속성의 값보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="9e4c7-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="9e4c7-105">—그리고—</span><span class="sxs-lookup"><span data-stu-id="9e4c7-105">—and—</span></span>  
  
-   <span data-ttu-id="9e4c7-106"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성의 값이 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>이었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e4c7-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9e4c7-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9e4c7-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="9e4c7-108"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 개체가 새 로그를 만들 수 있도록 기존 로그를 보관하고 컴퓨터에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9e4c7-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2.  <span data-ttu-id="9e4c7-109">더 큰 로그를 허용하도록 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 속성의 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9e4c7-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3.  <span data-ttu-id="9e4c7-110">로그가 너무 큰 경우 경고 없이 메시지를 무시하도록 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성을 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e4c7-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4c7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e4c7-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 [<span data-ttu-id="9e4c7-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="9e4c7-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [<span data-ttu-id="9e4c7-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="9e4c7-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
