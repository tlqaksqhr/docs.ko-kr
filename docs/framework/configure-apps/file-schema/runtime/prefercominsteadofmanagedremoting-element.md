---
title: '&lt;PreferComInsteadOfManagedRemoting&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4cac4ebb46fabad49e2e4e6a7d566522ca027094
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745476"
---
# <a name="ltprefercominsteadofmanagedremotinggt-element"></a>&lt;PreferComInsteadOfManagedRemoting&gt; 요소
여부를 런타임에서 COM interop를 사용 원격 서비스 대신 모든 호출에 대 한 응용 프로그램 도메인 경계를 지정 합니다.  
  
 \<configuration>  
\<runtime>  
\<PreferComInsteadOfManagedRemoting >  
  
## <a name="syntax"></a>구문  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에 사용할지 여부를 COM interop 원격 서비스 대신 응용 프로그램 도메인 경계를 나타냅니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임에 응용 프로그램 도메인 경계를 넘어 remoting을 사용 합니다. 이 값이 기본값입니다.|  
|`true`|런타임에 응용 프로그램 도메인 경계를 넘어 COM interop를 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 설정 하는 경우는 `enabled` 특성을 `true`, 런타임에서 다음과 같이 동작 합니다.  
  
-   런타임에서 호출 하지 않습니다 [iunknown:: Queryinterface](http://go.microsoft.com/fwlink/?LinkID=144867) 에 대 한 프로그램 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스는 [IUnknown](http://go.microsoft.com/fwlink/?LinkId=148003) 인터페이스가 COM 인터페이스를 통해 도메인을 입력 합니다. 대신, 생성 한 [런타임 호출 가능 래퍼](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) 개체 주위 합니다.  
  
-   런타임에 받을 때 하면 e_nointerface가 반환는 `QueryInterface` 에 대 한 호출는 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) 인터페이스에 대 한 [COM 호출 가능 래퍼](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW)이이 도메인에서 만든 합니다.  
  
 이러한 두 가지 동작 응용 프로그램 도메인 경계 사용 COM에서 관리 되는 개체 및 원격 서비스 대신 COM interop 사이 COM에 대 한 모든 호출 인터페이스 있는지 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 격리 경계를 넘어 런타임에서 COM을 사용 하도록 지정 하는 방법을 interop 보여 줍니다.  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
