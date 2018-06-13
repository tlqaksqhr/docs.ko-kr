---
title: 전송 보안
ms.date: 03/30/2017
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e7f804d34a47c5508839636a6fe5045ebce3972e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498217"
---
# <a name="transport-security"></a><span data-ttu-id="be68d-102">전송 보안</span><span class="sxs-lookup"><span data-stu-id="be68d-102">Transport Security</span></span>
<span data-ttu-id="be68d-103">선택한 바인딩에 따라 전송 보안에서 Windows Communication Foundation (WCF)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-103">Transport security in Windows Communication Foundation (WCF) depends on the binding selected.</span></span> <span data-ttu-id="be68d-104">바인딩이 구현하는 전송은 실제 보안 메커니즘을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-104">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="be68d-105">이 단원의 항목에서는 구현된 메커니즘 및 해당 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-105">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be68d-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="be68d-106">In This Section</span></span>  
 [<span data-ttu-id="be68d-107">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="be68d-107">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="be68d-108">Wcf에서 전송 보안 기본 사항에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-108">Explains the basics of transport security in WCF.</span></span>  
  
 [<span data-ttu-id="be68d-109">HTTP 전송 보안</span><span class="sxs-lookup"><span data-stu-id="be68d-109">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
 <span data-ttu-id="be68d-110">WCF Secure Sockets Layer (SSL 또는 HTTPS)을 구현 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-110">Explains how WCF implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="be68d-111">HTTP 인증 이해</span><span class="sxs-lookup"><span data-stu-id="be68d-111">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)  
 <span data-ttu-id="be68d-112">기본, 다이제스트, NTLM(NT LAN Manager) 등과 같은 HTTP 인증 스키마에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-112">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="be68d-113">전송 보안을 통해 가장 사용</span><span class="sxs-lookup"><span data-stu-id="be68d-113">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 <span data-ttu-id="be68d-114">전송 보안 모드를 사용하여 수행할 수 있는 5가지 가장 수준에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-114">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="be68d-115">방법: SSL 인증서로 포트 구성</span><span class="sxs-lookup"><span data-stu-id="be68d-115">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="be68d-116">SSL(전송) 보안용 X.509 인증서가 있는 컴퓨터에서의 포트 구성 기본 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="be68d-116">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="be68d-117">참조</span><span class="sxs-lookup"><span data-stu-id="be68d-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="be68d-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="be68d-118">Related Sections</span></span>  
 [<span data-ttu-id="be68d-119">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="be68d-119">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="be68d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be68d-120">See Also</span></span>  
 [<span data-ttu-id="be68d-121">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="be68d-121">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
