---
title: "서비스 성능 카운터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8145ff12f5a9befdef3cbf5edf69e5162c4d7014
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="service-performance-counters"></a><span data-ttu-id="61ab7-102">서비스 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="61ab7-102">Service Performance Counters</span></span>
<span data-ttu-id="61ab7-103">서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ab7-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="61ab7-104">이러한 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ab7-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="61ab7-105">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="61ab7-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="61ab7-106">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61ab7-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="61ab7-107">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 카운터 인스턴스 이름이 최대 길이를 초과하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 인스턴스 이름 부분을 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="61ab7-107">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ab7-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61ab7-108">See Also</span></span>  
 [<span data-ttu-id="61ab7-109">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="61ab7-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
