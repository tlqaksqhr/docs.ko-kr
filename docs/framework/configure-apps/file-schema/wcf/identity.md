---
title: '&lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 1fc47b9595f409cf375dc75f2bf43e83f58491df
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071294"
---
# <a name="ltidentitygt"></a><span data-ttu-id="5c20c-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="5c20c-102">&lt;identity&gt;</span></span>
<span data-ttu-id="5c20c-103">ID 요소를 사용하면 클라이언트 개발자가 서비스에 필요한 ID를 디자인 타임에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="5c20c-104">클라이언트와 서비스 간의 핸드셰이크 프로세스에서 Windows Communication Foundation (WCF) 인프라는 id가 확인 하는 일치 하는 예상 되는 서비스 항목이 요소의 값 및 인증 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-104">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="5c20c-105">자세한 내용은 참조 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="5c20c-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5c20c-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c20c-107">\<client></span><span class="sxs-lookup"><span data-stu-id="5c20c-107">\<client></span></span>  
<span data-ttu-id="5c20c-108">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="5c20c-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c20c-109">구문</span><span class="sxs-lookup"><span data-stu-id="5c20c-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c20c-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5c20c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5c20c-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c20c-112">특성</span><span class="sxs-lookup"><span data-stu-id="5c20c-112">Attributes</span></span>  
 <span data-ttu-id="5c20c-113">없음</span><span class="sxs-lookup"><span data-stu-id="5c20c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c20c-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5c20c-114">Child Elements</span></span>  
  
|<span data-ttu-id="5c20c-115">요소</span><span class="sxs-lookup"><span data-stu-id="5c20c-115">Element</span></span>|<span data-ttu-id="5c20c-116">설명</span><span class="sxs-lookup"><span data-stu-id="5c20c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c20c-117">certificate</span><span class="sxs-lookup"><span data-stu-id="5c20c-117">certificate</span></span>|<span data-ttu-id="5c20c-118">X.509 인증서의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="5c20c-119">이 요소는 <xref:System.ServiceModel.Configuration.CertificateElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="5c20c-120">이 요소에는 이 인증서로 인코딩된 값을 지정하는 문자열인 `encodedValue` 특성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="5c20c-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="5c20c-121">certificateReference</span></span>|<span data-ttu-id="5c20c-122">X.509 인증서 유효성 검사의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="5c20c-123">이 요소는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="5c20c-124">dns</span><span class="sxs-lookup"><span data-stu-id="5c20c-124">dns</span></span>|<span data-ttu-id="5c20c-125">서비스를 인증하는 데 사용되는 X.509 인증서의 DNS를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="5c20c-126">이 요소에는 문자열인 `value` 특성이 포함되며 실제 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="5c20c-127">rsa</span><span class="sxs-lookup"><span data-stu-id="5c20c-127">rsa</span></span>|<span data-ttu-id="5c20c-128">클라이언트에 서비스를 인증하는 데 사용되는 X.509 인증서의 RSA 필드 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="5c20c-129">이 요소에는 문자열인 `value` 특성이 포함되며 실제 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="5c20c-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="5c20c-130">servicePrincipalName</span></span>|<span data-ttu-id="5c20c-131">서비스의 인스턴스를 고유하게 식별하기 위해 클라이언트에서 사용하는 사용자 이름인 SPN(서버 사용자 이름) ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="5c20c-132">이 요소에는 문자열인 `value` 특성이 포함되며 실제 사용자 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="5c20c-133">이 요소는 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="5c20c-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="5c20c-134">userPrincipalName</span></span>|<span data-ttu-id="5c20c-135">네트워크 사용자의 로그온 이름 형식인 UPN(User Principal Name) ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="5c20c-136">사용자 계정 이름 뒤의 Active Directory에 사용 되는 사용자 개체 이름으로 구성 됩니다는 at 기호 (\@) 한 다음, 일반적으로 부모 도메인 Domain Name System.</span><span class="sxs-lookup"><span data-stu-id="5c20c-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="5c20c-137">예를 들어, Fabrikam.com 도메인 트리에 있는 Jeff 사용자 계정 이름 해야할 [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="5c20c-138">이 요소에는 문자열인 `value` 특성이 포함되며 실제 사용자 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-138">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="5c20c-139">이 요소는 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-139">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c20c-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5c20c-140">Parent Elements</span></span>  
  
|<span data-ttu-id="5c20c-141">요소</span><span class="sxs-lookup"><span data-stu-id="5c20c-141">Element</span></span>|<span data-ttu-id="5c20c-142">설명</span><span class="sxs-lookup"><span data-stu-id="5c20c-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c20c-143">\<custom></span><span class="sxs-lookup"><span data-stu-id="5c20c-143">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="5c20c-144">netPeerTcpBinding에 대한 사용자 지정 피어 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-144">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="5c20c-145">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="5c20c-145">\<endpoint></span></span>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="5c20c-146">다양한 형식의 끝점을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-146">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="5c20c-147">\<issuer></span><span class="sxs-lookup"><span data-stu-id="5c20c-147">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="5c20c-148">페더레이션 서비스에 대한 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-148">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="5c20c-149">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="5c20c-149">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="5c20c-150">페더레이션 서비스의 STS(보안 토큰 서비스)에 대한 메타데이터 끝점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-150">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="5c20c-151">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="5c20c-151">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="5c20c-152">사용자 지정 바인딩에서 발급된 토큰에 대한 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-152">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="5c20c-153">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="5c20c-153">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="5c20c-154">로컬 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c20c-154">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c20c-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c20c-155">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="5c20c-156">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="5c20c-156">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="5c20c-157">끝점: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="5c20c-157">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
