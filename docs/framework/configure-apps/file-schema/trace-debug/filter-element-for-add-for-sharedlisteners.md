---
title: "&lt;sharedListeners&gt;의 &lt;add&gt;에 대한 &lt;filter&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<sharedListeners>의 <add>에 대한 <filter> 요소"
  - "<sharedListeners>의 <add>에 대한 filter 요소"
  - "필터, 추적 수신기"
  - "initializeData 특성"
  - "추적 수신기, 필터"
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# &lt;sharedListeners&gt;의 &lt;add&gt;에 대한 &lt;filter&gt; 요소
`sharedListeners` 컬렉션의 수신기에 필터를 추가합니다.  
  
## 구문  
  
```  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**type**|필수 특성입니다.<br /><br /> 필터의 형식을 지정합니다.  <xref:System.Type.FullName%2A?displayProperty=fullName> 속성의 형식으로 된 형식의 전체 이름만 사용하거나 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName> 속성의 형식으로 된 어셈블리 정보가 포함된 정규화된 형식 이름을 사용할 수 있습니다.  정규화된 형식 이름을 만드는 데 대한 자세한 내용은 [정규화된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)을 참조하십시오.|  
|**initializeData**|선택적 특성입니다.<br /><br /> 지정한 클래스에 대해 생성자에 전달되는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
|`sharedListeners`|임의의 소스 또는 추적 요소가 참조할 수 있는 수신기의 컬렉션입니다.|  
|`add`|**sharedListeners** 컬렉션에 수신기를 추가합니다.|  
  
## 설명  
 `<sharedListeners>` 요소의 `<add>` 요소에서 수신기가 정의된 경우 해당 수신기의 필터는 `<add>` 요소의 자식인 `<filter>` 요소에서 정의되어야 합니다.  
  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `<filter>` 요소를 사용하여 `sharedListeners` 컬렉션의 추적 수신기 `console`에 필터를 추가하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.TraceFilter>   
 <xref:System.Diagnostics.TraceListener>   
 <xref:System.Diagnostics.TraceSource>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)