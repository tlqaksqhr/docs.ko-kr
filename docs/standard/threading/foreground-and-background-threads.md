---
title: "Foreground and Background Threads | Microsoft Docs"
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
  - "threading [.NET Framework], foreground"
  - "threading [.NET Framework], background"
  - "foreground threads"
  - "background threads"
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Foreground and Background Threads
관리되는 스레드는 백그라운드 스레드나 포그라운드 스레드 중 하나가 됩니다.  백그라운드 스레드는 관리되는 실행 환경을 유지하지 않는다는 한 가지 점을 제외하면 포그라운드 스레드와 동일합니다.  모든 포그라운드 스레드가 관리되는 프로세스\(.exe 파일이 관리되는 어셈블리인 경우\)에서 중단되면 시스템에서 모든 백그라운드 스레드를 중지하고 종료합니다.  
  
> [!NOTE]
>  프로세스가 종료되어 런타임에 백그라운드 스레드를 중단하면 스레드에서 예외가 throw되지 않습니다.  하지만 <xref:System.AppDomain.Unload%2A?displayProperty=fullName> 메서드가 응용 프로그램 도메인을 언로드하기 때문에 스레드가 중단되면 <xref:System.Threading.ThreadAbortException>이 포그라운드 스레드와 백그라운드 스레드 모두에서 throw됩니다.  
  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName> 속성을 사용하여 스레드가 백그라운드 스레드인지 아니면 포그라운드 스레드인지를 결정하거나 해당 상태를 변경합니다.  <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정하여 언제든지 스레드를 백그라운드 스레드로 변경할 수 있습니다.  
  
> [!IMPORTANT]
>  스레드의 포그라운드 또는 백그라운드 상태는 스레드에서 처리되지 않은 예외의 결과에 영향을 미치지 않습니다.  .NET Framework 버전 2.0의 경우 포그라운드 스레드나 백그라운드 스레드에서의 처리되지 않은 예외로 인해 응용 프로그램이 종료됩니다.  [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md)를 참조하십시오.  
  
 관리되는 스레드 풀에 속하는 스레드\(즉, <xref:System.Threading.Thread.IsThreadPoolThread%2A> 속성이 `true`인 스레드\)는 백그라운드 스레드입니다.  비관리 코드에서 관리되는 실행 환경으로 들어가는 모든 스레드는 백그라운드 스레드로 표시됩니다.  새 <xref:System.Threading.Thread> 개체를 만들고 시작함으로써 생성된 모든 스레드는 기본적으로 포그라운드 스레드입니다.  
  
 스레드를 사용하여 소켓 연결과 같은 동작을 모니터하는 경우 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정하여 스레드가 프로세스 종료를 막지 않도록 합니다.  
  
## 참고 항목  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=fullName>   
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadAbortException>