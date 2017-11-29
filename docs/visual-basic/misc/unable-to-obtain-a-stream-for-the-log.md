---
title: "로그에 대한 스트림을 가져올 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd3051b2331502c9f4f3430bbf88731b307d1b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a><span data-ttu-id="24619-102">로그에 대한 스트림을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24619-102">Unable to obtain a stream for the log</span></span>
<span data-ttu-id="24619-103">로그에 대한 스트림을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24619-103">Unable to obtain a stream for the log.</span></span> <span data-ttu-id="24619-104">에 기반한 파일 이름이 \<이름 >에서 이미 사용 중인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24619-104">Potential file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="24619-105"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 모든 잠재적 로그 파일 이름을 기반으로 하므로 클래스 새 로그 파일을 만들지 못했습니다 \<이름 >에서 이미 사용 중인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24619-105">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not create a new log file because all potential log file names based on \<name> are already in use.</span></span>  
  
 <span data-ttu-id="24619-106">로그 파일이 너무 많으면 응용 프로그램의 아키텍처 문제를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24619-106">Having too many log files may indicate an architectural problem with the application.</span></span> <span data-ttu-id="24619-107">자세한 내용은 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24619-107">See the documentation for the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class for more information.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="24619-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="24619-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="24619-109"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> 속성을 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> 또는 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> 로 설정하여 로그 파일 이름에 날짜 스탬프를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="24619-109">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> property to <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> or <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> to include a date-stamp in the log file name.</span></span>  
  
2.  <span data-ttu-id="24619-110"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 개체가 새 로그를 만들 수 있도록 기존 로그를 보관하고 컴퓨터에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="24619-110">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24619-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24619-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [<span data-ttu-id="24619-112">My.Application.Log 개체</span><span class="sxs-lookup"><span data-stu-id="24619-112">My.Application.Log Object</span></span>](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [<span data-ttu-id="24619-113">My.Log 개체</span><span class="sxs-lookup"><span data-stu-id="24619-113">My.Log Object</span></span>](../../visual-basic/language-reference/objects/my-log-object.md)
