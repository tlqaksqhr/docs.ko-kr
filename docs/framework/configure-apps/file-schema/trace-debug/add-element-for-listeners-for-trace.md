---
title: "&lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;add&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<listeners>의 <add> 요소"
  - "<listeners>의 add 요소"
  - "initializeData 특성"
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
caps.latest.revision: 24
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# &lt;trace&gt;의 &lt;listeners&gt;에 대한 &lt;add&gt; 요소
**Listeners** 컬렉션에 수신기를 추가합니다.  
  
## 구문  
  
```  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**type**|필수 특성입니다.<br /><br /> 수신기 형식을 지정합니다.  [정규화된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정된 조건에 맞는 문자열을 사용해야 합니다.|  
|**initializeData**|선택적 특성입니다.<br /><br /> 지정한 클래스에 대해 생성자에 전달되는 문자열입니다.|  
|**name**|선택적 특성입니다.<br /><br /> 수신기 이름을 지정합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|추적에 대한 `Listeners` 컬렉션의 수신기에 필터를 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`listeners`|메시지를 수집하여 저장하고 라우트하는 수신기를 지정합니다.  수신기는 추적 출력을 적절한 대상으로 안내합니다.|  
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
|`trace`|추적 메시지를 수집하여 저장하고 라우팅하는 수신기를 포함합니다.|  
  
## 설명  
 <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace> 클래스는 같은 **Listeners** 컬렉션을 공유하므로  둘 중 하나의 클래스에 있는 컬렉션에 수신기 개체를 추가하면 나머지 클래스도 같은 수신기를 사용하게 됩니다.  수신기 클래스는 [TraceListener 클래스](frlrfSystemDiagnosticsTraceListenerClassTopic)에서 파생됩니다.  
  
 추적 수신기의 `nam`e 특성을 지정하지 않으면 추적 수신기의 <xref:System.Diagnostics.TraceListener.Name%2A>은 기본적으로 빈 문자열\(""\)을 사용합니다.  응용 프로그램에 수신기가 하나만 있는 경우에는 이름을 지정하지 않고 추가할 수 있으며 빈 문자열을 이름으로 지정하여 제거할 수 있습니다.  하지만 응용 프로그램에 둘 이상의 수신기가 있으면 각 추적 수신기에 고유한 이름을 지정해야 합니다. 이렇게 하면 <xref:System.Diagnostics.Debug.Listeners%2A> 및 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션 내에서 각 추적 수신기를 식별하여 관리할 수 있습니다.  
  
> [!NOTE]
>  동일한 이름을 가진 동일한 형식의 추적 수신기를 둘 이상 추가하면 해당 형식과 이름의 추적 수신기가 하나만 `Listeners` 컬렉션에 추가됩니다.  그러나 여러 개의 동일한 수신기를 `Listeners` 컬렉션에 프로그래밍 방식으로 추가할 수 있습니다.  
  
 **initializeData** 특성 값은 만들 수신기 형식에 따라 결정됩니다.  모든 추적 수신기에 **initializeData**를 지정할 필요는 없습니다.  
  
> [!NOTE]
>  `initializeData` 특성을 사용하는 경우 컴파일러 경고 메시지 "'initializeData' 특성이 선언되지 않았습니다."가 나타납니다. 이 경고는 `initializeData` 특성을 인식하지 않는 추상 기본 클래스 <xref:System.Diagnostics.TraceListener>에 의해 구성 설정의 유효성이 검사된 경우 발생합니다.  일반적으로 매개 변수를 사용하는 생성자가 있는 추적 수신기 구현의 경우에는 이 경고를 무시해도 됩니다.  
  
 다음 표에서는 .NET Framework와 함께 제공되는 추적 수신기를 보여 주고 해당 **initializeData** 특성 값에 대해 설명합니다.  
  
|추적 수신기 클래스|initializeData 특성 값|  
|----------------|-------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName>|<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자에 대한 `useErrorStream` 값입니다.  추적 및 디버그 출력을 <xref:System.Console.Error%2A?displayProperty=fullName>에 기록하려면 `initializeData` 특성을 "`true`"로 설정하고 <xref:System.Console.Out%2A?displayProperty=fullName>에 기록하려면 "`false`"로 설정합니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName>|기존 이벤트 로그 소스의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=fullName>|<xref:System.Diagnostics.EventSchemaTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=fullName>|<xref:System.Diagnostics.TextWriterTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName>|<xref:System.Diagnostics.XmlWriterTraceListener>가 쓸 파일 이름입니다.|  
  
## 예제  
 다음 예제에서는 **\<add\>** 요소를 사용하여 수신기 `MyListener` 및 `MyEventListener` 를 **Listeners** 컬렉션에 추가하는 방법을 보여 줍니다.  `MyListener`는 `MyListener.log`라는 파일을 만들어 해당 파일에 출력을 씁니다.  `MyEventListener`는 이벤트 로그에 항목을 만듭니다.  
  
```  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.Debug>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics.TextWriterTraceListener>   
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Listeners](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)