---
title: "보안 투명 코드, 수준 2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
caps.latest.revision: "37"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba7b6bca4618b8de7c1b5ce2ef45b8455ee71c5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="c630a-102">보안 투명 코드, 수준 2</span><span class="sxs-lookup"><span data-stu-id="c630a-102">Security-Transparent Code, Level 2</span></span>
<a name="top"></a>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="c630a-103">수준 2 투명도는 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 새로 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-103">Level 2 transparency was introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c630a-104">이 모델의 세 가지 개념은 투명 코드, 보안 안전에 중요 코드 및 보안에 중요 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>  
  
-   <span data-ttu-id="c630a-105">완전 신뢰로 실행되는 코드를 포함하는 투명 코드는 다른 투명 코드나 보안 안전에 중요 코드만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="c630a-106">도메인의 부분 신뢰 권한 집합(있는 경우)에서 허용하는 작업만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="c630a-107">투명 코드는 다음을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-107">Transparent code cannot do the following:</span></span>  
  
    -   <span data-ttu-id="c630a-108"><xref:System.Security.CodeAccessPermission.Assert%2A> 또는 권한 상승을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>  
  
    -   <span data-ttu-id="c630a-109">안전하지 않거나 확인할 수 없는 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-109">Contain unsafe or unverifiable code.</span></span>  
  
    -   <span data-ttu-id="c630a-110">중요한 코드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-110">Directly call critical code.</span></span>  
  
    -   <span data-ttu-id="c630a-111"><xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 특성이 포함된 코드나 네이티브 코드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>  
  
    -   <span data-ttu-id="c630a-112"><xref:System.Security.Permissions.SecurityAction.LinkDemand>로 보호된 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>  
  
    -   <span data-ttu-id="c630a-113">중요한 형식에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-113">Inherit from critical types.</span></span>  
  
     <span data-ttu-id="c630a-114">또한 투명 메서드는 중요한 가상 메서드를 재정의하거나 중요한 인터페이스 메서드를 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>  
  
-   <span data-ttu-id="c630a-115">안전에 중요 코드는 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="c630a-116">이 코드는 완전 신뢰 코드의 제한된 노출 영역을 노출하고, 정확성 및 보안 확인은 안전에 중요 코드에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>  
  
-   <span data-ttu-id="c630a-117">보안에 중요 코드는 모든 코드를 호출할 수 있고 완전히 신뢰할 수 있지만 투명 코드를 통해 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>  
  
 <span data-ttu-id="c630a-118">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-118">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="c630a-119">사용 예제 및 동작</span><span class="sxs-lookup"><span data-stu-id="c630a-119">Usage Examples and Behaviors</span></span>](#examples)  
  
