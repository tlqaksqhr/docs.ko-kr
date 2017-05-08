---
title: "fatalExecutionEngineError MDA | Microsoft Docs"
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
  - "corrupted CLR"
  - "fatal execution error"
  - "terminated processes"
  - "unexpected terminations"
  - "fatal errors"
  - "MDAs (managed debugging assistants), fatal errors"
  - "process termination"
  - "FatalExecutionEngineError MDA"
  - "managed debugging assistants (MDAs), fatal errors"
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# fatalExecutionEngineError MDA
CLR\(공용 언어 런타임\)에서 심각한 오류가 발견된 경우 `fatalExecutionEngine``Error` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  프로세스가 종료됩니다.  
  
## 증상  
 예기치 않게 프로세스가 종료됩니다.  CLR 오류가 발생하는 이유는 다양하기 때문에 다른 증상은 발견할 수 없습니다.  
  
## 원인  
 CLR이 심각하게 손상되었습니다.  잘못된 플랫폼 호출 함수 호출, CLR에 잘못된 데이터 전달 등과 같은 다양한 문제로 인한 데이터 손상이 원인인 경우가 많습니다.  
  
## 해결  
 추가 MDA를 사용하면 문제를 파악하는 데 도움이 될 수 있습니다.  다음 MDA는 문제를 진단할 때 특히 유용할 수 있습니다.  
  
-   [invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## 런타임 효과  
 이 MDA는 런타임 동작에 아무런 영향을 주지 않습니다.  
  
## Output  
 심각한 오류를 일으킨 CLR 함수의 주소, 오류가 발생한 스레드의 ID 및 오류 코드입니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution.Cer>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)