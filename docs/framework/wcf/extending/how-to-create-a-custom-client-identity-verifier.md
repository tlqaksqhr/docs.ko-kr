---
title: '방법: 사용자 지정 클라이언트 ID 검증 도구 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
ms.openlocfilehash: a9f03419c5c924f129b3ec8580ee25693c218715
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804478"
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a><span data-ttu-id="44558-102">방법: 사용자 지정 클라이언트 ID 검증 도구 만들기</span><span class="sxs-lookup"><span data-stu-id="44558-102">How to: Create a Custom Client Identity Verifier</span></span>
<span data-ttu-id="44558-103">*identity* 기능 Windows Communication Foundation (WCF) 클라이언트는 서비스의 예상된 id를 미리 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44558-103">The *identity* feature of Windows Communication Foundation (WCF) enables a client to specify in advance the expected identity of the service.</span></span> <span data-ttu-id="44558-104">서버가 클라이언트에 자신을 인증할 때마다 이 ID와 비교하여 ID가 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="44558-104">Whenever a server authenticates itself to the client, the identity is checked against the expected identity.</span></span> <span data-ttu-id="44558-105">(참조에 대 한 id 및 작동 방법 설명은 [서비스 Id 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).)</span><span class="sxs-lookup"><span data-stu-id="44558-105">(For an explanation of identity and how it works, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).)</span></span>  
  
 <span data-ttu-id="44558-106">필요한 경우 사용자 지정 ID 검증 도구를 사용하여 확인을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44558-106">If needed, the verification can be customized using a custom identity verifier.</span></span> <span data-ttu-id="44558-107">예를 들어, 서비스 ID 확인 검사를 추가로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44558-107">For example, you can perform additional service identity verification checks.</span></span> <span data-ttu-id="44558-108">이 예에서 사용자 지정 ID 검증 도구는 서버에서 반환되는 X.509 인증서에서 추가 클레임을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-108">In this example, the custom identity verifier checks additional claims in the X.509 certificate returned from the server.</span></span> <span data-ttu-id="44558-109">샘플 응용 프로그램에 대 한 참조 [Service Identity 샘플](../../../../docs/framework/wcf/samples/service-identity-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-109">For a sample application, see [Service Identity Sample](../../../../docs/framework/wcf/samples/service-identity-sample.md).</span></span>  
  
### <a name="to-extend-the-endpointidentity-class"></a><span data-ttu-id="44558-110">EndpointIdentity 클래스를 확장하려면</span><span class="sxs-lookup"><span data-stu-id="44558-110">To extend the EndpointIdentity class</span></span>  
  
1.  <span data-ttu-id="44558-111"><xref:System.ServiceModel.EndpointIdentity> 클래스에서 파생되는 새 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-111">Define a new class that derives from the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="44558-112">이 예에서는 확장 이름을 `OrgEndpointIdentity`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-112">This example names the extension `OrgEndpointIdentity`.</span></span>  
  
2.  <span data-ttu-id="44558-113">서비스에서 반환된 보안 토큰의 클레임에 대해 ID 검사를 수행하기 위해 확장 <xref:System.ServiceModel.Security.IdentityVerifier> 클래스에서 사용할 속성과 함께 private 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-113">Add private members along with properties that will be used by the extended <xref:System.ServiceModel.Security.IdentityVerifier> class to perform the identity check against claims in the security token returned from the service.</span></span> <span data-ttu-id="44558-114">이 예에서는 `OrganizationClaim` 속성 하나를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-114">This example defines one property: the `OrganizationClaim` property.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a><span data-ttu-id="44558-115">IdentityVerifier 클래스를 확장하려면</span><span class="sxs-lookup"><span data-stu-id="44558-115">To extend the IdentityVerifier class</span></span>  
  
1.  <span data-ttu-id="44558-116"><xref:System.ServiceModel.Security.IdentityVerifier>에서 파생되는 새 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-116">Define a new class that derives from <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="44558-117">이 예에서는 확장 이름을 `CustomIdentityVerifier`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-117">This example names the extension `CustomIdentityVerifier`.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2.  <span data-ttu-id="44558-118"><xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-118">Override the <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> method.</span></span> <span data-ttu-id="44558-119">이 메서드는 ID 검사의 성공 또는 실패 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-119">The method determines whether the identity check succeeded or failed.</span></span>  
  
3.  <span data-ttu-id="44558-120">`CheckAccess` 메서드는 두 개의 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-120">The `CheckAccess` method has two parameters.</span></span> <span data-ttu-id="44558-121">하나는 <xref:System.ServiceModel.EndpointIdentity> 클래스의 인스턴스이고</span><span class="sxs-lookup"><span data-stu-id="44558-121">The first is an instance of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="44558-122">다른 하나는 <xref:System.IdentityModel.Policy.AuthorizationContext> 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="44558-122">The second is an instance of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
     <span data-ttu-id="44558-123">메서드 구현에서는 <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> 클래스의 <xref:System.IdentityModel.Policy.AuthorizationContext> 속성에서 반환된 클레임의 컬렉션을 검사한 다음 필요한 경우 인증 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-123">In the method implementation, examine the collection of claims returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class, and perform authentication checks as required.</span></span> <span data-ttu-id="44558-124">이 예에서는 먼저 형식이 "고유 이름"인 클레임을 찾은 다음 <xref:System.ServiceModel.EndpointIdentity>의 확장(`OrgEndpointIdentity`)과 이름을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-124">This example begins by finding any claim that is of type "Distinguished Name" and then compares the name to the extension of the <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a><span data-ttu-id="44558-125">TryGetIdentity 메서드를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="44558-125">To implement the TryGetIdentity method</span></span>  
  
