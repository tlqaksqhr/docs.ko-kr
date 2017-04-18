---
title: "네트워크 추적 사용 | Microsoft Docs"
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
  - "추적 대상"
  - "로그 파일로 추적 전송"
  - "추적 수신기, 네트워크 추적"
  - "네트워크 추적, 사용"
  - "CLR 디버거"
  - "기본 수신기"
  - "로그, 추적"
  - "추적 출력 대상"
ms.assetid: 5fff458c-51a6-4134-ba47-8a6137ddc41e
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 네트워크 추적 사용
네트워크 추적 정보는 관리 되는 응용 프로그램에서 생성 된 네트워크 트래픽 및 메서드 호출에 대 한 액세스를 제공 합니다.  응용 프로그램에서 네트워크 추적을 사용 하려면 다음 작업을 완료 해야 합니다.  
  
-   추적 기능을 사용 하면 코드를 컴파일하십시오.  참조 [How to: Compile Conditionally with Trace and Debug](../../../docs/framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) 추적을 설정 하는 데 필요한 컴파일러 스위치에 대 한 자세한 내용은.  
  
-   추적 출력의 대상을 지정 합니다.  
  
-   네트워크 추적의 동작을 구성 합니다.  참조  [방법: 네트워크 추적 구성](../../../docs/framework/network-programming/how-to-configure-network-tracing.md) 에 대 한 자세한 내용은.  
  
 추적 수신기로 라고도 가장 일반적인 추적 대상이 기본 수신기 및 로그 파일입니다.  
  
 추적 수신기를 지정 하지 않으면 추적이 기본 수신기를 사용 합니다.  CLR 디버거.NET Framework SDK와 함께 제공 된 또는 DBwin32.exe Windows SDK와 함께 제공 된 같은 관리 되는 코드 사용 디버거에서 코드를 실행 하면 기본 수신기에 전송 된 메시지를 볼 수 있습니다.  추적 메시지 표시는 CLR 디버거를 사용 하 여  **출력** 창.  
  
 추적을 받을 수 있는 파일을 사용 하는 경우 사용자는 로그 파일 구성 설정을 사용 하 여 다음과 같이 지정할 수 있습니다.  \(구성 파일에 대 한 일반 설명은 참조 하십시오.  [구성 파일](../../../docs/framework/configure-apps/index.md).\)  
  
 추적 로그 파일을 받을 수 있는 다음 노드에 추가 된 `<system.diagnostics>` 노드에 적절 한 구성 파일 \(응용 프로그램 또는 시스템\)의.  필요에 맞게 \(trace.log\) 파일의 이름을 변경할 수 있습니다.  
  
```  
<system.diagnostics>  
  <trace autoflush="true" indentsize="4">  
    <listeners>  
      <add name="file" type="System.Diagnostics.TextWriterTraceListener" initializeData="trace.log"/>  
    </listeners>   
  </trace>  
</system.diagnostics>  
```  
  
## 참고 항목  
 [네트워크 추적 해석](../../../docs/framework/network-programming/interpreting-network-tracing.md)   
 [.NET Framework의 네트워크 추적](../../../docs/framework/network-programming/network-tracing.md)   
 [Introduction to Instrumentation and Tracing](http://msdn.microsoft.com/ko-kr/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)