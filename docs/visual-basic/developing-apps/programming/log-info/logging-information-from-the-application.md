---
title: 응용 프로그램의 정보 기록(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: 68ec09dac026e46716ff18dce88acf9d60635026
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589934"
---
# <a name="logging-information-from-the-application-visual-basic"></a><span data-ttu-id="a5740-102">응용 프로그램의 정보 기록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5740-102">Logging Information from the Application (Visual Basic)</span></span>
<span data-ttu-id="a5740-103">이 섹션에는 `My.Application.Log` 또는 `My.Log` 개체를 사용하여 응용 프로그램의 정보를 기록하는 방법과 응용 프로그램의 로깅 기능을 확장하는 방법을 설명하는 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-103">This section contains topics that cover how to log information from your application using the `My.Application.Log` or `My.Log` object, and how to extend the application's logging capabilities.</span></span>  
  
 <span data-ttu-id="a5740-104">`Log` 개체는 응용 프로그램의 로그 수신기에 정보를 쓰기 위한 메서드를 제공하고, `Log` 개체의 고급 `TraceSource` 속성은 자세한 구성 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-104">The `Log` object provides methods for writing information to the application's log listeners, and the `Log` object's advanced `TraceSource` property provides detailed configuration information.</span></span> <span data-ttu-id="a5740-105">`Log` 개체는 응용 프로그램의 구성 파일에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-105">The `Log` object is configured by the application's configuration file.</span></span>  
  
 <span data-ttu-id="a5740-106">`My.Log` 개체는 ASP.NET 응용 프로그램에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-106">The `My.Log` object is available only for ASP.NET applications.</span></span> <span data-ttu-id="a5740-107">클라이언트 응용 프로그램의 경우 `My.Application.Log`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-107">For client applications, use `My.Application.Log`.</span></span> <span data-ttu-id="a5740-108">자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5740-108">For more information, see <xref:Microsoft.VisualBasic.Logging.Log>.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="a5740-109">작업</span><span class="sxs-lookup"><span data-stu-id="a5740-109">Tasks</span></span>  
  
|<span data-ttu-id="a5740-110">대상</span><span class="sxs-lookup"><span data-stu-id="a5740-110">To</span></span>|<span data-ttu-id="a5740-111">보기</span><span class="sxs-lookup"><span data-stu-id="a5740-111">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="a5740-112">응용 프로그램의 로그에 이벤트 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-112">Write event information to the application's logs.</span></span>|[<span data-ttu-id="a5740-113">방법: 로그 메시지 쓰기</span><span class="sxs-lookup"><span data-stu-id="a5740-113">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|<span data-ttu-id="a5740-114">응용 프로그램의 로그에 예외 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-114">Write exception information to the application's logs.</span></span>|[<span data-ttu-id="a5740-115">방법: 예외 기록</span><span class="sxs-lookup"><span data-stu-id="a5740-115">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|<span data-ttu-id="a5740-116">응용 프로그램을 시작 및 종료할 때 응용 프로그램의 로그에 추적 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-116">Write trace information to the application's logs when the application starts and shuts down.</span></span>|[<span data-ttu-id="a5740-117">방법: 응용 프로그램이 시작 또는 종료될 때 메시지 기록</span><span class="sxs-lookup"><span data-stu-id="a5740-117">How to: Log Messages When the Application Starts or Shuts Down</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|<span data-ttu-id="a5740-118">텍스트 파일에 정보를 쓰도록 `My.Application.Log`를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-118">Configure `My.Application.Log` to write information to a text file.</span></span>|[<span data-ttu-id="a5740-119">방법: 텍스트 파일에 이벤트 정보 쓰기</span><span class="sxs-lookup"><span data-stu-id="a5740-119">How to: Write Event Information to a Text File</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|<span data-ttu-id="a5740-120">이벤트 로그에 정보를 쓰도록 `My.Application.Log`를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-120">Configure `My.Application.Log` to write information to an event log.</span></span>|[<span data-ttu-id="a5740-121">방법: 응용 프로그램 이벤트 로그에 쓰기</span><span class="sxs-lookup"><span data-stu-id="a5740-121">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|<span data-ttu-id="a5740-122">`My.Application.Log`가 정보를 쓰는 위치를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-122">Change where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="a5740-123">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="a5740-123">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="a5740-124">`My.Application.Log`가 정보를 쓰는 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-124">Determine where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="a5740-125">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="a5740-125">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="a5740-126">`My.Application.Log`에 대한 사용자 지정 로그 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-126">Create a custom log listener for `My.Application.Log`.</span></span>|[<span data-ttu-id="a5740-127">연습: 사용자 지정 로그 수신기 만들기</span><span class="sxs-lookup"><span data-stu-id="a5740-127">Walkthrough: Creating Custom Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|<span data-ttu-id="a5740-128">`My.Application.Log` 로그의 출력을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="a5740-128">Filter the output of the `My.Application.Log` logs.</span></span>|[<span data-ttu-id="a5740-129">연습: My.Application.Log 출력 필터링</span><span class="sxs-lookup"><span data-stu-id="a5740-129">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a><span data-ttu-id="a5740-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5740-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [<span data-ttu-id="a5740-131">응용 프로그램 로그 작업</span><span class="sxs-lookup"><span data-stu-id="a5740-131">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="a5740-132">문제 해결: 로그 수신기</span><span class="sxs-lookup"><span data-stu-id="a5740-132">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
