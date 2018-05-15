---
title: 서비스 성능 카운터
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: bdc68fd2b629c538c097dab4e1cf3f89b7f3a091
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="service-performance-counters"></a><span data-ttu-id="e4f96-102">서비스 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="e4f96-102">Service Performance Counters</span></span>
<span data-ttu-id="e4f96-103">서비스 성능 카운터는 서비스 동작을 전반적으로 측정하며 전체 서비스 성능을 진단하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4f96-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="e4f96-104">이러한 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelService 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4f96-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="e4f96-105">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4f96-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="e4f96-106">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4f96-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="e4f96-107">Windows Communication Foundation (WCF) 카운터 인스턴스 이름이 최대 길이 초과 하는 경우 WCF는 인스턴스 이름 부분을 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e4f96-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f96-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4f96-108">See Also</span></span>  
 [<span data-ttu-id="e4f96-109">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="e4f96-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
