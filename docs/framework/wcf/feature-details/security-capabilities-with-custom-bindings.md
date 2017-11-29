---
title: "사용자 지정 바인딩을 사용하는 보안 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9d252dca363c952dde44b499363e285d4bb7eb82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="f6257-102">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="f6257-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="f6257-103">시스템에서 제공되는 바인딩 중 하나를 사용하여 일반적으로 사용되는 보안 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="f6257-104">하지만 좀더 제어가 필요한 경우에는 이 항목의 설명에 따라 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 사용하여 사용자 지정 바인딩을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f6257-105">사용자 지정 바인딩을 참조 [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-105"> custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f6257-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f6257-106">In This Section</span></span>  
 [<span data-ttu-id="f6257-107">SecurityBindingElement 인증 모드</span><span class="sxs-lookup"><span data-stu-id="f6257-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="f6257-108">사용자 지정 바인딩에서 가능한 인증 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="f6257-109">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f6257-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="f6257-110">보안 요소로 사용자 지정 바인딩을 만드는 기본 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="f6257-111">방법: 지정된 된 인증 모드에 대 한 SecurityBindingElement 만들기</span><span class="sxs-lookup"><span data-stu-id="f6257-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="f6257-112">지정된 인증 모드의 보안 요소를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="f6257-113">방법: 사용 안 함 보안 WSFederationHttpBinding에서 세션</span><span class="sxs-lookup"><span data-stu-id="f6257-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="f6257-114">페더레이션 서비스를 만드는 경우 보안 세션을 비활성화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="f6257-115">방법: 메시지 재생 검색을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f6257-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="f6257-116">재생 공격이 발생한 경우를 확인하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="f6257-117">방법: 지 원하는 자격 증명 만들기</span><span class="sxs-lookup"><span data-stu-id="f6257-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="f6257-118">필요한 경우 서비스에 지원하는 자격 증명을 제공하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="f6257-119">방법: 서명 확인 설정</span><span class="sxs-lookup"><span data-stu-id="f6257-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="f6257-120">메시지에 디지털 서명을 할 때 서명을 확인하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="f6257-121">방법: 최대 클럭 오차 설정</span><span class="sxs-lookup"><span data-stu-id="f6257-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="f6257-122">서비스와 클라이언트 사이에서 최대로 허용되는 시간 차이를 설정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="f6257-123">방법: 디지털 서명의 암호화를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f6257-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="f6257-124">디지털 서명의 암호화를 비활성화할 경우 얻을 수 있는 성능 상의 이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f6257-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f6257-125">참조</span><span class="sxs-lookup"><span data-stu-id="f6257-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="f6257-126">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="f6257-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="f6257-127">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f6257-127">Related Sections</span></span>  
 [<span data-ttu-id="f6257-128">보호 수준 이해</span><span class="sxs-lookup"><span data-stu-id="f6257-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="f6257-129">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f6257-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6257-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6257-130">See Also</span></span>  
 [<span data-ttu-id="f6257-131">바인딩 및 보안</span><span class="sxs-lookup"><span data-stu-id="f6257-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="f6257-132">보안 개요</span><span class="sxs-lookup"><span data-stu-id="f6257-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="f6257-133">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="f6257-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
