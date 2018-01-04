---
title: Queued Poison Messages Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8f22d200834927204918324ced70ac02c3c669f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="80203-102">Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="80203-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="80203-103">카운터 이름: Queued Poison Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="80203-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="80203-104">설명</span><span class="sxs-lookup"><span data-stu-id="80203-104">Description</span></span>  
 <span data-ttu-id="80203-105">1초 동안 이 서비스에 대기 중인 전송에 의해 포이즌으로 표시된 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="80203-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="80203-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="80203-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="80203-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="80203-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
