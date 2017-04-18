---
title: "&lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;clear&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<trace>의 <listeners>에 대한 <clear> 요소"
  - "<trace>의 <listeners>에 대한 clear 요소"
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;clear&gt; 요소
추적에 대한 `Listeners` 컬렉션을 지웁니다.  
  
## 구문  
  
```  
<clear/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
|`trace`|추적 메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.|  
|`listeners`|메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.  수신기는 추적 출력을 적절한 대상으로 안내합니다.|  
  
## 설명  
 `<clear>` 요소는 추적에 대한 `Listeners` 컬렉션에서 모든 수신기를 제거합니다.  `<add>` 요소를 사용하기 전에 `<clear>` 요소를 사용하여 컬렉션에 다른 활성 수신기가 없는지 확인할 수 있습니다.  
  
 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=fullName> 속성\(`System.Diagnostics.Trace.Listeners.Clear()`\)에서 <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 메서드를 호출하여 `Listeners` 컬렉션을 프로그래밍 방식으로 지울 수 있습니다.  
  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
> [!NOTE]
>  `<clear>` 요소는 `Listeners` 컬렉션에서 <xref:System.Diagnostics.DefaultTraceListener>를 제거하여 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=fullName>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=fullName> 메서드의 동작을 변경합니다.  `Assert` 또는 `Fail` 메서드를 호출하면 메시지 상자가 정상적으로 표시됩니다.  그러나 `Listeners` 컬렉션에 <xref:System.Diagnostics.DefaultTraceListener>가 없는 경우에는 메시지 상자가 표시되지 않습니다.  
  
## 예제  
 다음 예제에서는 `<add>` 요소를 사용하기 전에 `<clear>` 요소를 사용하여 `console` 수신기를 추적에 대한 `Listeners` 컬렉션에 추가하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## 참고 항목  
 <xref:System.Diagnostics.Trace.Listeners%2A>   
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.TraceSource>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)