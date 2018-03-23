---
title: '방법: X.509 인증서에 대 한 암호화 공급자를 변경&#39;s 개인 키'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e7dea9834b654be0b86155e18524053efa4b778b
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificate39s-private-key"></a><span data-ttu-id="0ca71-102">방법: X.509 인증서에 대 한 암호화 공급자를 변경&#39;s 개인 키</span><span class="sxs-lookup"><span data-stu-id="0ca71-102">How to: Change the Cryptographic Provider for an X.509 Certificate&#39;s Private Key</span></span>
<span data-ttu-id="0ca71-103">이 항목에서는 X.509 인증서의 개인 키를 제공하는 데 사용되는 암호화 공급자를 변경하는 방법 및 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 보안 프레임워크에 공급자를 통합하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-103">This topic shows how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security framework.</span></span> <span data-ttu-id="0ca71-104">인증서를 사용 하는 방법에 대 한 자세한 내용은 참조 [인증서 작업](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-104">For more information about using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="0ca71-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 프레임 워크에 설명 된 대로 새 보안 토큰 형식을 적용 하는 방법 제공 [하는 방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-105">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework provides a way to introduce new security token types as described in [How to: Create a Custom Token](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).</span></span> <span data-ttu-id="0ca71-106">사용자 지정 토큰을 사용하여 시스템에서 제공되는 기존 형식을 대체할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-106">It is also possible to use a custom token to replace existing system-provided token types.</span></span>  
  
 <span data-ttu-id="0ca71-107">이 항목에서는 시스템에서 제공되는 X.509 보안 토큰을 인증서 개인 키의 다른 구현을 제공하는 사용자 지정 X.509 토큰으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-107">In this topic, the system-provided X.509 security token is replaced by a custom X.509 token that provides a different implementation for the certificate private key.</span></span> <span data-ttu-id="0ca71-108">기본 Windows 암호화 공급자와 다른 암호화 공급자에서 실제 개인 키를 제공하는 경우에 유용한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-108">This is useful in scenarios where the actual private key is provided by a different cryptographic provider than the default Windows cryptographic provider.</span></span> <span data-ttu-id="0ca71-109">대체 암호화 공급자의 한 예로는 개인 키와 관련된 모든 암호화 작업을 수행하면서 개인 키를 메모리에 저장하지는 않는 방식으로 시스템 보안을 향상시키는 하드웨어 보안 모듈이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-109">One example of an alternative cryptographic provider is a hardware security module that performs all private key related cryptographic operations, and does not store the private keys in memory, thus improving security of the system.</span></span>  
  
 <span data-ttu-id="0ca71-110">다음 예는 데모용으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-110">The following example is for demonstration purposes only.</span></span> <span data-ttu-id="0ca71-111">여기서는 기본 Windows 암호화 공급자를 대체하지 않지만 그런 공급자를 통합하는 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-111">It does not replace the default Windows cryptographic provider, but it shows where such a provider could be integrated.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="0ca71-112">절차</span><span class="sxs-lookup"><span data-stu-id="0ca71-112">Procedures</span></span>  
 <span data-ttu-id="0ca71-113">보안 키가 연결된 모든 보안 토큰에서는 보안 토큰 인스턴스로부터 키 컬렉션을 반환하는 <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A> 속성을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-113">Every security token that has an associated security key or keys must implement the <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A> property, which returns a collection of keys from the security token instance.</span></span> <span data-ttu-id="0ca71-114">토큰이 X.509 보안 토큰인 경우 컬렉션에는 인증서와 연결된 공개 및 개인 키를 모두 나타내는 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> 클래스의 단일 인스턴스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-114">If the token is an X.509 security token, the collection contains a single instance of the <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> class that represents both public and private keys associated with the certificate.</span></span> <span data-ttu-id="0ca71-115">인증서의 키를 제공하는 데 사용되는 기본 암호화 공급자를 대체하려면 이 클래스의 새 구현을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-115">To replace the default cryptographic provider used to provide the certificate's keys, create a new implementation of this class.</span></span>  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a><span data-ttu-id="0ca71-116">사용자 지정 X.509 비대칭 키를 만들려면</span><span class="sxs-lookup"><span data-stu-id="0ca71-116">To create a custom X.509 asymmetric key</span></span>  
  
1.  <span data-ttu-id="0ca71-117"><xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> 클래스에서 파생된 새 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-117">Define a new class derived from the <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> class.</span></span>  
  
2.  <span data-ttu-id="0ca71-118"><xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A> 읽기 전용 속성을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-118">Override the <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A> read-only property.</span></span> <span data-ttu-id="0ca71-119">이 속성에서는 인증서의 공개/개인 키 쌍의 실제 키 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-119">This property returns the actual key size of the certificate's public/private key pair.</span></span>  
  
3.  <span data-ttu-id="0ca71-120"><xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-120">Override the <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> method.</span></span> <span data-ttu-id="0ca71-121">이 메서드는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 프레임워크에서 대칭 키를 인증서의 개인 키로 해독하기 위해 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-121">This method is called by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework to decrypt a symmetric key with the certificate's private key.</span></span> <span data-ttu-id="0ca71-122">키는 이전에 인증서의 공개 키로 암호화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-122">(The key was previously encrypted with the certificate's public key.)</span></span>  
  
4.  <span data-ttu-id="0ca71-123"><xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-123">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> method.</span></span> <span data-ttu-id="0ca71-124">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 프레임워크에서 이 메서드는 메서드로 전달되는 매개 변수에 따라 인증서의 개인 또는 공개 키의 암호화 공급자를 나타내는 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스의 인스턴스를 가져오기 위해 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-124">This method is called by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework to obtain an instance of the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class that represents the cryptographic provider for either the certificate's private or public key, depending on the parameters passed to the method.</span></span>  
  
