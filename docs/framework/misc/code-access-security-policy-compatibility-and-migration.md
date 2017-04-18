---
title: "코드 액세스 보안 정책 호환성 및 마이그레이션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "CLR 정책 마이그레이션"
  - "정책 마이그레이션, 호환성"
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# 코드 액세스 보안 정책 호환성 및 마이그레이션
CAS\(코드 액세스 보안\)의 정책 부분이 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 사용되지 않습니다.  따라서 사용되지 않는 정책 형식과 멤버를 [명시적](#explicit_use) 또는 [암시적으로](#implicit_use)\(다른 형식과 멤버를 통해\) 호출하는 경우 컴파일 경고 및 런타임 예외가 발생할 수 있습니다.  
  
 다음 중 하나를 수행하여 경고와 오류를 방지할 수 있습니다.  
  
-   사용되지 않는 호출에 대한 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 대체 항목으로 [마이그레이션](#migration)  
  
     또는  
  
-   [\<NetFx40\_LegacySecurityPolicy\> 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)를 사용하여 레거시 CAS 정책 동작을 선택하도록 지정  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [명시적 사용](#explicit_use)  
  
-   [암시적 사용](#implicit_use)  
  
-   [오류 및 경고](#errors_and_warnings)  
  
-   [마이그레이션: 사용되지 않는 호출에 대한 대체 항목](#migration)  
  
-   [호환성: CAS 정책 레거시 옵션 사용](#compatibility)  
  
> [!CAUTION]
>  코드 액세스 보안 및 부분적으로 신뢰할 수 있는 코드  
>   
>  .NET Framework는 동일한 응용 프로그램에서 실행되는 다른 코드에 다양한 신뢰 수준을 적용하기 위한 CAS\(코드 액세스 보안\)라는 메커니즘을 제공합니다.  .NET Framework의 코드 액세스 보안을 부분적으로 신뢰할 수 있는 코드, 특히 출처를 알 수 없는 코드의 보안 경계로 사용하면 안 됩니다.  대체 보안 조치를 적용하지 않고 출처를 알 수 없는 코드를 로드 및 실행하지 않는 것이 좋습니다.  
>   
>  이 정책은 모든 버전의 .NET Framework에 적용되지만 Silverlight에 포함된 .NET Framework에는 적용되지 않습니다.  
  
<a name="explicit_use"></a>   
## 명시적 사용  
 보안 정책을 직접 조작하거나 샌드박싱에 CAS 정책이 필요한 멤버는 사용되지 않으며 기본적으로 오류를 생성합니다.  
  
 다음은 이러한 예입니다.  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=fullName>  
  
<a name="implicit_use"></a>   
## 암시적 사용  
 어셈블리 로드 오버로드가 여러 개이면 CAS 정책의 암시적 사용 때문에 오류가 생성됩니다.  이러한 오버로드는 CAS 정책을 확인하고 어셈블리에 대한 권한 부여 집합을 제공하는 데 사용되는 <xref:System.Security.Policy.Evidence> 매개 변수를 받습니다.  
  
 다음은 몇 가지 예입니다.  사용되지 않는 오버로드는 <xref:System.Security.Policy.Evidence>를 매개 변수로 받는 오버로드입니다.  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
<a name="errors_and_warnings"></a>   
## 오류 및 경고  
 사용되지 않는 형식과 멤버를 사용할 경우 다음과 같은 오류 메시지가 생성됩니다.  <xref:System.Security.Policy.Evidence?displayProperty=fullName> 형식 자체는 사용이 중단되지 않았습니다.  
  
 컴파일 타임 경고:  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework.  Please use <suggested alternate API>.  See <link> for more information.'`  
  
 런타임 예외:  
  
 <xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`  
  
<a name="migration"></a>   
## 마이그레이션: 사용되지 않는 호출에 대한 대체 항목  
  
### 어셈블리의 신뢰 수준 결정  
 CAS 정책은 대체로 어셈블리 또는 응용 프로그램 도메인의 권한 부여 집합이나 신뢰 수준을 결정하는 데 사용됩니다.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 보안 정책을 확인할 필요가 없는 다음과 같은 유용한 속성을 노출합니다.  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=fullName>  
  
### 응용 프로그램 도메인 샌드박싱  
 <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName> 메서드는 일반적으로 응용 프로그램 도메인에 어셈블리를 샌드박싱하는 데 사용됩니다.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 이를 위해 <xref:System.Security.Policy.PolicyLevel>을 사용할 필요가 없는 멤버를 노출합니다. 자세한 내용은 [방법: 샌드박스에서 부분 신뢰 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)을 참조하세요.  
  
### 부분적으로 신뢰할 수 있는 코드에 대한 안전하거나 적절한 권한 집합 결정  
 호스트가 호스트된 코드를 샌드박싱하는 데 적절한 권한을 결정해야 하는 경우가 많습니다.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 이전에는 CAS 정책이 <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName> 메서드로 이 작업을 수행하는 방법을 제공했습니다.  대신, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 제공된 증거에 대한 안전한 표준 권한 집합을 반환하는 <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=fullName> 메서드를 제공합니다.  
  
### 비샌드박싱 시나리오: 어셈블리 로드 오버로드  
 어셈블리 로드 오버로드를 사용하는 이유는 어셈블리를 샌드박싱하는 대신 달리 사용할 수 없는 매개 변수를 사용하기 위한 것입니다.  [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터 <xref:System.Security.Policy.Evidence?displayProperty=fullName> 개체를 매개 변수로 요구하지 않는 어셈블리 로드 오버로드\(예: [AppDomain.ExecuteAssembly\(String, String\[\], Byte\<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=fullName>\)를 통해 이 시나리오가 가능합니다.  
  
 어셈블리를 샌드박싱하려는 경우 [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName> 오버로드를 사용합니다.  
  
<a name="compatibility"></a>   
## 호환성: CAS 정책 레거시 옵션 사용  
 [\<NetFx40\_LegacySecurityPolicy\> 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)를 사용하면 프로세스나 라이브러리에서 레거시 CAS 정책을 사용하도록 지정할 수 있습니다.  이 요소를 사용하도록 설정하면 정책 및 증거 오버로드가 이전 버전의 프레임워크와 동일하게 작동합니다.  
  
> [!NOTE]
>  CAS 정책 동작은 런타임 버전별로 지정되므로 특정 런타임 버전에 대해 CAS 정책을 수정해도 다른 버전의 CAS 정책에는 영향을 주지 않습니다.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [방법: 샌드박스에서 부분 신뢰 코드 실행](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)