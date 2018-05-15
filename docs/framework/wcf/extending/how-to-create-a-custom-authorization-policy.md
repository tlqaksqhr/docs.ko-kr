---
title: '방법: 사용자 지정 권한 부여 정책 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
ms.openlocfilehash: 0bacf874e09aca82b2f2685a146612cdef0673db
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-create-a-custom-authorization-policy"></a><span data-ttu-id="1b84d-102">방법: 사용자 지정 권한 부여 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1b84d-102">How to: Create a Custom Authorization Policy</span></span>
<span data-ttu-id="1b84d-103">Id 모델 인프라 Windows Communication Foundation (WCF)에서 클레임 기반 권한 부여 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports a claim-based authorization model.</span></span> <span data-ttu-id="1b84d-104">클레임은 토큰에서 추출되어 사용자 지정 권한 부여 정책에 의해 선택적으로 처리된 다음,이후에 권한 부여를 결정하기 위해 검사할 수 있는 <xref:System.IdentityModel.Policy.AuthorizationContext>에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-104">Claims are extracted from tokens, optionally processed by custom authorization policy, and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext> that can then be examined to make authorization decisions.</span></span> <span data-ttu-id="1b84d-105">사용자 지정 정책은 들어오는 토큰을 응용 프로그램에서 필요로 하는 클레임으로 변형하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-105">A custom policy can be used to transform claims from incoming tokens into claims expected by the application.</span></span> <span data-ttu-id="1b84d-106">이러한 방식으로 WCF에서 지 원하는 다른 토큰 형식으로 된 다른 클레임에 대 한 세부 정보에서 점으로부터 보호 응용 프로그램 계층 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-106">In this way, the application layer can be insulated from the details on the differing claims served up by the different token types that WCF supports.</span></span> <span data-ttu-id="1b84d-107">이 항목에서는 사용자 지정 권한 부여 정책을 구현하는 방법과 이 정책을 서비스에 사용된 정책 컬렉션에 추가하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-107">This topic shows how to implement a custom authorization policy and how to add that policy to the collection of policies used by a service.</span></span>  
  
### <a name="to-implement-a-custom-authorization-policy"></a><span data-ttu-id="1b84d-108">사용자 지정 권한 부여 정책을 구현하려면</span><span class="sxs-lookup"><span data-stu-id="1b84d-108">To implement a custom authorization policy</span></span>  
  
1.  <span data-ttu-id="1b84d-109"><xref:System.IdentityModel.Policy.IAuthorizationPolicy>에서 파생되는 새 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-109">Define a new class that derives from <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2.  <span data-ttu-id="1b84d-110">클래스에 대해 생성자에서 고유 문자열을 생성하고 속성에 액세스할 때마다 해당 문자열을 반환하여 읽기 전용 <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-110">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> property by generating a unique string in the constructor for the class and returning that string whenever the property is accessed.</span></span>  
  