5.  <span data-ttu-id="0ca71-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-125">Optional.</span></span> <span data-ttu-id="0ca71-126"><xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-126">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A> method.</span></span> <span data-ttu-id="0ca71-127">다른 <xref:System.Security.Cryptography.HashAlgorithm> 클래스 구현이 필요한 경우 이 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-127">Override this method if a different implementation of the <xref:System.Security.Cryptography.HashAlgorithm> class is required.</span></span>  
  
6.  <span data-ttu-id="0ca71-128"><xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-128">Override the <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A> method.</span></span> <span data-ttu-id="0ca71-129">이 메서드에서는 인증서의 개인 키와 연결된 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-129">This method returns an instance of the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> class that is associated with the certificate's private key.</span></span>  
  
7.  <span data-ttu-id="0ca71-130"><xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-130">Override the <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A> method.</span></span> <span data-ttu-id="0ca71-131">이 메서드는 보안 키 구현에서 특정 암호화 알고리즘이 지원되는지 여부를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-131">This method is used to indicate whether a particular cryptographic algorithm is supported by the security key implementation.</span></span>  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 <span data-ttu-id="0ca71-132">다음 절차에서는 이전 절차에서 만든 사용자 지정 X.509 비대칭 보안 키 구현을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 프레임워크에 통합하여 시스템에서 제공되는 X.509 보안 토큰을 대체하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-132">The following procedure shows how to integrate the custom X.509 asymmetric security key implementation created in the preceding procedure with the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework in order to replace the system-provided X.509 security token.</span></span>  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a><span data-ttu-id="0ca71-133">시스템에서 제공되는 X.509 보안 토큰을 사용자 지정 X.509 비대칭 보안 키 토큰으로 대체하려면</span><span class="sxs-lookup"><span data-stu-id="0ca71-133">To replace the system-provided X.509 security token with a custom X.509 asymmetric security key token</span></span>  
  
1.  <span data-ttu-id="0ca71-134">다음 예와 같이 시스템에서 제공되는 보안 키 대신 사용자 지정 X.509 비대칭 보안 키를 반환하는 사용자 지정 X.509 보안 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-134">Create a custom X.509 security token that returns the custom X.509 asymmetric security key instead of the system-provided security key, as shown in the following example.</span></span> <span data-ttu-id="0ca71-135">사용자 지정 보안 토큰에 대 한 자세한 내용은 참조 [하는 방법: 사용자 지정 토큰 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-135">For more information about custom security tokens, see [How to: Create a Custom Token](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2.  <span data-ttu-id="0ca71-136">예와 같이 사용자 지정 X.509 보안 토큰을 반환하는 사용자 지정 보안 토큰 공급자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-136">Create a custom security token provider that returns a custom X.509 security token, as shown in the example.</span></span> <span data-ttu-id="0ca71-137">사용자 지정 보안 토큰 공급자에 대 한 자세한 내용은 참조 [하는 방법: 사용자 지정 보안 토큰 공급자 만들기](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-137">For more information about custom security token providers, see [How to: Create a Custom Security Token Provider](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3.  <span data-ttu-id="0ca71-138">게시자 쪽에서 사용자 지정 보안 키를 사용해야 하는 경우에는 다음 예와 같이 사용자 지정 클라이언트 보안 토큰 관리자 및 사용자 지정 클라이언트 자격 증명 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-138">If the custom security key needs to be used on the initiator side, create a custom client security token manager and custom client credentials classes, as shown in the following example.</span></span> <span data-ttu-id="0ca71-139">사용자 지정 클라이언트 자격 증명 및 클라이언트 보안 토큰 관리자에 대 한 자세한 내용은 참조 [연습: 사용자 지정 클라이언트 만들기 및 서비스 자격 증명](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-139">For more information about custom client credentials and client security token managers, see [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4.  <span data-ttu-id="0ca71-140">받는 사람 쪽에서 사용자 지정 보안 키를 사용해야 하는 경우에는 다음 예와 같이 사용자 지정 서비스 보안 토큰 관리자 및 사용자 지정 서비스 자격 증명 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-140">If the custom security key needs to be used on the recipient side, create a custom service security token manager and custom service credentials, as shown in the following example.</span></span> <span data-ttu-id="0ca71-141">사용자 지정 서비스 자격 증명 및 서비스 보안 토큰 관리자에 대 한 자세한 내용은 참조 [연습: 사용자 지정 클라이언트 만들기 및 서비스 자격 증명](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca71-141">For more information about custom service credentials and service security token managers, see [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="0ca71-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ca71-142">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>  
 <xref:System.IdentityModel.Tokens.SecurityKey>  
 <xref:System.Security.Cryptography.AsymmetricAlgorithm>  
 <xref:System.Security.Cryptography.HashAlgorithm>  
 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>  
 [<span data-ttu-id="0ca71-143">연습: 사용자 지정 클라이언트 및 서비스 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="0ca71-143">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="0ca71-144">방법: 사용자 지정 보안 토큰 인증자 만들기</span><span class="sxs-lookup"><span data-stu-id="0ca71-144">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="0ca71-145">방법: 사용자 지정 보안 토큰 공급자 만들기</span><span class="sxs-lookup"><span data-stu-id="0ca71-145">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [<span data-ttu-id="0ca71-146">방법: 사용자 지정 토큰 만들기</span><span class="sxs-lookup"><span data-stu-id="0ca71-146">How to: Create a Custom Token</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)  
 [<span data-ttu-id="0ca71-147">보안 아키텍처</span><span class="sxs-lookup"><span data-stu-id="0ca71-147">Security Architecture</span></span>](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
