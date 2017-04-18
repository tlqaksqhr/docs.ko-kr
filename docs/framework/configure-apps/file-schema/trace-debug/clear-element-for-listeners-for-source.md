---
title: "&lt;source&gt;의 &lt;listeners&gt;에 대한 &lt;clear&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<source>의 <listeners>에 대한 <clear> 요소"
  - "<source>의 <listeners>에 대한 clear 요소"
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;source&gt;의 &lt;listeners&gt;에 대한 &lt;clear&gt; 요소
추적 소스에 대한 `Listeners` 컬렉션을 지웁니다.  
  
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
|`sources`|추적 메시지를 발생시키는 추적 소스를 포함합니다.|  
|`source`|추적 메시지를 발생시키는 추적 소스를 지정합니다.|  
|`listeners`|메시지를 수집하여 저장하고 라우팅하는 수신기를 지정합니다.|  
  
## 설명  
 `<clear>` 요소는 추적 소스에 대한 `Listeners` 컬렉션에서 <xref:System.Diagnostics.DefaultTraceListener>를 포함하여 모든 수신기를 제거합니다.  `<add>` 요소를 사용하기 전에 `<clear>` 요소를 사용하여 컬렉션에 다른 활성 수신기가 없는지 확인할 수 있습니다.  
  
## 구성 파일  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `<add>` 요소를 사용하기 전에 `<clear>` 요소를 사용하여 `console` 및 `textListener` 수신기를 추적 소스 `TraceSourceApp`에 대한 `Listeners` 컬렉션에 추가하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## 참고 항목  
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.TraceListener>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)