---
title: "동작 ID 전파 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 동작 ID 전파
ServiceModel 동작 추적을 사용하면 ServiceModel 동작을 통해 전파가 발생하고, ServiceModel 동작 추적을 사용하지 않으면 사용자 간에 전파가 발생합니다.  
  
## ServiceModel 동작 추적 사용  
 ServiceModel ActivityTracing을 사용하면 ProcessAction 동작 간에 전파가 발생합니다.  
  
### 서버  
 클라이언트와 서버 모두에서 `propagateActivity` 특성이 `true`로 설정된 경우 서버의 `ProcessAction` 동작 ID는 전파된 `ActivityId` 메시지 헤더의 ID와 동일합니다.  
  
 메시지에 `ActivityId` 헤더가 없는 경우\(클라이언트에서 `propagateActivity`가 `false`로 설정된 경우\)나 서버에서 `propagateActivity`가 `false`로 설정된 경우에는 서버에서 새 동작 ID를 생성합니다.  
  
### 클라이언트  
 클라이언트가 동기 단일 스레드인 경우 클라이언트는 클라이언트나 서버의 `propagateActivity` 설정을 모두 무시합니다.  대신 요청 동작에서 응답이 처리됩니다.  클라이언트가 비동기 또는 동기 다중 스레드이고 클라이언트에서 `propagateActivity`가`true`로 설정된 경우이며 서버에서 전송된 메시지에 동작 ID 헤더가 있으면 클라이언트는 메시지에서 동작 ID를 검색하여 전파된 동작 ID를 포함하는 Process Action 동작으로 전송합니다.  그렇지 않으면 클라이언트는 Process Message 동작에서 새 Process Action 동작으로 전송합니다.  새 Process Action 동작으로의 이 추가 전송은 일관성을 위해 수행됩니다.  이 동작 내에서 클라이언트는 응답 메시지 처리를 위해 스레드가 할당될 때 로컬 스레드 컨텍스트에서 BeginCall 동작의 동작 ID를 검색합니다.  그런 다음 초기 Process Action 동작으로 전송합니다.  
  
 클라이언트가 이중이면 메시지를 수신할 때 클라이언트가 서버 역할을 합니다.  
  
### 오류 메시지의 전파  
 올바른 메시지와 오류 메시지의 처리에는 차이가 없습니다.  `propagateActivity`가 `true`로 설정된 경우이면 SOAP 오류 메시지 헤더에 추가된 동작 ID가 앰비언트 동작과 같습니다.  
  
## ServiceModel 동작 추적 사용 안 함  
 ServiceModel ActivityTracing을 사용하지 않으면 ServiceModel 동작을 거치지 않고 직접 사용자 코드 동작 간에 전파가 발생합니다.  사용자 정의 동작 ID도 메시지 동작 ID 헤더를 통해 전파됩니다.  
  
 ServiceModel에서 추적을 사용하는지 여부에 관계없이 ServiceModel 추적 수신기에 대해 `ActivityTracing`\=`off`이고 `propagateActivity`가`true`로 설정된 경우이면 클라이언트와 서버 모두에서 다음 작업이 수행됩니다.  
  
-   작업 요청 또는 응답 전송 시 메시지가 구성될 때까지 TLS의 동작 ID가 사용자 코드에서 전파됩니다.  메시지가 전송되기 전에 동작 ID 헤더도 메시지에 삽입됩니다.  
  
-   요청이나 응답을 받을 때 수신된 메시지 개체를 만드는 즉시 메시지 헤더에서 동작 ID가 검색됩니다.  TLS의 동작 ID는 사용자 코드에 도달할 때까지 메시지가 범위에서 사라지는 즉시 전파됩니다.  
  
 이러한 작업은 전파가 설정된 경우 사용자 추적이 동일한 동작에 나타나도록 합니다.  그러나 ServiceModel 추적의 경우는 다릅니다.  ServiceModel 추적은 사용자 코드 동작이 설정된 스레드와 동일한 스레드에서 추적 처리가 실행되는 경우에만 사용자 코드 동작에서 발생합니다.  
  
 일반적으로 ServiceModel 추적은 다음 위치에서 확인할 수 있습니다.  
  
-   ServiceModel 추적을 사용하지 않으면 내보낸 모든 추적이 사용자 동작에 나타납니다.  서버와 클라이언트에서 모두 전파를 사용하는 경우 이러한 추적이 동일한 동작에 있습니다.  
  
-   ServiceModel 추적을 사용하지만 ActivityTracing을 사용하지 않으면 양쪽에서 모두 전파를 사용하는 경우 사용자 추적이 동일한 동작에 나타납니다.  ServiceModel 추적은 동작이 처음에 설정된 사용자 코드 처리와 동일한 스레드에서 발생하지 않는 한 기본 0000 동작에 나타납니다.  
  
-   ServiceModel 추적과 ActivityTracing을 모두 사용하면 사용자 추적이 사용자 정의 동작에 나타나고 ServiceModel 추적은 ServiceModel에서 정의된 동작에 나타납니다.  전파는 ServiceModel 수준에서 발생합니다.