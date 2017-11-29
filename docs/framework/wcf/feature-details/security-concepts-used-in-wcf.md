---
title: "WCF에서 사용되는 보안 개념"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0f490fc09ada9ee80cb6cee12e9e9061e820026e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="security-concepts-used-in-wcf"></a><span data-ttu-id="1efe8-102">WCF에서 사용되는 보안 개념</span><span class="sxs-lookup"><span data-stu-id="1efe8-102">Security Concepts Used in WCF</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="1efe8-103"> 보안은 이미 사용 중인 개념을 기반으로 빌드되고 다양한 보안 인프라에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-103"> security is built upon concepts already in use and deployed in various security infrastructures.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="1efe8-104">는 HTTPS(HTTP를 통한 SSL(Secure Sockets Layer))와 같은 이러한 인프라 중 일부를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-104"> supports some of those infrastructures, such as Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="1efe8-105">그러나 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 SOAP 인코딩된 메시지를 통해 WS-Security와 같은 최신 상호 운용 가능한 보안 표준을 구현하여 기존 보안 인프라를 지원하는 것 이상의 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-105">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] goes beyond supporting existing security infrastructures by implementing newer interoperable security standards (such as WS-Security) over SOAP-encoded messages.</span></span> <span data-ttu-id="1efe8-106">기존 메커니즘 또는 새로운 상호 운용 가능한 표준을 사용하는지 여부에 따라 두 가지의 보안 개념은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-106">Whether you are using existing mechanisms or new interoperable standards, the security concepts behind both are the same.</span></span> <span data-ttu-id="1efe8-107">따라서 기존 인프라 및 최신 표준에 적용된 개념을 이해하는 것이 특정 응용 프로그램에 대해 가장 적합한 보안 모델을 구현하는 데 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-107">Understanding the concepts behind existing infrastructures and the newer standards is central to implementing the best security model for an application.</span></span>  
  
