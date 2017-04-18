---
title: "&lt;sharedListeners&gt;의 &lt;add&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<sharedListeners>의 <add> 요소"
  - "<sharedListeners>에 대한 add 요소"
  - "initializeData 특성"
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;sharedListeners&gt;의 &lt;add&gt; 요소
`sharedListeners` 컬렉션에 수신기를 추가합니다.  `sharedListeners`는 임의의 [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) 또는 [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)가 참조할 수 있는 수신기 컬렉션입니다.  기본적으로 `sharedListeners` 컬렉션의 수신기는 `Listeners` 컬렉션에 배치되지 않으며  [\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) 또는 [\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)에 이름별로 추가되어야 합니다.  런타임에 코드에서 `sharedListeners` 컬렉션의 수신기를 가져오는 것은 불가능합니다.  
  
## 구문  
  
```  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 특성입니다.<br /><br /> `Listeners` 컬렉션에 공유 수신기를 추가하는 데 사용되는 수신기의 이름을 지정합니다.|  
|`type`|필수 특성입니다.<br /><br /> 수신기 형식을 지정합니다.  [정규화된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정된 요구 사항을 충족하는 문자열을 사용해야 합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정한 클래스에 대해 생성자에 전달되는 문자열입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|`sharedListeners` 컬렉션의 수신기에 필터를 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하여 저장하고 라우트하는 추적 수신기와 추적 스위치를 설정할 수준을 지정합니다.|  
|`sharedListeners`|임의의 소스 또는 추적 요소가 참조할 수 있는 수신기의 컬렉션입니다.|  
  
## 설명  
 .NET Framework와 함께 제공되는 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생됩니다.  `name` 특성 값은 공유 수신기를 추적 또는 추적 소스에 대한 `Listeners` 컬렉션에 추가하는 데 사용됩니다.  `initializeData` 특성 값은 만들 수신기 형식에 따라 결정됩니다.  모든 추적 수신기에 `initializeData`를 지정할 필요는 없습니다.  
  
> [!NOTE]
>  `initializeData` 특성을 사용하는 경우 컴파일러 경고 메시지 "'initializeData' 특성이 선언되지 않았습니다."가 나타납니다. 이 경고는 `initializeData` 특성을 인식하지 않는 추상 기본 클래스 <xref:System.Diagnostics.TraceListener>에 의해 구성 설정의 유효성이 검사된 경우 발생합니다.  일반적으로 매개 변수를 사용하는 생성자가 있는 추적 수신기 구현의 경우에는 이 경고를 무시해도 됩니다.  
  
 다음 표에서는 .NET Framework와 함께 제공되는 추적 수신기를 보여 주고 해당 `initializeData` 특성 값에 대해 설명합니다.  
  
|추적 수신기 클래스|initializeData 특성 값|  
|----------------|-------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자에 대한 `useErrorStream` 값입니다.  추적 및 디버그 출력을 표준 오류 스트림에 쓰려면 `initializeData` 특성을 "`true`"로 설정하고 표준 출력 스트림에 쓰려면 "`false`"로 설정합니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|기존 이벤트 로그 소스의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|<xref:System.Diagnostics.EventSchemaTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|<xref:System.Diagnostics.TextWriterTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<xref:System.Diagnostics.XmlWriterTraceListener>가 쓸 파일 이름입니다.|  
  
## 구성 파일  
 이 요소는 컴퓨터 구성 파일\(Machine.config\) 및 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 예제  
 다음 예제는 `<add>` 요소를 사용하여 <xref:System.Diagnostics.TextWriterTraceListener> `textListener` 를  `sharedListeners` 컬렉션에 추가하는 방법을 보여줍니다. `textListener` 는 `Listeners` 컬렉션을 추적 원본 `TraceSourceApp` 에 이름이 추가되어 집니다.  `textListener` 수신기는 추적 출력을 myListener.log 파일에 씁니다.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
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