---
title: "asynchronousThreadAbort MDA | Microsoft Docs"
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
  - "asynchronous thread aborts"
  - "AsynchronousThreadAbort MDA"
  - "managed debugging assistants (MDAs), asynchronous thread aborts"
  - "threading [.NET Framework], managed debugging assistants"
  - "MDAs (managed debugging assistants), asynchronous thread aborts"
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# asynchronousThreadAbort MDA
스레드가 다른 스레드에 비동기 중단을 적용하려고 하면 `asynchronousThreadAbort` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  동기 스레드 중단은 `asynchronousThreadAbort` MDA를 활성화하지 않습니다.  
  
## 증상  
 주 응용 프로그램 스레드가 중단되면 처리되지 않은 <xref:System.Threading.ThreadAbortException>이 발생하며 응용 프로그램이 충돌합니다.  응용 프로그램이 계속 실행되는 경우 응용 프로그램 충돌보다 더 심각한 결과가 발생하여 데이터가 추가로 손상될 수 있습니다.  
  
 원자 단위 작업이 부분 완료 후 중단되어 응용 프로그램 데이터가 예기치 않은 상태가 되었을 수 있습니다.  <xref:System.Threading.ThreadAbortException>은 코드 실행 중 임의의 시점에 예외가 발생하리라고 예상할 수 없는 위치에서 생성될 수 있습니다.  코드에서 이러한 예외를 처리할 수 없어 상태가 손상될 수 있습니다.  
  
 문제의 성격이 똑같지 않기 때문에 증상도 매우 다양할 수 있습니다.  
  
## 원인  
 한 스레드의 코드에서 대상 스레드의 <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> 메서드를 호출하여 비동기 스레드 중단을 적용했습니다.  <xref:System.Threading.Thread.Abort%2A>를 호출한 코드가 중단 작업의 대상과 다른 스레드에서 실행되고 있으므로 스레드 중단은 비동기적입니다.  동기 스레드 중단은 응용 프로그램 상태가 일치하는 안전한 검사점에서만 <xref:System.Threading.Thread.Abort%2A>를 실행해야 하므로 문제를 일으키면 안 됩니다.  
  
 비동기 스레드 중단은 대상 스레드 실행의 예기치 않은 시점에 처리되므로 문제를 일으킵니다.  이 문제를 방지하려면 응용 프로그램 데이터가 일관된 상태로 있도록 하여 이와 같이 중단될 수 있는 스레드에서 실행되도록 작성된 코드의 거의 모든 코드 줄에서 <xref:System.Threading.ThreadAbortException>을 처리해야 합니다.  이 문제를 고려하여 작성된 코드를 발견하거나 가능한 모든 상황을 보호하는 코드를 작성하기는 어렵습니다.  
  
 비관리 코드와 `finally` 블록에 대한 호출은 비동기적으로 중단되지 않지만 이 범주 중 하나의 출구에서 바로 중단됩니다.  
  
 문제 본래의 무작위성으로 인해 원인을 결정하기가 어렵습니다.  
  
## 해결  
 비동기 스레드 중단을 사용해야 하는 코드 디자인을 피합니다.  대상 스레드 중단을 위해 <xref:System.Threading.Thread.Abort%2A>를 호출할 필요가 없는 더 적합한 방법이 몇 가지 있습니다.  대상 스레드에 중단을 요청하도록 알리는 일반 속성과 같은 메커니즘을 사용하는 것이 가장 안전합니다.  대상 스레드는 이 신호에서 안전한 검사점을 확인합니다.  대상 스레드는 중단이 요청되었다는 알림을 받으면 안전하게 종료될 수 있습니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  비동기 스레드 중단에 대한 데이터를 보고하기만 합니다.  
  
## Output  
 MDA는 중단을 실행하는 스레드의 ID와 중단의 대상인 스레드의 ID를 보고합니다.  이는 비동기 중단으로만 제한되기 때문에 이러한 내용이 같을 수는 없습니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <asynchronousThreadAbort />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 `asynchronousThreadAbort` MDA를 활성화하려면 별도로 실행되는 스레드에서 <xref:System.Threading.Thread.Abort%2A>를 호출하기만 하면 됩니다.  스레드 시작 함수 내용이 중단에 의해 임의의 시점에 중단될 수 있는 더욱 복잡한 일련의 작업인 경우에 발생하는 결과를 고려할 수 있습니다.  
  
```  
using System.Threading;  
void FireMda()  
{  
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Abort();   
    t.Join();  
}  
```  
  
## 참고 항목  
 <xref:System.Threading.Thread>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)