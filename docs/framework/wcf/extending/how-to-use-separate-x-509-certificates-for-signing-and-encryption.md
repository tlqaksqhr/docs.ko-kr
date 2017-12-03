---
title: "방법: 서명 및 암호화에 별도의 X.509 인증서 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, extensibility
- ClientCredentials class
- ClientCredentialsSecurityTokenManager class
ms.assetid: 0b06ce4e-7835-4d82-8baf-d525c71a0e49
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 312a4b854cb527e63d6866247d4147720ce0710c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-separate-x509-certificates-for-signing-and-encryption"></a><span data-ttu-id="28068-102">방법: 서명 및 암호화에 별도의 X.509 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="28068-102">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>
<span data-ttu-id="28068-103">이 항목에서는 클라이언트와 서비스에서 메시지 서명 및 암호화에 서로 다른 인증서를 사용하기 위한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 구성 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-103">This topic shows how to configure [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to use different certificates for message signing and encryption on both the client and service.</span></span>  
  
 <span data-ttu-id="28068-104">서명 및 암호화에 별도의 인증서를 사용하려면, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 여러 클라이언트 또는 서비스 인증서를 설정하기 위한 API가 제공되지 않으므로 사용자 지정 클라이언트나 서비스 자격 증명(또는 모두)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-104">To enable separate certificates to be used for signing and encryption, a custom client or service credentials (or both) must be created because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not provide an API to set multiple client or service certificates.</span></span> <span data-ttu-id="28068-105">또한 여러 개의 인증서 정보를 활용하고 지정된 키 사용과 메시지 방향에 적합한 보안 토큰 공급자를 만들기 위해 보안 토큰 관리자도 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-105">Additionally, a security token manager must be provided to leverage the multiple certificates' information and to create an appropriate security token provider for specified key usage and message direction.</span></span>  
  
 <span data-ttu-id="28068-106">다음 다이어그램에서는 사용되는 주 클래스, 상속하는 클래스(위쪽 화살표로 표시), 특정 메서드 및 속성의 반환 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28068-106">The following diagram shows the main classes used, the classes they inherit from (shown by an upward-pointing arrow), and the return types of certain methods and properties.</span></span>  
  
-   <span data-ttu-id="28068-107">`MyClientCredentials`는 <xref:System.ServiceModel.Description.ClientCredentials>의 사용자 지정 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="28068-107">`MyClientCredentials` is a custom implementation of <xref:System.ServiceModel.Description.ClientCredentials>.</span></span>  
  
    -   <span data-ttu-id="28068-108">다이어그램에 표시된 속성은 모두 <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-108">Its properties shown in the diagram all return instances of <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.</span></span>  
  
    -   <span data-ttu-id="28068-109">메서드 <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A>는 `MyClientCredentialsSecurityTokenManager`인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-109">Its method <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> returns an instance of `MyClientCredentialsSecurityTokenManager`.</span></span>  
  