-   [<span data-ttu-id="c630a-120">재정의 패턴</span><span class="sxs-lookup"><span data-stu-id="c630a-120">Override Patterns</span></span>](#override)  
  
-   [<span data-ttu-id="c630a-121">상속 규칙</span><span class="sxs-lookup"><span data-stu-id="c630a-121">Inheritance Rules</span></span>](#inheritance)  
  
-   [<span data-ttu-id="c630a-122">추가 정보 및 규칙</span><span class="sxs-lookup"><span data-stu-id="c630a-122">Additional Information and Rules</span></span>](#additional)  
  
<a name="examples"></a>   
## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="c630a-123">사용 예제 및 동작</span><span class="sxs-lookup"><span data-stu-id="c630a-123">Usage Examples and Behaviors</span></span>  
 <span data-ttu-id="c630a-124">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 규칙(수준 2 투명도)을 지정하려면 어셈블리에 대한 다음 주석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-124">To specify [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules (level 2 transparency), use the following annotation for an assembly:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level2)]  
```  
  
 <span data-ttu-id="c630a-125">.NET Framework 2.0 규칙(수준 1 투명도)으로 잠그려면 다음 주석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-125">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 <span data-ttu-id="c630a-126">어셈블리를 주석으로 처리하지 않으면 기본적으로 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-126">If you do not annotate an assembly, the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules are used by default.</span></span> <span data-ttu-id="c630a-127">그러나, 사용 하는 권장된 모범 사례는 <xref:System.Security.SecurityRulesAttribute> 특성 대신 기본값에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-127">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>  
  
### <a name="assembly-wide-annotation"></a><span data-ttu-id="c630a-128">어셈블리 수준 주석</span><span class="sxs-lookup"><span data-stu-id="c630a-128">Assembly-wide Annotation</span></span>  
 <span data-ttu-id="c630a-129">어셈블리 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-129">The following rules apply to the use of attributes at the assembly level:</span></span>  
  
-   <span data-ttu-id="c630a-130">특성 없음: 특성을 지정하지 않으면 보안에 중요하게 되어 상속 규칙을 위반하는 경우(예: 투명한 가상 또는 인터페이스 메서드를 재정의하거나 구현할 경우)를 제외하고 런타임은 모든 코드를 보안에 중요 코드로 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-130">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="c630a-131">이 경우 메서드는 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-131">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="c630a-132">특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-132">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>  
  
-   <span data-ttu-id="c630a-133">`SecurityTransparent`: 모든 코드가 투명합니다. 전체 어셈블리는 권한이 필요하거나 안전하지 않은 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-133">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>  
  
-   <span data-ttu-id="c630a-134">`SecurityCritical`: 이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-134">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="c630a-135">이 시나리오는 특성을 지정하지 않는 것과 비슷하지만, 공용 언어 런타임이 투명도 규칙을 자동으로 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-135">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="c630a-136">예를 들어 가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 기본적으로 해당 메서드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-136">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="c630a-137">메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석으로 처리해야 합니다. 그러지 않으면 로드 시 <xref:System.TypeLoadException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-137">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="c630a-138">이 규칙은 기본 클래스와 파생 클래스가 둘 다 같은 어셈블리에 있을 경우에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-138">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>  
  
-   <span data-ttu-id="c630a-139">`AllowPartiallyTrustedCallers`(수준 2만 해당): 모든 코드가 기본적으로 투명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-139">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="c630a-140">그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-140">However, individual types and members can have other attributes.</span></span>  
  
 <span data-ttu-id="c630a-141">다음 표에서는 수준 2에 대한 어셈블리 수준 동작을 수준 1과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-141">The following table compares the assembly level behavior for Level 2 with Level 1 .</span></span>  
  
|<span data-ttu-id="c630a-142">Assembly 특성</span><span class="sxs-lookup"><span data-stu-id="c630a-142">Assembly attribute</span></span>|<span data-ttu-id="c630a-143">수준 2</span><span class="sxs-lookup"><span data-stu-id="c630a-143">Level 2</span></span>|<span data-ttu-id="c630a-144">수준 1</span><span class="sxs-lookup"><span data-stu-id="c630a-144">Level 1</span></span>|  
|------------------------|-------------|-------------|  
|<span data-ttu-id="c630a-145">부분적으로 신뢰할 수 있는 어셈블리에 대한 특성 없음</span><span class="sxs-lookup"><span data-stu-id="c630a-145">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="c630a-146">형식 및 멤버는 기본적으로 투명하지만 보안에 중요하거나 보안 안전에 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-146">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="c630a-147">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-147">All types and members are transparent.</span></span>|  
|<span data-ttu-id="c630a-148">특성 없음</span><span class="sxs-lookup"><span data-stu-id="c630a-148">No attribute</span></span>|<span data-ttu-id="c630a-149">특성을 지정하지 않으면 공용 언어 런타임이 투명도 규칙을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-149">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="c630a-150">보안에 중요하게 되어 상속 규칙을 위반하는 경우를 제외하고 모든 형식 및 멤버가 보안에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-150">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="c630a-151">완전히 신뢰할 수 있는 어셈블리(전역 어셈블리 캐시에 포함 또는 `AppDomain`에서 완전 신뢰로 식별됨)에서 모든 형식은 투명하고 모든 멤버는 보안 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-151">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|  
|`SecurityTransparent`|<span data-ttu-id="c630a-152">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-152">All types and members are transparent.</span></span>|<span data-ttu-id="c630a-153">모든 형식 및 멤버가 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-153">All types and members are transparent.</span></span>|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="c630a-154">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c630a-154">Not applicable.</span></span>|<span data-ttu-id="c630a-155">모든 형식 및 멤버가 보안에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-155">All types and members are security-critical.</span></span>|  
|`SecurityCritical`|<span data-ttu-id="c630a-156">이 어셈블리에서 형식으로 도입되는 모든 코드가 중요합니다. 기타 모든 코드는 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-156">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="c630a-157">가상 또는 추상 메서드를 재정의하거나 인터페이스 메서드를 구현할 경우 해당 메서드를 `SecurityCritical` 또는 `SecuritySafeCritical`로 명시적으로 주석으로 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-157">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="c630a-158">모든 코드가 기본적으로 투명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-158">All code defaults to transparent.</span></span> <span data-ttu-id="c630a-159">그러나 개별 형식 및 멤버는 다른 특성을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-159">However, individual types and members can have other attributes.</span></span>|  
  
### <a name="type-and-member-annotation"></a><span data-ttu-id="c630a-160">형식 및 멤버 주석</span><span class="sxs-lookup"><span data-stu-id="c630a-160">Type and Member Annotation</span></span>  
 <span data-ttu-id="c630a-161">형식에 적용되는 보안 특성은 형식에 의해 도입되는 멤버에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-161">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="c630a-162">그러나 기본 클래스 또는 인터페이스 구현의 가상 또는 추상 재정의에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-162">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="c630a-163">형식 및 멤버 수준에서 특성을 사용할 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-163">The following rules apply to the use of attributes at the type and member level:</span></span>  
  
-   <span data-ttu-id="c630a-164">`SecurityCritical`: 형식 또는 멤버가 중요하고 완전 신뢰 코드를 통해서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-164">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="c630a-165">보안에 중요 형식에 도입된 메서드는 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-165">Methods that are introduced in a security-critical type are critical.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c630a-166">기본 클래스 또는 인터페이스에 도입되고 보안에 중요 클래스에서 재정의되거나 구현되는 가상 및 추상 메서드는 기본적으로 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-166">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="c630a-167">이들 메서드는 `SecuritySafeCritical` 또는 `SecurityCritical`로 식별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-167">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>  
  
-   <span data-ttu-id="c630a-168">`SecuritySafeCritical`: 형식 또는 멤버가 안전에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-168">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="c630a-169">그러나 형식 또는 멤버는 투명(부분적으로 신뢰할 수 있는) 코드에서 호출할 수 있고 다른 중요한 코드와 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-169">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="c630a-170">코드는 보안을 위해 감사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-170">The code must be audited for security.</span></span>  
  
 [<span data-ttu-id="c630a-171">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="c630a-171">Back to top</span></span>](#top)  
  
<a name="override"></a>   
## <a name="override-patterns"></a><span data-ttu-id="c630a-172">재정의 패턴</span><span class="sxs-lookup"><span data-stu-id="c630a-172">Override Patterns</span></span>  
 <span data-ttu-id="c630a-173">다음 표에서는 수준 2 투명도에 허용되는 메서드 재정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-173">The following table shows the method overrides allowed for level 2 transparency.</span></span>  
  
|<span data-ttu-id="c630a-174">기본 가상/인터페이스 멤버</span><span class="sxs-lookup"><span data-stu-id="c630a-174">Base virtual/interface member</span></span>|<span data-ttu-id="c630a-175">재정의/인터페이스</span><span class="sxs-lookup"><span data-stu-id="c630a-175">Override/interface</span></span>|  
|------------------------------------|-------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 [<span data-ttu-id="c630a-176">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="c630a-176">Back to top</span></span>](#top)  
  
<a name="inheritance"></a>   
## <a name="inheritance-rules"></a><span data-ttu-id="c630a-177">상속 규칙</span><span class="sxs-lookup"><span data-stu-id="c630a-177">Inheritance Rules</span></span>  
 <span data-ttu-id="c630a-178">이 섹션에서는 액세스 권한과 기능에 따라 다음 순서가 `Transparent`, `Critical` 및 `SafeCritical` 코드에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-178">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>  
  
 `Transparent` < `SafeCritical` < `Critical`  
  
-   <span data-ttu-id="c630a-179">형식에 대한 규칙: 왼쪽에서 오른쪽으로 이동하면 액세스 권한이 더 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-179">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="c630a-180">파생 형식은 기본 형식 이상으로 제한적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-180">Derived types must be at least as restrictive as the base type.</span></span>  
  
-   <span data-ttu-id="c630a-181">메서드에 대한 규칙: 파생 메서드는 기본 메서드의 접근성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-181">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="c630a-182">기본 동작의 경우 주석으로 처리되지 않은 모든 파생 메서드는 `Transparent`입니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-182">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="c630a-183">재정의된 메서드가 `SecurityCritical`로 명시적으로 주석으로 처리되지 않으면 중요한 형식의 파생 항목으로 인해 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-183">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>  
  
 <span data-ttu-id="c630a-184">다음 표에서는 허용되는 형식 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-184">The following table shows the allowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="c630a-185">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="c630a-185">Base class</span></span>|<span data-ttu-id="c630a-186">파생 클래스는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-186">Derived class can be</span></span>|  
|----------------|--------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`SafeCritical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="c630a-187">다음 표에서는 허용되지 않는 형식 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-187">The following table shows the disallowed type inheritance patterns.</span></span>  
  
|<span data-ttu-id="c630a-188">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="c630a-188">Base class</span></span>|<span data-ttu-id="c630a-189">파생 클래스는 다음과 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-189">Derived class cannot be</span></span>|  
|----------------|-----------------------------|  
|`SafeCritical`|`Transparent`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
 <span data-ttu-id="c630a-190">다음 표에서는 허용되는 메서드 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-190">The following table shows the allowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="c630a-191">기본 메서드</span><span class="sxs-lookup"><span data-stu-id="c630a-191">Base method</span></span>|<span data-ttu-id="c630a-192">파생 메서드는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-192">Derived method can be</span></span>|  
|-----------------|---------------------------|  
|`Transparent`|`Transparent`|  
|`Transparent`|`SafeCritical`|  
|`SafeCritical`|`Transparent`|  
|`SafeCritical`|`SafeCritical`|  
|`Critical`|`Critical`|  
  
 <span data-ttu-id="c630a-193">다음 표에서는 허용되지 않는 메서드 상속 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-193">The following table shows the disallowed method inheritance patterns.</span></span>  
  
|<span data-ttu-id="c630a-194">기본 메서드</span><span class="sxs-lookup"><span data-stu-id="c630a-194">Base method</span></span>|<span data-ttu-id="c630a-195">파생 메서드는 다음과 같을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-195">Derived method cannot be</span></span>|  
|-----------------|------------------------------|  
|`Transparent`|`Critical`|  
|`SafeCritical`|`Critical`|  
|`Critical`|`Transparent`|  
|`Critical`|`SafeCritical`|  
  
> [!NOTE]
>  <span data-ttu-id="c630a-196">이들 상속 규칙은 수준 2 형식 및 멤버에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-196">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="c630a-197">수준 1 어셈블리의 형식은 수준 2 보안에 중요 형식 및 멤버에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-197">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="c630a-198">따라서 수준 2 형식 및 멤버에는 수준 1 상속자에 대한 별도의 상속 요청이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-198">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>  
  
 [<span data-ttu-id="c630a-199">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="c630a-199">Back to top</span></span>](#top)  
  
<a name="additional"></a>   
## <a name="additional-information-and-rules"></a><span data-ttu-id="c630a-200">추가 정보 및 규칙</span><span class="sxs-lookup"><span data-stu-id="c630a-200">Additional Information and Rules</span></span>  
  
### <a name="linkdemand-support"></a><span data-ttu-id="c630a-201">LinkDemand 지원</span><span class="sxs-lookup"><span data-stu-id="c630a-201">LinkDemand Support</span></span>  
 <span data-ttu-id="c630a-202">수준 2 투명도 모델은 <xref:System.Security.Permissions.SecurityAction.LinkDemand>를 <xref:System.Security.SecurityCriticalAttribute> 특성으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-202">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="c630a-203">레거시(수준 1) 코드에서 <xref:System.Security.Permissions.SecurityAction.LinkDemand>는 자동으로 <xref:System.Security.Permissions.SecurityAction.Demand>로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-203">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>  
  
### <a name="reflection"></a><span data-ttu-id="c630a-204">반사</span><span class="sxs-lookup"><span data-stu-id="c630a-204">Reflection</span></span>  
 <span data-ttu-id="c630a-205">중요한 메서드를 호출하거나 중요한 필드를 읽으면 private 메서드나 필드를 호출한 것처럼 완전 신뢰에 대한 요청이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-205">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="c630a-206">따라서 완전 신뢰 코드는 중요한 메서드를 호출할 수 있지만 부분 신뢰 코드는 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-206">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>  
  
 <span data-ttu-id="c630a-207">형식, 메서드 또는 필드가 `SecurityCritical`, `SecuritySafeCritical` 또는 `SecurityTransparent`인지 확인하려고 <xref:System.Reflection> 네임스페이스에 <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> 및 <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A> 속성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-207">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="c630a-208">이들 속성을 사용하여 특성이 있는지 확인하는 것이 아니라 리플렉션을 통해 투명도를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-208">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="c630a-209">투명도 규칙은 복잡하고 특성이 있는지 확인하는 것으로는 충분하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-209">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c630a-210">A `SafeCritical` 메서드 반환 `true` 모두에 대 한 <xref:System.Type.IsSecurityCritical%2A> 및 <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>때문에, `SafeCritical` 실제로 중요 (중요 한 코드와 동일한 기능을 포함 하지만 투명 코드에서 호출할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="c630a-210">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>  
  
 <span data-ttu-id="c630a-211">동적 메서드는 연결된 모듈의 투명도를 상속합니다. 형식의 투명도를 상속하지 않습니다(형식에 연결된 경우).</span><span class="sxs-lookup"><span data-stu-id="c630a-211">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>  
  
### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="c630a-212">완전 신뢰에서 확인 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="c630a-212">Skip Verification in Full Trust</span></span>  
 <span data-ttu-id="c630a-213"><xref:System.Security.SecurityRulesAttribute> 특성에서 <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성을 `true`로 설정하여 완전히 신뢰할 수 있는 어셈블리에 대한 확인을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-213">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>  
  
 `[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`  
  
 <span data-ttu-id="c630a-214"><xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 속성은 기본적으로 `false`이므로 확인을 건너뛰려면 속성을 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-214">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="c630a-215">이 작업은 최적화 목적으로만 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-215">This should be done for optimization purposes only.</span></span> <span data-ttu-id="c630a-216">사용 하 여 어셈블리의 투명 코드를 확인할 수 있는지 확인 해야는 `transparent` 옵션에 [PEVerify 도구](../../../docs/framework/tools/peverify-exe-peverify-tool.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c630a-216">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c630a-217">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c630a-217">See Also</span></span>  
 [<span data-ttu-id="c630a-218">보안 투명 코드, 수준 1</span><span class="sxs-lookup"><span data-stu-id="c630a-218">Security-Transparent Code, Level 1</span></span>](../../../docs/framework/misc/security-transparent-code-level-1.md)  
 [<span data-ttu-id="c630a-219">보안 변경 내용</span><span class="sxs-lookup"><span data-stu-id="c630a-219">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)
