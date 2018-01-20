---
title: "보안 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: "23"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: cdd9b91ba7ff9b1e431f7d9107e72df084ba8af3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="extending-security"></a><span data-ttu-id="e08f2-102">보안 확장</span><span class="sxs-lookup"><span data-stu-id="e08f2-102">Extending Security</span></span>
<span data-ttu-id="e08f2-103">새 클레임 형식 및 사용자 지정 토큰을 적용하기 위해 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 보안 인프라를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="e08f2-104">이 단원의 각 항목에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e08f2-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e08f2-105">In This Section</span></span>  
 [<span data-ttu-id="e08f2-106">보안 아키텍처</span><span class="sxs-lookup"><span data-stu-id="e08f2-106">Security Architecture</span></span>](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="e08f2-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 시스템의 아키텍처에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-107">Walks through the architecture of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security system.</span></span>  
  
 [<span data-ttu-id="e08f2-108">사용자 지정 자격 증명 및 자격 증명 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e08f2-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="e08f2-109">사용자 지정 자격 증명의 유효성을 검사할 때 ID 모델을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="e08f2-110">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="e08f2-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="e08f2-111">일반적으로 STS(보안 토큰 서비스)에서 발행된 토큰은 SAML 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="e08f2-112">이 항목에서는 사용자 지정 토큰 형식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="e08f2-113">사용자 지정 권한 부여</span><span class="sxs-lookup"><span data-stu-id="e08f2-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="e08f2-114">사용자 지정 인증을 구현하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="e08f2-115">인증을 위해 서비스 ID 재정의</span><span class="sxs-lookup"><span data-stu-id="e08f2-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="e08f2-116">인증을 위해 서비스의 ID를 재지정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="e08f2-117">방법: 사용자 지정 클라이언트 ID 검증 도구 만들기</span><span class="sxs-lookup"><span data-stu-id="e08f2-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="e08f2-118">사용자 지정 끝점 ID의 유효성을 검사하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="e08f2-119">방법: 서명 및 암호화에 별도의 X.509 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="e08f2-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="e08f2-120">일반적으로 메시지는 단일 인증서를 사용하여 서명되고 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="e08f2-121">이 항목에서는 필요한 경우 두 가지 인증서를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="e08f2-122">방법: X.509 인증서의 개인 키에 대한 암호화 공급자 변경</span><span class="sxs-lookup"><span data-stu-id="e08f2-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="e08f2-123">X.509 인증서의 개인 키를 제공하는 데 사용되는 암호화 공급자를 변경하는 방법 및 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 프레임워크에 공급자를 통합하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e08f2-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e08f2-124">참조</span><span class="sxs-lookup"><span data-stu-id="e08f2-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="e08f2-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e08f2-125">Related Sections</span></span>  
 [<span data-ttu-id="e08f2-126">보안</span><span class="sxs-lookup"><span data-stu-id="e08f2-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="e08f2-127">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e08f2-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="e08f2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e08f2-128">See Also</span></span>  
 [<span data-ttu-id="e08f2-129">보안 개요</span><span class="sxs-lookup"><span data-stu-id="e08f2-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
