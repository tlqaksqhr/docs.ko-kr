---
title: "Garbage Collection | Microsoft Docs"
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
  - "memory, garbage collection"
  - "garbage collection, automatic memory management"
  - "GC [.NET Framework]"
  - "memory, allocating"
  - "common language runtime, garbage collection"
  - "garbage collector"
  - "cleanup operations"
  - "garbage collection"
  - "memory, releasing"
  - "common language runtime, automatic memory management"
  - "automatic memory management"
  - "runtime, automatic memory management"
  - "runtime, garbage collection"
  - "garbage collection, about"
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
caps.latest.revision: 36
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 36
---
# Garbage Collection
.NET Framework 가비지 수집기는 응용 프로그램의 메모리 할당 및 해제를 관리합니다.  사용자가 새 개체를 만들 때마다 런타임에서는 관리되는 힙에서 해당 개체에 메모리를 할당하며  관리되는 힙에 주소 공간이 남아 있으면 새 개체에 필요한 공간을 계속하여 할당합니다.  그러나 메모리는 한정되어 있기 때문에  시간이 지나면 가비지 수집기가 수집을 수행하여 일부 메모리를 해제해야 합니다.  가비지 수집기의 최적화 엔진은 할당되는 메모리에 기반하여, 가비지를 수집할 가장 좋은 시기를 파악합니다.  가비지를 수집할 때 가비지 수집기는 응용 프로그램에서 더 이상 사용하지 않는 관리되는 힙에서 개체를 확인하고 메모리를 회수하는 데 필요한 작업을 수행합니다.  
  
<a name="related_topics"></a>   
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[Fundamentals of Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md)|가비지 수집이 작동하는 방법, 관리되는 힙에 개체가 할당되는 방법 및 기타 핵심 개념에 대해 설명합니다.|  
|[Garbage Collection and Performance](../../../docs/standard/garbage-collection/performance.md)|가비지 수집 및 성능 문제를 진단하는 데 사용할 수 있는 성능 검사에 대해 설명합니다.|  
|[인덱싱된 컬렉션](../../../docs/standard/garbage-collection/induced.md)|가비지 수집을 발생시키는 방법에 대해 설명합니다.|  
|[Latency Modes](../../../docs/standard/garbage-collection/latency.md)|가비지 수집의 실행 시기를 결정하는 모드에 대해 설명합니다.|  
|[Optimization for Shared Web Hosting](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|여러 개의 작은 웹 사이트에서 공유하는 서버에 대해 가비지 수집을 최적화하는 방법에 대해 설명합니다.|  
|[Garbage Collection Notifications](../../../docs/standard/garbage-collection/notifications.md)|전체 가비지 수집이 임박한 시점과 완료된 시점을 확인하는 방법에 대해 설명합니다.|  
|[Application Domain Resource Monitoring](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|응용 프로그램 도메인별로 CPU 및 메모리 사용량을 모니터링하는 방법에 대해 설명합니다.|  
|[Weak References](../../../docs/standard/garbage-collection/weak-references.md)|응용 프로그램에서 개체에 계속 액세스하는 동안 가비지 수집기가 해당 개체를 수집할 수 있도록 하는 기능에 대해 설명합니다.|  
  
## 참고 항목  
 <xref:System.GC?displayProperty=fullName>  
  
 <xref:System.GCCollectionMode?displayProperty=fullName>  
  
 <xref:System.GCNotificationStatus?displayProperty=fullName>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings?displayProperty=fullName>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName>  
  
 <xref:System.Object.Finalize%2A?displayProperty=fullName>  
  
 <xref:System.IDisposable?displayProperty=fullName>  
  
## 참고 항목  
 [Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md)