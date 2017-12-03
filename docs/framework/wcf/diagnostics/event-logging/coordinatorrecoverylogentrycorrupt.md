---
title: CoordinatorRecoveryLogEntryCorrupt
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cd0c3e3-84c8-4d43-a561-a8851c78e565
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4d57f0e7528c8df6ebf98aa712fe3efd728b421d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="95b9b-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="95b9b-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="95b9b-103">Id: 139</span><span class="sxs-lookup"><span data-stu-id="95b9b-103">Id: 139</span></span>  
  
 <span data-ttu-id="95b9b-104">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="95b9b-104">Severity: Error</span></span>  
  
 <span data-ttu-id="95b9b-105">범주: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="95b9b-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="95b9b-106">설명</span><span class="sxs-lookup"><span data-stu-id="95b9b-106">Description</span></span>  
 <span data-ttu-id="95b9b-107">이 이벤트는 코디네이터 복구 로그 항목이 손상되어 deserialize할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95b9b-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="95b9b-108">이 오류로 인해 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b9b-108">Data loss may result from this error.</span></span> <span data-ttu-id="95b9b-109">이벤트에는 트랜잭션 ID, 복구 데이터(Base64 인코딩), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95b9b-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b9b-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95b9b-110">See Also</span></span>  
 [<span data-ttu-id="95b9b-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="95b9b-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="95b9b-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="95b9b-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
