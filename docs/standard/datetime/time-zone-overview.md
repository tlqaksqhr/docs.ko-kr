---
title: "표준 시간대 개요 | Microsoft Docs"
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
  - "조정 규칙[.NET Framework]"
  - "모호한 시간[.NET Framework]"
  - "일광 절약 시간[.NET Framework]"
  - "고정 규칙[.NET Framework]"
  - "유동 규칙[.NET Framework]"
  - "잘못된 시간[.NET Framework]"
  - "표준 시간대[.NET Framework], 표준 시간대 정보"
  - "표준 시간대[.NET Framework], 만들기"
  - "표준 시간대[.NET Framework], 용어"
  - "TimeZoneInfo 클래스, TimeZoneInfo 클래스 정보"
  - "전환 시간[.NET Framework]"
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 표준 시간대 개요
<xref:System.TimeZoneInfo> 클래스를 사용하면 표준 시간대 인식 응용 프로그램을 쉽게 만들 수 있습니다.  <xref:System.TimeZone> 클래스는 현지 표준 시간대 및 UTC\(협정 세계시\)를 사용한 작업을 지원합니다.  <xref:System.TimeZoneInfo> 클래스는 이러한 두 표준 시간대는 물론 레지스트리에 정보가 미리 정의되어 있는 모든 표준 시간대를 지원합니다.  또한 <xref:System.TimeZoneInfo>를 사용하여 시스템에 해당 정보가 없는 사용자 지정 표준 시간대를 정의할 수 있습니다.  
  
## 표준 시간대 주요 사항  
 표준 시간대는 같은 시간이 사용되는 지역입니다.  항상 그런 것은 아니지만 일반적으로 인접한 표준 시간대의 간격은 한 시간입니다.  전 세계 어떤 표준 시간대의 시간도 UTC\(협정 세계시\)에서의 오프셋으로 나타낼 수 있습니다.  
  
 전 세계 대부분의 표준 시간대는 일광 절약 시간을 지원합니다.  일광 절약 시간에서는 봄 또는 초여름에는 한 시간 앞당기고, 늦은 여름 또는 가을에는 보통 시간이나 표준 시간으로 돌려 일광 시간을 최대한 늘리려고 합니다.  이렇게 표준 시간에서 다른 시간으로 변경하거나 다른 시간에서 표준 시간으로 변경하는 것을 조정 규칙이라고 합니다.  
  
 특정 표준 시간대에 일광 절약 시간에서 전환하거나 일광 절약 시간으로 전환하는 작업은 고정 조정 규칙 또는 유동 조정 규칙을 통해 정의할 수 있습니다.  고정 조정 규칙은 매년 이러한 일광 절약 시간 전환이 수행되는 특정 날짜를 설정합니다.  예를 들어 매년 10월 25일에 수행되는 일광 절약 시간에서 표준 시간으로의 전환은 고정 조정 규칙을 따릅니다.  보다 일반적인 조정 규칙은 유동 조정 규칙으로, 이 규칙은 일광 절약 시간 전환이 수행될 특정 월, 주, 일을 설정합니다.  예를 들어 3월 셋째 일요일에 수행되는 표준 시간에서 일광 절약 시간으로의 전환은 유동 조정 규칙을 따릅니다.  
  
 조정 규칙을 지원하는 표준 시간대의 경우 일광 절약 시간 전환을 수행하면 두 가지 예외적인 시간인 잘못된 시간과 모호한 시간이 생성됩니다.  잘못된 시간은 표준 시간에서 일광 절약 시간으로 전환할 때 생성되는 존재하지 않는 시간입니다.  예를 들어 특정 일의 오전 2시에 이러한 전환이 수행 되어 및 시간을 변경 하려면, 오전 3시로 변경을 야기합니다. 오전 2시와 오전 2:59:99 사이의 각 시간 간격은 유효 하지 않습니다.  모호한 시간은 단일 표준 시간대의 서로 다른 두 가지 시간으로 매핑될 수 있는 시간입니다.  이 시간은 일광 절약 시간에서 표준 시간으로 전환할 때 생성됩니다.  예를 들어, 특정 일의 오전 2시에 이러한 전환이 수행 되어 시간을 오전 1시로 변경한다면, 오전 1시와 오전 1:59:99 사이의 각 시간 간격은 오전 표준 시간 또는 일광 절약 시간으로 해석할 수 있습니다.  
  