1.  <span data-ttu-id="44558-126">클라이언트가 <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> 클래스의 인스턴스를 반환할 수 있는지 여부를 확인하는 <xref:System.ServiceModel.EndpointIdentity> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-126">Implement the <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> method, which determines whether an instance of the <xref:System.ServiceModel.EndpointIdentity> class can be returned by the client.</span></span> <span data-ttu-id="44558-127">구현을 호출 하는 WCF 인프라는 `TryGetIdentity` 메서드는 메시지에서 서비스의 id를 검색 하기 위해 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-127">The WCF infrastructure calls the implementation of the `TryGetIdentity` method first to retrieve the service's identity from the message.</span></span> <span data-ttu-id="44558-128">그런 다음 반환된 `CheckAccess` 및 `EndpointIdentity`와 함께 <xref:System.IdentityModel.Policy.AuthorizationContext> 구현을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-128">Next, the infrastructure calls the `CheckAccess` implementation with the returned `EndpointIdentity` and <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span>  
  
2.  <span data-ttu-id="44558-129">`TryGetIdentity` 메서드에서 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-129">In the `TryGetIdentity` method, put the following code:</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a><span data-ttu-id="44558-130">사용자 지정 바인딩을 구현하고 사용자 지정 IdentityVerifier를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="44558-130">To implement a custom binding and set the custom IdentityVerifier</span></span>  
  
1.  <span data-ttu-id="44558-131"><xref:System.ServiceModel.Channels.Binding> 개체를 반환하는 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44558-131">Create a method that returns a <xref:System.ServiceModel.Channels.Binding> object.</span></span> <span data-ttu-id="44558-132">이 예에서는 먼저 <xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만든 다음 보안 모드를 <xref:System.ServiceModel.SecurityMode.Message>로 설정하고 <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A>을 <xref:System.ServiceModel.MessageCredentialType.None>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-132">This example begins creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class and sets its security mode to <xref:System.ServiceModel.SecurityMode.Message>, and its <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> to <xref:System.ServiceModel.MessageCredentialType.None>.</span></span>  
  
2.  <span data-ttu-id="44558-133"><xref:System.ServiceModel.Channels.BindingElementCollection> 메서드를 사용하여 <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44558-133">Create a <xref:System.ServiceModel.Channels.BindingElementCollection> using the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3.  <span data-ttu-id="44558-134">컬렉션에서 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 반환한 다음 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 변수로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-134">Return the <xref:System.ServiceModel.Channels.SecurityBindingElement> from the collection and cast it to a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variable.</span></span>  
  
4.  <span data-ttu-id="44558-135"><xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> 클래스의 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> 속성을 이전에 만든 `CustomIdentityVerifier` 클래스의 새 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="44558-135">Set the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> property of the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class to a new instance of the `CustomIdentityVerifier` class created previously.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5.  <span data-ttu-id="44558-136">반환된 사용자 지정 바인딩을 사용하여 클라이언트 및 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44558-136">The custom binding that is returned is used to create an instance of the client and class.</span></span> <span data-ttu-id="44558-137">그런 다음 클라이언트는 다음 코드에서와 같이 서비스에 대해 사용자 지정 ID 확인 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44558-137">The client can then perform a custom identity verification check of the service as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="44558-138">예제</span><span class="sxs-lookup"><span data-stu-id="44558-138">Example</span></span>  
 <span data-ttu-id="44558-139">다음 예제에서는 <xref:System.ServiceModel.Security.IdentityVerifier> 클래스의 전체 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44558-139">The following example shows a complete implementation of the <xref:System.ServiceModel.Security.IdentityVerifier> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="44558-140">예제</span><span class="sxs-lookup"><span data-stu-id="44558-140">Example</span></span>  
 <span data-ttu-id="44558-141">다음 예제에서는 <xref:System.ServiceModel.EndpointIdentity> 클래스의 전체 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44558-141">The following example shows a complete implementation of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="44558-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44558-142">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 <xref:System.ServiceModel.EndpointIdentity>  
 <xref:System.ServiceModel.Security.IdentityVerifier>  
 [<span data-ttu-id="44558-143">서비스 ID 샘플</span><span class="sxs-lookup"><span data-stu-id="44558-143">Service Identity Sample</span></span>](../../../../docs/framework/wcf/samples/service-identity-sample.md)  
 [<span data-ttu-id="44558-144">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="44558-144">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [<span data-ttu-id="44558-145">권한 부여 정책</span><span class="sxs-lookup"><span data-stu-id="44558-145">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