-   <span data-ttu-id="28068-110">`MyClientCredentialsSecurityTokenManager`는 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>의 사용자 지정 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="28068-110">`MyClientCredentialsSecurityTokenManager` is a custom implementation of <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.</span></span>  
  
    -   <span data-ttu-id="28068-111">메서드 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A>는 <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider>인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-111">Its method <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> returns an instance of <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider>.</span></span>  
  
 <span data-ttu-id="28068-112">![클라이언트 자격 증명을 사용 하는 방법을 보여 주는 차트](../../../../docs/framework/wcf/extending/media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span><span class="sxs-lookup"><span data-stu-id="28068-112">![Chart showing how client credentials are used](../../../../docs/framework/wcf/extending/media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="28068-113">사용자 지정 자격 증명 참조 [연습: 사용자 지정 클라이언트 만들기 및 서비스 자격 증명](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-113"> custom credentials, see [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="28068-114">또한 사용자 지정 ID 검증 도구를 만들고 사용자 지정 바인딩의 보안 바인딩 요소에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-114">In addition, you must create a custom identity verifier, and link it to a security binding element in a custom binding.</span></span> <span data-ttu-id="28068-115">그리고 기본 자격 증명 대신 사용자 지정 자격 증명을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-115">You must also use the custom credentials instead of the default credentials.</span></span>  
  
 <span data-ttu-id="28068-116">다음 다이어그램에서는 사용자 지정 바인딩에 관련된 클래스 및 사용자 지정 ID 검증 도구를 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28068-116">The following diagram shows the classes involved in the custom binding, and how the custom identity verifier is linked.</span></span> <span data-ttu-id="28068-117">여러 바인딩 요소가 관련되어 있으며 이들 요소는 모두 <xref:System.ServiceModel.Channels.BindingElement>에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-117">There are several binding elements involved, all of which inherit from <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="28068-118"><xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>에는 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> 속성이 있습니다. 이 속성은 <xref:System.ServiceModel.Security.IdentityVerifier>가 사용자 지정되는 `MyIdentityVerifier`인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-118">The <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> has the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> property, which returns an instance of <xref:System.ServiceModel.Security.IdentityVerifier>, from which `MyIdentityVerifier` is customized.</span></span>  
  
 <span data-ttu-id="28068-119">![사용자 지정 바인딩 요소를 보여 주는 차트](../../../../docs/framework/wcf/extending/media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span><span class="sxs-lookup"><span data-stu-id="28068-119">![Chart showing a custom binding element](../../../../docs/framework/wcf/extending/media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="28068-120">만드는 사용자 지정 id 검증 도구를 참조 하는 방법: [하는 방법: 사용자 지정 클라이언트 Id 검증 도구 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-120"> creating a custom identity verifier, see How to: [How to: Create a Custom Client Identity Verifier](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md).</span></span>  
  
### <a name="to-use-separate-certificates-for-signing-and-encryption"></a><span data-ttu-id="28068-121">서명 및 암호화에 별도의 인증서를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="28068-121">To use separate certificates for signing and encryption</span></span>  
  
1.  <span data-ttu-id="28068-122"><xref:System.ServiceModel.Description.ClientCredentials> 클래스에서 상속되는 새로운 클라이언트 자격 증명 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-122">Define a new client credentials class that inherits from the <xref:System.ServiceModel.Description.ClientCredentials> class.</span></span> <span data-ttu-id="28068-123">여러 인증서 지정을 허용하는 네 가지 새 속성인 `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate``ServiceEncryptingCertificate`및 를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-123">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="28068-124">또한 <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> 메서드를 재정의하여 다음 단계에 정의된 사용자 지정된 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-124">Also override the <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>  
  
     [!code-csharp[c_FourCerts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#1)]
     [!code-vb[c_FourCerts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#1)]  
  
2.  <span data-ttu-id="28068-125"><xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> 클래스에서 상속되는 새로운 클라이언트 보안 토큰 관리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-125">Define a new client security token manager that inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="28068-126">올바른 보안 토큰 공급자를 만들기 위해 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-126">Override the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider.</span></span> <span data-ttu-id="28068-127">메시지 방향과 키 사용은 `requirement` 매개 변수(<xref:System.IdentityModel.Selectors.SecurityTokenRequirement>)를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="28068-127">The `requirement` parameter (a <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>) provides the message direction and key usage.</span></span>  
  
     [!code-csharp[c_FourCerts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#2)]
     [!code-vb[c_FourCerts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#2)]  
  
3.  <span data-ttu-id="28068-128"><xref:System.ServiceModel.Description.ServiceCredentials> 클래스에서 상속되는 새로운 서비스 자격 증명 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-128">Define a new service credentials class that inherits from the <xref:System.ServiceModel.Description.ServiceCredentials> class.</span></span> <span data-ttu-id="28068-129">여러 인증서 지정을 허용하는 네 가지 새 속성인 `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate``ServiceEncryptingCertificate`및 를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-129">Implement four new properties to allow multiple certificates specification: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate`, and `ServiceEncryptingCertificate`.</span></span> <span data-ttu-id="28068-130">또한 <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> 메서드를 재정의하여 다음 단계에 정의된 사용자 지정된 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-130">Also override the <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> method to return an instance of the customized <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class that is defined in the next step.</span></span>  
  
     [!code-csharp[c_FourCerts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#3)]
     [!code-vb[c_FourCerts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#3)]  
  
4.  <span data-ttu-id="28068-131"><xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> 클래스에서 상속되는 새로운 서비스 보안 토큰 관리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-131">Define a new service security token manager that inherits from the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class.</span></span> <span data-ttu-id="28068-132">전달된 메시지 방향과 키 사용에 적합한 보안 토큰 공급자를 만들기 위해 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-132">Override the <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> method to create an appropriate security token provider given the passed-in message direction and key usage.</span></span>  
  
     [!code-csharp[c_FourCerts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#4)]
     [!code-vb[c_FourCerts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#4)]  
  
### <a name="to-use-multiple-certificates-on-the-client"></a><span data-ttu-id="28068-133">클라이언트에 여러 인증서를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="28068-133">To use multiple certificates on the client</span></span>  
  
1.  <span data-ttu-id="28068-134">사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28068-134">Create a custom binding.</span></span> <span data-ttu-id="28068-135">보안 바인딩 요소는 요청 및 응답에 서로 다른 보안 토큰 공급자를 사용할 수 있도록 이중 모드로 작동되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-135">The security binding element must operate in duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="28068-136">이를 위한 한 가지 방법은 다음 코드에서와 같이 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>를 사용하거나 이중 가능 전송을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="28068-136">One way to do this is to use a duplex-capable transport or to use the <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="28068-137">다음 단계에 정의된 사용자 지정된 <xref:System.ServiceModel.Security.IdentityVerifier>를 보안 바인딩 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-137">Link the customized <xref:System.ServiceModel.Security.IdentityVerifier> which is defined in the next step to the security binding element.</span></span> <span data-ttu-id="28068-138">기본 클라이언트 자격 증명을 이전에 만든 사용자 지정된 클라이언트 자격 증명으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="28068-138">Replace the default client credentials with the customized client credentials previously created.</span></span>  
  
     [!code-csharp[c_FourCerts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#5)]
     [!code-vb[c_FourCerts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#5)]  
  
2.  <span data-ttu-id="28068-139">사용자 지정 <xref:System.ServiceModel.Security.IdentityVerifier>를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-139">Define a custom <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="28068-140">요청을 암호화하고 응답을 서명하는 데 서로 다른 인증서가 사용되므로 서비스에는 여러 개의 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28068-140">The service has multiple identities because different certificates are used to encrypt the request and to sign the response.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28068-141">다음 샘플에 제공된 사용자 지정 ID 검증 도구는 끝점 ID 확인을 수행하지 않는 데모용이므로,</span><span class="sxs-lookup"><span data-stu-id="28068-141">In the following sample, the provided custom identity verifier does not perform any endpoint identity checking for demonstration purposes.</span></span> <span data-ttu-id="28068-142">프로덕션 코드에 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="28068-142">This is not recommended practice for production code.</span></span>  
  
     [!code-csharp[c_FourCerts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#6)]
     [!code-vb[c_FourCerts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#6)]  
  
### <a name="to-use-multiple-certificates-on-the-service"></a><span data-ttu-id="28068-143">서비스에 여러 인증서를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="28068-143">To use multiple certificates on the service</span></span>  
  
1.  <span data-ttu-id="28068-144">사용자 지정 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="28068-144">Create a custom binding.</span></span> <span data-ttu-id="28068-145">보안 바인딩 요소는 요청 및 응답에 서로 다른 보안 토큰 공급자를 사용할 수 있도록 이중 모드로 작동되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-145">The security binding element must operate in a duplex mode to allow different security token providers to be present for requests and responses.</span></span> <span data-ttu-id="28068-146">클라이언트와 마찬가지로, 다음 코드에서와 같이 <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>를 사용하거나 이중 가능 전송을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28068-146">As with the client, use a duplex-capable transport or use <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> as shown in the following code.</span></span> <span data-ttu-id="28068-147">기본 서비스 자격 증명을 이전에 만든 사용자 지정된 서비스 자격 증명으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="28068-147">Replace the default service credentials with the customized service credentials previously created.</span></span>  
  
     [!code-csharp[c_FourCerts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#7)]
     [!code-vb[c_FourCerts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="28068-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28068-148">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
 <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>  
 <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>  
 <xref:System.ServiceModel.Security.IdentityVerifier>  
 [<span data-ttu-id="28068-149">연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="28068-149">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
