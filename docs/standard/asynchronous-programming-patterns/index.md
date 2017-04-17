---
title: "Asynchronous Programming Patterns | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "asynchronous design patterns, .NET Framework"
  - ".NET Framework, asynchronous design patterns"
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Asynchronous Programming Patterns
.NET Framework에서는 비동기 작업을 수행하기 위한 세 가지 패턴을 제공합니다.  
  
-   <xref:System.IAsyncResult> 패턴이라고도 하는 APM\(비동기 프로그래밍 모델\) 패턴. 이 패턴에서는 비동기 작업을 수행하려면 `Begin` 및 `End` 메서드가 필요합니다. 예를 들어 비동기 쓰기 작업의 경우에는 `BeginWrite` 및 `EndWrite` 메서드가 필요합니다.  신규 개발에서는 이 패턴을 더 이상 사용하지 않는 것이 좋습니다.  자세한 내용은 [Asynchronous Programming Model \(APM\)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)을 참조하세요.  
  
-   EAP\(이벤트 기반 비동기 패턴\). 이 패턴에서는 `Async` 접미사가 있는 메서드가 필요하며 하나 이상의 이벤트, 이벤트 처리기 대리가 형식 및 `EventArg`에서 파생된 형식도 필요합니다.  EAP는 .NET Framework 2.0에 도입되었습니다.  이 패턴 역시 신규 개발에서는 더 이상 사용하지 않는 것이 좋습니다.  자세한 내용은 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)을 참조하세요.  
  
-   단일 메서드를 사용하여 비동기 작업 시작과 완료를 나타내는 TAP\(작업 기반 비동기 패턴\).  TAP는 .NET Framework 4에 도입되었으며, .NET Framework에서 비동기 프로그래밍을 수행할 때는 이 패턴을 사용하는 것이 좋습니다.  C\#의 [async](../Topic/async%20\(C%23%20Reference\).md) 및 [await](../Topic/await%20\(C%23%20Reference\).md) 키워드와 Visual Basic 언어의 [Async](../Topic/Async%20\(Visual%20Basic\).md) 및 [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md) 연산자는 TAP에 대한 언어 지원을 추가합니다.  자세한 내용은 [Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)을 참조하세요.  
  
## 패턴 비교  
 위의 세 가지 패턴 모델이 비동기 작업을 수행하는 방법을 빠르게 비교하려는 경우 지정한 오프셋에서부터 지정된 양의 데이터를 제공된 버퍼로 읽어 들이는 `Read` 메서드를 사용할 수 있습니다.  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
 이 메서드에 해당하는 APM 코드는 `BeginRead` 및 `EndRead` 메서드를 노출합니다.  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
 그리고 이 메서드에 해당하는 EAP 코드는 다음 형식 및 멤버 집합을 노출합니다.  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
 TAP에 해당하는 코드는 다음의 단일 `ReadAsync` 메서드를 노출합니다.  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
 TAP, APM 및 EAP에 대한 포괄적인 설명은 다음 섹션에 나와 있는 링크를 참조하세요.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[Asynchronous Programming Model \(APM\)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)|<xref:System.IAsyncResult> 인터페이스를 사용하여 비동기 동작을 제공하는 레거시 모델에 대해 설명합니다.  신규 개발에서는 이 모델을 더 이상 사용하지 않는 것이 좋습니다.|  
|[Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)|비동기 동작을 제공하기 위한 이벤트 기반 레거시 모델에 대해 설명합니다.  신규 개발에서는 이 모델을 더 이상 사용하지 않는 것이 좋습니다.|  
|[Task\-based Asynchronous Pattern \(TAP\)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|<xref:System.Threading.Tasks> 네임스페이스를 기반으로 하는 새 비동기 패턴에 대해 설명합니다.  .NET Framework 4 이상 버전에서 비동기 프로그래밍을 수행할 때는 이 모델을 사용하는 것이 좋습니다.|