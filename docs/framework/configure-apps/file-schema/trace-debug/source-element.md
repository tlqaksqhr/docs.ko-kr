---
title: "&lt;source&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#source"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<source> 요소"
  - "source 요소"
ms.assetid: ecf86505-735d-4844-aaba-266fdd134218
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;source&gt; 요소
추적 메시지를 발생시키는 추적 소스를 지정합니다.  
  
## 구문  
  
```  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`name`|선택적 특성입니다.<br /><br /> 추적 소스의 이름을 지정합니다.|  
|`switchName`|선택적 특성입니다.<br /><br /> 응용 프로그램에서 추적 스위치 인스턴스의 이름을 지정합니다.  `<switches>` 요소에서 스위치가 식별되지 않으면 이 값에 의해 스위치의 수준이 지정됩니다.|  
|`switchType`|선택적 특성입니다.<br /><br /> 추적 스위치 형식을 지정합니다.  형식이 있는 경우 해당 형식은 유효한 클래스 이름이어야 하고 빈 문자열일 수 없습니다.|  
|`extraAttribute`|선택적 특성입니다.<br /><br /> 해당 추적 소스에 대한 <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> 메서드가 식별하는 추적 소스 고유의 특성 값을 지정합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
|`sources`|추적 메시지를 발생시키는 추적 소스를 포함합니다.|  
  
## 설명  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `<source>`  요소를 사용하여 추적 소스 `mySource`를 추가하고 소스 스위치 `sourceSwitch`의 수준을 설정하는 방법을 보여 줍니다.  콘솔에 추적 정보를 쓰는 콘솔 추적 수신기가 추가됩니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## 참고 항목  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Switches](../../../../../docs/framework/debug-trace-profile/trace-switches.md)