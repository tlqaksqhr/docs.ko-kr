---
title: '&lt;필터&gt; 요소에 대 한 &lt;추가&gt; 에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 095212f73adb906d9d80db747c331c436c1cf846
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745788"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a>&lt;필터&gt; 요소에 대 한 &lt;추가&gt; 에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;
필터에 수신기를 추가 `Listeners` 추적에 대 한 컬렉션입니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<추적 >  
\<수신기 >  
\<add>  
\<필터 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`type`|필수 특성입니다.<br /><br /> 상속 해야 하는 필터의 형식을 지정 된 <xref:System.Diagnostics.TraceFilter> 클래스입니다. 형식에 해당 하는 형식의 정규화 된 네임 스페이스 이름을 사용할 수 있습니다 <xref:System.Type.FullName%2A> 속성 또는 있습니다에 해당 하는 어셈블리 정보를 포함 한 정규화 된 형식 이름을 사용할 수는 <xref:System.Type.AssemblyQualifiedName%2A> 속성입니다. 정규화 된 형식 이름에 대 한 정보를 참조 하십시오. [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정 된 필터 클래스에 대 한 생성자에 전달 된 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`trace`|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
|`listeners`|수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다. 수신기는 추적 출력을 적절 한 대상에 전달 합니다.|  
|`add`|`Listeners` 컬렉션에 수신기를 추가합니다.|  
  
## <a name="remarks"></a>설명  
 `<filter>` 요소에 포함 되어야 합니다는 `<add>` 수신기의 유형을 지정 하는 추적 수신기에 대 한 요소에 정의 된 수신기의 이름 뿐 아니라는 [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)합니다. 수신기에 정의 된 경우는 [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), 해당 요소에 해당 수신기에 대 한 필터를 정의 해야 합니다.  
  
 이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `<filter>` 수신기에 필터를 추가 하는 요소 `console` 에 `Listeners` 으로 이벤트 수준 필터를 지정 하는 추적에 대 한 컬렉션 `Error`합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.TraceFilter>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
