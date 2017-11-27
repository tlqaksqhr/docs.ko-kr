---
title: "&lt;추적&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 157adb6c7317aa047976cdb9e30711d20c9e543b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttracegt-element"></a>&lt;추적&gt; 요소
추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<추적 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`autoflush`|선택적 특성입니다.<br /><br /> 추적 수신기 모든 쓰기 작업 후 출력 버퍼를 자동으로 플러시 있는지 여부를 지정 합니다.|  
|`indentsize`|선택적 특성입니다.<br /><br /> 들여쓰기를 공백 수를 지정 합니다.|  
|`useGlobalLock`|선택적 특성입니다.<br /><br /> 전역 잠금을 사용 해야 하는지 여부를 나타냅니다.|  
  
## <a name="autoflush-attribute"></a>autoflush 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|출력 버퍼를 자동으로 플러시하지 않습니다. 이 값이 기본값입니다.|  
|`true`|자동으로 출력 버퍼를 플러시합니다.|  
  
## <a name="usegloballock-attribute"></a>useGlobalLock 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|수신기가 스레드로부터 안전; 전역 잠금을 사용 하지 않습니다. 그렇지 않으면 전역 잠금을 사용합니다.|  
|`true`|수신기가 스레드로부터 안전 하 게 보호 하는 여부에 관계 없이 전역 잠금을 사용 합니다. 이 값이 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `<trace>` 수신기에 추가할 요소의 `MyListener` 에 `Listeners` 컬렉션입니다. `MyListener`명명 된 파일을 만듭니다. `MyListener.log` 출력 파일에 씁니다. `useGlobalLock` 특성이로 설정 된 `false`, 추적 수신기가 스레드로부터 안전 하 게 보호 하는 경우 사용할 필요가 없는 전역 잠금에 이르게 됩니다. `autoflush` 특성이로 설정 된 `true`, 여부에 관계 없이 파일에 쓸 추적 수신기에 이르게는 <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> 메서드를 호출 합니다. `indentsize` 특성이 하면 들여쓰기 0 공간 수신기 0 (영)으로 설정 된 경우는 <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> 메서드를 호출 합니다.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
