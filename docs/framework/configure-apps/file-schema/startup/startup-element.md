---
title: "&lt;startup&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#startup"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<startup> 요소"
  - "컨테이너 태그, <startup> 요소"
  - "startup 요소"
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# &lt;startup&gt; 요소
공용 언어 런타임 시작 정보를 지정합니다.  
  
## 구문  
  
```  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`useLegacyV2RuntimeActivationPolicy`|선택적 특성입니다.<br /><br /> [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] 런타임 정품 인증 정책을 활성화할지 또는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 정품 인증 정책을 사용할지 여부를 지정합니다.|  
  
## useLegacyV2RuntimeActivationPolicy 특성  
  
|값|설명|  
|-------|--------|  
|`true`|레거시 런타임 활성화 기술\(예: [CorBindToRuntimeEx function](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)\)을 CLR 버전 2.0에 캐핑하는 대신 구성 파일에서 선택한 런타임에 바인딩하는 [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] 런타임 활성화 정책을 선택한 런타임에 사용하도록 설정합니다.  따라서 이전 버전의 .NET Framework를 사용하여 만든 혼합 모드 어셈블리인 구성 파일에서 CLR 버전 4 이상을 선택하는 경우 .NET Framework는 선택된 CLR 버전으로 로드됩니다.  이 값을 설정하면 CLR 버전 1.1 또는 CLR 버전 2.0이 같은 프로세스로 로드되지 않아 in\-process side\-by\-side 기능이 효과적으로 비활성화됩니다.|  
|`false`|[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]에 레거시 런타임 활성화 기술에서 CLR 버전 1.1 또는 2.0을 프로세스로 로드를 허용하는 기본 활성화 정책을 사용합니다.  이 값을 설정하면 복합 모드 어셈블리가 .NET Framework 4 이상으로 빌드되지 않은 이상 .NET Framework 4 이상으로 로드되지 않습니다.  이 값이 기본값입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|응용 프로그램이 공용 언어 런타임 버전 1.0만 지원하도록 지정합니다.  런타임 버전 1.1 이상으로 작성된 응용 프로그램은 **\<supportedRuntime\>** 요소를 사용해야 합니다.|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## 설명  
 **\<supportedRuntime\>** 요소는 런타임 버전 1.1 이상으로 작성된 모든 응용 프로그램에서 사용되어야 합니다.  런타임 버전 1.0만 지원하도록 작성된 응용 프로그램은 **\<requiredRuntime\>** 요소를 사용해야 합니다.  
  
 Microsoft Internet Explorer에 호스팅되는 응용 프로그램의 시작 코드는 **\<startup\>** 요소 및 그 자식 요소를 무시합니다.  
  
## useLegacyV2RuntimeActivationPolicy 특성  
 이 속성은 응용 프로그램이 [CorBindToRuntimeEx 함수](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)와 같은 레거시 활성화 경로를 사용하면서 해당 경로로 CLR 4 이후 버전을 활성화하려는 경우 또는 응용 프로그램이 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]로 빌드되었지만 이전 버전의 .NET Framework로 빌드된 혼합 모드 어셈블리에 종속성이 있는 경우에 유용합니다.  그러한 시나리오에서는 속성을 `true`로 설정합니다.  
  
> [!NOTE]
>  특성을 `true`로 설정하면 CLR 버전 1.1 또는 CLR 버전 2.0이 같은 프로세스로 로드되지 않아 in\-process side\-by\-side 기능이 효과적으로 비활성화됩니다\([Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/ko-kr/4302318c-3586-49bf-8620-b9a39cdf4a32) 참조\).  
  
## 예제  
 다음 예제에서는 구성 파일에 런타임 버전을 지정하는 방법을 보여 줍니다.  
  
```  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## 참고 항목  
 [시작 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/ko-kr/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/ko-kr/4302318c-3586-49bf-8620-b9a39cdf4a32)   
 [In\-Process Side\-by\-Side 실행](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)