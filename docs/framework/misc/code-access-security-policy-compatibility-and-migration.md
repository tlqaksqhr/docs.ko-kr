---
title: 코드 액세스 보안 정책 호환성 및 마이그레이션
ms.date: 03/30/2017
helpviewer_keywords:
- policy migration, compatibility
- CLR poliicy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5007e07340621fa76dc37a48eaf8c17bc048339
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393249"
---
# <a name="code-access-security-policy-compatibility-and-migration"></a>코드 액세스 보안 정책 호환성 및 마이그레이션
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 CAS(코드 액세스 보안)의 정책 부분이 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 사용되지 않습니다. 결과적으로, 있습니다 수 컴파일 경고 및 런타임 예외가 발생할 사용 되지 않는 정책 형식과 멤버를 호출 하는 경우 [명시적으로](#explicit_use) 또는 [암시적으로](#implicit_use) (다른 형식과 멤버의) 통해 합니다.  
  
 다음 중 하나를 수행하여 경고와 오류를 방지할 수 있습니다.  
  
-   [마이그레이션](#migration) 에 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 사용 되지 않는 호출에 대 한 대체 합니다.  
  
     \- 또는 -  
  
-   사용 하 여 [< NetFx40_LegacySecurityPolicy > 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 레거시 CAS 정책 동작을 선택 하도록 합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [명시적으로 사용](#explicit_use)  
  
-   [암시적 사용](#implicit_use)  
  
-   [오류 및 경고](#errors_and_warnings)  
  
-   [사용 되지 않는 호출에 대 한 마이그레이션: 대체 항목](#migration)  
  
-   [호환성: CAS 정책 레거시 옵션 사용](#compatibility)  
  
<a name="explicit_use"></a>   
## <a name="explicit-use"></a>명시적 사용  
 보안 정책을 직접 조작하거나 샌드박싱에 CAS 정책이 필요한 멤버는 사용되지 않으며 기본적으로 오류를 생성합니다.  
  
 다음은 이러한 예입니다.  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>  
  
<a name="implicit_use"></a>   
## <a name="implicit-use"></a>암시적 사용  
 어셈블리 로드 오버로드가 여러 개이면 CAS 정책의 암시적 사용 때문에 오류가 생성됩니다. 이러한 오버로드는 CAS 정책을 확인하고 어셈블리에 대한 권한 부여 집합을 제공하는 데 사용되는 <xref:System.Security.Policy.Evidence> 매개 변수를 받습니다.  
  
 다음은 몇 가지 예입니다. 사용되지 않는 오버로드는 <xref:System.Security.Policy.Evidence>를 매개 변수로 받는 오버로드입니다.  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
<a name="errors_and_warnings"></a>   
## <a name="errors-and-warnings"></a>오류 및 경고  
 사용되지 않는 형식과 멤버를 사용할 경우 다음과 같은 오류 메시지가 생성됩니다. <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 형식 자체는 사용이 중단되지 않았습니다.  
  
 컴파일 시간 경고:  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`  
  
 런타임 예외:  
  
 <xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`  
  
<a name="migration"></a>   
## <a name="migration-replacement-for-obsolete-calls"></a>마이그레이션: 사용되지 않는 호출에 대한 대체 항목  
  
### <a name="determining-an-assemblys-trust-level"></a>어셈블리의 신뢰 수준 결정  
 CAS 정책은 대체로 어셈블리 또는 응용 프로그램 도메인의 권한 부여 집합이나 신뢰 수준을 결정하는 데 사용됩니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 보안 정책을 확인할 필요가 없는 다음과 같은 유용한 속성을 노출합니다.  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
### <a name="application-domain-sandboxing"></a>응용 프로그램 도메인 샌드박싱  
 <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> 메서드는 일반적으로 응용 프로그램 도메인에 어셈블리를 샌드박싱하는 데 사용됩니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 사용할 필요가 없는 멤버를 노출 <xref:System.Security.Policy.PolicyLevel> 이 목적을 위해 합니다. 자세한 내용은 참조 [하는 방법: 부분적으로 신뢰할 수 있는 코드 실행 샌드박스에서](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)합니다.  
  
### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a>부분적으로 신뢰할 수 있는 코드에 대한 안전하거나 적절한 권한 집합 결정  
 호스트가 호스트된 코드를 샌드박싱하는 데 적절한 권한을 결정해야 하는 경우가 많습니다. 전에 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS 정책에는이 작업을 수행 하는 방법을 제공는 <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> 메서드. 대신, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 제공는 <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> 메서드를 안전 하 고 표준 권한 제공된 된 증거에 대 한 집합을 반환 합니다.  
  
### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a>비샌드박싱 시나리오: 어셈블리 로드 오버로드  
 어셈블리 로드 오버로드를 사용하는 이유는 어셈블리를 샌드박싱하는 대신 달리 사용할 수 없는 매개 변수를 사용하기 위한 것입니다. 부터는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], 필요로 하지 않는 어셈블리 로드 오버 로드는 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 개체를 매개 변수로 <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>,이 시나리오를 사용 하도록 설정 합니다.  
  
 어셈블리를 샌드박싱하려는 경우 <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> 오버로드를 사용합니다.  
  
<a name="compatibility"></a>   
## <a name="compatibility-using-the-cas-policy-legacy-option"></a>호환성: CAS 정책 레거시 옵션 사용  
 [< NetFx40_LegacySecurityPolicy > 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 프로세스나 라이브러리에서 레거시 CAS 정책을 사용 하도록 지정할 수 있습니다. 이 요소를 사용하도록 설정하면 정책 및 증거 오버로드가 이전 버전의 프레임워크와 동일하게 작동합니다.  
  
> [!NOTE]
>  CAS 정책 동작은 런타임 버전별로 지정되므로 특정 런타임 버전에 대해 CAS 정책을 수정해도 다른 버전의 CAS 정책에는 영향을 주지 않습니다.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [보안 코딩 지침](../../standard/security/secure-coding-guidelines.md)
