---
title: "페더레이션 및 발급된 토큰"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 017d3e51022ad9980dc8f058415697c80a2a6b35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="195a7-102">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="195a7-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="195a7-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하면 WS-Federation 및 WS-Trust 사양을 구현하는 서비스와 안전하게 통신하는 클라이언트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="195a7-104">사양은 XML, SOAP 및 WSDL(웹 서비스 기술 언어)을 사용하여 여러 신뢰 영역 간에 인증 및 권한을 사용할 수 있는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="195a7-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="195a7-105">In This Section</span></span>  
 [<span data-ttu-id="195a7-106">페더레이션</span><span class="sxs-lookup"><span data-stu-id="195a7-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="195a7-107">페더레이션을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="195a7-108">페더레이션 및 트러스트</span><span class="sxs-lookup"><span data-stu-id="195a7-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="195a7-109">페더레이션 서비스 또는 클라이언트를 만들 때 알아야 할 디자인 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="195a7-110">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="195a7-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="195a7-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 페더레이션 클라이언트를 만들기 위한 기본적인 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="195a7-112">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="195a7-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="195a7-113">페더레이션 서비스를 만드는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="195a7-114">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="195a7-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="195a7-115">`WSFederationHttpBinding`을 사용하는 클라이언트 및 서비스를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="195a7-116">방법: 보안 토큰 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="195a7-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="195a7-117">보안 토큰 서비스를 만드는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="195a7-118">SAML(Security Assertions Markup Language) 토큰 및 클레임</span><span class="sxs-lookup"><span data-stu-id="195a7-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="195a7-119">확장 가능하고 다양한 클레임 형식을 만들 수 있는 SAML(Security Assertions Markup Language) 토큰에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="195a7-120">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="195a7-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="195a7-121">보안 토큰 로컬 발급자를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="195a7-122">방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="195a7-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="195a7-123">`WSFederationHttpBinding`에서 보안 세션을 비활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="195a7-124">각 클라이언트에 대해 세션이 필요한 웹 팜을 만드는 경우 보안 세션을 비활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="195a7-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="195a7-125">참조</span><span class="sxs-lookup"><span data-stu-id="195a7-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="195a7-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="195a7-126">See Also</span></span>  
 [<span data-ttu-id="195a7-127">권한 부여</span><span class="sxs-lookup"><span data-stu-id="195a7-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="195a7-128">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="195a7-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="195a7-129">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="195a7-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
