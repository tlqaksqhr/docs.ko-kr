---
title: "&lt;소스&gt; 요소"
ms.date: 09/29/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d6c5c65be8a540fdbba64d5a604c0963f9797e0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsourcegt-element"></a>&lt;소스&gt; 요소
추적 메시지를 시작하는 추적 소스를 지정합니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<소스 >  
\<소스 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|선택적 특성입니다.<br /><br /> 추적 소스 이름을 지정합니다.|  
|`switchName`|선택적 특성입니다.<br /><br /> 응용 프로그램에서 추적 스위치 인스턴스 이름을 지정합니다. 스위치에서 식별 되지 않는 경우는 `<switches>` 요소 값에 스위치에 대 한 수준을 지정 합니다.|  
|`switchType`|선택적 특성입니다.<br /><br /> 추적 스위치의 유형을 지정합니다. 있는 경우 유효한 클래스 이름 이어야 합니다 형식과 빈 문자열일 수 없습니다.|  
|`extraAttribute`|선택적 특성입니다.<br /><br /> 로 식별 되는 추적 소스 관련 특성에 대 한 값을 지정 된 <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> 해당 추적 소스에 대 한 메서드.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 사용 하는 방법을 보여 주는 다음 예제는 `<source>` 추적 소스를 추가할 요소의 `mySource` 명명 된 소스 스위치에 대 한 수준을 설정 하 고 `sourceSwitch`합니다. 콘솔 추적 수신기는 추적 정보를 콘솔에 작성 하는 추가 됩니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [추적 스위치](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
