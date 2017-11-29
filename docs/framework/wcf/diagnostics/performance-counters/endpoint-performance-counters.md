---
title: "끝점 성능 카운터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d34df7c70e0edeef831843d9afcb2db32422ebe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="b495c-102">끝점 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="b495c-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="b495c-103">끝점 성능 카운터는 끝점이 메시지를 수신하는 방식을 나타내는 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b495c-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="b495c-104">이러한 카운터는 성능 모니터에서 볼 때 `ServiceModelEndpoint 4.0.0.0` 성능 개체 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b495c-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="b495c-105">인스턴스 이름은 다음 패턴으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b495c-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="b495c-106">데이터는 개별 작업을 위해 수집된 데이터와 비슷하지만 끝점에서만 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="b495c-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b495c-107">성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b495c-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="b495c-108">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 카운터 인스턴스 이름이 최대 길이를 초과하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 인스턴스 이름 부분을 해시 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b495c-108">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b495c-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b495c-109">See Also</span></span>  
 [<span data-ttu-id="b495c-110">성능 카운터</span><span class="sxs-lookup"><span data-stu-id="b495c-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
