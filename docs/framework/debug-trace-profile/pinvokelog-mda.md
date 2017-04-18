---
title: "pInvokeLog MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "signatures, platform invoke"
  - "MDAs (managed debugging assistants), platform invoke"
  - "platform invoke, run-time errors"
  - "platform invoke log"
  - "PInvokeLog MDA"
  - "managed debugging assistants (MDAs), platform invoke"
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# pInvokeLog MDA
실행 중에 사용되는 각각의 고유한 플랫폼 호출 시그니처에 대해 `pInvokeLog` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  
  
## Output  
 실행 중에 사용되는 플랫폼 호출 시그니처를 나타내는 메시지입니다.  
  
## Configuration  
 일치하는 각 요소는 P\/Invoke 호출이 수행된 .dll 파일을 필터링합니다.  
  
```  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [관리되지 않는 DLL 함수 사용](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)