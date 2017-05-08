---
title: "CLR ETW 공급자 | Microsoft Docs"
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
  - "CLR ETW 공급자"
  - "ETW, CLR 공급자"
ms.assetid: 0beafad4-b2c8-47f4-b342-83411d57a51f
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# CLR ETW 공급자
CLR\(공용 언어 런타임\)에는 런타임 공급자 및 런다운 공급자라는 2개의 공급자가 있습니다.  
  
 런타임 공급자는 어떤 키워드\(이벤트 범주\)가 사용되는지에 따라 이벤트를 발생시킵니다.  예를 들어 `LoaderKeyword` 키워드를 사용하여 로더 이벤트를 수집할 수 있습니다.  
  
 ETW\(Event tracking for Windows\) 이벤트는 확장명이 .etl인 파일에 기록됩니다. 나중에 필요에 따라 이 파일을 쉼표로 구분된 값 파일\(.csv\)로 사후 처리할 수 있습니다.  .etl 파일을 .csv 파일로 변환하는 방법에 대한 자세한 내용은 [.NET Framework 로깅 제어](../../../docs/framework/performance/controlling-logging.md)를 참조하십시오.  
  
## 런타임 공급자  
 런타임 공급자가 주 CLR ETW 공급자입니다.  
  
 CLR 런타임 공급자 GUID는 e13c0d23\-ccbc\-4e12\-931b\-d9cc2eee27e4입니다.  
  
 일반적으로 사용할 수 있는 도구를 사용하여 CLR ETW 이벤트를 기록하고 보는 방법에 대한 예제는 [.NET Framework 로깅 제어](../../../docs/framework/performance/controlling-logging.md)을 참조하십시오.  
  
 `LoaderKeyword` 등의 키워드 외에도 너무 자주 발생할 수 있는 이벤트를 기록하기 위한 키워드를 사용해야 할 수도 있습니다.  이러한 이벤트는 `StartEnumerationKeyword` 및 `EndEnumerationKeyword` 키워드에 의해 활성화되며 두 키워드는 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)에 요약되어 있습니다.  
  
## 런다운 공급자  
 런다운 공급자는 일부 특별한 용도로 설정되어야 합니다.  대부분의 사용자에게는 런타임 공급자만으로도 충분합니다.  
  
 CLR 런다운 공급자 GUID는 A669021C\-C450\-4609\-A035\-5AF59AF4DF18입니다.  
  
 일반적으로 ETW 로깅은 프로세스가 시작되기 전에 설정되고, 프로세스가 종료된 후에는 로깅이 해제됩니다.  하지만 프로세스가 실행 중일 때 ETW 로깅이 켜져 있으면 프로세스에 대한 추가 정보가 필요합니다.  예를 들어 기호 확인의 경우 로깅이 켜지기 전에 이미 로드된 메서드에 대한 메서드 이벤트를 기록해야 합니다.  
  
 `DCStart` 및 `DCEnd` 이벤트는 데이터 수집이 시작되고 중지되었을 때의 프로세스 상태를 캡처합니다. 상태는 이미 JIT\(Just\-In\-Time\) 컴파일된 메서드 및 로드된 어셈블리를 비롯한 높은 수준의 정보를 참조합니다. 이러한 두 가지 이벤트는 JIT 컴파일된 메서드 등 프로세스에서 이미 발생한 내용에 대한 정보를 제공할 수 있습니다.  
  
 런다운 공급자에서는 이름에 `DC`, `DCStart`, `DCEnd` 또는 `DCInit`가 있는 이벤트만 발생합니다.  또한 이러한 이벤트는 런다운 공급자에서만 발생합니다.  
  
 이벤트 키워드 필터 외에도 런다운 공급자는 `StartRundownKeyword` 및 `EndRundownKeyword` 키워드를 지원하여 대상 필터링을 제공합니다.  
  
### 시작 런다운  
 시작 런다운은 `StartRundownKeyword` 키워드를 사용하여 런다운 공급자에 기록할 수 있도록 설정되었을 때 트리거됩니다.  시작 런다운이 트리거되면 `DCStart` 이벤트가 발생하고 시스템 상태가 캡처됩니다.  열거형이 시작되기 전에 `DCStartInit` 이벤트가 발생합니다.  열거형이 끝나면 데이터 수집이 정상적으로 종료되었다는 것을 컨트롤러에 알리기 위해 `DCStartComplete` 이벤트가 발생합니다.  
  
