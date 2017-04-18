---
title: "&lt;trace&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#trace"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<trace> 요소"
  - "수신기"
  - "trace 요소"
  - "추적 수신기, <trace> 요소"
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;trace&gt; 요소
추적 메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.  
  
## 구문  
  
```  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`autoflush`|선택적 특성입니다.<br /><br /> 매 쓰기 작업 후 추적 수신기가 출력 버퍼를 자동으로 플러시할지 지정합니다.|  
|`indentsize`|선택적 특성입니다.<br /><br /> 들여쓸 공백의 수를 지정합니다.|  
|`useGlobalLock`|선택적 특성입니다.<br /><br /> 전역 잠금 사용 여부를 나타냅니다.|  
  
## autoflush 특성  
  
|값|설명|  
|-------|--------|  
|`false`|출력 버퍼를 자동으로 플러시하지 않습니다.  이 값이 기본값입니다.|  
|`true`|출력 버퍼를 자동으로 플러시합니다.|  
  
## useGlobalLock 특성  
  
|값|설명|  
|-------|--------|  
|`false`|수신기가 스레드로부터 안전하면 전역 잠금을 사용하지 않고, 그렇지 않으면 전역 잠금을 사용합니다.|  
|`true`|수신기가 스레드로부터 안전한지 여부와 상관없이 전역 잠금을 사용합니다.  이 값이 기본값입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<수신기\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|메시지를 수집하여 저장하고 라우트하는 수신기를 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
  
## 예제  
 다음 예제에서는 `<trace>` 요소를 사용하여 `Listeners` 컬렉션에 `MyListener` 수신기를 추가하는 방법을 보여 줍니다.  `MyListener`는 `MyListener.log`라는 파일을 만들어 해당 파일에 출력을 씁니다.  `useGlobalLock` 특성을 `false`로 설정하면 추적 수신기가 스레드로부터 안전한 경우 전역 잠금이 사용되지 않습니다.  `autoflush` 특성을 `true`로 설정하면 <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=fullName> 메서드 호출 여부와 관계없이 추적 수신기가 파일에 쓸 수 있습니다.  `indentsize` 특성을 0으로 설정하면 <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=fullName> 메서드가 호출될 때 수신기가 들여쓰기하지 않습니다.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)