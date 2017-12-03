---
title: "&lt;message&gt;의 &lt;claimTypeRequirements&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 158aad6a6a11bb889df74e1222a8881a1c38803f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a><span data-ttu-id="cf243-102">&lt;message&gt;의 &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="cf243-102">&lt;claimTypeRequirements&gt; for &lt;message&gt;</span></span>
<span data-ttu-id="cf243-103">필요한 클레임 형식의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf243-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="cf243-104">컬렉션은 필수 및 선택적 클레임을 지정하는 데 서비스에서 사용됩니다. 이러한 클레임은 클라이언트에서 서비스에 액세스하는 데 사용하는 발급된 토큰에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf243-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="cf243-105">WSDL 게시가 활성화되어 있지만 WCF에서는 발급된 토큰이 지정된 클레임 형식을 포함하지 않아도 되는 경우 서비스는 필수 클레임 형식을 메타데이터로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="cf243-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="cf243-106">서비스에서 필수 클레임 형식을 표시하려면 인증 정책을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf243-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="cf243-107">페더레이션 클라이언트에서 이 컬렉션은 필수 및 선택적 클레임 목록을 포함하며, 이 목록은 발급된 토큰에 대한 클라이언트의 요청에서 보안 토큰 서비스로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf243-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf243-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf243-108">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
