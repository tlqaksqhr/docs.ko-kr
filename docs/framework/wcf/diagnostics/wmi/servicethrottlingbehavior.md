---
title: "ServiceThrottlingBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## 구문  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## 메서드  
 ServiceThrottlingBehavior 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 ServiceThrottlingBehavior 클래스에는 다음과 같은 속성이 있습니다.  
  
### MaxConcurrentCalls  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 ServiceHost의 모든 디스패처 개체에서 동시에 처리하는 최대 메시지 수입니다.  
  
### MaxConcurrentInstances  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 한 번에 실행할 수 있는 최대 서비스 개체 수입니다.  
  
### MaxConcurrentSessions  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 호스트가 한 번에 수락할 수 있는 최대 세션 수입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>