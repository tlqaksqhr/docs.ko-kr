---
title: "&lt;필터&gt; 요소에 대 한 &lt;추가&gt; 에 대 한 &lt;sharedListeners&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ce4134d9059d1f1d5bd2e435a3cc87d3fbccd422
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a>&lt;필터&gt; 요소에 대 한 &lt;추가&gt; 에 대 한 &lt;sharedListeners&gt;
`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<sharedListeners > 요소  
\<add>  
\<필터 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**type**|필수 특성입니다.<br /><br /> 필터의 유형을 지정합니다. 형식의 전체 이름을 사용할 수 있습니다 (의 형식에는 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 속성), 하거나 어셈블리 정보를 포함 하 여 정규화 된 형식 이름을 사용할 수 있습니다 (의 형식에는 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> 속성). 정규화 된 형식 이름을 만드는 방법에 대 한 정보를 참조 하십시오. [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|**initializeData**|선택적 특성입니다.<br /><br /> 지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sharedListeners`|모든 원본이 나 추적 요소를 참조할 수 있는 수신기의 컬렉션입니다.|  
|`add`|수신기를 추가 **sharedListeners** 컬렉션입니다.|  
  
## <a name="remarks"></a>설명  
 수신기에 정의 된 경우는 `<add>` 의 요소는 `<sharedListeners>` 요소를 해당 수신기에 대 한 필터에 정의 되어야 합니다는 `<filter>` 의 자식인 요소는 `<add>` 요소입니다.  
  
 이 요소는 응용 프로그램 구성 파일 및 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `<filter>` 추적 수신기에 필터를 추가 하는 요소 `console` 에 `sharedListeners` 컬렉션입니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.TraceFilter>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceSource>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
