---
title: "&lt;NetFx40_LegacySecurityPolicy&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<NetFx40_LegacySecurityPolicy> 요소"
  - "NetFx40_LegacySecurityPolicy 요소"
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;NetFx40_LegacySecurityPolicy&gt; 요소
런타임에서 레거시 CAS\(코드 액세스 보안\) 정책을 사용하는지 여부를 지정합니다.  
  
## 구문  
  
```  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에서 레거시 CAS 정책을 사용하는지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|`false`|런타임에서 레거시 CAS 정책을 사용하지 않습니다.  이 값이 기본값입니다.|  
|`true`|런타임에서 레거시 CAS 정책을 사용합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## 설명  
 .NET Framework 버전 3.5 및 이전 버전에서는 CAS 정책이 항상 적용되지만  [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]에서는 CAS 정책을 사용하도록 설정해야 합니다.  
  
 CAS 정책은 버전에 따라 다르므로  이전 버전의 .NET Framework에 있는 사용자 지정 CAS 정책은 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]에서 다시 지정해야 합니다.  
  
 `<NetFx40_LegacySecurityPolicy>` 요소를 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 어셈블리에 적용해도 [보안 투명 코드](../../../../../docs/framework/misc/security-transparent-code.md)에는 아무 영향이 없습니다. 투명성 규칙이 계속 적용됩니다.  
  
> [!IMPORTANT]
>  `<NetFx40_LegacySecurityPolicy>` 요소를 적용하면 [글로벌 어셈블리 캐시](../../../../../docs/framework/app-domains/gac.md)에 설치되지 않은 [네이티브 이미지 생성기\(Ngen.exe\)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md)에서 만든 네이티브 이미지 어셈블리의 성능이 대폭 저하될 수 있습니다.  특성을 적용할 때 런타임이 어셈블리를 네이티브 이미지로 로드하지 못하면 성능이 저하되어 Just\-In\-Time 어셈블리로 로드될 수 있습니다.  
  
> [!NOTE]
>  Visual Studio 프로젝트의 프로젝트 설정에서 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]보다 이전 버전의 대상 .NET Framework을 지정하면 해당 버전에 대해 지정된 사용자 지정 CAS 정책을 포함한 CAS 정책이 활성화됩니다.  그러나 이 경우 새로운 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 형식 및 멤버는 사용할 수 없습니다.  .NET Framework의 이전 버전을 [\<supportedRuntime\> 요소](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)를 사용하여 [응용 프로그램 구성 파일](../../../../../docs/framework/configure-apps/index.md)에서 시작 설정 스키마에서 지정할 수 있습니다.  
  
> [!NOTE]
>  구성 파일의 구문은 대\/소문자를 구분합니다.  구문 및 예제 섹션에 나와 있는 대로 구문을 사용해야 합니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일에서만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램에 대해 레거시 CAS 정책을 사용하도록 설정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)