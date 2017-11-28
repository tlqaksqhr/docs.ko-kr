---
title: "방법: Visual Basic에서 예외 기록"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 320bc5d06f4c8e673745b600fd369af287fe8105
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="d88e5-102">방법: Visual Basic에서 예외 기록</span><span class="sxs-lookup"><span data-stu-id="d88e5-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="d88e5-103">`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에서 발생하는 예외에 대한 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="d88e5-104">이 예제에서는 `My.Application.Log.WriteException` 메서드를 사용하여 명시적으로 catch하는 예외 및 처리되지 않은 예외를 기록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="d88e5-105">추적 정보를 기록하려면 `My.Application.Log.WriteEntry` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="d88e5-106">자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d88e5-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="d88e5-107">처리된 예외를 기록하려면</span><span class="sxs-lookup"><span data-stu-id="d88e5-107">To log a handled exception</span></span>  
  
1.  <span data-ttu-id="d88e5-108">예외 정보를 생성하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-108">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  <span data-ttu-id="d88e5-109">`Try...Catch` 블록을 사용하여 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-109">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  <span data-ttu-id="d88e5-110">예외를 생성할 수 있는 코드를 `Try` 블록에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-110">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="d88e5-111">`Dim` 및 `MsgBox` 줄의 주석 처리를 제거하여 <xref:System.NullReferenceException> 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-111">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  <span data-ttu-id="d88e5-112">`Catch` 블록에서 `My.Application.Log.WriteException` 메서드를 사용하여 예외 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-112">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     <span data-ttu-id="d88e5-113">다음 예제에서는 처리된 예외를 기록하기 위한 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-113">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="d88e5-114">처리되지 않은 예외를 기록하려면</span><span class="sxs-lookup"><span data-stu-id="d88e5-114">To log an unhandled exception</span></span>  
  
1.  <span data-ttu-id="d88e5-115">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d88e5-116">**프로젝트** 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-116">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="d88e5-117">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-117">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="d88e5-118">**응용 프로그램 이벤트 보기** 단추를 클릭하여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-118">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="d88e5-119">그러면 ApplicationEvents.vb 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-119">This opens the ApplicationEvents.vb file.</span></span>  
  
4.  <span data-ttu-id="d88e5-120">코드 편집기에서 ApplicationEvents.vb 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-120">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="d88e5-121">**일반** 메뉴에서 **MyApplication 이벤트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-121">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5.  <span data-ttu-id="d88e5-122">**선언** 메뉴에서 **UnhandledException**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-122">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="d88e5-123">주 응용 프로그램이 실행되기 전에 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-123">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6.  <span data-ttu-id="d88e5-124">`My.Application.Log.WriteException` 이벤트 처리기에 `UnhandledException` 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-124">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     <span data-ttu-id="d88e5-125">다음 예제에서는 처리되지 않은 예외를 기록하기 위한 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d88e5-125">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d88e5-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d88e5-126">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [<span data-ttu-id="d88e5-127">응용 프로그램 로그 작업</span><span class="sxs-lookup"><span data-stu-id="d88e5-127">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="d88e5-128">방법: 로그 메시지 쓰기</span><span class="sxs-lookup"><span data-stu-id="d88e5-128">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [<span data-ttu-id="d88e5-129">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="d88e5-129">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [<span data-ttu-id="d88e5-130">연습: My.Application.Log가 정보를 기록하는 위치 변경</span><span class="sxs-lookup"><span data-stu-id="d88e5-130">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
