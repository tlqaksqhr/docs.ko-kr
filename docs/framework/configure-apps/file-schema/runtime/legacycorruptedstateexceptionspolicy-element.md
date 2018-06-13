---
title: '&lt;legacyCorruptedStateExceptionsPolicy&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6228aaf4c7da70337d9d1a99adcb78f71a0039b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744618"
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a>&lt;legacyCorruptedStateExceptionsPolicy&gt; 요소
공용 언어 런타임에서 액세스 위반 및 기타 손상 된 상태 예외를 catch 하는 관리 되는 코드를 허용 하는지 여부를 지정 합니다.  
  
 \<configuration>  
\<runtime>  
\<legacyCorruptedStateExceptionsPolicy >  
  
## <a name="syntax"></a>구문  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 응용 프로그램은 catch 지정 액세스 위반과 같이 손상 된 상태 예외입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|응용 프로그램이 검색 되지 것입니다 액세스 위반과 같이 손상 된 상태 예외입니다. 이 값이 기본값입니다.|  
|`true`|응용 프로그램은 catch 액세스 위반과 같이 손상 된 상태 예외입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 3.5 및 이전 버전에서는 공용 언어 런타임 손상 된 프로세스 상태에 의해 발생 된 예외를 catch 하는 관리 되는 코드를 허용 합니다. 액세스 위반은 이러한 유형의 예외의 예시입니다.  
  
 부터는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 관리 되는 코드는 더 이상 이러한 유형의 예외를 catch `catch` 블록입니다. 그러나 이러한 변경 내용을 재정의 수 있고 두 가지 방법으로 손상 된 상태 예외 처리를 유지 관리 됩니다.  
  
-   설정의 `<legacyCorruptedStateExceptionsPolicy>` 요소의 `enabled` 특성을 `true`합니다. 이 구성 설정은 프로세스 전체에 적용된 되 고 모든 메서드에 영향을 줍니다.  
  
 -또는-  
  
-   적용 된 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> 특성을 제외 하 고 포함 된 메서드에 `catch` 블록입니다.  
  
 이 구성 요소는 에서만 사용할 수는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상.  
  
## <a name="example"></a>예제  
 다음 예제에서는 앞의 동작으로 응용 프로그램을 되돌려야 함을 지정 하는 방법을 보여 줍니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], 모든 손상 된 상태 예외 오류를 catch 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
