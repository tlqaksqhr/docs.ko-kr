---
title: "Reader-Writer Locks | Microsoft Docs"
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
  - "ReaderWriterLock class, about ReaderWriterLock class"
  - "threading [.NET Framework], ReaderWriterLock class"
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Reader-Writer Locks
<xref:System.Threading.ReaderWriterLockSlim> 클래스를 사용하면 다중 스레드가 동시에 하나의 리소스를 읽을 수 있지만 리소스를 쓰기 위해서는 배타적 잠금을 기다려야 합니다.  
  
 응용 프로그램 내에서 <xref:System.Threading.ReaderWriterLockSlim>을 사용하여 공유 리소스에 액세스하는 여러 스레드 간에 원활한 동기화를 제공할 수 있습니다.  잠금은 <xref:System.Threading.ReaderWriterLockSlim> 자체에 대해 수행됩니다.  
  
 다른 스레드 동기화 메커니즘과 마찬가지로 <xref:System.Threading.ReaderWriterLockSlim>에서 제공하는 잠금을 스레드가 무시하지 않도록 해야 합니다.  이렇게 하는 한 가지 방법은 공유 리소스를 캡슐화하는 클래스를 설계하는 것입니다.  이 클래스는 전용 공개 리소스에 액세스하고 동기화를 위해 전용 <xref:System.Threading.ReaderWriterLockSlim>을 사용하는 멤버를 제공할 수 있습니다.  예제를 보려면 <xref:System.Threading.ReaderWriterLockSlim> 클래스에 대한 코드 예제를 참조하십시오.  <xref:System.Threading.ReaderWriterLockSlim>은 개별 개체를 동기화하는 데 사용할 수 있는 효율적인 클래스입니다.  
  
 읽기 및 쓰기 작업 기간이 최소되도록 응용 프로그램을 구성해야 합니다.  쓰기 잠금은 배타적이므로 쓰기 작업이 오래 걸리면 처리량에 직접적인 영향을 줍니다.  읽기 작업이 오래 걸리면 대기 중인 작성기가 차단되며 하나 이상의 스레드가 쓰기 잠금을 기다리는 경우 읽기 액세스를 요청하는 스레드도 차단됩니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에는 두 개의 판독기\/작성기 잠금 <xref:System.Threading.ReaderWriterLockSlim> 및 <xref:System.Threading.ReaderWriterLock>이 있습니다.  <xref:System.Threading.ReaderWriterLockSlim>은 새로운 모든 개발에 권장됩니다.  <xref:System.Threading.ReaderWriterLockSlim>은 <xref:System.Threading.ReaderWriterLock>과 비슷하지만 재귀 규칙과 잠금 상태를 업그레이드하고 다운그레이드하는 규칙이 간단합니다.  <xref:System.Threading.ReaderWriterLockSlim>은 많은 잠재적인 교착 상태를 방지합니다.  또한 <xref:System.Threading.ReaderWriterLockSlim>의 성능이 <xref:System.Threading.ReaderWriterLock>보다 훨씬 더 좋습니다.  
  
## 참고 항목  
 <xref:System.Threading.ReaderWriterLockSlim>   
 <xref:System.Threading.ReaderWriterLock>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)