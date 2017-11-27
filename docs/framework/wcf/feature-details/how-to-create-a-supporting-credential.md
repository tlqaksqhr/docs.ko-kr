---
title: "방법: 지원하는 자격 증명 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c140b96fab0227a1563c8c1a511053d8d1ab944
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-supporting-credential"></a><span data-ttu-id="f64d3-102">방법: 지원하는 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="f64d3-102">How to: Create a Supporting Credential</span></span>
<span data-ttu-id="f64d3-103">둘 이상의 자격 증명이 필요한 사용자 지정 보안 체계를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-103">It is possible to have a custom security scheme that requires more than one credential.</span></span> <span data-ttu-id="f64d3-104">예를 들어 서비스는 클라이언트로부터 사용자 이름과 암호뿐 아니라 클라이언트가 18세 이상임을 입증하는 자격 증명을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-104">For example, a service may demand from the client not just a user name and password, but also a credential that proves the client is over the age of 18.</span></span> <span data-ttu-id="f64d3-105">두 번째 자격 증명은는 *지원 자격 증명*합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-105">The second credential is a *supporting credential*.</span></span> <span data-ttu-id="f64d3-106">이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트에 이러한 자격 증명을 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-106">This topic explains how to implement such credentials in an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f64d3-107">지원 자격 증명의 사양은 WS-SecurityPolicy 사양의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-107">The specification for supporting credentials is part of the WS-SecurityPolicy specification.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="f64d3-108">[웹 서비스 보안 사양](http://go.microsoft.com/fwlink/?LinkId=88537)합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-108"> [Web Services Security Specifications](http://go.microsoft.com/fwlink/?LinkId=88537).</span></span>  
  
## <a name="supporting-tokens"></a><span data-ttu-id="f64d3-109">Supporting Tokens</span><span class="sxs-lookup"><span data-stu-id="f64d3-109">Supporting Tokens</span></span>  
 <span data-ttu-id="f64d3-110">간단히 말해서 사용 하는 경우 메시지 보안을 한 *기본 자격 증명* (예: X.509 인증서 또는 Kerberos 티켓) 메시지 보안을 위해 항상 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-110">In brief, when you use message security, a *primary credential* is always used to secure the message (for example, an X.509 certificate or a Kerberos ticket).</span></span>  
  
 <span data-ttu-id="f64d3-111">보안 바인딩에서 사용 하 여 사양에 정의 된 대로 *토큰* 를 메시지 교환의 보안을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-111">As defined by the specification, a security binding uses *tokens* to secure the message exchange.</span></span> <span data-ttu-id="f64d3-112">A *토큰* 보안 자격 증명의 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-112">A *token* is a representation of a security credential.</span></span>  
  
 <span data-ttu-id="f64d3-113">보안 바인딩은 보안 바인딩 정책에 식별된 기본 토큰을 사용하여 서명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-113">The security binding uses a primary token identified in the security binding policy to create a signature.</span></span> <span data-ttu-id="f64d3-114">이 서명은 라고는 *메시지 서명에*합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-114">This signature is referred to as the *message signature*.</span></span>  
  
 <span data-ttu-id="f64d3-115">추가 토큰을 지정하여 메시지 서명과 연결된 토큰이 제공하는 클레임을 증대시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-115">Additional tokens can be specified to augment the claims provided by the token associated with the message signature.</span></span>  
  
## <a name="endorsing-signing-and-encrypting"></a><span data-ttu-id="f64d3-116">보증, 서명 및 암호화</span><span class="sxs-lookup"><span data-stu-id="f64d3-116">Endorsing, Signing, and Encrypting</span></span>  
 <span data-ttu-id="f64d3-117">지원 자격 증명으로 인해 한 *지원 토큰* 메시지 내부에서 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-117">A supporting credential results in a *supporting token* transmitted inside the message.</span></span> <span data-ttu-id="f64d3-118">WS-SecurityPolicy 사양은 다음 표에 설명된 것처럼 지원 토큰을 메시지에 첨부하는 네 가지 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-118">The WS-SecurityPolicy specification defines four ways to attach a supporting token to the message, as described in the following table.</span></span>  
  
|<span data-ttu-id="f64d3-119">용도</span><span class="sxs-lookup"><span data-stu-id="f64d3-119">Purpose</span></span>|<span data-ttu-id="f64d3-120">설명</span><span class="sxs-lookup"><span data-stu-id="f64d3-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f64d3-121">서명</span><span class="sxs-lookup"><span data-stu-id="f64d3-121">Signed</span></span>|<span data-ttu-id="f64d3-122">지원 토큰은 보안 헤더에 포함되고 메시지 서명으로 서명됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-122">The supporting token is included in the security header and is signed by the message signature.</span></span>|  
|<span data-ttu-id="f64d3-123">보증</span><span class="sxs-lookup"><span data-stu-id="f64d3-123">Endorsing</span></span>|<span data-ttu-id="f64d3-124">*보증 토큰* 메시지 서명에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-124">An *endorsing token* signs the message signature.</span></span>|  
|<span data-ttu-id="f64d3-125">서명 및 보증</span><span class="sxs-lookup"><span data-stu-id="f64d3-125">Signed and Endorsing</span></span>|<span data-ttu-id="f64d3-126">서명된 보증 토큰은 메시지 서명에서 생성된 `ds:Signature` 요소에 서명하고 그 자체가 해당 메시지 서명으로 서명됩니다. 즉, 두 토큰(메시지 서명에 사용된 토큰과 서명된 보증 토큰)이 서로에 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-126">Signed, endorsing tokens sign the entire `ds:Signature` element produced from the message signature and are themselves signed by that message signature; that is, both tokens (the token used for the message signature and the signed endorsing token) sign each other.</span></span>|  
|<span data-ttu-id="f64d3-127">서명 및 암호화</span><span class="sxs-lookup"><span data-stu-id="f64d3-127">Signed and Encrypting</span></span>|<span data-ttu-id="f64d3-128">서명 및 암호화된 지원 토큰은 `wsse:SecurityHeader`에 나타날 때 암호화되는 서명된 지원 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-128">Signed, encrypted supporting tokens are signed supporting tokens that are also encrypted when they appear in the `wsse:SecurityHeader`.</span></span>|  
  
## <a name="programming-supporting-credentials"></a><span data-ttu-id="f64d3-129">지원 자격 증명 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f64d3-129">Programming Supporting Credentials</span></span>  
 <span data-ttu-id="f64d3-130">지원 토큰을 만들어야 합니다를 사용 하는 서비스를 만들려면는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-130">To create a service that uses supporting tokens you must create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span> <span data-ttu-id="f64d3-131">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [하는 방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span><span class="sxs-lookup"><span data-stu-id="f64d3-131">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).)</span></span>  
  
 <span data-ttu-id="f64d3-132">사용자 지정 바인딩을 만들 때의 첫 단계는 다음 세 가지 형식 중 하나일 수 있는 보안 바인딩 요소를 만드는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-132">The first step when creating a custom binding is to create a security binding element, which can be one of three types:</span></span>  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="f64d3-133">모든 클래스는 다음 네 가지 관련 속성을 포함하는 <xref:System.ServiceModel.Channels.SecurityBindingElement>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-133">All classes inherit from the <xref:System.ServiceModel.Channels.SecurityBindingElement>, which includes four relevant properties:</span></span>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### <a name="scopes"></a><span data-ttu-id="f64d3-134">범위</span><span class="sxs-lookup"><span data-stu-id="f64d3-134">Scopes</span></span>  
 <span data-ttu-id="f64d3-135">지원 자격 증명에 대한 두 가지 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-135">Two scopes exist for supporting credentials:</span></span>  
  
-   <span data-ttu-id="f64d3-136">*끝점 지원 토큰* 끝점의 모든 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-136">*Endpoint supporting tokens* support all operations of an endpoint.</span></span> <span data-ttu-id="f64d3-137">즉, 끝점 작업을 호출할 때마다 지원 토큰이 나타내는 자격 증명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-137">That is, the credential that the supporting token represents can be used whenever any endpoint operations are invoked.</span></span>  
  
-   <span data-ttu-id="f64d3-138">*작업 지원 토큰* 특정 끝점 작업만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-138">*Operation supporting tokens* support only a specific endpoint operation.</span></span>  
  
 <span data-ttu-id="f64d3-139">속성 이름이 나타내는 것처럼 지원 자격 증명은 필수 또는 옵션일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-139">As indicated by the property names, supporting credentials can be either required or optional.</span></span> <span data-ttu-id="f64d3-140">즉, 지원 자격 증명이 있으면 필요하지 않아도 사용되지만 없어도 인증이 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-140">That is, if the supporting credential is used if it is present, although it is not necessary, but the authentication will not fail if it is not present.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="f64d3-141">절차</span><span class="sxs-lookup"><span data-stu-id="f64d3-141">Procedures</span></span>  
  
#### <a name="to-create-a-custom-binding-that-includes-supporting-credentials"></a><span data-ttu-id="f64d3-142">지원 자격 증명을 포함하는 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f64d3-142">To create a custom binding that includes supporting credentials</span></span>  
  
1.  <span data-ttu-id="f64d3-143">보안 바인딩 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-143">Create a security binding element.</span></span> <span data-ttu-id="f64d3-144">아래 예제에서는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 인증 모드로 `UserNameForCertificate`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-144">The example below creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> with the `UserNameForCertificate` authentication mode.</span></span> <span data-ttu-id="f64d3-145"><xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> 메서드를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f64d3-145">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> method.</span></span>  
  
2.  <span data-ttu-id="f64d3-146">해당 속성(`Endorsing`, `Signed`, `SignedEncrypted` 또는 `SignedEndorsed`)에 의해 반환된 형식 컬렉션에 지원 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-146">Add the supporting parameter to the collection of types returned by the appropriate property (`Endorsing`, `Signed`, `SignedEncrypted`, or `SignedEndorsed`).</span></span> <span data-ttu-id="f64d3-147"><xref:System.ServiceModel.Security.Tokens> 네임스페이스의 형식에는 <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters> 같은 자주 사용되는 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-147">The types in the <xref:System.ServiceModel.Security.Tokens> namespace include commonly used types, such as the <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f64d3-148">예제</span><span class="sxs-lookup"><span data-stu-id="f64d3-148">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f64d3-149">설명</span><span class="sxs-lookup"><span data-stu-id="f64d3-149">Description</span></span>  
 <span data-ttu-id="f64d3-150">다음 예제에서는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>의 인스턴스를 만들고 <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> 클래스의 인스턴스를 반환된 Endorsing 속성 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f64d3-150">The following example creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and adds an instance of the <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> class to the collection the Endorsing property returned.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f64d3-151">코드</span><span class="sxs-lookup"><span data-stu-id="f64d3-151">Code</span></span>  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f64d3-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f64d3-152">See Also</span></span>  
 [<span data-ttu-id="f64d3-153">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f64d3-153">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
