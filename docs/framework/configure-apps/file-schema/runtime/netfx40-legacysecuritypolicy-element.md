---
title: '&lt;NetFx40_LegacySecurityPolicy&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d9312d25842ccfcdf84e678d34b9bfde3fe7dd0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a>&lt;NetFx40_LegacySecurityPolicy&gt; 요소
런타임이 레거시 CAS(코드 액세스 보안) 정책을 사용할지를 지정합니다.  
  
 \<configuration>  
\<runtime>  
< NetFx40_LegacySecurityPolicy >  
  
## <a name="syntax"></a>구문  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임이 레거시 CAS 정책을 사용 하는지 여부를 지정 합니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임이 레거시 CAS 정책을 사용 하지 않습니다. 이 값이 기본값입니다.|  
|`true`|런타임이 레거시 CAS 정책을 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework 버전 3.5 및 이전 버전에서는 CAS 정책을 항상 적용 합니다. 에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS 정책을 사용 하도록 설정 해야 합니다.  
  
 CAS 정책에는 버전 별로 다릅니다. 이전 버전의.NET Framework에 존재 하는 CAS 정책을 사용자 지정에서 없게 해야 합니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.  
  
 적용 된 `<NetFx40_LegacySecurityPolicy>` 요소를 한 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 어셈블리에 영향을 주지 않습니다 [보안 투명 코드](../../../../../docs/framework/misc/security-transparent-code.md); 투명도 규칙이 계속 적용 합니다.  
  
> [!IMPORTANT]
>  적용 된 `<NetFx40_LegacySecurityPolicy>` 요소에서 만든 네이티브 이미지 어셈블리에 대 한 성능이 크게 저하 될 수 있습니다는 [네이티브 이미지 생성기 (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) 에 설치 되어 있지는 [전역 어셈블리 캐시 ](../../../../../docs/framework/app-domains/gac.md). 성능 저하는 특성이 적용 되는 때로 네이티브 이미지 어셈블리를 로드 해야 런타임 없을 때 발생, 될 같이-just-in-time 어셈블리를 로드 합니다.  
  
> [!NOTE]
>  이전 대상.NET Framework 버전을 지정 하는 경우는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Visual Studio 프로젝트에 대 한 프로젝트 설정에서 CAS 정책을 활성화 되며 해당 버전에 대해 지정 된 사용자 지정 CAS 정책을 포함 하 여 합니다. 그러나 됩니다 new를 사용 하려면 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 형식 및 멤버입니다. 사용 하 여.NET Framework의 이전 버전을 지정할 수도 있습니다는 [ \<supportedRuntime > 요소](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 시작 설정 스키마에서의 프로그램 [응용 프로그램 구성 파일](../../../../../docs/framework/configure-apps/index.md)합니다.  
  
> [!NOTE]
>  구성 파일의 구문은 대/소문자 구분 합니다. 구문 및 예제 섹션에 제공 된 구문을 사용 해야 합니다.  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 응용 프로그램에 대 한 레거시 CAS 정책을 사용 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
