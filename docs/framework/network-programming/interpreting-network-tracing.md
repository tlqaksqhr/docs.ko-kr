---
title: "네트워크 추적 해석 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "TraceMode 특성"
  - "16진수 데이터, 네트워크 추적 출력"
  - "네트워크 추적, 분석"
  - "protocolonly"
  - "텍스트, 네트워크 추적 출력"
  - "includehex"
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 네트워크 추적 해석
네트워크 추적을 사용 하면 사용자 추적 호출 응용 프로그램에 있는 여러 있습니다 캡처할 수 있습니다 <xref:System.Net> 클래스 멤버입니다.  이러한 호출의 출력은 다음 예와 비슷한 수 있습니다.  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 앞의 예에서 \[588\]은 현재 스레드의 고유 식별자입니다.  \(4357\) 및 \(4387\)는 타임 스탬프를 나타내는 수 응용 프로그램이 시작 된 이후 경과한 시간 \(밀리초\)입니다.  다음 타임 스탬프 데이터 입력 메서드를 종료 하 고 응용 프로그램을 보여 줍니다.  **Socket.Send**.  실행 개체는  **보내기** 메서드는 고유 식별자로 33574638가.  메서드 종료 추적에는 반환 값을 \(앞의 예에서 61\) 포함 되어 있습니다.  
  
 네트워크 추적에서 전송 되거나 응용 프로그램 수준 프로토콜 같은 HTTP \(하이퍼텍스트 전송 프로토콜\)를 사용 하 여 응용 프로그램에서 수신 네트워크 트래픽을 캡처할 수 있습니다.  이 데이터는 텍스트로 캡처할 수 있습니다 하 고 선택적으로 16 진수 데이터입니다.  16 진수 데이터를 지정할 때 사용할  **includehex** 의 값으로는  **tracemode** 특성.  \(이 특성에 대 한 자세한 내용은  [방법: 네트워크 추적 구성](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).\) 다음 예제에서는 추적을 사용 하 여 생성 된  **includehex**.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 16 진수 데이터를 생략 하도록 지정 합니다.  **protocolonly** 의 값으로는  **tracemode** 특성.  다음 예제에서는 추적 하면  **protocolonly** 지정 된.  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## 참고 항목  
 [네트워크 추적 사용](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [방법: 네트워크 추적 구성](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [.NET Framework의 네트워크 추적](../../../docs/framework/network-programming/network-tracing.md)