## 표준 시간대 용어  
 다음 표에서는 표준 시간대를 사용하여 작업하고 표준 시간대 인식 응용 프로그램을 개발할 때 일반적으로 사용되는 용어를 정의합니다.  
  
|용어|정의|  
|--------|--------|  
|조정 규칙|표준 시간에서 일광 절약 시간으로 전환하고 다시 일광 절약 시간에서 표준 시간으로 전환할 때 정의하는 규칙입니다.  각 조정 규칙에는 규칙이 적용되는 시기\(예: 1986년 1월 1일에서 2006년 12월 31일까지의 조정 규칙\)를 정의하는 시작 및 종료 날짜, 델타\(조정 규칙 적용 결과로 변경되는 표준 시간 간격\), 조정 기간 동안 전환이 수행될 특정 날짜 및 시간에 대한 정보가 들어 있습니다.  전환은 고정 규칙 또는 유동 규칙을 따를 수 있습니다.|  
|모호한 시간|단일 표준 시간대의 서로 다른 두 가지 시간으로 매핑될 수 있는 시간입니다.  표준 시간대의 일광 절약 시간에서 표준 시간으로의 전환과 같이 클럭 시간이 제시간에 원래 시간으로 맞춰질 때 이러한 시간이 발생합니다.  예를 들어, 특정 일의 오전 2시에 이러한 전환이 수행 되어 시간을 오전 1시로 변경한다면, 오전 1시와 오전 1:59:99 사이의 각 시간 간격은 오전 표준 시간 또는 일광 절약 시간으로 해석할 수 있습니다.|  
|고정 규칙|일광 절약 시간 전환이 수행될 특정 날짜를 설정하는 조정 규칙입니다.  예를 들어 매년 10월 25일에 수행되는 일광 절약 시간에서 표준 시간으로의 전환은 고정 조정 규칙을 따릅니다.|  
|유동 규칙|일광 절약 시간 전환이 수행될 특정 월, 주, 일을 설정하는 조정 규칙입니다.  예를 들어 3월 셋째 일요일에 수행되는 표준 시간에서 일광 절약 시간으로의 전환은 유동 조정 규칙을 따릅니다.|  
|잘못된 시간|표준 시간에서 일광 절약 시간으로의 전환에 대한 아티팩트인 존재하지 않는 시간입니다.  표준 시간대의 표준 시간에서 일광 절약 시간으로의 전환과 같이 클럭 시간이 제시간에 원래 시간으로 맞춰질 때 이러한 시간이 발생합니다.  예를 들어 특정 일의 오전 2시에 이러한 전환이 수행 되어 및 시간을 변경 하려면, 오전 3시로 변경을 야기합니다. 오전 2시와 오전 2:59:99 사이의 각 시간 간격은 유효 하지 않습니다.|  
|전환 시간|특정 표준 시간대에서의 일광 절약 시간에서 표준 시간으로, 표준 시간에서 일광 절약 시간으로의 변경과 같은 특정 시간 변경에 대한 정보입니다.|  
  
