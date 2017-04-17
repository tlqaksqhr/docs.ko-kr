---
title: "WCF에서 이벤트 로깅 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "이벤트 로깅 [WCF]"
ms.assetid: aac0530d-f44c-45a1-bada-e30e0677b41f
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# WCF에서 이벤트 로깅
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 Windows 이벤트 로그에 있는 내부 이벤트를 추적합니다.  
  
## 이벤트 로그 보기  
 이벤트 로깅은 기본적으로 활성화되며 비활성화 메커니즘이 없습니다.[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 기록된 이벤트는 이벤트 뷰어를 사용하여 볼 수 있습니다.이 도구를 시작하려면 **시작**, **제어판**을 차례로 클릭한 다음 **관리 도구**, **이벤트 뷰어**를 차례로 두 번 클릭합니다.  
  
### 응용 프로그램 이벤트 로그  
 **응용 프로그램 이벤트 로그**에는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 생성되는 대부분의 이벤트가 포함됩니다.대부분의 항목은 응용 프로그램에서 특정 기능을 시작하지 못한 것을 나타냅니다.예를 들면 다음과 같습니다.  
  
-   메시지 로깅\/추적: [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 추적 및 메시지 로깅에 실패하면 이벤트 로그에 이벤트를 기록합니다.그러나 모든 추적 실패가 이벤트를 트리거하는 것은 아닙니다.이벤트 로그가 추적 오류로 가득 차는 것을 방지하기 위해, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 그와 같은 이벤트가 발생한 후 10분 동안 블랙아웃 기간을 구현합니다.즉, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서 이벤트 로그에 추적 실패를 기록하면 적어도 10분 동안은 다시 기록하지 않습니다.  
  
-   공유 수신기: WCF TCP Port Sharing Service에서는 시작에 실패하면 이벤트를 기록합니다.  
  
-   [!INCLUDE[infocard](../../../../../includes/infocard-md.md)]: 서비스를 시작하지 못하면 이벤트를 기록합니다.  
  
-   시작 실패 또는 크래시 등의 위험 및 오류 이벤트  
  
-   메시지 로깅 켜짐: 메시지 로깅이 켜지면 이벤트를 기록합니다.이는 관리자에게 중요한 응용 프로그램 관련 정보가 메시지 헤더 및 본문에 기록될 수 있다는 것을 알리기 위해서입니다.  
  
-   `machine.config` 파일의 `machineSettings` 요소에서 `enableLoggingKnownPII` 특성이 설정되면 이벤트가 기록됩니다.이 특성에서는 시스템에서 실행 중인 응용 프로그램 중 알려진 PII\(개인적으로 식별할 수 있는 정보\)의 로그가 허용되는 것이 있는지 여부를 지정합니다.  
  
-   특정 응용 프로그램에 대해 `app.config` 또는 `web.config` 파일에서 `logKnownPii` 특성이 PII 로깅을 켜도록 `true`로 설정되어 있지만 `machine.config` 파일의 `machineSettings` 요소에 있는 `enableLoggingKnownPII` 특성이 `false`로 설정되어 있으면 이벤트가 기록됩니다.또한 `logKnownPii` 및 `enableLoggingKnownPII`가 모두 `true`로 설정되어 있으면 이벤트가 기록됩니다.이러한 구성 설정에 대한 자세한 내용은 [메시지 로깅 구성](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) 항목의 보안 단원을 참조하십시오.  
  
### 보안 이벤트 로그  
 **보안 이벤트 로그**에는 WCF에서 기록된 보안 감사 이벤트가 포함됩니다.  
  
### 시스템 이벤트 로그  
 WCF에서는 **시스템 이벤트 로그**에 아무 것도 기록하지 않습니다.  
  
### 이벤트 로그 항목  
 이벤트의 **소스**는 로그 항목을 생성하는 어셈블리의 이름입니다.  
  
 이벤트 로그 항목의 형식은 이벤트의 심각도를 나타내는 데 사용됩니다.각 이벤트는 응용 프로그램에서 이벤트를 보고할 때 나타내는 단일 형식이어야 합니다.이벤트 뷰어는 이 형식을 사용하여 로그의 목록 보기에 표시할 아이콘을 결정합니다.이벤트 로그 항목의 다른 이벤트 형식은 <xref:System.Diagnostics.EventLogEntryType>을 참조하십시오.  
  
 이벤트 뷰어에서 이벤트를 볼 때 "추가 정보"를 클릭하면 이벤트 뷰어에서 인터넷을 통해 정보를 보낼 수 있습니다.자세한 내용은 이벤트 뷰어 도움말을 참조하십시오.  
  
## 참고 항목  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [이벤트 일반 참조](../../../../../docs/framework/wcf/diagnostics/event-logging/events-general-reference.md)