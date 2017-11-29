---
title: "&lt;GCCpuGroup&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: abcb6d1b5f9dbb7a866b55628aabfe996a0a747c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltgccpugroupgt-element"></a>&lt;GCCpuGroup&gt; 요소
가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.  
  
 \<configuration>  
\<런타임 >  
\<GCCpuGroup >  
  
## <a name="syntax"></a>구문  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|가비지 수집 여러 CPU 그룹을 지원 하지 않습니다. 이 값이 기본값입니다.|  
|`true`|가비지 수집이 서버 가비지 수집이 사용 되는 경우 여러 CPU 그룹을 지원 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 때 컴퓨터에 여러 CPU 그룹 및 서버 가비지 수집이 설정 되었는지 (참조는 [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) 요소),이 요소를 사용 하도록 설정을 모든 CPU 그룹에서 가비지 수집을 확장 하 고 모든 코어를 사용 합니다. 힙을 분산와 만들 때 계정입니다.  
  
> [!NOTE]
>  이 요소는 가비지 수집 스레드만 적용 됩니다. 런타임에서 모든 CPU 그룹 사용자 스레드를 분산 시킬 수 있도록,도 설정 해야는 [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 요소입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 CPU 그룹에 대 한 가비지 컬렉션을 사용 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [방법: 동시 가비지 수집을 사용 하지 않도록 설정](http://msdn.microsoft.com/en-us/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [워크스테이션 및 서버 가비지 수집](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
