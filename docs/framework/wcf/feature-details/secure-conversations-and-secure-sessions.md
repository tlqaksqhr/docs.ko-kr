---
title: "보안 대화 및 보안 세션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d519640c40daf248a01a19f0450f3aea8de6cc04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="secure-conversations-and-secure-sessions"></a><span data-ttu-id="11f76-102">보안 대화 및 보안 세션</span><span class="sxs-lookup"><span data-stu-id="11f76-102">Secure Conversations and Secure Sessions</span></span>
<span data-ttu-id="11f76-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 특징은 서로를 인증하고 암호화 및 디지털 서명 프로세스에 동의하는 두 개의 끝점 사이에 보안 세션을 설정하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-103">A feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is the ability to establish secure sessions between two endpoints that authenticate each other and agree upon an encryption and digital signature process.</span></span> <span data-ttu-id="11f76-104">예를 들어, 서비스 끝점은 인증을 위해 X.509 인증서에 기반한 보안 토큰을 보낼 클라이언트 끝점이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-104">For example, the service endpoint might require a client endpoint to send a security token based upon an X.509 certificate for authentication.</span></span> <span data-ttu-id="11f76-105">클라이언트가 인증되면 서비스 끝점은 세션 내의 모든 후속 메시지 보안을 설정하는 데 사용되는 클라이언트에게 SCT(보안 컨텍스트 토큰)를 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-105">Once the client is authenticated, the service endpoint returns a security context token (SCT) back to the client that is then used to secure all subsequent messages within the session.</span></span> <span data-ttu-id="11f76-106">이 보안 세션을 설정하면 SCT에 대칭 키가 포함되기 때문에 두 개의 끝점 간에 교환되는 메시지 집합이 훨씬 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-106">Establishing this secure session enables the set of messages that are exchanged between the two endpoints to be more efficient, because the SCT has a symmetric key.</span></span> <span data-ttu-id="11f76-107">X.509 인증서가 기준으로 하는 비대칭 키는 디지털 서명을 생성하거나 데이터 집합을 암호화할 때 대칭 키보다 훨씬 더 많은 계산 능력이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-107">Asymmetric keys, which X.509 certificates are based upon, require significantly more computational power than symmetric keys when generating a digital signature or encrypting a set of data.</span></span>  
  
 <span data-ttu-id="11f76-108">부트스트랩 정책 (의 6.2.7 섹션에 정의 된 [Ws-securitypolicy](http://go.microsoft.com/fwlink/?LinkId=99817) 표준) 채널을 보호 하 고 RST/SCT 및 RSTR/SCT 교환 하기 전에 클라이언트를 인증 하는 데 사용 하는 메시지 보안 어설션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-108">The bootstrap policy (defined in section 6.2.7 of the [WS-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817) standard) contains the message security assertions used to secure the channel and authenticate the client prior to the RST/SCT and RSTR/SCT exchange.</span></span> <span data-ttu-id="11f76-109">특정 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 표준 바인딩에는 보안 대화를 사용할지 여부를 제어하는 `Security.Message.EstablishSecurityContext` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-109">Certain [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] standard bindings have a `Security.Message.EstablishSecurityContext` property which controls whether secure conversation is used.</span></span> <span data-ttu-id="11f76-110">부트스트랩을 통해 중첩 보안 바인딩 요소를 가리키는 사용자 지정 바인딩을 사용 하는 경우 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 구성 파일 또는 호출 하 여 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> 코드에서입니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-110">When using custom bindings the bootstrap is indicated by nesting security binding elements, either through [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) in the configuration file, or by calling <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> in code.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="11f76-111">세션은 참조 [를 사용 하 여 세션](../../../../docs/framework/wcf/using-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11f76-111"> sessions, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11f76-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11f76-112">See Also</span></span>  
 [<span data-ttu-id="11f76-113">세션, 인스턴스 및 동시성</span><span class="sxs-lookup"><span data-stu-id="11f76-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="11f76-114">방법: 세션이 필요한 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="11f76-114">How to: Create a Service That Requires Sessions</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
