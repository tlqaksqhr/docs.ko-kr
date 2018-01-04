---
title: Queued Rejected Messages Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b413c5076e41990a794b9aa33efd371480835353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="fcfe6-102">Queued Rejected Messages Per Second</span><span class="sxs-lookup"><span data-stu-id="fcfe6-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="fcfe6-103">카운터 이름: Queued Messages Rejected Per Second</span><span class="sxs-lookup"><span data-stu-id="fcfe6-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fcfe6-104">설명</span><span class="sxs-lookup"><span data-stu-id="fcfe6-104">Description</span></span>  
 <span data-ttu-id="fcfe6-105">초당 이 서비스에 대기 중인 전송에 의해 거부된 메시지의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe6-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="fcfe6-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe6-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="fcfe6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="fcfe6-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
