---
title: "CLR ETW 이벤트 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR ETW 이벤트"
  - "ETW, CLR 이벤트"
  - "ETW, 공용 언어 런타임"
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: 45
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 45
---
# CLR ETW 이벤트
이 단원의 항목에서는 ETW\(Window용 이벤트 추적\) 이벤트에 대해 설명합니다.  각 이벤트에는 연결된 키워드와 수준이 있으며 이에 대해서는 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) 항목에서 설명합니다.  CLR에는 이벤트에 대한 두 가지 공급자가 있습니다.  
  
-   런타임 공급자. 이 공급자는 어떤 키워드\(이벤트 범주\)가 사용되는지에 따라 이벤트를 발생시킵니다.  CLR 런타임 공급자 GUID는 e13c0d23\-ccbc\-4e12\-931b\-d9cc2eee27e4입니다.  
  
-   런다운 공급자. 이 공급자는 특별한 용도로 사용됩니다.  CLR 런다운 공급자 GUID는 a669021c\-c450\-4609\-a035\-5af59af4df18입니다.  
  
 이 공급자에 대한 자세한 내용은 [CLR ETW 공급자](../../../docs/framework/performance/clr-etw-providers.md)를 참조하십시오.  
  
## 단원 내용  
 [런타임 정보 이벤트](../../../docs/framework/performance/runtime-information-etw-events.md)  
 SKU, 버전 번호, 런타임이 활성화된 방식, 시작될 때 사용된 명령줄 매개 변수, GUID\(해당하는 경우\), 기타 관련 정보 등 런타임에 대한 정보를 캡처합니다.  
  
 [예외가 throw된 V1 이벤트](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 throw된 예외와 관련된 정보를 캡처합니다.  
  
 [경합 이벤트](../../../docs/framework/performance/contention-etw-events.md)  
 런타임에서 사용하는 모니터 잠금 또는 네이티브 잠금의 경합에 대한 정보를 캡처합니다.  
  
 [스레드 풀 이벤트](../../../docs/framework/performance/thread-pool-etw-events.md)  
 작업자 스레드 풀 및 I\/O 스레드 풀에 대한 정보를 캡처합니다.  
  
 [로더 이벤트](../../../docs/framework/performance/loader-etw-events.md)  
 응용 프로그램 도메인, 어셈블리, 모듈의 로드 및 언로드에 대한 정보를 캡처합니다.  
  
 [메서드 이벤트](../../../docs/framework/performance/method-etw-events.md)  
 기호 확인을 위해 CLR 메서드에 대한 정보를 캡처합니다.  
  
 [가비지 수집 이벤트](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 진단 및 디버깅을 지원하기 위해 가비지 수집에 대한 정보를 캡처합니다.  
  
 [JIT 추적 이벤트](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 JIT\(Just\-In\-Time\) 인라이닝 및 마무리 호출에 대한 정보를 캡처합니다.  
  
 [Interop 이벤트](../../../docs/framework/performance/interop-etw-events.md)  
 MSIL\(Microsoft Intermediate Language\) 스텁 생성 및 캐싱에 대한 정보를 캡처합니다.  
  
 [ARM 이벤트](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 응용 프로그램 도메인의 상태에 대한 자세한 진단 정보를 캡처합니다.  
  
 [보안 이벤트](../../../docs/framework/performance/security-etw-events.md)  
 강력한 이름 및 Authenticode 확인에 대한 정보를 캡처합니다.  
  
 [스택 이벤트](../../../docs/framework/performance/stack-etw-event.md)  
 이벤트 발생 이후 스택 추적을 생성하기 위해 다른 이벤트와 함께 사용되는 정보를 캡처합니다.  
  
## 참고 항목  
 [ETW를 사용한 디버깅 및 성능 튜닝 향상](http://go.microsoft.com/fwlink/?LinkId=179696)   
 [Windows 성능 블로그](http://go.microsoft.com/fwlink/?LinkId=179509)   
 [.NET Framework 로깅 제어](../../../docs/framework/performance/controlling-logging.md)   
 [CLR ETW 공급자](../../../docs/framework/performance/clr-etw-providers.md)   
 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)   
 [공용 언어 런타임의 ETW 이벤트](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)