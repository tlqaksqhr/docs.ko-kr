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
ms.workload: dotnet
ms.openlocfilehash: ae2b8a8bb536d914edd6c7154136867caee553b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="coordinatorrecoverylogentrycorrupt"></a><span data-ttu-id="f8282-102">CoordinatorRecoveryLogEntryCorrupt</span><span class="sxs-lookup"><span data-stu-id="f8282-102">CoordinatorRecoveryLogEntryCorrupt</span></span>
<span data-ttu-id="f8282-103">Id: 139</span><span class="sxs-lookup"><span data-stu-id="f8282-103">Id: 139</span></span>  
  
 <span data-ttu-id="f8282-104">심각도: 오류</span><span class="sxs-lookup"><span data-stu-id="f8282-104">Severity: Error</span></span>  
  
 <span data-ttu-id="f8282-105">범주: TransactionBridge</span><span class="sxs-lookup"><span data-stu-id="f8282-105">Category: TransactionBridge</span></span>  
  
## <a name="description"></a><span data-ttu-id="f8282-106">설명</span><span class="sxs-lookup"><span data-stu-id="f8282-106">Description</span></span>  
 <span data-ttu-id="f8282-107">이 이벤트는 코디네이터 복구 로그 항목이 손상되어 deserialize할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f8282-107">This event indicates that a  coordinator recovery log entry was corrupt and could not be deserialized.</span></span> <span data-ttu-id="f8282-108">이 오류로 인해 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8282-108">Data loss may result from this error.</span></span> <span data-ttu-id="f8282-109">이벤트에는 트랜잭션 ID, 복구 데이터(Base64 인코딩), 예외, 프로세스 이름 및 프로세스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8282-109">The event lists the Transaction ID, Recovery data (Base64 encoded), exception, process name and process ID.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8282-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8282-110">See Also</span></span>  
 [<span data-ttu-id="f8282-111">이벤트 로깅</span><span class="sxs-lookup"><span data-stu-id="f8282-111">Event Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/index.md)  
 [<span data-ttu-id="f8282-112">이벤트 일반 참조</span><span class="sxs-lookup"><span data-stu-id="f8282-112">Events General Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)
