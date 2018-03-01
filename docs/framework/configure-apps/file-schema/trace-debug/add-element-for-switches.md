---
title: "&lt;추가&gt; 요소에 대 한 &lt;스위치&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 4406caa4da1375bea9809843ca96774e24421d5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-ltswitchesgt"></a>&lt;추가&gt; 요소에 대 한 &lt;스위치&gt;
추적 스위치를 설정하는 수준을 지정합니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<스위치 >  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**name**|필수 특성입니다.<br /><br /> 스위치의 이름을 지정합니다. 이 특성의 값에 해당 하는 *displayName* 전환 생성자에 전달 되는 매개 변수입니다.|  
|**value**|필수 특성입니다.<br /><br /> 스위치의 수준을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`switches`|추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 구성 파일에 배치 하 여 추적 스위치의 수준을 변경할 수 있습니다. 스위치가 경우는 <xref:System.Diagnostics.BooleanSwitch>를 켜거나 끌 수 있습니다. 스위치가 경우는 <xref:System.Diagnostics.TraceSwitch>, 서로 다른 수준 추적의 유형을 지정할 항목을 할당할 수 있습니다 또는 응용 프로그램 출력 하는 디버그 메시지입니다.  
  
## <a name="example"></a>예  
 사용 하는 방법을 보여 주는 다음 예제는  **\<추가 >** 설정 하는 요소는 `General` 추적 스위치를는 <xref:System.Diagnostics.TraceLevel> 선택 하며, 사용 하도록 설정는 `Data` Boolean 추적 스위치입니다.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
