---
title: "클레임 및 리소스 액세스 거부"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 156856ddd1a4c3b1d8f77a8a61f7e0336f993839
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="ceb60-102">클레임 및 리소스 액세스 거부</span><span class="sxs-lookup"><span data-stu-id="ceb60-102">Claims and Denying Access to Resources</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="ceb60-103">에서는 클레임 기반 권한 부여 메커니즘을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb60-103"> supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="ceb60-104">시스템은 클레임을 기반으로 한 리소스에 대한 액세스를 허용할 뿐 아니라 거부하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb60-104">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="ceb60-105">이러한 시스템은 결과적으로 액세스가 허용되는 클레임을 찾기 전에 액세스가 거부되는 클레임을 <xref:System.IdentityModel.Policy.AuthorizationContext>에서 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb60-105">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="ceb60-106">예를 들어 시스템은 ID의 클레임 형식과 권한 및 리소스 값이 각각 `Age`, <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, `Under 21`인 사용자에 대해클레임의 형식과 권한 및 리소스 값이 `Name`, <xref:System.IdentityModel.Claims.Rights.Identity%2A>, `Mallory`이면 리소스에 대한 액세스를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb60-106">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="ceb60-107">즉, 시스템은 21살 이하의 모든 사람에 대해 액세스를 거부하고 이름이 Mallory인 경우에는 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb60-107">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="ceb60-108">이러한 의미 체계를 올바르게 구현하려면 `Age` 클레임을 먼저 조사하여 나이가 21살 이하인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb60-108">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="ceb60-109">그렇지 않으면 `Name` 클레임에 따라 21살 이하의 Mallory에게도 리소스에 대한 액세스를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceb60-109">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb60-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ceb60-110">See Also</span></span>  
 [<span data-ttu-id="ceb60-111">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="ceb60-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="ceb60-112">클레임 및 토큰</span><span class="sxs-lookup"><span data-stu-id="ceb60-112">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
