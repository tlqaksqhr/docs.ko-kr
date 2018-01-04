---
title: "작업 성능 카운터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5724e32c61bb49c3251f4fd9785396e6c97f55f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="operation-performance-counters"></a><span data-ttu-id="9ad9c-102">작업 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="9ad9c-102">Operation Performance Counters</span></span>
<span data-ttu-id="9ad9c-103">작업 성능 카운터는 성능 모니터(Perfmon.exe)에서 볼 때 `ServiceModelOperation 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="9ad9c-104">각 작업에는 개별 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-104">Each operation has an individual instance.</span></span> <span data-ttu-id="9ad9c-105">즉, 지정된 계약에 10개의 작업이 있는 경우 10개의 작업 카운터 인스턴스가 해당 계약에 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="9ad9c-106">개체 인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="9ad9c-107">이 카운터를 사용하면 호출이 사용되는 방법과 작업 진행 상태를 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9ad9c-108">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="9ad9c-109">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 카운터 인스턴스 이름이 최대 길이를 초과하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 인스턴스 이름 부분을 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-109">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ad9c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ad9c-110">See Also</span></span>  
 [<span data-ttu-id="9ad9c-111">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="9ad9c-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
