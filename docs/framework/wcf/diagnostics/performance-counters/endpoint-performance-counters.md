---
title: 끝점 성능 카운터
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: 8354cff600f8c16a5ab9b4f6efd3c0b93a46276c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803139"
---
# <a name="endpoint-performance-counters"></a>끝점 성능 카운터
끝점 성능 카운터는 끝점이 메시지를 수신하는 방식을 나타내는 데이터를 저장합니다. 이러한 카운터는 성능 모니터에서 볼 때 `ServiceModelEndpoint 4.0.0.0` 성능 개체 아래에 있습니다. 인스턴스 이름은 다음 패턴으로 지정됩니다.  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 데이터는 개별 작업을 위해 수집된 데이터와 비슷하지만 끝점에서만 집계됩니다.  
  
> [!CAUTION]
>  성능 카운터 인스턴스의 이름 길이에는 제한이 있습니다. Windows Communication Foundation (WCF) 카운터 인스턴스 이름이 최대 길이 초과 하는 경우 WCF는 인스턴스 이름 부분을 해시 값으로 바꿉니다.  
  
## <a name="see-also"></a>참고 항목  
 [성능 카운터](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
