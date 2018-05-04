---
title: '&lt;추가&gt; 요소에 대 한 &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 27d83ba706b4d93b4ac5426bf5bae59b4bfc0d9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-element-for-ltsharedlistenersgt"></a>&lt;추가&gt; 요소에 대 한 &lt;sharedListeners&gt;
`sharedListeners` 컬렉션에 수신기를 추가합니다. `sharedListeners` 모든 수신기의 컬렉션은 [ \<소스 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) 또는 [ \<추적 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) 참조할 수 있습니다.  기본적으로 수신기에는 `sharedListeners` 컬렉션에 배치 되지는 `Listeners` 컬렉션입니다. 이름으로 추가 해야 합니다는 [ \<소스 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) 또는 [ \<추적 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)합니다. 수신기 가져올 수 없으면는 `sharedListeners` 런타임에 코드에서 컬렉션입니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<sharedListeners > 요소  
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
|`name`|필수 특성입니다.<br /><br /> 공유 수신기를 추가 하는 데 사용 되는 수신기의 이름을 지정는 `Listeners` 컬렉션입니다.|  
|`type`|필수 특성입니다.<br /><br /> 수신기의 유형을 지정합니다. 에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sharedListeners`|모든 원본이 나 추적 요소를 참조할 수 있는 수신기의 컬렉션입니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework와 함께 제공 되는 수신기 클래스에서 파생 되는 <xref:System.Diagnostics.TraceListener> 클래스입니다. 에 대 한 값은 `name` 특성 공유 수신기를 추가 하는 데 사용 되는 `Listeners` 추적 또는 추적 소스에 대 한 컬렉션입니다. 에 대 한 값은 `initializeData` 특성 만들 수신기의 형식에 따라 달라 집니다. 지정 하는 모든 추적 수신기 필요 `initializeData`합니다.  
  
> [!NOTE]
>  사용 하는 경우는 `initializeData` 특성을 "'initializeData' 특성이 선언 되지 않았습니다." 경고는 컴파일러 발생할 수 있습니다 구성 설정의 추상 기본 클래스에 대해 유효성을 검사 하기 때문에이 경고가 발생 <xref:System.Diagnostics.TraceListener>를 인식 하지 않으므로 `initializeData` 특성입니다. 일반적으로 매개 변수를 사용 하는 생성자가 있는 추적 수신기 구현에 대 한이 경고를 무시할 수 있습니다.  
  
 다음 표에서.NET Framework에 포함 된 추적 수신기가 표시 하 고 값을 설명 자신의 `initializeData` 특성입니다.  
  
|추적 수신기 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|`useErrorStream` 에 대 한 값은 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자입니다.  설정의 `initializeData` 특성을 "`true`"쓰려는 추적 및 디버그 출력을 표준 오류 스트림에;로 설정"`false`" 표준 출력 스트림에 쓸 수 있습니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|파일의 이름에서 <xref:System.Diagnostics.DelimitedListTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 원본의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.EventSchemaTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|파일의 이름 하 여 <xref:System.Diagnostics.TextWriterTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|파일의 이름 하 여 <xref:System.Diagnostics.XmlWriterTraceListener> 를 씁니다.|  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다. `<add>` 요소를 추가 하는 <xref:System.Diagnostics.TextWriterTraceListener> `textListener` 에 `sharedListeners` 컬렉션입니다.   `textListener` 이름으로 추가 되 고 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`합니다. `textListener` 수신기에 추적 출력 파일 myListener.log을 씁니다.  
  
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
