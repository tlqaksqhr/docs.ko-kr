---
title: "Managed Threading | Microsoft Docs"
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
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: 7b46a7d9-c6f1-46d1-a947-ae97471bba87
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Managed Threading
응용 프로그램을 개발할 때 대상 컴퓨터의 프로세서 개수에 관계없이 응용 프로그램에서 현재 다른 작업을 수행 중이라도 사용자에게 신속한 상호 작용을 제공하기를 바랄 것입니다.  다중 스레드 실행을 사용하면 응용 프로그램에서 사용자에게 응답하는 속도가 향상될 뿐 아니라 사용자 이벤트 사이나 사용자 이벤트를 실행하는 중에도 프로세서를 활용할 수 있습니다.  이 단원에서는 스레딩의 기본 개념을 소개하고 관리되는 스레딩 개념 및 그 사용에 대해 설명합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스, [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md), <xref:System.Collections.Concurrent?displayProperty=fullName> 네임스페이스의 새 동시 컬렉션 클래스, 스레드 개념이 아닌 작업 개념을 기반으로 하는 새 프로그래밍 모델 등을 통해 다중 스레드 프로그래밍을 매우 간단하게 수행할 수 있습니다.  자세한 내용은 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)을 참조하십시오.  
  
## 단원 내용  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)  
 관리되는 스레딩에 대해 간략히 설명하고 여러 스레드를 사용해야 하는 경우에 대해 설명합니다.  
  
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)  
 스레드를 만들고, 시작하고, 일시 중지하고, 다시 시작하고, 취소하는 방법에 대해 설명합니다.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 동기화 수준, 교착 상태 및 경쟁 상태를 피하는 방법, 단일 프로세서 및 다중 프로세서 컴퓨터, 기타 스레딩 문제를 다룹니다.  
  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)  
 여러 다른 스레드에서 스레드 활동 및 액세스되는 개체 데이터를 동기화하는 데 사용할 수 있는 관리되는 클래스에 대해 설명하고 스레드 풀 스레드에 대해 간략히 설명합니다.  
  
## 참조  
 <xref:System.Threading>  
 관리되는 스레드를 사용하고 동기화하는 클래스를 포함합니다.  
  
 <xref:System.Collections.Concurrent>  
 다중 스레드와 함께 사용해도 안전한 컬렉션 클래스를 포함합니다.  
  
 <xref:System.Threading.Tasks>  
 동시 처리 작업을 만들고 예약하기 위한 클래스를 포함합니다.  
  
## 관련 단원  
 [응용 프로그램 도메인](../../../docs/framework/app-domains/application-domains.md)  
 응용 프로그램 도메인과 공용 언어 인프라에서 이를 사용하는 방법에 대한 개요를 제공합니다.  
  
 [비동기 파일 I\/O](../../../docs/standard/io/비동기-파일-i-o.md)  
 비동기 I\/O의 기본 연산 및 성능상의 이점에 대해 설명합니다.  
  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 비동기 프로그래밍에 대한 개요를 제공합니다.  
  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 대리자의 기본 제공 기능을 사용하여 스레드 풀 스레드의 메서드를 호출하는 방법에 대해 설명합니다.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 응용 프로그램에서 다중 스레드의 사용을 단순화하는 병렬 프로그래밍 라이브러리에 대해 설명합니다.  
  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 다중 프로세스를 활용하기 위해 쿼리를 병렬로 실행하는 시스템에 대해 설명합니다.