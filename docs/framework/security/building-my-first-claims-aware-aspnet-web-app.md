---
title: "내 첫 번째 클레임 인식 ASP.NET 웹 응용 프로그램 구축"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 182f7c1646e112026852efcb5bb110607fe19360
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="5660d-102">내 첫 번째 클레임 인식 ASP.NET 웹 응용 프로그램 구축</span><span class="sxs-lookup"><span data-stu-id="5660d-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="5660d-103">적용 대상</span><span class="sxs-lookup"><span data-stu-id="5660d-103">Applies To</span></span>  
  
-   <span data-ttu-id="5660d-104">WIF(Windows Identity Foundation)</span><span class="sxs-lookup"><span data-stu-id="5660d-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="5660d-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5660d-105">ASP.NET</span></span>  
  
 <span data-ttu-id="5660d-106">이 항목에서는 WIF를 사용하여 클레임 인식 ASP.NET 웹 응용 프로그램을 구축하는 시나리오에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="5660d-107">일반적으로 클레임 인식 응용 프로그램 시나리오에는 응용 프로그램, 최종 사용자 및 STS(보안 토큰 서비스)와 같은 세 가지 참가 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="5660d-108">다음 그림은 이 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-108">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="5660d-109">![WIF 기본 웹앱](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span><span class="sxs-lookup"><span data-stu-id="5660d-109">![WIF Basic Web App](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span></span>  
  
1.  <span data-ttu-id="5660d-110">클레임 인식 응용 프로그램은 WIF를 사용하여 인증되지 않은 요청을 식별하고 STS로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2.  <span data-ttu-id="5660d-111">최종 사용자가 STS에 자격 증명을 제공하고, 성공적으로 인증되면 STS에서 해당 사용자에게 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3.  <span data-ttu-id="5660d-112">사용자가 요청에서 STS 발급 토큰을 사용해 STS에서 클레임 인식 응용 프로그램으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4.  <span data-ttu-id="5660d-113">클레임 인식 응용 프로그램은 STS 및 발급되는 토큰을 신뢰하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="5660d-114">클레임 인식 응용 프로그램은 WIF를 사용하여 토큰의 유효성을 검사하고 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="5660d-115">개발자가 인증 구현과 같이 응용 프로그램의 요구에 맞는 적절한 WIF API 및 형식(예: **ClaimsPrincpal**)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="5660d-116">.NET 4.5부터 WIF가 .NET Framework 패키지의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="5660d-117">WIF 클래스를 프레임워크에서 직접 사용할 수 있도록 하면 .NET에 클레임 기반 ID를 더욱 심층적으로 통합하여 클레임을 더욱 쉽게 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="5660d-118">WIF 4.5를 사용하면 클레임 인식 웹 응용 프로그램 개발을 시작하기 위해 대역 외 구성 요소를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="5660d-119">현재 WIF 클래스가 다양한 어셈블리에 분산되어 있으며, 주요 클래스는 System.Security.Claims, System.IdentityModel 및 System.IdentityModel.Services입니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="5660d-120">STS는 성공적으로 인증되면 토큰을 발급하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="5660d-121">Microsoft는 다음과 같은 두 가지 업계 표준 STS를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="5660d-122">[AD FS(Active Directory Federation Services) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516)(http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="5660d-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="5660d-123">[Microsoft Azure ACS(Access Control Service)](http://go.microsoft.com/fwlink/?LinkID=247517)(http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="5660d-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="5660d-124">ADFS 2.0은 Windows Server R2에 속하며, 온-프레미스 시나리오의 STS로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="5660d-125">ACS는 Microsoft Azure 플랫폼의 일부로 제공되는 클라우드 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="5660d-126">테스트 또는 교육용으로 클레임 인식 응용 프로그램을 작성하기 위해 다른 STS를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="5660d-127">예를 들어, 온라인에서 무료로 제공되는 [Visual Studio용 ID 및 액세스 도구](http://go.microsoft.com/fwlink/?LinkID=245849)(http://go.microsoft.com/fwlink/?LinkID=245849)에 속하는 로컬 개발 STS를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5660d-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="5660d-128">WIF를 사용하여 첫 번째 클레임 인식 ASP.NET 응용 프로그램을 작성하려면 다음 중 하나의 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="5660d-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
-   [<span data-ttu-id="5660d-129">방법: WIF를 사용하여 클레임 인식 ASP.NET MVC 웹 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="5660d-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [<span data-ttu-id="5660d-130">방법: WIF를 사용하여 클레임 인식 ASP.NET Web Forms 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="5660d-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [<span data-ttu-id="5660d-131">방법: 양식 기반 인증을 사용하여 클레임 인식 ASP.NET 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="5660d-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="5660d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5660d-132">See Also</span></span>  
 [<span data-ttu-id="5660d-133">WIF 시작</span><span class="sxs-lookup"><span data-stu-id="5660d-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
