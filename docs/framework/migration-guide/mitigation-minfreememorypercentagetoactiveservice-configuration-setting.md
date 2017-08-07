---
title: "완화: minFreeMemoryPercentageToActiveService 구성 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7f228890476d45517a21bc09806538139c5e389
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a>완화: minFreeMemoryPercentageToActiveService 구성 설정
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]에서는 웹 서버의 사용 가능한 메모리가 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 구성 설정에서 지정된 백분율보다 적으면 예외가 발생합니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 이 설정이 무시되었습니다.  
  
## <a name="impact"></a>영향  
 대부분의 경우 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 설정을 관찰하는 것이 좋습니다. 제한된 메모리가 있는 시스템에서 WCF(Windows Communication Foundation) 서비스를 시작할 때 발생할 수 있는 <xref:System.OutOfMemoryException> 예외를 방지하여 시스템 안정성을 향상합니다.  
  
 그러나 이전에 성공적으로 시작된 서비스를 시작할 수 없는 경우도 있습니다. 이 경우 다음과 같은 자세한 오류 메시지가 나타납니다.  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a>완화  
 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 설정을 무시한 이전 동작으로 되돌리려면 web.config 파일을 다음과 같이 수정합니다.  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

