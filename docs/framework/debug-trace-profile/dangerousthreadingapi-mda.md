---
title: "dangerousThreadingAPI MDA | Microsoft Docs"
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
  - "suspending threads"
  - "DangerousThreadingAPI MDA"
  - "managed debugging assistants (MDAs), dangerous threading operations"
  - "threading [.NET Framework], suspending"
  - "MDAs (managed debugging assistants), dangerous threading operations"
  - "Suspend method"
  - "threading [.NET Framework], managed debugging assistants"
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# dangerousThreadingAPI MDA
<xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 메서드가 현재 스레드가 아닌 다른 스레드에서 호출되면 `dangerousThreadingAPI` MDA\(관리 디버깅 도우미\)가 활성화됩니다.  
  
## 증상  
 응용 프로그램이 응답이 없거나 정지된 채로 무한히 지속됩니다.  시스템 또는 응용 프로그램 데이터가 잠깐 또는 응용 프로그램을 종료한 후에도 예측할 수 없는 상태에 놓일 수 있습니다.  일부 작업이 예상한 대로 완료되지 않습니다.  
  
 문제의 성격이 똑같지 않기 때문에 증상도 매우 다양할 수 있습니다.  
  
## 원인  
 스레드는 <xref:System.Threading.Thread.Suspend%2A> 메서드를 사용하여 다른 스레드에서 비동기 방식으로 일시 중단됩니다.  작업 중간에 다른 스레드를 일시 중단하는 경우 언제가 안전할 것인지 확인할 방법은 없습니다.  스레드 일시 중단의 경우 데이터 손상이나 고정 중단이 발생할 수 있습니다.  스레드가 일시 중단된 상태로 배치되고 <xref:System.Threading.Thread.Resume%2A> 메서드를 사용하여 재개되지 않은 경우 응용 프로그램은 무한정 정지 상태에 놓이게 되고 응용 프로그램 데이터가 손상될 수 있습니다.  이러한 메서드는 사용되지 않는 것으로 표시됩니다.  
  
 동기화 기본 형식을 대상 스레드에서 보관한 경우 일시 중단 중 보관된 상태로 남게 됩니다.  이에 따라 다른 스레드가 <xref:System.Threading.Thread.Suspend%2A>를 수행하는 경우와 같이 기본 형식에 잠금을 가져오려는 경우 교착 상태가 발생합니다.  이 경우 문제 자체가 교착 상태로 나타나게 됩니다.  
  
## 해결  
 <xref:System.Threading.Thread.Suspend%2A> 및 <xref:System.Threading.Thread.Resume%2A>의 사용이 필요한 디자인은 피하도록 합니다.  스레드 간 협조를 위해서는 <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex> 또는 C\# `lock`문 같은 동기화 기본 형식을 사용합니다.  이러한 메서드를 사용해야 할 경우에는 시간 창을 줄이고 스레드가 일시 중단된 상태에 있는 동안 수행되는 코드의 분량을 최소화합니다.  
  
## 런타임 효과  
 이 MDA는 CLR에 아무런 영향을 주지 않습니다.  위험한 스레드 작업에 대한 데이터만 보고합니다.  
  
## Output  
 MDA는 활성화되도록 만든 위험한 스레드 메서드를 식별합니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 다음 코드 예제는 `dangerousThreadingAPI` 활성화의 원인이 된 <xref:System.Threading.Thread.Suspend%2A> 메서드에 대한 호출을 보여 줍니다.  
  
```  
using System.Threading;  
void FireMda()  
{  
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## 참고 항목  
 <xref:System.Threading.Thread>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [lock 문](../Topic/lock%20Statement%20\(C%23%20Reference\).md)