## <a name="introduction-to-security-for-wcf-web-services"></a><span data-ttu-id="1efe8-108">WCF 웹 서비스 보안에 대한 소개</span><span class="sxs-lookup"><span data-stu-id="1efe8-108">Introduction to Security for WCF Web Services</span></span>  
 <span data-ttu-id="1efe8-109">Microsoft Patterns and Practices 그룹은 여기에서 다운로드할 수 있는 WCF 보안 지침을 자세한 백서 썼습니다: [WCF 보안 가이드](http://go.microsoft.com/fwlink/?LinkId=210210)합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-109">The Microsoft Patterns and Practices group wrote an in-depth whitepaper on WCF security guidance which is available for download here: [WCF Security Guide](http://go.microsoft.com/fwlink/?LinkId=210210).</span></span> <span data-ttu-id="1efe8-110">이 백서에서는 웹 서비스와 관련된 기본 보안 개념, 주요 WCF 보안 개념, 인트라넷 응용 프로그램 시나리오 및 인터넷 응용 프로그램 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-110">This whitepaper describes the fundamental security concepts as they relate to web services, key WCF security concepts, intranet application scenarios, and internet application scenarios.</span></span>  
  
## <a name="industry-wide-security-specifications"></a><span data-ttu-id="1efe8-111">산업 전반 보안 사양</span><span class="sxs-lookup"><span data-stu-id="1efe8-111">Industry-Wide Security Specifications</span></span>  
  
### <a name="public-key-infrastructure"></a><span data-ttu-id="1efe8-112">공개 키 인프라</span><span class="sxs-lookup"><span data-stu-id="1efe8-112">Public Key Infrastructure</span></span>  
 <span data-ttu-id="1efe8-113">PKI(공개 키 인프라)는 공개 키 암호화 사용을 통해 전자 트랜잭션에 참여하는 각각의 상대방을 확인하고 인증하는 디지털 인증서, 인증 기관 및 기타 등록 기관의 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-113">Public Key Infrastructure (PKI) is a system of digital certificates, certification authorities, and other registration authorities that verify and authenticate each party involved in an electronic transaction through the use of public key cryptography.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="1efe8-114">[Windows Server 2008 R2 인증서 서비스](http://go.microsoft.com/fwlink/?LinkId=210211)합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-114"> [Windows Server 2008 R2 Certificate Services](http://go.microsoft.com/fwlink/?LinkId=210211).</span></span>  
  
### <a name="kerberos-protocol"></a><span data-ttu-id="1efe8-115">Kerberos 프로토콜</span><span class="sxs-lookup"><span data-stu-id="1efe8-115">Kerberos Protocol</span></span>  
 <span data-ttu-id="1efe8-116">*Kerberos 프로토콜* 는 Windows 도메인에서 사용자를 인증 하는 보안 메커니즘을 만들기에 대 한 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-116">The *Kerberos protocol* is a specification for creating a security mechanism that authenticates users on a Windows domain.</span></span> <span data-ttu-id="1efe8-117">이를 통해 사용자가 도메인 내의 다른 엔터티로 보안 컨텍스트를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-117">It allows a user to establish a secure context with other entities within a domain.</span></span> <span data-ttu-id="1efe8-118">Windows 2000 이상 플랫폼은 기본적으로 Kerberos 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-118">Windows 2000 and later platforms use the Kerberos protocol by default.</span></span> <span data-ttu-id="1efe8-119">인트라넷 클라이언트와 상호 작용할 서비스를 만들 때 시스템의 메커니즘을 이해하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-119">Understanding the mechanisms of the system is useful when creating a service that will interact with intranet clients.</span></span> <span data-ttu-id="1efe8-120">또한 이후에 *웹 서비스 보안 Kerberos 바인딩* 이 널리 게시 수는 Kerberos 프로토콜을 사용 하면 인터넷 클라이언트와 통신 (즉, Kerberos 프로토콜은 상호 운용 가능).</span><span class="sxs-lookup"><span data-stu-id="1efe8-120">In addition, since the *Web Services Security Kerberos Binding* is widely published, you can use the Kerberos protocol to communicate with Internet clients (that is, the Kerberos protocol is interoperable).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1efe8-121">Windows의 Kerberos 프로토콜 구현 되는 경우 참조 [Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212)합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-121"> how the Kerberos protocol is implemented in Windows, see  [Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212).</span></span>  
  
### <a name="x509-certificates"></a><span data-ttu-id="1efe8-122">X.509 인증서</span><span class="sxs-lookup"><span data-stu-id="1efe8-122">X.509 Certificates</span></span>  
 <span data-ttu-id="1efe8-123">X.509 인증서는 보안 응용 프로그램에 사용되는 기본 자격 증명 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-123">X.509 certificates are a primary credential form used in security applications.</span></span> <span data-ttu-id="1efe8-124">인증서 참조 X.509 대 한 자세한 내용은 [X.509 공개 키 인증서](http://go.microsoft.com/fwlink/?LinkId=210213)합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-124">For more information on X.509 certificates see [X.509 Public Key Certificates](http://go.microsoft.com/fwlink/?LinkId=210213).</span></span> <span data-ttu-id="1efe8-125">X.509 인증서는 인증서 저장소 내에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-125">X.509 certificates are stored within a certificate store.</span></span> <span data-ttu-id="1efe8-126">Windows를 실행하는 컴퓨터에는 여러 종류의 인증서 저장소가 있으며 저장소마다 용도가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-126">A computer running Windows has several kinds of certificate stores, each with a different purpose.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1efe8-127">다른 저장소 참조 [인증서 저장소](http://go.microsoft.com/fwlink/?LinkID=87787)합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-127"> the different stores, see [Certificate Stores](http://go.microsoft.com/fwlink/?LinkID=87787).</span></span>  
  
## <a name="web-services-security-specifications"></a><span data-ttu-id="1efe8-128">웹 서비스 보안 사양</span><span class="sxs-lookup"><span data-stu-id="1efe8-128">Web Services Security Specifications</span></span>  
 <span data-ttu-id="1efe8-129">시스템 정의 바인딩에서는 일반적으로 많이 사용되는 웹 서비스 보안 사양을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-129">The system-defined bindings support many commonly used web services security specifications.</span></span> <span data-ttu-id="1efe8-130">참조 지 원하는 시스템 제공 바인딩 및 웹 서비스 사양의 전체 목록은: [웹 서비스 프로토콜 바인딩에서 지 원하는 시스템 제공 상호 운용성](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="1efe8-130">For a complete list of system-provided bindings and the web services specifications they support see: [Web Services Protocols Supported by System-Provided Interoperability Bindings](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)</span></span>  
  
## <a name="access-control-mechanisms"></a><span data-ttu-id="1efe8-131">Access Control 메커니즘</span><span class="sxs-lookup"><span data-stu-id="1efe8-131">Access Control Mechanisms</span></span>  
 <span data-ttu-id="1efe8-132">WCF에서는 서비스 또는 작업에 대한 액세스를 제어하는 여러 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-132">WCF provides a number of ways to control access to a service or operation.</span></span> <span data-ttu-id="1efe8-133">다음과 같은 방법이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1efe8-133">Among them are</span></span>  
  
1.  <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2.  <span data-ttu-id="1efe8-134">ASP.NET 멤버 자격 공급자</span><span class="sxs-lookup"><span data-stu-id="1efe8-134">ASP.NET Membership Provider</span></span>  
  
3.  <span data-ttu-id="1efe8-135">ASP.NET 역할 공급자</span><span class="sxs-lookup"><span data-stu-id="1efe8-135">ASP.NET Role Provider</span></span>  
  
4.  <span data-ttu-id="1efe8-136">권한 부여 관리자</span><span class="sxs-lookup"><span data-stu-id="1efe8-136">Authorization Manager</span></span>  
  
5.  <span data-ttu-id="1efe8-137">ID 모델</span><span class="sxs-lookup"><span data-stu-id="1efe8-137">Identity Model</span></span>  
  
 <span data-ttu-id="1efe8-138">이러한 항목 참조에 대 한 자세한 내용은 [액세스 제어 메커니즘](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)</span><span class="sxs-lookup"><span data-stu-id="1efe8-138">For more information on these topics see, [Access Control Mechanisms](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1efe8-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1efe8-139">See Also</span></span>  
 [<span data-ttu-id="1efe8-140">보안 개요</span><span class="sxs-lookup"><span data-stu-id="1efe8-140">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="1efe8-141">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="1efe8-141">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
