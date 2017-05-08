---
title: "&lt;source&gt;의 &lt;listeners&gt;에 대한 &lt;remove&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<source>의 <listeners>에 대한 <remove> 요소"
  - "<source>의 <listeners>에 대한 remove 요소"
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;source&gt;의 &lt;listeners&gt;에 대한 &lt;remove&gt; 요소
추적 소스에 대한 `Listeners` 컬렉션에서 수신기를 제거합니다.  
  
## 구문  
  
```  
<remove name="listenerName" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 특성입니다.<br /><br /> `Listeners` 컬렉션에서 제거할 수신기 이름입니다.|  
  
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
 `<remove>` 요소는 추적 소스에 대한 `Listeners` 컬렉션에서 지정한 수신기를 제거합니다.  
  
 <xref:System.Diagnostics.TraceSource> 인스턴스의 <xref:System.Diagnostics.TraceSource.Listeners%2A> 속성에서 <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> 메서드를 호출하여 추적 소스에 대한 `Listeners` 컬렉션에서 요소를 프로그래밍 방식으로 제거할 수 있습니다.  
  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `<add>` 요소를 사용하기 전에 `<remove>` 요소를 사용하여 `console` 수신기를 추적 소스 `TraceSourceApp`에 대한 `Listeners` 컬렉션에 추가하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## 참고 항목  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>   
 <xref:System.Diagnostics.TraceSource>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)