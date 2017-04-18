---
title: "완화: minFreeMemoryPercentageToActiveService 구성 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# 완화: minFreeMemoryPercentageToActiveService 구성 설정
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)]에서는 웹 서버의 사용 가능한 메모리가 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 구성 설정에서 지정된 백분율보다 적으면 예외가 발생합니다.  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서는 이 설정이 무시되었습니다.  
  
## 영향  
 대부분의 경우 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 설정을 관찰하는 것이 좋습니다. 제한된 메모리가 있는 시스템에서 WCF\(Windows Communication Foundation\) 서비스를 시작할 때 발생할 수 있는 <xref:System.OutOfMemoryException> 예외를 방지하여 시스템 안정성을 향상시킵니다.  
  
 그러나 이전에 성공적으로 시작된 서비스를 시작할 수 없는 경우도 있습니다.  이 경우 다음과 같은 자세한 오류 메시지가 나타납니다.  
  
```Output  
  
사용 가능한 메모리(nnnn바이트)가 총 메모리의 nn%보다 작아 메모리 게이트 검사에 실패했습니다.  그 결과, 들어오는 요청에 서비스를 사용할 수 없습니다.  이 문제를 해결하려면 컴퓨터의 부하를 줄이거나 minFreeMemoryPercentageToActivateService serviceHostingEnvironment 구성 요소의 값을 조정합니다.    
```  
  
## 완화  
 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 설정을 무시한 이전 동작으로 되돌리려면 web.config 파일을 다음과 같이 수정합니다.  
  
```  
  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
  
```  
  
## 참고 항목  
 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)