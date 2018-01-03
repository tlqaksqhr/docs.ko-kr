---
title: "코드 액세스 보안 정책 호환성 및 마이그레이션"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- policy migration, compatibility
- CLR poliicy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9feb4553b1b9e013c5c299d867d74499a09e1434
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="2b1e2-102">코드 액세스 보안 정책 호환성 및 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2b1e2-102">Code Access Security Policy Compatibility and Migration</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="2b1e2-103">CAS(코드 액세스 보안)의 정책 부분이 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-103">The policy portion of code access security (CAS) has been made obsolete in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="2b1e2-104">결과적으로, 있습니다 수 컴파일 경고 및 런타임 예외가 발생할 사용 되지 않는 정책 형식과 멤버를 호출 하는 경우 [명시적으로](#explicit_use) 또는 [암시적으로](#implicit_use) (다른 형식과 멤버의) 통해 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>  
  
 <span data-ttu-id="2b1e2-105">다음 중 하나를 수행하여 경고와 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-105">You can avoid the warnings and errors by either:</span></span>  
  
-   <span data-ttu-id="2b1e2-106">[마이그레이션](#migration) 에 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 사용 되지 않는 호출에 대 한 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-106">[Migrating](#migration) to the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] replacements for the obsolete calls.</span></span>  
  
     <span data-ttu-id="2b1e2-107">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="2b1e2-107">\- or -</span></span>  
  
-   <span data-ttu-id="2b1e2-108">사용 하 여 [< NetFx40_LegacySecurityPolicy > 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 레거시 CAS 정책 동작을 선택 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-108">Using the [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>  
  
 <span data-ttu-id="2b1e2-109">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-109">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="2b1e2-110">명시적으로 사용</span><span class="sxs-lookup"><span data-stu-id="2b1e2-110">Explicit Use</span></span>](#explicit_use)  
  
-   [<span data-ttu-id="2b1e2-111">암시적 사용</span><span class="sxs-lookup"><span data-stu-id="2b1e2-111">Implicit Use</span></span>](#implicit_use)  
  
-   [<span data-ttu-id="2b1e2-112">오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="2b1e2-112">Errors and Warnings</span></span>](#errors_and_warnings)  
  
-   [<span data-ttu-id="2b1e2-113">사용 되지 않는 호출에 대 한 마이그레이션: 대체 항목</span><span class="sxs-lookup"><span data-stu-id="2b1e2-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)  
  
-   [<span data-ttu-id="2b1e2-114">호환성: CAS 정책 레거시 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="2b1e2-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)  
  
<a name="explicit_use"></a>   
## <a name="explicit-use"></a><span data-ttu-id="2b1e2-115">명시적 사용</span><span class="sxs-lookup"><span data-stu-id="2b1e2-115">Explicit Use</span></span>  
 <span data-ttu-id="2b1e2-116">보안 정책을 직접 조작하거나 샌드박싱에 CAS 정책이 필요한 멤버는 사용되지 않으며 기본적으로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>  
  
 <span data-ttu-id="2b1e2-117">다음은 이러한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-117">Examples of these are:</span></span>  
  
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
## <a name="implicit-use"></a><span data-ttu-id="2b1e2-118">암시적 사용</span><span class="sxs-lookup"><span data-stu-id="2b1e2-118">Implicit Use</span></span>  
 <span data-ttu-id="2b1e2-119">어셈블리 로드 오버로드가 여러 개이면 CAS 정책의 암시적 사용 때문에 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="2b1e2-120">이러한 오버로드는 CAS 정책을 확인하고 어셈블리에 대한 권한 부여 집합을 제공하는 데 사용되는 <xref:System.Security.Policy.Evidence> 매개 변수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>  
  
 <span data-ttu-id="2b1e2-121">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-121">Here are some examples.</span></span> <span data-ttu-id="2b1e2-122">사용되지 않는 오버로드는 <xref:System.Security.Policy.Evidence>를 매개 변수로 받는 오버로드입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>  
  
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
## <a name="errors-and-warnings"></a><span data-ttu-id="2b1e2-123">오류 및 경고</span><span class="sxs-lookup"><span data-stu-id="2b1e2-123">Errors and Warnings</span></span>  
 <span data-ttu-id="2b1e2-124">사용되지 않는 형식과 멤버를 사용할 경우 다음과 같은 오류 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="2b1e2-125"><xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 형식 자체는 사용이 중단되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>  
  
 <span data-ttu-id="2b1e2-126">컴파일 시간 경고:</span><span class="sxs-lookup"><span data-stu-id="2b1e2-126">Compile-time warning:</span></span>  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`  
  
 <span data-ttu-id="2b1e2-127">런타임 예외:</span><span class="sxs-lookup"><span data-stu-id="2b1e2-127">Run-time exception:</span></span>  
  
 <span data-ttu-id="2b1e2-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="2b1e2-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>  
  
<a name="migration"></a>   
## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="2b1e2-129">마이그레이션: 사용되지 않는 호출에 대한 대체 항목</span><span class="sxs-lookup"><span data-stu-id="2b1e2-129">Migration: Replacement for Obsolete Calls</span></span>  
  
### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="2b1e2-130">어셈블리의 신뢰 수준 결정</span><span class="sxs-lookup"><span data-stu-id="2b1e2-130">Determining an Assembly’s Trust Level</span></span>  
 <span data-ttu-id="2b1e2-131">CAS 정책은 대체로 어셈블리 또는 응용 프로그램 도메인의 권한 부여 집합이나 신뢰 수준을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="2b1e2-132">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 보안 정책을 확인할 필요가 없는 다음과 같은 유용한 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-132">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes the following useful properties that do not need to resolve security policy:</span></span>  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
### <a name="application-domain-sandboxing"></a><span data-ttu-id="2b1e2-133">응용 프로그램 도메인 샌드박싱</span><span class="sxs-lookup"><span data-stu-id="2b1e2-133">Application Domain Sandboxing</span></span>  
 <span data-ttu-id="2b1e2-134"><xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> 메서드는 일반적으로 응용 프로그램 도메인에 어셈블리를 샌드박싱하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="2b1e2-135">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 사용할 필요가 없는 멤버를 노출 <xref:System.Security.Policy.PolicyLevel> 이 목적을 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-135">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="2b1e2-136">자세한 내용은 참조 [하는 방법: 부분적으로 신뢰할 수 있는 코드 실행 샌드박스에서](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>  
  
### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="2b1e2-137">부분적으로 신뢰할 수 있는 코드에 대한 안전하거나 적절한 권한 집합 결정</span><span class="sxs-lookup"><span data-stu-id="2b1e2-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>  
 <span data-ttu-id="2b1e2-138">호스트가 호스트된 코드를 샌드박싱하는 데 적절한 권한을 결정해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="2b1e2-139">전에 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS 정책에는이 작업을 수행 하는 방법을 제공는 <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-139">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2b1e2-140">대신, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 제공는 <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> 메서드를 안전 하 고 표준 권한 제공된 된 증거에 대 한 집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-140">As a replacement, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>  
  
### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="2b1e2-141">비샌드박싱 시나리오: 어셈블리 로드 오버로드</span><span class="sxs-lookup"><span data-stu-id="2b1e2-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>  
 <span data-ttu-id="2b1e2-142">어셈블리 로드 오버로드를 사용하는 이유는 어셈블리를 샌드박싱하는 대신 달리 사용할 수 없는 매개 변수를 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="2b1e2-143">부터는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], 필요로 하지 않는 어셈블리 로드 오버 로드는 <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 개체를 매개 변수로 <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>,이 시나리오를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-143">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>  
  
 <span data-ttu-id="2b1e2-144">어셈블리를 샌드박싱하려는 경우 <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
<a name="compatibility"></a>   
## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="2b1e2-145">호환성: CAS 정책 레거시 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="2b1e2-145">Compatibility: Using the CAS Policy Legacy Option</span></span>  
 <span data-ttu-id="2b1e2-146">[< NetFx40_LegacySecurityPolicy > 구성 요소](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) 프로세스나 라이브러리에서 레거시 CAS 정책을 사용 하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-146">The [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="2b1e2-147">이 요소를 사용하도록 설정하면 정책 및 증거 오버로드가 이전 버전의 프레임워크와 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b1e2-148">CAS 정책 동작은 런타임 버전별로 지정되므로 특정 런타임 버전에 대해 CAS 정책을 수정해도 다른 버전의 CAS 정책에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1e2-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b1e2-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b1e2-149">See Also</span></span>  
 [<span data-ttu-id="2b1e2-150">방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행</span><span class="sxs-lookup"><span data-stu-id="2b1e2-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="2b1e2-151">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="2b1e2-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