## 표준 시간대와 TimeZoneInfo 클래스  
 .NET Framework에서 <xref:System.TimeZoneInfo> 개체는 표준 시간대를 나타냅니다.  <xref:System.TimeZoneInfo> 클래스에는 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 배열을 반환하는 <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> 메서드가 포함되어 있습니다.  이 배열의 각 요소는 특정 기간 동안의 일광 절약 시간 전환에 대한 정보를 제공합니다. 일광 절약 시간을 지원하지 않는 표준 시간대의 경우 이 메서드는 빈 배열을 반환합니다. 각 <xref:System.TimeZoneInfo.AdjustmentRule> 개체에는 일광 절약 시간 전환이 수행되는 특정 날짜 및 시간을 정의하는 <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> 및 <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> 속성이 있습니다.  <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> 속성은 전환이 고정인지, 아니면 유동인지를 나타냅니다.  
  
 .NET Framework는 레지스트리에 저장되어 있고 Windows 운영 체제에서 제공하는 표준 시간대 정보를 사용합니다.  전 세계적으로 표준 시간대가 많이 있으므로 기존 표준 시간대가 모두 레지스트리에 나타나는 것은 아닙니다.  또한 레지스트리는 동적 구조이므로 미리 정의된 표준 시간대를 레지스트리에 추가하거나 레지스트리에서 제거할 수 있습니다.  결국 레지스트리에 기록 표준 시간대 데이터를 포함하지 않아도 됩니다.  예를 들어 Windows XP 레지스트리에는 단일 표준 시간대 조정 집합에 대한 데이터만 포함되어 있습니다.  Windows Vista에서는 동적 표준 시간대 데이터를 지원하므로 단일 표준 시간대에서 특정 연 간격에 적용되는 여러 조정 규칙을 사용할 수 있습니다.  그러나 Windows Vista 레지스트리에 정의되어 있으며 일광 절약 시간을 지원하는 대부분의 표준 시간대는 하나 또는 두 개의 미리 정의된 조정 규칙만 사용합니다.  
  
 레지스트리에 대한 <xref:System.TimeZoneInfo> 클래스의 독립성으로 인해 표준 시간대 인식 응용 프로그램의 경우 레지스트리에 특정 표준 시간대가 정의되어 있다고 확신할 수 없습니다.  따라서 현지 표준 시간대 또는 UTC를 나타내는 표준 시간대가 아닌 특정 표준 시간대를 인스턴스화하려고 할 때 예외 처리를 사용해야 합니다.  또한 레지스트리에서 필수 <xref:System.TimeZoneInfo> 개체를 인스턴스화할 수 없는 경우 응용 프로그램을 계속 진행하는 데 사용되는 일부 메서드를 제공해야 합니다.  
  
 필수 표준 시간대가 없는 경우를 위해 레지스트리에서 찾을 수 없는 사용자 지정 표준 시간대를 만드는 데 사용할 수 있는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드가 <xref:System.TimeZoneInfo> 클래스에 포함되어 있습니다.  사용자 지정 표준 시간대 만들기에 대한 자세한 내용은 [방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 및 [방법: 조정 규칙을 사용하여 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)를 참조하십시오.  또한 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드를 사용하면 새로 만든 표준 시간대를 문자열로 변환한 다음 데이터베이스, 텍스트 파일, 레지스트리 또는 응용 프로그램 리소스 등의 데이터 저장소에 저장할 수 있습니다.  그리고 나서 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드를 사용하여 이 문자열을 <xref:System.TimeZoneInfo> 개체로 다시 변환할 수 있습니다.  자세한 내용은 [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 및 [방법: 포함 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)을 참조하십시오.  
  
 각 표준 시간대의 특성은 UTC에서의 기본 오프셋은 물론 기존 조정 규칙을 반영하는 UTC에서의 오프셋을 통해 지정되므로 한 표준 시간대의 시간을 다른 표준 시간대의 시간으로 쉽게 변환할 수 있습니다.  이를 위해  <xref:System.TimeZoneInfo> 개체에 다음을 비롯한 여러 변환 메서드가 포함되어 있습니다.  
  
-   UTC를 지정한 표준 시간대의 시간으로 변환하는 <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>  
  
-   지정한 표준 시간대의 시간을 UTC로 변환하는 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>  
  
-   한 지정한 표준 시간대의 시간을 다른 지정한 표준 시간대의 시간으로 변환하는 <xref:System.TimeZoneInfo.ConvertTime%2A>  
  
-   <xref:System.TimeZoneInfo> 개체 대신 표준 시간대 식별자를 매개 변수로 사용하여 한 지정한 표준 시간대의 시간을 다른 지정한 표준 시간대의 시간으로 변환하는 <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>  
  
 표준 시간대 간의 시간 변환에 대한 자세한 내용은 [표준 시간대 간에 시간 변환](../../../docs/standard/datetime/converting-between-time-zones.md)을 참조하십시오.  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)