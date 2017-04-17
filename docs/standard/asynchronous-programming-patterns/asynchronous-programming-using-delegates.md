---
title: "Asynchronous Programming Using Delegates | Microsoft Docs"
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
  - "BeginInvoke method"
  - "asynchronous programming, delegates"
  - "asynchronous delegates"
  - "calling synchronous methods in asynchronous manner"
  - "EndInvoke method"
  - "calling asynchronous methods"
  - "delegates [.NET Framework], asynchronous"
  - "synchronous calling in asynchronous manner"
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Asynchronous Programming Using Delegates
대리자를 사용하면 비동기 방식으로 동기 메서드를 호출할 수 있습니다.  대리자를 동기식으로 호출하면 `Invoke` 메서드는 현재 스레드에서 직접 대상 메서드를 호출합니다.  `BeginInvoke` 메서드가 호출되면 CLR\(공용 언어 런타임\)에서 요청을 대기시키고 호출자로 즉시 돌아갑니다.  대상 메서드는 스레드 풀의 스레드에서 비동기 방식으로 호출됩니다.  요청을 제출한 원본 스레드는 대상 메서드와 함께 계속 실행될 수 있습니다.  `BeginInvoke` 메서드를 호출할 때 콜백 메서드를 지정하면 대상 메서드가 종료될 때 콜백 메서드가 호출됩니다.  콜백 메서드에서 `EndInvoke` 메서드는 반환 값과 입출력 또는 출력 전용 매개 변수를 가져옵니다.  `BeginInvoke`를 호출할 때 콜백 메서드를 지정하지 않으면 `BeginInvoke`를 호출한 스레드에서 `EndInvoke`가 호출될 수 있습니다.  
  
> [!IMPORTANT]
>  컴파일러는 사용자가 지정한 대리자 시그니처를 사용하여 `Invoke`, `BeginInvoke` 및 `EndInvoke` 메서드의 대리자 클래스를 내보내야 합니다.  `BeginInvoke` 및 `EndInvoke` 메서드는 네이티브 메서드로 데코레이팅되어야 합니다.  이러한 메서드는 네이티브 메서드로 표시되므로 CLR가 클래스 로드 타임에 해당 메서드의 구현 부분을 자동으로 제공합니다.  로더는 해당 메서드가 재정의되지 않았는지 확인합니다.  
  
## 단원 내용  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 대리자를 사용하여 일반적인 메서드를 비동기 방식으로 호출하는 방법에 대해 설명하고 비동기 호출이 반환되기를 기다리는 네 가지 방법을 보여 주는 간단한 코드 예제를 제공합니다.  
  
 [비동기 대리자 프로그래밍 샘플](../Topic/Asynchronous%20Delegates%20Programming%20Sample.md)  
 숫자를 인수분해하는 복잡한 코드 샘플을 통해 대리자를 사용하여 비동기 호출을 수행하는 방법을 보여 줍니다.  
  
## 관련 단원  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 .NET Framework를 사용한 비동기 프로그래밍에 대해 설명합니다.  
  
## 참고 항목  
 <xref:System.Delegate>