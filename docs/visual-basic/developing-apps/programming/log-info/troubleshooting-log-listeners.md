---
title: "문제 해결: 로그 수신기(Visual Basic)"
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
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
caps.latest.revision: 11
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
ms.openlocfilehash: 0542aef4dc60821939e85760e6fadf0dfb528dec
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="a4374-102">문제 해결: 로그 수신기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4374-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="a4374-103">`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에서 발생하는 이벤트에 대한 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="a4374-104">해당 메시지를 받는 로그 수신기를 확인하려면 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4374-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="a4374-105">`Log` 개체는 로그 필터링을 사용하여 기록하는 정보의 양을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="a4374-106">필터가 잘못 구성된 경우 로그에 잘못된 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="a4374-107">필터링에 대한 자세한 내용은 [연습: My.Application.Log 출력 필터링](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4374-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="a4374-108">그러나 로그가 잘못 구성된 경우 현재 구성에 대한 자세한 정보가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="a4374-109">이 정보는 로그의 고급 `TraceSource` 속성을 통해 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="a4374-110">코드에서 Log 개체에 대한 로그 수신기를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="a4374-110">To determine the log listeners for the Log object in code</span></span>  
  
1.  <span data-ttu-id="a4374-111">코드 파일의 시작 부분에 있는 <xref:System.Diagnostics> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="a4374-112">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4374-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     <span data-ttu-id="a4374-113">[!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a4374-113">[!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]</span></span>  
  
2.  <span data-ttu-id="a4374-114">각 로그 수신기에 대한 정보로 구성된 문자열을 반환하는 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-114">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     <span data-ttu-id="a4374-115">[!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a4374-115">[!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]</span></span>  
  
3.  <span data-ttu-id="a4374-116">로그의 추적 수신기 컬렉션을 `GetListeners` 함수에 전달하고 반환 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4374-116">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     <span data-ttu-id="a4374-117">[!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a4374-117">[!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]</span></span>  
  
     <span data-ttu-id="a4374-118">자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4374-118">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4374-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4374-119">See Also</span></span>  
 <span data-ttu-id="a4374-120"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a4374-120"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="a4374-121">[응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="a4374-121">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 [<span data-ttu-id="a4374-122">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="a4374-122">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)