### 끝 런다운  
 끝 런다운은 `EndRundownKeyword` 키워드를 사용하여 런다운 공급자에 기록할 수 있도록 설정되었을 때 트리거됩니다.  끝 런다운은 계속 실행되는 프로세스에서 프로파일링을 중지합니다.  프로파일링이 중지될 때 `DCEnd` 이벤트가 시스템의 상태를 캡처합니다.  
  
 열거형이 시작되기 전에 `DCEndInit` 이벤트가 발생합니다.  열거형이 끝나면 데이터 수집이 정상적으로 종료되었다는 것을 소비자에 알리기 위해 `DCEndComplete` 이벤트가 발생합니다.  시작 런다운 및 끝 런다운은 관리되는 기호 확인에 주로 사용됩니다.  시작 런다운은 프로파일링 세션이 시작되기 전에 이미 JIT 컴파일된 메서드에 대한 주소 범위 정보를 제공할 수 있습니다.  끝 런다운은 프로파일링이 종료될 때쯤에 JIT 컴파일된 모든 메서드에 주소 범위 정보를 제공할 수 있습니다.  
  
 끝 런다운은 프로파일링 세션이 중지될 때 자동으로 발생하지 않습니다.  대신, 관리되는 기호 확인을 수행하는 도구가 프로파일링이 중지되기 직전에 `EndRundownKeyword` 키워드를 사용하여 CLR 런다운 공급자 세션을 명시적으로 호출해야 합니다.  
  
 시작 런다운 또는 끝 런다운이 관리되는 기호 확인을 위한 메서드 주소 범위를 제공할 수는 있지만 `DCStart` 이벤트를 제공하는 `StartRundownKeyword` 키워드 대신 `DCEnd` 이벤트를 제공하는 `EndRundownKeyword` 키워드를 사용하는 것이 좋습니다.  `StartRundownKeyword`를 사용하면 프로파일링 세션 도중에 런다운이 발생함으로써 프로파일링된 시나리오를 방해할 수 있습니다.  
  
## 런타임 및 런다운 공급자를 사용한 ETW 데이터 수집  
 다음 예제에서는 프로세스가 프로파일링된 기간 이내 또는 이외에 시작되거나 끝나는지에 관계없이 최소한의 영향을 주면서 관리되는 프로세스의 기호 확인을 허용하는 방식으로 CLR 런다운 공급자를 사용하는 방법을 보여 줍니다.  
  
1.  CLR 런타임 공급자를 사용하여 ETW 로깅을 설정합니다.  
  
    ```  
    xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:0x5 -f clr1.etl      
    ```  
  
     이 로그는 clr1.etl 파일에 저장됩니다.  
  
2.  프로세스가 계속 실행 중일 때 프로파일링을 중지하려면 런다운 공급자를 시작하여 `DCEnd` 이벤트를 캡처합니다.  
  
    ```  
    xperf -start clrRundown -on A669021C-C450-4609-A035-5AF59AF4DF18:0xB8:0x5 -f clr2.etl      
    ```  
  
     그러면 `DCEnd` 이벤트 수집이 런다운 세션을 시작할 수 있습니다.  모든 이벤트가 수집될 때까지 30\-60초 동안 기다려야 할 수도 있습니다.  이 로그는 clr1.et2 파일에 저장됩니다.  
  
3.  모든 ETW 프로파일링을 해제합니다.  
  
    ```  
    xperf -stop clrRundown   
    xperf -stop clr  
    ```  
  
4.  프로필을 병합하여 하나의 로그 파일을 만듭니다.  
  
    ```  
    xperf -merge -d clr1.etl clr2.etl merged.etl  
    ```  
  
     merged.etl 파일에는 런타임 및 런다운 공급자 세션의 이벤트가 포함됩니다.  
  
 사용자가 프로파일링 중지를 요청하면 도구에서 프로파일링을 즉시 해제하는 대신 2단계와 3단계를 실행\(런다운 세션을 시작한 다음 프로파일링을 종료\)할 수 있습니다.  또한 도구에서 4단계를 실행할 수도 있습니다.  
  
## 참고 항목  
 [공용 언어 런타임의 ETW 이벤트](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)