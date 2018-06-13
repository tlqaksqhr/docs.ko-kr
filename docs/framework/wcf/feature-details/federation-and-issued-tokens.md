---
title: 페더레이션 및 발급된 토큰
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: b6a5411b74b53cb5e3b18cced7fd8fc09e9a9676
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491579"
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="1aa9b-102">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="1aa9b-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="1aa9b-103">와 WCF Windows Communication Foundation (), Ws-federation 및 Ws-trust 사양을 구현 하는 서비스와 안전 하 게 통신 하는 클라이언트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-103">With Windows Communication Foundation (WCF), you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="1aa9b-104">사양은 XML, SOAP 및 WSDL(웹 서비스 기술 언어)을 사용하여 여러 신뢰 영역 간에 인증 및 권한을 사용할 수 있는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1aa9b-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1aa9b-105">In This Section</span></span>  
 [<span data-ttu-id="1aa9b-106">페더레이션</span><span class="sxs-lookup"><span data-stu-id="1aa9b-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="1aa9b-107">페더레이션을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="1aa9b-108">페더레이션 및 트러스트</span><span class="sxs-lookup"><span data-stu-id="1aa9b-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="1aa9b-109">페더레이션 서비스 또는 클라이언트를 만들 때 알아야 할 디자인 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="1aa9b-110">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="1aa9b-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="1aa9b-111">WCF를 사용 하 여 페더레이션된 클라이언트 만들기의 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-111">Describes the basics of creating a federated client with WCF.</span></span>  
  
 [<span data-ttu-id="1aa9b-112">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="1aa9b-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="1aa9b-113">페더레이션 서비스를 만드는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="1aa9b-114">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="1aa9b-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="1aa9b-115">`WSFederationHttpBinding`을 사용하는 클라이언트 및 서비스를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="1aa9b-116">방법: 보안 토큰 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="1aa9b-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="1aa9b-117">보안 토큰 서비스를 만드는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="1aa9b-118">SAML(Security Assertions Markup Language) 토큰 및 클레임</span><span class="sxs-lookup"><span data-stu-id="1aa9b-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="1aa9b-119">확장 가능하고 다양한 클레임 형식을 만들 수 있는 SAML(Security Assertions Markup Language) 토큰에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="1aa9b-120">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="1aa9b-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="1aa9b-121">보안 토큰 로컬 발급자를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="1aa9b-122">방법: WSFederationHttpBinding에서 보안 세션을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="1aa9b-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="1aa9b-123">`WSFederationHttpBinding`에서 보안 세션을 비활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="1aa9b-124">각 클라이언트에 대해 세션이 필요한 웹 팜을 만드는 경우 보안 세션을 비활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1aa9b-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1aa9b-125">참조</span><span class="sxs-lookup"><span data-stu-id="1aa9b-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="1aa9b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1aa9b-126">See Also</span></span>  
 [<span data-ttu-id="1aa9b-127">권한 부여</span><span class="sxs-lookup"><span data-stu-id="1aa9b-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="1aa9b-128">사용자 지정 토큰</span><span class="sxs-lookup"><span data-stu-id="1aa9b-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="1aa9b-129">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="1aa9b-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