3.  <span data-ttu-id="1b84d-111">정책 발급자를 나타내는<xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A>를 반환하여 읽기 전용 <xref:System.IdentityModel.Claims.ClaimSet> 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-111">Implement the read-only <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> property by returning a <xref:System.IdentityModel.Claims.ClaimSet> that represents the policy issuer.</span></span> <span data-ttu-id="1b84d-112">이는 응용 프로그램을 나타내는 `ClaimSet`이거나 기본 제공된`ClaimSet`(예를 들면 정적 `ClaimSet` 속성에 의해 반환된 <xref:System.IdentityModel.Claims.ClaimSet.System%2A>)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-112">This could be a `ClaimSet` that represents the application or a built-in `ClaimSet` (for example, the `ClaimSet` returned by the static <xref:System.IdentityModel.Claims.ClaimSet.System%2A> property.</span></span>  
  
4.  <span data-ttu-id="1b84d-113">다음 절차에 따라 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-113">Implement the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method as described in the following procedure.</span></span>  
  
### <a name="to-implement-the-evaluate-method"></a><span data-ttu-id="1b84d-114">Evaluate 메서드를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="1b84d-114">To implement the Evaluate method</span></span>  
  
1.  <span data-ttu-id="1b84d-115">두 매개 변수인 개체 참조와 <xref:System.IdentityModel.Policy.EvaluationContext> 클래스의 인스턴스를 이 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-115">Two parameters are passed to this method: an instance of the <xref:System.IdentityModel.Policy.EvaluationContext> class and an object reference.</span></span>  
  
2.  <span data-ttu-id="1b84d-116">사용자 지정 권한 부여 정책에 추가 하는 경우 <xref:System.IdentityModel.Claims.ClaimSet> 의 현재 내용에 관계 없이 인스턴스에 <xref:System.IdentityModel.Policy.EvaluationContext>, 각를 추가할 `ClaimSet` 호출 하 여는 <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> 메서드 및 반환 `true` 에서 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1b84d-116">If the custom authorization policy adds <xref:System.IdentityModel.Claims.ClaimSet> instances without regard to the current content of the <xref:System.IdentityModel.Policy.EvaluationContext>, then add each `ClaimSet` by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and return `true` from the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> method.</span></span> <span data-ttu-id="1b84d-117">`true`가 반환되면 권한 부여 정책의 작업이 수행되어 이를 다시 호출할 필요가 없음을 권한 부여 인프라에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-117">Returning `true` indicates to the authorization infrastructure that the authorization policy has performed its work and does not need to be called again.</span></span>  
  
3.  <span data-ttu-id="1b84d-118">특정 클레임이 `EvaluationContext`에 이미 있는 경우에만 사용자 지정 권한 부여 정책을 통해 클레임 집합을 추가하려면 `ClaimSet` 속성에 의해 반환된 <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> 인스턴스를 검사하여 이러한 클레임을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-118">If the custom authorization policy adds claim sets only if certain claims are already present in the `EvaluationContext`, then look for those claims by examining the `ClaimSet` instances returned by the <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A> property.</span></span> <span data-ttu-id="1b84d-119">클레임이 있으면 <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> 메서드를 호출하여 새로운 클레임 집합을 추가하고, 추가할 클레임 집합이 없으면 권한 부여 정책의 작업이 완료되었음을 권한 부여 인프라에 알리는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-119">If the claims are present, then add the new claim sets by calling the <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29> method and, if no more claim sets are to be added, return `true`, indicating to the authorization infrastructure that the authorization policy has completed its work.</span></span> <span data-ttu-id="1b84d-120">클레임이 없으면 `false`를 반환하는 데, 이는 다른 권한 부여 정책을 통해 클레임 집합을 `EvaluationContext`에 추가하려면 권한 부여 정책을 다시 호출해야 함을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-120">If the claims are not present, return `false`, indicating that the authorization policy should be called again if other authorization policies add more claim sets to the `EvaluationContext`.</span></span>  
  
4.  <span data-ttu-id="1b84d-121">더 복잡한 처리 시나리오에서는 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드의 두 번째 매개 변수를 사용하여 상태 변수를 저장합니다. 이 상태 변수는 이후 각 호출 동안 특정 평가를 목적으로 권한 부여 인프라가 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 메서드에 다시 전달하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-121">In more complex processing scenarios, the second parameter of the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method is used to store a state variable that the authorization infrastructure will pass back during each subsequent call to the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method for a particular evaluation.</span></span>  
  
### <a name="to-specify-a-custom-authorization-policy-through-configuration"></a><span data-ttu-id="1b84d-122">구성을 통해 사용자 지정 권한 부여 정책을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="1b84d-122">To specify a custom authorization policy through configuration</span></span>  
  
1.  <span data-ttu-id="1b84d-123">`policyType` 요소에서 `add` 요소에 있는 `authorizationPolicies` 요소의 `serviceAuthorization` 특성에 사용자 지정 권한 부여 정책 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-123">Specify the type of the custom authorization policy in the `policyType` attribute in the `add` element in the `authorizationPolicies` element in the `serviceAuthorization` element.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>         
            <add policyType="Samples.MyAuthorizationPolicy"  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-specify-a-custom-authorization-policy-through-code"></a><span data-ttu-id="1b84d-124">코드를 통해 사용자 지정 권한 부여 정책을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="1b84d-124">To specify a custom authorization policy through code</span></span>  
  
1.  <span data-ttu-id="1b84d-125"><xref:System.Collections.Generic.List%601>의 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-125">Create a <xref:System.Collections.Generic.List%601> of <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>  
  
2.  <span data-ttu-id="1b84d-126">사용자 지정 권한 부여 정책의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-126">Create an instance of the custom authorization policy.</span></span>  
  
3.  <span data-ttu-id="1b84d-127">권한 부여 정책 인스턴스를 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-127">Add the authorization policy instance to the list.</span></span>  
  
4.  <span data-ttu-id="1b84d-128">각 사용자 지정 권한 부여 정책에 대해 2단계와 3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-128">Repeat steps 2 and 3 for each custom authorization policy.</span></span>  
  
5.  <span data-ttu-id="1b84d-129">읽기 전용 버전의 목록을 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> 속성에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-129">Assign a read-only version of the list to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A> property.</span></span>  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="1b84d-130">예제</span><span class="sxs-lookup"><span data-stu-id="1b84d-130">Example</span></span>  
 <span data-ttu-id="1b84d-131">다음 예제에서는 전체 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b84d-131">The following example shows a complete <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementation.</span></span>  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="1b84d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b84d-132">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="1b84d-133">방법: 클레임 비교</span><span class="sxs-lookup"><span data-stu-id="1b84d-133">How to: Compare Claims</span></span>](../../../../docs/framework/wcf/extending/how-to-compare-claims.md)  
 [<span data-ttu-id="1b84d-134">방법: 서비스에 대한 사용자 지정 권한 부여 관리자 만들기</span><span class="sxs-lookup"><span data-stu-id="1b84d-134">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="1b84d-135">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="1b84d-135">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
