---
title: "&lt;system.diagnostics&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.diagnostics> 요소"
  - "system.diagnostics 요소"
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# &lt;system.diagnostics&gt; 요소
메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.  
  
## 구문  
  
```  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<어설션\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정하고 메시지를 쓸 파일 이름도 지정합니다.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|임의의 소스 또는 추적 요소가 참조할 수 있는 수신기를 포함합니다.  공유 수신기로 식별된 수신기는 소스 또는 추적에 이름별로 추가할 수 있습니다.|  
|[\<소스\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|추적 메시지를 발생시키는 추적 소스를 지정합니다.|  
|[\<스위치\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|추적 스위치와 추적 스위치를 설정할 수준이 들어 있습니다.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|추적 메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## 예제  
 다음 예제에서는 **\<system.diagnostics\>** 요소 안에 추적 수신기와 추적 스위치를 포함하는 방법을 보여 줍니다.  `General` 추적 스위치는 [TraceLevel.Error](frlrfSystemDiagnosticsTraceLevelClassTopic) 수준으로 설정됩니다.  추적 수신기 `myListener`는 `MyListener.log`라는 파일을 만들어 그 파일에 출력을 씁니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서는 텍스트를 사용하여 스위치 값을 지정할 수 있습니다.  예를 들어, <xref:System.Diagnostics.BooleanSwitch>에 `true`를 지정하거나, <xref:System.Diagnostics.TraceSwitch>에 `Error`를 지정하는 것과 같이 열거형 값을 나타내는 텍스트를 사용할 수 있습니다.  `<add name="myTraceSwitch" value="Error" />` 줄은 `<add name="myTraceSwitch" value="1" />`과 같습니다.  
  
```  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)