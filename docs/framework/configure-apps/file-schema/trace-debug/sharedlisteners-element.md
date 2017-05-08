---
title: "&lt;sharedListeners&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<sharedListeners> 요소"
  - "수신기"
  - "공유 수신기"
  - "sharedListeners 요소"
  - "추적 수신기, <sharedListeners> 요소"
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;sharedListeners&gt; 요소
임의의 소스 또는 추적 요소가 참조할 수 있는 수신기를 포함합니다.  이러한 수신기는 기본적으로 추적을 수신하지 않기 때문에 런타임에 이러한 수신기를 검색할 수 없습니다.  공유 수신기로 식별된 수신기는 소스 또는 추적에 이름별로 추가할 수 있습니다.  
  
## 구문  
  
```  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|`sharedListeners` 컬렉션에 수신기를 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`Configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
  
## 설명  
 공유 수신기 컬렉션에 수신기를 추가해도 이 수신기가 활성 수신기가 되지 않습니다.  별도로 해당 추적 요소에 대한 `Listeners` 컬렉션에 추가하여 추적 소스 또는 추적에 추가해야 합니다.  .NET Framework의 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생됩니다.  
  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `<sharedListeners>` 요소를 사용하여 `console` 수신기를 <xref:System.Diagnostics.TraceSource> 및 <xref:System.Diagnostics.Trace> 클래스 모두에 대한 `Listeners` 컬렉션에 추가하는 방법을 보여 줍니다.  콘솔 추적 수신기는 <xref:System.Diagnostics.TraceSource> 또는 <xref:System.Diagnostics.Trace>를 호출하여 콘솔에 추적 정보를 씁니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## 참고 항목  
 <xref:System.Diagnostics.TraceListener>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)