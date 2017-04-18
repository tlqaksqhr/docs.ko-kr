---
title: "&lt;supportedRuntime&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<supportedRuntime> 요소"
  - "supportedRuntime 요소"
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
caps.latest.revision: 33
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 28
---
# &lt;supportedRuntime&gt; 요소
응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다. 이 요소는 .NET Framework 1.1 이상 버전으로 작성된 모든 응용 프로그램에서 사용되어야 합니다.  
  
 [\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
  
 **\<supportedRuntime\>**  
  
## 구문  
  
```  
  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## 특성  
  
|특성|설명|  
|--------|--------|  
|**버전**|선택적 특성입니다.<br /><br /> 응용 프로그램이 지원하는 공용 언어 런타임\(CLR\) 버전을 지정하는 문자열 값입니다.`version` 특성의 유효한 값에 대해서는 ["런타임 버전" 값](#version) 섹션을 참조하세요. **Note:**  .NET Framework 3.5에서는 "*런타임 버전*" 값이 *major*.*minor*.*build* 형식을 취합니다.[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터는 주 및 부 버전 번호만 필요합니다\(즉, "v4.0.30319"가 아니라 "v4.0"만 필요\). 짧은 문자열이 권장됩니다.|  
|**sku**|선택적 특성입니다.<br /><br /> 이 응용 프로그램이 지원하는 .NET Framework 버전을 지정하는 SKU\(Stock Keeping Unit\)를 지정하는 문자열 값입니다.<br /><br /> .NET Framework 4.0을 시작할 때에는 `sku` 특성을 사용하는 것이 좋습니다.  존재한다면 앱이 대상으로 하는 .NET Framework의 버전을 나타냅니다.<br /><br /> SKU 특성의 유효한 값에 대해서는 ["sku id" 값](#sku) 섹션을 참조하세요.|  
  
## 설명  
 **\<supportedRuntime\>** 요소가 응용 프로그램 구성 파일에 없다면, 응용 프로그램 빌드에 사용된 런타임 버전이 사용됩니다.  
  
 **\<supportedRuntime\>** 요소는 런타임 버전 1.1 이상으로 작성된 모든 응용 프로그램에서 사용되어야 합니다. 런타임 버전 1.0만 지원하도록 작성된 응용 프로그램은 [\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) 요소를 사용해야 합니다.  
  
> [!NOTE]
>  [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 함수를 사용하여 구성 파일을 지정하는 경우 모든 버전의 런타임에 대해 `<requiredRuntime>` 요소를 사용해야 합니다.[CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)를 사용할 때 `<supportedRuntime>` 요소는 무시됩니다.  
  
 .NET Framework 1.1~3.5의 런타임 버전을 지원하는 앱의 경우 여러 버전의 런타임이 지원되면 첫 번째 요소는 우선 순위가 가장 높은 런타임 버전을 지정하고 마지막 요소는 우선 순위가 가장 낮은 버전을 지정해야 합니다. .NET Framework 4.0 이상 버전을 원하는 앱의 경우 `version` 특성은 .NET Framework 4 이상 버전에 공통적으로 적용되는 CLR 버전을 나타내며, `sku` 특성은 앱이 대상으로 하는 단일 .NET Framework 버전을 나타냅니다.  
  
> [!NOTE]
>  응용 프로그램이 [CorBindToRuntimeEx 함수](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)와 같은 레거시 활성화 경로를 사용하면서 해당 경로로 CLR 4 이후 버전을 활성화하려는 경우 또는 응용 프로그램이 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]\(으\)로 빌드되었지만 이전 버전의 .NET Framework로 빌드된 혼합 모드 어셈블리에 종속성이 있는 경우는 지원되는 런타임 목록에 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]을\(를\) 지정할 수 없습니다. 또한 구성 파일 안의 [\<startup\> 요소](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)에서 `useLegacyV2RuntimeActivationPolicy` 특성을 `true`로 설정해야 합니다. 그러나 이 특성을 `true`로 설정하면 .NET Framework의 이전 버전으로 빌드된 모든 구성 요소가 빌드 시 사용된 런타임 대신 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]을\(를\) 사용하여 실행됩니다.  
  
 실행할 수 있는 모든 .NET Framework 버전을 사용하여 응용 프로그램을 테스트하는 것이 좋습니다.  
  
<a name="version"></a>   
## "런타임 버전" 값  
 다음 표에 `version` 특성의 *런타임 버전* 값에 대한 유효한 값이 나와 있습니다.  
  
|.NET Framework 버전|`version` 특성|  
|-----------------------|------------------|  
|1.0|"v1.0.3705"|  
|1.1|"v1.1.4322"|  
|2.0|"v2.0.50727"|  
|3.0|"v2.0.50727"|  
|3.5|"v2.0.50727"|  
|4.0|"v4.0"|  
|4.5|"v4.0"|  
|4.5.1|"v4.0"|  
|4.5.2|"v4.0"|  
|4.6|"v4.0"|  
|4.6.1|"v4.0"|  
  
<a name="sku"></a>   
## "sku id" 값  
 다음 표에 `sku` 특성이 지원하는 .NET Framework 버전이 .NET Framework 4부터 나와 있습니다.  .NET Framework 4로 시작하는 `sku` 특성은 앱이 대상으로 하는 .NET Framework 버전을 나타냅니다.  
  
|.NET Framework 버전|`sku` 특성|  
|-----------------------|--------------|  
|4.0|".NETFramework,Version\=v4.0"|  
|4.0, Client Profile|".NETFramework,Version\=v4.0,Profile\=Client"|  
|4.0, 플랫폼 업데이트 1|.NETFramework,Version\=v4.0.1|  
|4.0, Client Profile, 업데이트 1|.NETFramework,Version\=v4.0.1,Profile\=Client|  
|4.0, 플랫폼 업데이트 2|.NETFramework,Version\=v4.0.2|  
|4.0, Client Profile, 업데이트 2|.NETFramework,Version\=v4.0.2,Profile\=Client|  
|4.0, 플랫폼 업데이트 3|.NETFramework,Version\=v4.0.3|  
|4.0, Client Profile, 업데이트 3|.NETFramework,Version\=v4.0.3,Profile\=Client|  
|4.5|".NETFramework,Version\=v4.5"|  
|4.5.1|".NETFramework,Version\=v4.5.1"|  
|4.5.2|".NETFramework,Version\=v4.5.2"|  
|4.6|".NETFramework,Version\=v4.6"|  
|4.6.1|".NETFramework,Version\=v4.6.1"|  
  
 다음 표는 `version` 특성이 v 4.0이고 `sku` 특성이 .NET Framework 4 또는 해당 PU\(플랫폼 업데이트\) 중 하나를 식별할 때, 서로 다른 `sku` 특성 값에 대해 설치된 .NET Framework 4 버전 중 어느 버전에서 응용 프로그램이 실행될 것인지를 보여줍니다.  
  
|`sku` 특성 값|4.0 Client|4.0 Full|4.0 Client \+ PU 1|4.0 Full \+ PU 1|4.0 Client \+ PU 2|4.0 Full \+ PU 2|4.0 Client \+ PU 3|4.0 Full \+ PU 3|4.5 이상|  
|----------------|----------------|--------------|------------------------|----------------------|------------------------|----------------------|------------------------|----------------------|------------|  
|.NETFramework,Version\=v4.0,Profile\=Client|예|예|예|예|예|예|예|예|예|  
|.NETFramework,Version\=v4.0||예||예||예||예|예|  
|.NETFramework,Version\=v4.0.1,Profile\=Client|||예|예|예|예|예|예|예|  
|.NETFramework,Version\=v4.0.1||||예||예||예|예|  
|.NETFramework,Version\=v4.0.2,Profile\=Client|||||예|예|예|예|예|  
|.NETFramework,Version\=v4.0.2||||||예||예|예|  
|.NETFramework,Version\=v4.0.3,Profile\=Client|||||||예|예|예|  
|.NETFramework,Version\=v4.0.3||||||||예|예|  
  
## 예제  
 다음 예제에서는 구성 파일에 지원되는 런타임 버전을 지정하는 방법을 보여줍니다. 이 구성 파일은 응용 프로그램이 .NET Framework 4.6을 대상으로 함을 나타냅니다.  
  
```xml  
  
<configuration> <startup> <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" /> </startup> </configuration>  
  
```  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일에 사용할 수 있습니다.  
  
## 참고 항목  
 [시작 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> 사용할 런타임 버전 지정](http://msdn.microsoft.com/ko-kr/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [In\-Process Side\-by\-Side 실행](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)