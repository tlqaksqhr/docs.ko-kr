---
title: "&lt;alwaysFlowImpersonationPolicy&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<alwaysFlowImpersonationPolicy> 요소"
  - "alwaysFlowImpersonationPolicy 요소"
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;alwaysFlowImpersonationPolicy&gt; 요소
가장이 수행된 방법에 관계없이 Windows ID가 항상 비동기 지점 간에 전달되도록 지정합니다.  
  
## 구문  
  
```  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> Windows ID가 비동기 지점 간에 전달되는지 여부를 나타냅니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> 등의 관리되는 메서드를 통해 가장이 수행되는 경우에만 Windows ID가 비동기 지점 간에 전달됩니다.  이 값이 기본값입니다.|  
|`true`|가장이 수행된 방법에 관계없이 Windows ID가 항상 비동기 지점 간에 전달됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
  
## 설명  
 .NET Framework 버전 1.0 및 1.1에서는 Windows ID는 비동기 지점 간에 전달되지 않습니다.  .NET Framework 버전 2.0에는 현재 실행 중인 스레드에 대한 정보를 포함하고 응용 프로그램 도메인 내의 비동기 지점 간에 이러한 정보를 전달하는 <xref:System.Threading.ExecutionContext> 개체가 있습니다.  네이티브 메서드에 대한 플랫폼 호출과 같은 방법이 아니라 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>와 같은 관리되는 메서드를 사용하여 가장이 수행된 경우에는 <xref:System.Security.Principal.WindowsIdentity>가 비동기 지점 간에 전달되는 정보의 일부로 전달될 수도 있습니다.  이 요소는 가장이 수행된 방법에 관계없이 Windows ID가 비동기 지점 간에 전달되도록 지정하는 데 사용됩니다.  
  
 이 기본 동작은 다음의 두 가지 방법으로 변경할 수 있습니다.  
  
1.  스레드별로 관리 코드를 사용합니다.  
  
     <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=fullName>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=fullName> 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=fullName> 메서드를 사용하여 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 수정하면 스레드별로 흐름을 억제할 수 있습니다.  
  
2.  관리되지 않는 호스팅 인터페이스에 대한 호출에서 CLR\(공용 언어 런타임\)를 로드합니다.  
  
     간단한 관리되는 실행 파일 대신 관리되지 않는 호스팅 인터페이스를 사용하여 CLR을 로드하는 경우에는 [CorBindToRuntimeEx 함수](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수에 대한 호출에서 특수 플래그를 지정할 수 있습니다.  전체 프로세스에 대해 호환성 모드를 사용할 수 있게 하려면 [CorBindToRuntimeEx 함수](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)의 `flags` 매개 변수를 STARTUP\_ALWAYSFLOW\_IMPERSONATION으로 설정합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 관리되는 메서드 이외의 방법을 통해 가장이 수행되는 경우에도 Windows ID가 비동기 지점 간에 전달되도록 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<legacyImpersonationPolicy\> 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)