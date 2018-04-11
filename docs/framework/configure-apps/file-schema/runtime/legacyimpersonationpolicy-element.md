---
title: '&lt;legacyImpersonationPolicy&gt; Element'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9a50ad06026b6ef2f819abefc22016aee29f8ab5
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="ltlegacyimpersonationpolicygt-element"></a>&lt;legacyImpersonationPolicy&gt; Element
현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.  
  
 \<configuration>  
\<runtime>  
\<legacyImpersonationPolicy>  
  
## <a name="syntax"></a>구문  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 지정 하는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 관계 없이 전달 되지 않습니다는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity> 흐름에 따라 비동기 지점 간에 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다. 이 값이 기본값입니다.|  
|`true`|<xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 관계 없이 전달 되지 않습니다는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 1.0 및 1.1에서는 <xref:System.Security.Principal.WindowsIdentity> 어떠한 사용자 지정 비동기 요소 간에 전달 되지 않습니다. .NET Framework 버전 2.0 부터는 <xref:System.Threading.ExecutionContext> 응용 프로그램 도메인 내에서 비동기 지점 간에 전달 하며 현재 실행 중인 스레드에 대 한 정보를 포함 하는 개체입니다. <xref:System.Security.Principal.WindowsIdentity> 이 실행 컨텍스트에 포함 되 고 따라서 흐르는 비동기 지점 간에 가장 컨텍스트의 있으면 것 흐릅니다도 의미 합니다.  
  
 .NET Framework 2.0 이상에서는 사용할 수 있습니다는 `<legacyImpersonationPolicy>` 를 지정 하는 요소 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 전달 되지 않습니다.  
  
> [!NOTE]
>  공용 언어 런타임 (CLR)은 비관리 코드에 또는 Win32 함수를 직접 호출을 통해 관리 코드만와 같은 플랫폼을 통해 관리 되는 코드 외부에서 수행 된 가장의를 사용 하 여 수행 되는 작업을 호출 하는 가장 인식 합니다. 관리 되는 <xref:System.Security.Principal.WindowsIdentity> 경우가 아니면 개체 비동기 지점 간에 전달 될 수 있습니다는 `alwaysFlowImpersonationPolicy` 요소가 설정에 true로 (`<alwaysFlowImpersonationPolicy enabled="true"/>`). 설정의 `alwaysFlowImpersonationPolicy` 요소를 true로 Windows id 항상 가장이 수행 하는 방법에 관계 없이 비동기 요소 간에 전달 되도록 지정 합니다. 자세한 내용을 비동기 지점 간에 관리 되지 않는 가장 흐르는 대 한 정보를 참조 하십시오. [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.  
  
 다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.  
  
1.  스레드 단위 별로 관리 되는 코드입니다.  
  
     수정 하 여 스레드 단위 별로 흐름을 표시 하지 않을 수 있습니다는 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 사용 하 여는 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드.  
  
2.  공용 언어 런타임 (CLR)를 로드 하는 관리 되지 않는 호스팅 인터페이스 호출에입니다.  
  
     CLR을 로드 하는 관리 되지 않는 호스팅 인터페이스 (간단한 관리 되는 실행 파일) 대신 사용 하는 경우에 대 한 호출에서 특수 플래그를 지정할 수 있습니다는 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수입니다. 전체 프로세스에 대 한 호환성 모드를 사용 하도록 설정 된 `flags` 에 대 한 매개 변수 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) STARTUP_LEGACY_IMPERSONATION를 합니다.  
  
 자세한 내용은 참조는 [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.  
  
## <a name="configuration-file"></a>구성 파일  
 .NET Framework 응용 프로그램에서는이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
 ASP.NET 응용 프로그램에 대 한 가장 흐름에서에서 구성할 수 있습니다 aspnet.config 파일에서 찾을 수는 \<Windows 폴더 > \Microsoft.NET\Framework\vx.x.xxxx 디렉터리입니다.  
  
 기본적으로 ASP.NET 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 비활성화 합니다.  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 Asp.net에서는 대신, 가장의 흐름을 허용 하려면 다음 구성 설정을 사용 해야 합니다 명시적으로.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 비동기 지점에 걸쳐 Windows id를 전달 하지 않는 레거시 동작을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
