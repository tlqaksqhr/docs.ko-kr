---
title: '&lt;추가&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;소스&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ba8ff652003a9167ec370643797ac9300b83889a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745658"
---
# <a name="ltaddgt-element-for-ltlistenersgt-for-ltsourcegt"></a>&lt;추가&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;소스&gt;
추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<소스 >  
\<소스 >  
\<수신기 >  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`type`|필수 특성을 수신기에 참조 중인 하지 않는 경우는 `sharedListeners` 컬렉션에 있는 경우 이름으로 참조 하기만 (참조는 [예제](#example)).<br /><br /> 수신기의 유형을 지정합니다. 에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다. A <xref:System.Configuration.ConfigurationException> 클래스에는 문자열을 사용 하는 생성자가 없는 경우 throw 됩니다.|  
|`name`|선택적 특성입니다.<br /><br /> 수신기의 이름을 지정합니다.|  
|`traceOutputOptions`|선택적 특성입니다.<br /><br /> 지정 된 <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> 추적 수신기에 대 한 속성 값입니다.|  
|[사용자 지정 특성]|선택적 특성입니다.<br /><br /> 으로 식별 된 수신기 별 특성에 대 한 값을 지정 된 <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> 해당 수신기에 대 한 메서드. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> 추가 특성의 예에 고유한는 <xref:System.Diagnostics.DelimitedListTraceListener> 클래스입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
|`source`|추적 메시지를 시작하는 추적 소스를 지정합니다.|  
|`listeners`|수집, 저장 하 고 메시지를 라우팅하는 수신기를 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework와 함께 제공 되는 수신기 클래스에서 파생 되는 <xref:System.Diagnostics.TraceListener> 클래스입니다.  
  
 지정 하지 않는 경우는 `name` 추적 수신기의 특성은 <xref:System.Diagnostics.TraceListener.Name%2A> 추적 수신기의 속성의 기본값은 빈 문자열은 (""). 수신기를 하나만 응용 프로그램에 이름을 지정 하지 않고 추가할 수 있습니다 및 이름에 대 한 빈 문자열을 지정 하 여 제거할 수 있습니다. 그러나 응용 프로그램에 둘 이상의 수신기를 하는 경우 식별 하 고 개별 추적 수신기에 관리할 수 있는 각 추적 수신기에 대 한 고유한 이름을 지정 해야는 <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> 컬렉션입니다.  
  
> [!NOTE]
>  해당 유형의 하나만 추적 수신기에서 결과 이름을 지정 하 고에 추가 되 고 이름을 동일한 같은 종류의 추적 수신기를 여러 개 추가 `Listeners` 컬렉션입니다. 그러나 여러 명의 동일한 수신기를 프로그래밍 방식으로 추가할 수는 `Listeners` 컬렉션입니다.  
  
 에 대 한 값은 `initializeData` 특성 만들 수신기의 형식에 따라 달라 집니다. 지정 하는 모든 추적 수신기 필요 `initializeData`합니다.  
  
> [!NOTE]
>  사용 하는 경우는 `initializeData` 특성을 "'initializeData' 특성이 선언 되지 않았습니다." 경고는 컴파일러 발생할 수 있습니다 구성 설정의 추상 기본 클래스에 대해 유효성을 검사 하기 때문에이 경고가 발생 <xref:System.Diagnostics.TraceListener>를 인식 하지 않으므로 `initializeData` 특성입니다. 일반적으로 매개 변수를 사용 하는 생성자가 있는 추적 수신기 구현에 대 한이 경고를 무시할 수 있습니다.  
  
 다음 표에서.NET Framework에 포함 된 추적 수신기가 표시 하 고 값을 설명 자신의 `initializeData` 특성입니다.  
  
|추적 수신기 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|`useErrorStream` 에 대 한 값은 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자입니다.  설정의 `initializeData` 특성을 "`true`"쓰려는 추적 및 디버그 출력을 표준 오류 스트림에;로 설정"`false`" 표준 출력 스트림에 쓸 수 있습니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|파일의 이름에서 <xref:System.Diagnostics.DelimitedListTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 원본의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.EventSchemaTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.TextWriterTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.XmlWriterTraceListener> 를 씁니다.|  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다. `<add>` 요소를 추가 하는 수신기 `console` 및 `textListener` 에 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`합니다. `textListener` 수신기에 추적 출력 파일 myListener.log을 씁니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [추적 수신기](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
