---
title: "raceOnRCWCleanup MDA | Microsoft Docs"
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
  - "RCW"
  - "managed debugging assistants (MDAs), RCWs"
  - "race on RCW cleanup"
  - "MDAs (managed debugging assistants), RCWs"
  - "RaceOnRCWCleanup MDA"
  - "runtime callable wrappers"
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# raceOnRCWCleanup MDA
`raceOnRCWCleanup` MDA\(관리 디버깅 도우미\)는 CLR\(공용 언어 런타임\)에서 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName> 메서드와 같은 명령을 사용하여 해제 호출을 수행할 때 RCW\([RCW](../../../docs/framework/interop/runtime-callable-wrapper.md)\)가 사용 중임을 발견할 경우 활성화됩니다.  
  
## 증상  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 또는 이와 비슷한 메서드를 사용하여 RCW를 해제하는 중이나 그 이후에 액세스 위반 또는 메모리 손상이 발생합니다.  
  
## 원인  
 RCW가 다른 스레드나 해제 스레드 스택에서 사용 중입니다.  사용 중인 RCW는 해제할 수 없습니다.  
  
## 해결  
 현재 스레드나 다른 스레드에서 사용 중일 수 있는 RCW는 해제하지 마세요.  
  
## 런타임에 대한 영향  
 이 MDA는 CLR에 아무런 영향을 미치지 않습니다.  
  
## 출력  
 오류를 설명하는 메시지입니다.  
  
## 구성  
  
```  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)