---
title: "&lt;serviceAuthorization&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9572cea14b7c15893459133aa75e9fa62b10d4f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthorizationgt-element"></a><span data-ttu-id="4aa1a-102">&lt;serviceAuthorization&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="4aa1a-102">&lt;serviceAuthorization&gt; element</span></span>
<span data-ttu-id="4aa1a-103">서비스 작업에 대한 액세스 권한을 부여하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="4aa1a-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4aa1a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4aa1a-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="4aa1a-105">\<behaviors></span></span>  
<span data-ttu-id="4aa1a-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4aa1a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4aa1a-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="4aa1a-107">\<behavior></span></span>  
<span data-ttu-id="4aa1a-108">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="4aa1a-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aa1a-109">구문</span><span class="sxs-lookup"><span data-stu-id="4aa1a-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization  
     impersonateCallerForAllOperations="Boolean"  
      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"  
      roleProviderName="String"  
      serviceAuthorizationManagerType="String" />  
      <authorizationPolicies>  
         <add policyType="String" />  
      </authorizationPolicies>  
</serviceAuthorization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aa1a-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4aa1a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4aa1a-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aa1a-112">특성</span><span class="sxs-lookup"><span data-stu-id="4aa1a-112">Attributes</span></span>  
  
|<span data-ttu-id="4aa1a-113">특성</span><span class="sxs-lookup"><span data-stu-id="4aa1a-113">Attribute</span></span>|<span data-ttu-id="4aa1a-114">설명</span><span class="sxs-lookup"><span data-stu-id="4aa1a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4aa1a-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="4aa1a-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="4aa1a-116">서비스의 모든 작업이 호출자를 가장하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="4aa1a-117">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="4aa1a-118">특정 서비스 작업이 호출자를 가장하면 지정된 서비스를 실행하기 전에 스레드 컨텍스트가 호출자 컨텍스트로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="4aa1a-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="4aa1a-119">principalPermissionMode</span></span>|<span data-ttu-id="4aa1a-120">서버에서 작업을 수행할 때 사용되는 사용자를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="4aa1a-121">여기에는 다음 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="4aa1a-122">-없음</span><span class="sxs-lookup"><span data-stu-id="4aa1a-122">-   None</span></span><br /><span data-ttu-id="4aa1a-123">-UseWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="4aa1a-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="4aa1a-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="4aa1a-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="4aa1a-125">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4aa1a-125">-   Custom</span></span><br /><br /> <span data-ttu-id="4aa1a-126">기본값은 UseWindowsGroups입니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="4aa1a-127">값은 <xref:System.ServiceModel.Description.PrincipalPermissionMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="4aa1a-128">이 특성을 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [하는 방법: PrincipalPermissionAttribute 클래스에 대 한 액세스 제한](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="4aa1a-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="4aa1a-129">roleProviderName</span></span>|<span data-ttu-id="4aa1a-130">역할 공급자의 이름을 지정하는 문자열로, WCF(Windows Communication Foundation) 응용 프로그램에 대한 역할 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4aa1a-131">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="4aa1a-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="4aa1a-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="4aa1a-133">서비스 인증 관리자의 형식을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="4aa1a-134">자세한 내용은 <xref:System.ServiceModel.ServiceAuthorizationManager>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aa1a-135">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4aa1a-135">Child Elements</span></span>  
  
|<span data-ttu-id="4aa1a-136">요소</span><span class="sxs-lookup"><span data-stu-id="4aa1a-136">Element</span></span>|<span data-ttu-id="4aa1a-137">설명</span><span class="sxs-lookup"><span data-stu-id="4aa1a-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4aa1a-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="4aa1a-138">authorizationPolicies</span></span>|<span data-ttu-id="4aa1a-139">`add` 키워드를 사용하여 추가할 수 있는 인증 정책 형식 컬렉션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="4aa1a-140">각 인증 정책에는 문자열에 해당하는 단일 필수 `policyType` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="4aa1a-141">이 특성은 한 입력 클레임 집합을 다른 클레임 집합으로 변환할 수 있도록 하는 인증 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4aa1a-142">그에 따라 액세스 제어가 부여되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="4aa1a-143">자세한 내용은 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4aa1a-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4aa1a-144">Parent Elements</span></span>  
  
|<span data-ttu-id="4aa1a-145">요소</span><span class="sxs-lookup"><span data-stu-id="4aa1a-145">Element</span></span>|<span data-ttu-id="4aa1a-146">설명</span><span class="sxs-lookup"><span data-stu-id="4aa1a-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4aa1a-147">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="4aa1a-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4aa1a-148">서비스의 동작에 대한 설정 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aa1a-149">설명</span><span class="sxs-lookup"><span data-stu-id="4aa1a-149">Remarks</span></span>  
 <span data-ttu-id="4aa1a-150">이 섹션에는 권한 부여, 사용자 지정 역할 공급자 및 가장에 영향을 주는 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="4aa1a-151">`principalPermissionMode` 특성은 보호된 메서드의 사용 권한을 부여할 때 사용할 사용자 그룹을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="4aa1a-152">기본값은 `UseWindowsGroups`이며 리소스에 액세스하려는 ID에 대해 "Administrators" 또는 "Users"와 같은 Windows 그룹을 검색하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="4aa1a-153">지정할 수 있습니다 `UseAspNetRoles` 아래에서 구성 된 사용자 지정 역할 공급자를 사용 하는 \<system.web > 요소를 다음 코드에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
          type="System.Web.Security.SqlMembershipProvider"   
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 <span data-ttu-id="4aa1a-154">다음 코드에서는 `roleProviderName` 특성과 함께 사용되는 `principalPermissionMode`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>  
   <behavior name="ServiceBehaviour">  
     <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                           roleProviderName ="SqlProvider" />  
   </behavior>   
<!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
 <span data-ttu-id="4aa1a-155">이 구성 요소를 사용 하 여의 자세한 예제를 보려면 [서비스 작업에 대 한 액세스 권한을 부여](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) 및 [권한 부여 정책](../../../../../docs/framework/wcf/samples/authorization-policy.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa1a-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aa1a-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4aa1a-156">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 [<span data-ttu-id="4aa1a-157">보안 동작</span><span class="sxs-lookup"><span data-stu-id="4aa1a-157">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="4aa1a-158">서비스 작업에 대한 액세스 승인</span><span class="sxs-lookup"><span data-stu-id="4aa1a-158">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="4aa1a-159">방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="4aa1a-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="4aa1a-160">방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="4aa1a-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [<span data-ttu-id="4aa1a-161">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="4aa1a-161">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
