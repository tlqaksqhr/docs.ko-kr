---
title: MessageQueueDuplicatedSocketLeak
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9721a463-15d1-43dc-8e3a-cae44448de91
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e1356c1b6146d2c54f81a8f4221579490068f5c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="messagequeueduplicatedsocketleak"></a><span data-ttu-id="d56bc-102">MessageQueueDuplicatedSocketLeak</span><span class="sxs-lookup"><span data-stu-id="d56bc-102">MessageQueueDuplicatedSocketLeak</span></span>
<span data-ttu-id="d56bc-103">Id: 165</span><span class="sxs-lookup"><span data-stu-id="d56bc-103">Id: 165</span></span>  
  
 <span data-ttu-id="d56bc-104">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="d56bc-104">Severity: Error</span></span>  
  
 <span data-ttu-id="d56bc-105">범주: SMSvcHost</span><span class="sxs-lookup"><span data-stu-id="d56bc-105">Category: SMSvcHost</span></span>  
  
## <a name="description"></a><span data-ttu-id="d56bc-106">설명</span><span class="sxs-lookup"><span data-stu-id="d56bc-106">Description</span></span>  
 <span data-ttu-id="d56bc-107">이 이벤트는 중복 소켓을 발송하는 동안 발생한 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d56bc-107">This event indicates that an error occurred while dispatching a duplicated socket.</span></span> <span data-ttu-id="d56bc-108">현재 이 핸들은 프로세스에서 누락됩니다.</span><span class="sxs-lookup"><span data-stu-id="d56bc-108">This handle is now leaked in the process.</span></span> <span data-ttu-id="d56bc-109">이 이벤트는 소스, 예외, 프로세스 이름 및 프로세스 ID를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d56bc-109">The event lists the Source, Exception, Process Name and Process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56bc-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d56bc-110">See Also</span></span>  
 [<span data-ttu-id="d56bc-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="d56bc-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="d56bc-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="d56bc-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
