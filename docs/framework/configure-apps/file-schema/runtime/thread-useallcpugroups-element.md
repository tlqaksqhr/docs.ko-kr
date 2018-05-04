---
title: '&lt;Thread_UseAllCpuGroups&gt; 요소'
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47d8bcdb9bbb7ec6f5a5386a5ac5951ad8891c28
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltthreaduseallcpugroupsgt-element"></a>&lt;Thread_UseAllCpuGroups&gt; 요소
런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.  
  
 \<configuration>  
\<runtime>  
< Thread_UseAllCpuGroups >  
  
## <a name="syntax"></a>구문  
  
```xml
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임에에서는 여러 CPU 그룹에 걸쳐 관리 되는 스레드를 배포 하지 않습니다. 이 값이 기본값입니다.|  
|`true`|런타임 컴퓨터에 있는 경우 여러 CPU 그룹 여러 CPU 그룹에 걸쳐 관리 되는 스레드를 배포 및 [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 요소를 사용할 수 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 컴퓨터에 여러 CPU 그룹을이 요소를 사용 하도록 설정 하면 모든 CPU 그룹에서 관리 되는 스레드를 배포할 runtime 합니다. 이 기능을 사용 하려면도 설정 해야는 [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 모든 CPU 그룹에 가비지 컬렉션을 확장 하 고 모든 코어는 만들고 힙을 분산 때 고려 하는 요소입니다. 사용 하도록 설정 된 [ \<GCCpuGroup >](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) 요소 사용 하도록 설정 해야는 [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) 요소입니다. 이러한 요소가 활성화 되지 않은 경우 사용 하도록 설정 된 `<Thread_UseAllCpuGroups>` 요소에 영향을 주지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 CPU 그룹에 대 한 지원을 사용 하도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<GCCpuGroup > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)
