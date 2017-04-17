---
title: "인덱싱된 컬렉션 | Microsoft Docs"
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
  - "가비지 수집, 강제 적용"
ms.assetid: 019008fe-4708-4e65-bebf-04fd9941e149
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# 인덱싱된 컬렉션
대부분의 경우, 가비지 수집기가 수집을 수행할 적절한 시기를 결정할 수 있으며, 가비지 수집기의 실행을 따로 조정하지 않는 것이 좋습니다.  경우에 따라서는 가비지 수집을 강제로 실행하여 응용 프로그램의 성능을 높일 수도 있습니다.  이런 경우 <xref:System.GC.Collect%2A?displayProperty=fullName> 메서드를 사용하여 가비지 수집을 강제로 실행할 수 있습니다.  
  
 응용 프로그램의 특정 코드 부분에 사용되는 메모리를 상당히 줄일 수 있는 경우 <xref:System.GC.Collect%2A?displayProperty=fullName> 메서드를 사용합니다.  예를 들어, 응용 프로그램에서 여러 개의 컨트롤이 포함된 복잡한 대화 상자를 사용하는 경우 대화 상자를 닫을 때 <xref:System.GC.Collect%2A>를 호출하면 대화 상자에서 사용하는 메모리를 즉시 확보하여 성능을 개선할 수 있습니다.  응용 프로그램에서 가비지 수집을 너무 자주 실행하면 가비지 수집기가 적절하지 않은 시간에 개체를 수집하려고 시도하여 응용 프로그램의 성능이 저하될 수 있으므로 가비지 수집은 너무 자주 실행하지 않는 것이 좋습니다.  다음 섹션에서 설명한 대로 컬렉션이 생산적일 때만 수집하도록 <xref:System.GCCollectionMode?displayProperty=fullName> 열거형 값을 <xref:System.GC.Collect%2A> 메서드에 제공할 수 있습니다.  
  
## GC 수집 모드  
 <xref:System.GCCollectionMode> 값이 포함된 <xref:System.GC.Collect%2A?displayProperty=fullName> 메서드 중 하나를 사용해서 다음과 같이 강제 적용되는 컬렉션의 동작을 지정할 수 있습니다.  
  
|`GCCollectionMode` 값|설명|  
|--------------------------|--------|  
|<xref:System.GCCollectionMode>|.NET Framework의 실행 버전에 대해 기본 가비지 수집 설정을 사용합니다.|  
|<xref:System.GCCollectionMode>|가비지 수집이 즉시 실행되도록 지정합니다.  <xref:System.GC.Collect?displayProperty=fullName> 오버로드를 호출하는 것과 동일합니다.  모든 세대의 전체 차단 컬렉션이 발생합니다.<br /><br /> 즉시 전체 차단 가비지 수집을 강제로 수행하기 전에 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName> 속성을 <xref:System.Runtime.GCLargeObjectHeapCompactionMode?displayProperty=fullName>로 설정하여 대형 개체 힙을 압축할 수도 있습니다.|  
|<xref:System.GCCollectionMode>|가비지 수집기가 현재 시간이 개체를 확보하기에 적절한 시점인지 결정하도록 합니다.<br /><br /> 가비지 수집기는 수집 작업이 생산적인지를 결정하여 충분히 생산적이지 않은 경우 개체를 확보하지 않고 반환합니다.|  
  
## 배경 또는 차단 컬렉션  
 유도된 컬렉션의 차단 여부를 지정하기 위해 <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29?displayProperty=fullName> 메서드 오버로드를 호출할 수 있습니다.  수행 컬렉션 유형은 메서드의 `mode` 및 `blocking` 매개 변수의 조합에 따라 달라집니다.  `mode`는 <xref:System.GCCollectionMode> 열거형의 멤버이고 `blocking`은 <xref:System.Boolean> 값입니다.  다음 표에서는 `mode` 및 `blocking` 인수의 상호 작용을 요약해서 보여줍니다.  
  
|`mode`|`blocking` \= `true`|`blocking` \= `false`|  
|------------|--------------------------|---------------------------|  
|<xref:System.GCCollectionMode> 또는 <xref:System.GCCollectionMode>|차단 컬렉션은 가능한 빨리 수행됩니다.  백그라운드 수집이 진행 중이고 생성이 0 또는 1인 경우 <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> 메서드는 차단 수집을 즉시 트리거하고 수집이 완료되면 반환합니다.  배경 수집이 진행 중이고 `generation` 매개 변수가 2인 경우 메서드는 배경 수집이 완료될 때까지 대기하고 차단 생성 2 수집을 트리거한 다음 반환합니다.|컬렉션은 가능한 빨리 수행됩니다.  <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> 메서드는 백그라운드 컬렉션을 요청하지만 이 작업이 항상 수행되지는 않으며 상황에 따라 차단 컬렉션이 계속 수행될 수도 있습니다.  백그라운드 수집이 이미 진행 중이면 메서드가 즉시 반환합니다.|  
|<xref:System.GCCollectionMode>|차단 컬렉션은 가비지 수집기의 상태와 `generation` 매개 변수에 따라 수행될 수 있습니다.  가비지 수집기가 최적의 성능을 제공하기 위해 시도합니다.|컬렉션은 가비지 수집기의 상태에 따라 수행될 수 있습니다.  <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%29> 메서드는 백그라운드 컬렉션을 요청하지만 이 작업이 항상 수행되지는 않으며 상황에 따라 차단 컬렉션이 계속 수행될 수도 있습니다.  가비지 수집기가 최적의 성능을 제공하기 위해 시도합니다.  백그라운드 수집이 이미 진행 중이면 메서드가 즉시 반환합니다.|  
  
## 참고 항목  
 [Latency Modes](../../../docs/standard/garbage-collection/latency.md)   
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)