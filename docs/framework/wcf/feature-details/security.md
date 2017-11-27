---
title: "Windows Communication Foundation 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
caps.latest.revision: "21"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 38f62a6ccc0c9291f3963173475f99d5800feb39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="037b7-102">Windows Communication Foundation 보안</span><span class="sxs-lookup"><span data-stu-id="037b7-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="037b7-103">이 단원의 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 보안 기능과 이러한 보안 기능을 사용하여 메시지의 보안을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-103">The topics in this section describe [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security features and how to use them to help secure messages.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="037b7-104">Windows Server AppFabric과 보안을 참조 하십시오. [Windows Server AppFabric 보안 모델](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="037b7-104"> Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="037b7-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="037b7-105">In This Section</span></span>  
 [<span data-ttu-id="037b7-106">보안 개요</span><span class="sxs-lookup"><span data-stu-id="037b7-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="037b7-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 보안 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-107">Describes the security features in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="037b7-108">보안 개념</span><span class="sxs-lookup"><span data-stu-id="037b7-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="037b7-109">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안에 사용되는 기본 용어와 개념을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-109">Describes the basic terminology and concepts used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security.</span></span>  
  
 [<span data-ttu-id="037b7-110">일반적인 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="037b7-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="037b7-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]로 구성할 수 있는 시나리오와 토폴로지를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-111">Describes scenarios and topologies you can configure with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="037b7-112">보안 동작</span><span class="sxs-lookup"><span data-stu-id="037b7-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="037b7-113">보안에 영향을 주는 WCF 동작에 대한 개요를 제공합니다(예: 자격 증명 설정).</span><span class="sxs-lookup"><span data-stu-id="037b7-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="037b7-114">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="037b7-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="037b7-115">사용자 지정 보안 바인딩을 만드는 방법을 보여 주는 항목을 비롯한 바인딩의 보안 지향적인 뷰입니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="037b7-116">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="037b7-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="037b7-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 기능을 사용하여 메시지의 보안을 유지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-117">Describes how to secure messages using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security features.</span></span>  
  
 [<span data-ttu-id="037b7-118">인증</span><span class="sxs-lookup"><span data-stu-id="037b7-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="037b7-119">일반적인 인증 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="037b7-120">권한 부여</span><span class="sxs-lookup"><span data-stu-id="037b7-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="037b7-121">보안 구현을 사용하여 일반적인 인증 시나리오를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="037b7-122">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="037b7-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="037b7-123">페더레이션 기본 사항 및 페더레이션 서버와 통신하는 클라이언트를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="037b7-124">부분 신뢰</span><span class="sxs-lookup"><span data-stu-id="037b7-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="037b7-125">부분적으로 신뢰할 수 있는 시나리오를 실행하는 방법과 그러한 시나리오를 실행할 때의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 제한 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-125">Describes how to run partially-trusted scenarios and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="037b7-126">감사</span><span class="sxs-lookup"><span data-stu-id="037b7-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="037b7-127">보안 이벤트를 감사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="037b7-128">보안 지침 및 모범 사례</span><span class="sxs-lookup"><span data-stu-id="037b7-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="037b7-129">보안 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램을 만드는 데 필요한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="037b7-129">Guidelines for creating secure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="037b7-130">참조</span><span class="sxs-lookup"><span data-stu-id="037b7-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="037b7-131">관련 단원</span><span class="sxs-lookup"><span data-stu-id="037b7-131">Related Sections</span></span>  
 [<span data-ttu-id="037b7-132">WCF 기능 정보</span><span class="sxs-lookup"><span data-stu-id="037b7-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="037b7-133">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="037b7-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="037b7-134">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="037b7-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="037b7-135">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="037b7-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="037b7-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="037b7-136">See Also</span></span>  
 [<span data-ttu-id="037b7-137">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="037b7-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
