---
title: "&lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;add&gt;의 &lt;filter&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<trace>의 <listeners>에 대한 <add>의 <filter> 요소"
  - "<trace>의 <listeners>에 대한 <add>의 filter 요소"
  - "initializeData 특성"
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;add&gt;의 &lt;filter&gt; 요소
추적에 대한 `Listeners` 컬렉션의 수신기에 필터를 추가합니다.  
  
## 구문  
  
```  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`type`|필수 특성입니다.<br /><br /> <xref:System.Diagnostics.TraceFilter> 클래스에서 상속해야 하는 필터 형식을 지정합니다.  형식의 네임스페이스로 한정된 이름\(형식의  <xref:System.Type.FullName%2A> 속성에 해당\)을 사용하거나 어셈블리 정보를 포함하는 정규화된 형식 이름\(<xref:System.Type.AssemblyQualifiedName%2A> 속성에 해당\)을 사용할 수 있습니다.  정규화된 형식 이름에 대한 자세한 내용은 [정규화된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)을 참조하십시오.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정한 필터 클래스에 대해 생성자에 전달되는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
|`trace`|추적 메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.|  
|`listeners`|메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.  수신기는 추적 출력을 적절한 대상으로 안내합니다.|  
|`add`|`Listeners` 컬렉션에 수신기를 추가합니다.|  
  
## 설명  
 `<filter>` 요소는 [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)에 정의된 수신기의 이름뿐 아니라 수신기의 형식을 지정하는 추적 수신기의 `<add>` 요소에 포함되어야 합니다.  [\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)에 수신기가 정의되어 있으면 이 수신기의 필터가 해당 요소에 정의되어 있어야 합니다.  
  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 필터 이벤트 수준을 `Error`로 지정하여 `<filter>` 요소를 통해 추적에 대한 `Listeners` 컬렉션의 `console` 수신기에 필터를 추가하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.TraceFilter>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)