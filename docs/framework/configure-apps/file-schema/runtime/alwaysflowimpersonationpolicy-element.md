---
title: "&lt;alwaysFlowImpersonationPolicy&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be1df955f7586848968cb32cd66a4c6889cfffa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a>&lt;alwaysFlowImpersonationPolicy&gt; 요소
가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.  
  
 \<configuration>  
\<런타임 >  
\<alwaysFlowImpersonationPolicy >  
  
## <a name="syntax"></a>구문  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 비동기 지점에 걸쳐 Windows id가 전달 하는지 여부를 나타냅니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|통해 가장이 수행 하지 않으면 identity 비동기 지점 간에 이동 하지 않는 Windows 관리 되는 메서드 같은 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>합니다. 이 값이 기본값입니다.|  
|`true`|Windows id는 항상 가장이 수행 하는 방법에 관계 없이 비동기 요소 간에 전달 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 1.0 및 1.1에서는 Windows id 비동기 지점 간에 전달 되지 않습니다. .NET Framework 버전 2.0에는 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대 한 정보가 포함 된 응용 프로그램 도메인 내에서 비동기 지점 간에 전달 합니다. <xref:System.Security.Principal.WindowsIdentity> 또한를 사용 하 여 가장이 수행 하는 경우 비동기 지점에서 전송 되는 정보의 일부로 흐름 관리 되는 메서드 같은 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> 플랫폼 등의 다른 방법을 통해서가 아니라 네이티브 메서드를 호출 합니다. 이 요소는 Windows id가 가장이 수행 하는 방법에 관계 없이 비동기 요소 간에 전달 지정에 사용 됩니다.  
  
 다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.  
  
1.  스레드 단위 별로 관리 되는 코드입니다.  
  
     수정 하 여 스레드 단위 별로 흐름을 표시 하지 않을 수 있습니다는 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 사용 하 여는 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드.  
  
2.  공용 언어 런타임 (CLR)를 로드 하는 관리 되지 않는 호스팅 인터페이스 호출에입니다.  
  
     CLR을 로드 하는 관리 되지 않는 호스팅 인터페이스 (간단한 관리 되는 실행 파일) 대신 사용 하는 경우에 대 한 호출에서 특수 플래그를 지정할 수 있습니다는 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수입니다. 전체 프로세스에 대 한 호환성 모드를 사용 하도록 설정 된 `flags` 에 대 한 매개 변수 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 를 `STARTUP_ALWAYSFLOW_IMPERSONATION`합니다.  
  
## <a name="configuration-file"></a>구성 파일  
 .NET Framework 응용 프로그램에서는이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
 ASP.NET 응용 프로그램에 대 한 가장 흐름에서에서 구성할 수 있습니다 aspnet.config 파일에서 찾을 수는 \<Windows 폴더 > \Microsoft.NET\Framework\vx.x.xxxx 디렉터리입니다.  
  
 기본적으로 ASP.NET 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 비활성화 합니다.  
  
```  
configuration>  
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
  
## <a name="example"></a>예  
 다음 예제에서는 관리 되는 메서드 이외의 방법을 통해 가장이 수행 하는 경우에 비동기 지점에 걸쳐 Windows id가 전달 되도록 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<legacyImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
