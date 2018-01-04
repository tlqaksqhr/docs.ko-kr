---
title: "끝점: Calls Failed Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a6aaf1e504909805a542840fe92a6591c9083d8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="a93da-102">끝점: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="a93da-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="a93da-103">카운터 이름: Calls Failed Per Second</span><span class="sxs-lookup"><span data-stu-id="a93da-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a93da-104">설명</span><span class="sxs-lookup"><span data-stu-id="a93da-104">Description</span></span>  
 <span data-ttu-id="a93da-105">처리되지 않은 예외가 있고 초당 이 끝점에서 받은 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a93da-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="a93da-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="a93da-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="a93da-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="a93da-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="a93da-108">이 카운터는 이 끝점에서 처리되지 않은 예외가 발생할 때마다 증가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a93da-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93da-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a93da-109">See Also</span></span>  
 [<span data-ttu-id="a93da-110">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="a93da-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
