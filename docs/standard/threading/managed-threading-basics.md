---
title: "Managed Threading Basics | Microsoft Docs"
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
  - "multiple threads"
  - "threading [.NET Framework], multiple threads"
  - "threading [.NET Framework], about threading"
  - "managed threading"
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Managed Threading Basics
이 단원의 처음 다섯 가지 항목에서는 관리되는 스레딩을 사용해야 하는 경우를 결정하는 데 도움이 되는 정보와 몇 가지 기본 기능에 대해 설명합니다.  추가 기능을 제공하는 클래스에 대한 내용은 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)과 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하십시오.  
  
 이 단원의 나머지 항목은 Windows 운영 체제와 관리되는 스레딩의 상호 작용을 포함하여 보다 수준 높은 내용을 다룹니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 작업 병렬 라이브러리 및 PLINQ를 통해 다중 스레드 프로그램의 작업 및 데이터 병렬 처리를 위한 API를 제공합니다.  자세한 내용은 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)을 참조하십시오.  
  
## 단원 내용  
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)  
 다중 스레드의 장\/단점을 소개하고 스레드를 만들거나 스레드 풀 스레드를 사용하게 되는 상황을 논의합니다.  
  
 [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 .NET Framework의 여러 버전에 대해 스레드에서 처리되지 않은 예외의 동작, 특히 응용 프로그램이 종료되는 상황에 대해 설명합니다.  
  
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 여러 스레드에서 사용될 클래스의 데이터를 동기화하기 위한 전략에 대해 설명합니다.  
  
 [관리되는 스레드 상태](../../../docs/standard/threading/managed-thread-states.md)  
 기본적인 스레드 상태 및 스레드의 실행 여부를 판별하는 방법에 대해 설명합니다.  
  
 [Foreground and Background Threads](../../../docs/standard/threading/foreground-and-background-threads.md)  
 포그라운드 및 백그라운드 스레드의 차이에 대해 설명합니다.  
  
 [Managed and Unmanaged Threading in Windows](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 관리되는 스레딩과 관리되지 않는 스레딩 간의 관계를 설명하고, Windows 스레딩 API에 해당하는 관리되는 스레딩 API를 나열하고, COM 아파트와 관리되는 스레드의 상호 작용에 대해 설명합니다.  
  
 [Thread.Suspend, Garbage Collection, and Safe Points](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 스레드 보류와 가비지 수집에 대해 설명합니다.  
  
 [Thread Local Storage: Thread\-Relative Static Fields and Data Slots](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 스레드 상대 저장 메커니즘에 대해 설명합니다.  
  
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 비동기 방식 또는 실행 시간이 긴 동기 작업을 취소 토큰을 사용하여 취소하는 방법에 대해 설명합니다.  
  
## 참조  
 <xref:System.Threading.Thread>  
 관리되는 스레드가 비관리 코드에서 파생되었는지 또는 관리되는 응용 프로그램에서 만들어졌는지 여부에 관계없이 관리되는 스레드를 나타내는 **Thread** 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 사용자 인터페이스 개체와 다중 스레딩을 안전하게 함께 구현할 수 있는 방법을 제공합니다.  
  
## 관련 단원  
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 다중 스레드의 활동을 동기화하는 데 사용되는 관리되는 클래스에 대해 설명합니다.  
  
 [Managed Threading Best Practices](../../../docs/standard/threading/managed-threading-best-practices.md)  
 다중 스레딩과 관련된 일반적인 문제와 이러한 문제를 막기 위한 방법에 대해 설명합니다.  
  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)  
 비동기 및 다중 스레드 .NET Framework 응용 프로그램을 만드는 작업을 크게 단순화하는 작업 병렬 라이브러리 및 PLINQ에 대해 설명합니다.