---
title: '&lt;추가&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e27187c05b49b7f73ef19243a3286e8c1de71579
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;추가&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;
수신기를 추가 **수신기** 컬렉션입니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<추적 >  
\<수신기 >  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**type**|필수 특성입니다.<br /><br /> 수신기의 유형을 지정합니다. 에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|**initializeData**|선택적 특성입니다.<br /><br /> 지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.|  
|**name**|선택적 특성입니다.<br /><br /> 수신기의 이름을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|필터에 수신기를 추가 `Listeners` 추적에 대 한 컬렉션입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`listeners`|저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다. 수신기는 추적 출력을 적절 한 대상에 전달 합니다.|  
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
|`trace`|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 <xref:System.Diagnostics.Debug> 및 <xref:System.Diagnostics.Trace> 클래스 공유할지 **수신기** 컬렉션입니다. 이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가 하 고 다른 클래스 동일한 수신기를 사용 합니다. 수신기 클래스에서 파생 된 <xref:System.Diagnostics.TraceListener>합니다.  
  
 지정 하지 않는 경우는 `name` 추적 수신기의 특성의 <xref:System.Diagnostics.TraceListener.Name%2A> 의 추적 수신기 기본값을 빈 문자열 (""). 응용 프로그램에 수신기가 하나만 있는 경우에 이름을 지정 하지 않고 추가 하 고 이름에 대 한 빈 문자열을 지정 하 여 제거할 수 있습니다. 그러나 응용 프로그램에 수신기를 하나 이상 있으면 식별 하 고 내에서 개별 추적 수신기를 관리할 수 있는 각 추적 수신기에 대 한 고유한 이름을 지정 해야는 <xref:System.Diagnostics.Debug.Listeners%2A> 및 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션입니다.  
  
> [!NOTE]
>  해당 유형의 하나만 추적 수신기에서 결과 이름을 지정 하 고에 추가 되 고 이름을 동일한 같은 종류의 추적 수신기를 여러 개 추가 `Listeners` 컬렉션입니다. 그러나 여러 명의 동일한 수신기를 프로그래밍 방식으로 추가할 수는 `Listeners` 컬렉션입니다.  
  
 에 대 한 값은 **initializeData** 특성 만들 수신기의 형식에 따라 달라 집니다. 지정 하는 모든 추적 수신기 필요 **initializeData**합니다.  
  
> [!NOTE]
>  사용 하는 경우는 `initializeData` 특성을 "'initializeData' 특성이 선언 되지 않았습니다." 경고는 컴파일러 발생할 수 있습니다 구성 설정의 추상 기본 클래스에 대해 유효성을 검사 하기 때문에이 경고가 발생 <xref:System.Diagnostics.TraceListener>를 인식 하지 않으므로 `initializeData` 특성입니다. 일반적으로 매개 변수를 사용 하는 생성자가 있는 추적 수신기 구현에 대 한이 경고를 무시할 수 있습니다.  
  
 다음 표에서.NET Framework에 포함 된 추적 수신기가 표시 하 고 값을 설명 자신의 **initializeData** 특성입니다.  
  
|추적 수신기 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` 에 대 한 값은 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자입니다.  설정의 `initializeData` 특성을 "`true`" 쓸 추적 및 디버그 출력을 <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`"에 쓸 수 <xref:System.Console.Out%2A?displayProperty=nameWithType>합니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|파일의 이름에서 <xref:System.Diagnostics.DelimitedListTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 원본의 이름의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.EventSchemaTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.TextWriterTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.XmlWriterTraceListener> 를 씁니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다.  **\<추가 >** 요소를 추가 하는 수신기 `MyListener` 및 `MyEventListener` 에 **수신기** 컬렉션입니다. `MyListener` 라는 파일을 만들어 `MyListener.log` 출력 파일에 씁니다. `MyEventListener` 이벤트 로그에 항목을 만듭니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [추적 수신기](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
