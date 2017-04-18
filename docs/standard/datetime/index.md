---
title: "날짜, 시간 및 표준 시간대 | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "날짜 및 시간 데이터[.NET Framework]"
  - "시간[.NET Framework], 시간대"
  - "표준 시간대 개체[.NET Framework]"
  - "표준 시간대[.NET Framework]"
  - "시간[.NET Framework], 시간대"
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# 날짜, 시간 및 표준 시간대
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 기본 <xref:System.DateTime> 구조체 이외에도 표준 시간대 작업에 사용할 수 있는 다음과 같은 클래스를 제공합니다.  
  
-   <xref:System.TimeZone>  
  
     이 클래스를 사용하여 시스템의 현지 표준 시간대 및 UTC\(협정 세계시\) 시간대 작업을 수행합니다.  <xref:System.TimeZoneInfo> 클래스가 대부분의 <xref:System.TimeZone> 클래스 기능보다 우선합니다.  
  
-   <xref:System.TimeZoneInfo>  
  
     이 클래스를 사용하여 시스템에 미리 정의되어 있는 표준 시간대 작업을 수행하고, 새 표준 시간대를 만들고, 표준 시간대 간에 날짜 및 시간을 쉽게 변환할 수 있습니다.  그러나 새로운 개발 작업에는 <xref:System.TimeZone> 클래스 대신 <xref:System.TimeZoneInfo> 클래스를 사용해야 합니다.  
  
-   <xref:System.DateTimeOffset>  
  
     이 구조체를 사용하여 UTC와의 해당 오프셋\(차이\)을 알 수 없는 날짜 및 시간 관련 작업을 수행합니다.  <xref:System.DateTimeOffset> 구조체는 날짜와 시간 값을 해당 시간의 UTC 오프셋과 결합합니다.  이러한 UTC와의 관계로 인해 개별 날짜 및 시간 값이 단일 시점을 명확하게 식별합니다.  그러므로 <xref:System.DateTimeOffset> 값이 <xref:System.DateTime> 값에 비해 컴퓨터 간 이식성이 높습니다.  
  
 이 단원에서는 표준 시간대 작업을 수행하고 표준 시간대 간에 날짜 및 시간을 변환할 수 있는 표준 시간대 인식 응용 프로그램을 만드는 데 필요한 정보를 제공합니다.  
  
## 단원 내용  
 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)  
 표준 시간대 인식 응용 프로그램을 만들 때 사용되는 용어, 개념 및 발생하는 문제점에 대해 설명합니다.  
  
 [DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중 선택](../../../docs/standard/datetime/choosing-between-datetime.md)  
 날짜 및 시간 데이터 작업 시 <xref:System.DateTime>, <xref:System.DateTimeOffset> 및 <xref:System.TimeZoneInfo> 형식을 사용하는 경우에 대해 설명합니다.  
  
 [로컬 시스템에 정의된 표준 시간대 찾기](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)  
 로컬 시스템의 표준 시간대를 열거하는 방법에 대해 설명합니다.  
  
 [방법: 컴퓨터에 있는 표준 시간대 열거](../../../docs/standard/datetime/enumerate-time-zones.md)  
 컴퓨터 레지스트리에 정의되어 있는 표준 시간대를 열거하며 사용자가 목록에서 미리 정의된 표준 시간대를 선택할 수 있도록 하는 예제를 제공합니다.  
  
 [방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스](../../../docs/standard/datetime/access-utc-and-local.md)  
 협정 세계시 및 현지 표준 시간대에 액세스하는 방법에 대해 설명합니다.  
  
 [방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)  
 로컬 시스템 레지스트리에서 <xref:System.TimeZoneInfo> 개체를 인스턴스화하는 방법에 대해 설명합니다.  
  
 [DateTimeOffset 개체 인스턴스화](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)  
 <xref:System.DateTimeOffset> 개체를 인스턴스화하는 방법 및 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값으로 변환하는 방법에 대해 설명합니다.  
  
 [방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)  
 일광 절약 시간 전환을 지원하지 않는 사용자 지정 표준 시간대를 만드는 방법에 대해 설명합니다.  
  
 [방법: 조정 규칙을 사용하여 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)  
 일광 절약 시간 전환을 하나 이상 지원하는 사용자 지정 표준 시간대를 만드는 방법에 대해 설명합니다.  
  
 [표준 시간대 저장 및 복원](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)  
 <xref:System.TimeZoneInfo>의 표준 시간대 데이터 serialization 및 deserialization 지원에 대해 설명하고 이러한 기능을 사용할 수 있는 몇 가지 시나리오를 제공합니다.  
  
 [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)  
 사용자 지정 표준 시간대를 만들어 리소스 파일에 해당 정보를 저장하는 방법에 대해 설명합니다.  
  
 [방법: 포함 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)  
 포함된 리소스 파일에 저장된 사용자 지정 표준 시간대를 인스턴스화하는 방법에 대해 설명합니다.  
  
 [날짜 및 시간에 대한 산술 연산 수행](../../../docs/standard/datetime/performing-arithmetic-operations.md)  
 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값을 더하거나 빼거나 비교할 때 발생할 수 있는 문제에 대해 설명합니다.  
  
 [방법: 날짜 및 시간 산술 연산의 표준 시간대 사용](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)  
 표준 시간대의 조정 규칙을 반영하는 날짜 및 시간 연산을 수행하는 방법에 대해 설명합니다.  
  
 [DateTime과 DateTimeOffset 간 변환](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)  
 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값 간의 변환 방법에 대해 설명합니다.  
  
 [표준 시간대 간에 시간 변환](../../../docs/standard/datetime/converting-between-time-zones.md)  
 표준 시간대 간에 시간을 변환하는 방법에 대해 설명합니다.  
  
 [방법: 모호한 시간 확인](../../../docs/standard/datetime/resolve-ambiguous-times.md)  
 모호한 시간을 표준 시간대의 표준 시간에 매핑하여 확인하는 방법에 대해 설명합니다.  
  
 [방법: 사용자의 모호한 시간 확인 작업 허용](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)  
 사용자가 모호한 현지 시간과 협정 세계시 간의 매핑을 결정할 수 있도록 하는 방법에 대해 설명합니다.  
  
## 참조  
 <xref:System.TimeZoneInfo?displayProperty=fullName>