---
title: '&lt;assert&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ab1644d23e4d6d78b62e701902e5ec39e134b38b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745122"
---
# <a name="ltassertgt-element"></a>&lt;assert&gt; 요소
<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<assert >  
  
## <a name="syntax"></a>구문  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`assertuienabled`|선택적 특성입니다.<br /><br /> 지정 여부를 표시 하는 메시지 상자는 **Debug.Assert** 메서드를 평가 **false**합니다.|  
|`logfilename`|선택적 특성입니다.<br /><br /> 경우에는 메시지를 기록할 파일의 이름을 지정 **Debug.Assert** 계산 **false**합니다.|  
  
## <a name="assertuienabled-attribute"></a>assertuienabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`true`|메시지 상자를 표시합니다. 이 값이 기본값입니다.|  
|`false`|메시지 상자를 표시 하지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 두 특성 모두에  **\<assert >** 요소는 선택 사항입니다. 메시지를 쓸 파일을 지정 하지 않고 메시지 상자를 해제할 수 있습니다 또는 메시지 상자가 활성화 된 상태에서 메시지를 쓸 파일을 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 호출 하는 경우 메시지 상자 표시를 해제 하는 방법을 보여 줍니다 **Debug.Assert** 에 메시지 쓰기 및 `c:\log.txt`합니다.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Debug>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
