---
title: "추적 및 디버그 설정 스키마 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "구성 스키마[.NET Framework], 추적 및 디버그 설정"
  - "구성 섹션[.NET Framework]"
  - "구성 설정[.NET Framework], 디버깅"
  - "구성 설정[.NET Framework], 추적"
  - "요소[.NET Framework], 추적 및 디버그 설정"
  - "스키마 구성 설정"
  - "추적 수신기, 추적 및 디버그 설정 스키마"
  - "추적[.NET Framework], 추적 및 디버그 설정 스키마"
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# 추적 및 디버그 설정 스키마
추적 및 디버그 설정은 메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.  
  
 다음 표에서는 각 추적 및 디버그 설정 요소의 기능에 대해 설명합니다.  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|추적 소스에 대한 `Listeners` 컬렉션에 수신기를 추가합니다.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|`Listeners` 컬렉션에 수신기를 추가합니다.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|`sharedListeners` 컬렉션에 수신기를 추가합니다.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|추적 스위치를 설정할 수준을 지정합니다.|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정하고 메시지를 쓸 파일 이름도 지정합니다.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|추적 소스에 대한 `Listeners` 컬렉션을 지웁니다.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|추적에 대한 `Listeners` 컬렉션을 지웁니다.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|추적 소스에 대한 `Listeners` 컬렉션의 수신기에 필터를 추가합니다.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|추적에 대한 `Listeners` 컬렉션의 수신기에 필터를 추가합니다.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|`sharedListeners` 컬렉션의 수신기에 필터를 추가합니다.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|추적 소스에 대한 `Listeners` 컬렉션의 수신기를 지정합니다.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|추적에 대한 `Listeners` 컬렉션의 수신기를 지정합니다.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|추적에 대한 `Listeners` 컬렉션에서 수신기를 제거합니다.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|추적 소스에 대한 `Listeners` 컬렉션에서 수신기를 제거합니다.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|임의의 소스 또는 추적 요소가 참조할 수 있는 수신기를 포함합니다.|  
|[\<sources\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|추적 메시지를 발생시키는 추적 소스를 포함합니다.|  
|[\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|추적 메시지를 발생시키는 추적 소스를 지정합니다.|  
|[\<switches\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|추적 스위치와 추적 스위치를 설정할 수준이 들어 있습니다.|  
|[\<system.diagnostics\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|추적 메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.|  
  
## 참고 항목  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.Debug>   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)