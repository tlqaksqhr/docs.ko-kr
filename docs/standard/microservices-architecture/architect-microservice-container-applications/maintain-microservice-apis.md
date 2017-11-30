---
title: "만들기, 진화 하 고 버전 관리 마이크로 서비스 Api 및 계약"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 만들기, 진화 하 고 버전 관리 마이크로 서비스 Api 및 계약"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 433711c3479eafd52bf9f5d53faf8e5707c6c624
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a><span data-ttu-id="10f55-104">만들기, 진화 하 고 버전 관리 마이크로 서비스 Api 및 계약</span><span class="sxs-lookup"><span data-stu-id="10f55-104">Creating, evolving, and versioning microservice APIs and contracts</span></span>

<span data-ttu-id="10f55-105">마이크로 서비스 API는 서비스와 클라이언트 간 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-105">A microservice API is a contract between the service and its clients.</span></span> <span data-ttu-id="10f55-106">마이크로 서비스는 독립적으로 개발할는 그렇게 중요 한지이 계약의 API 계약을 중단 하지 않도록 하는 경우에 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-106">You will be able to evolve a microservice independently only if you do not break its API contract, which is why the contract is so important.</span></span> <span data-ttu-id="10f55-107">계약을 변경 하면 클라이언트 응용 프로그램 또는 API 게이트웨이 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-107">If you change the contract, it will impact your client applications or your API Gateway.</span></span>

<span data-ttu-id="10f55-108">API 정의의 특성 사용 중인 프로토콜에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-108">The nature of the API definition depends on which protocol you are using.</span></span> <span data-ttu-id="10f55-109">예를 들어, 메시징 사용 하는 경우 (같은 [AMQP](https://www.amqp.org/)), API는 메시지 유형을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-109">For instance, if you are using messaging (like [AMQP](https://www.amqp.org/)), the API consists of the message types.</span></span> <span data-ttu-id="10f55-110">HTTP 및 RESTful 서비스를 사용 하는 경우 API Url 및 요청 및 응답 JSON 형식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-110">If you are using HTTP and RESTful services, the API consists of the URLs and the request and response JSON formats.</span></span>

<span data-ttu-id="10f55-111">그러나 초기 계약에 대 한 신중한을 경우에 서비스 API는 시간이 지나도 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-111">However, even if you are thoughtful about your initial contract, a service API will need to change over time.</span></span> <span data-ttu-id="10f55-112">이런 경우-특히 사용자가 API는 공용 API 여러 클라이언트 응용 프로그램에서 사용 하는 경우-일반적으로 새 API 계약으로 업그레이드 하는 모든 클라이언트를 강제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-112">When that happens—and especially if your API is a public API consumed by multiple client applications—you typically cannot force all clients to upgrade to your new API contract.</span></span> <span data-ttu-id="10f55-113">일반적으로 증분 방식으로 서비스 계약의 이전 버전과 새 버전을 모두 동시에 실행 중인 서비스의 새 버전을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-113">You usually need to incrementally deploy new versions of a service in a way that both old and new versions of a service contract are running simultaneously.</span></span> <span data-ttu-id="10f55-114">따라서이 사용자 서비스 버전 관리를 위한 전략에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-114">Therefore, it is important to have a strategy for your service versioning.</span></span>

<span data-ttu-id="10f55-115">API 변경이 특성 또는 매개 변수 API에 추가 하는 경우와 같은 작은 오래 된 API를 사용 하는 클라이언트를 전환 하 고 서비스의 새 버전에서 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-115">When the API changes are small, like if you add attributes or parameters to your API, clients that use an older API should switch and work with the new version of the service.</span></span> <span data-ttu-id="10f55-116">기본값, 필요한 모든 누락 된 특성을 제공할 수 있습니다 및 클라이언트가 추가 응답 특성을 무시 하는 일을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-116">You might be able to provide default values for any missing attributes that are required, and the clients might be able to ignore any extra response attributes.</span></span>

<span data-ttu-id="10f55-117">그러나 때로는 해야 서비스 API에 대 한 주 버전과 호환 되지 않는 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-117">However, sometimes you need to make major and incompatible changes to a service API.</span></span> <span data-ttu-id="10f55-118">새 버전으로 즉시 업그레이드 하는 클라이언트 응용 프로그램이 나 서비스를 강제로 못할 수 있습니다, 때문에 서비스는 일정 기간 동안 이전 버전의 API 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-118">Because you might not be able to force client applications or services to upgrade immediately to the new version, a service must support older versions of the API for some period.</span></span> <span data-ttu-id="10f55-119">HTTP 기반 메커니즘 등 REST 사용 하는 한 가지 방법은 url에서 또는 HTTP 헤더에 API 버전 번호를 포함 하려면.</span><span class="sxs-lookup"><span data-stu-id="10f55-119">If you are using an HTTP-based mechanism such as REST, one approach is to embed the API version number in the URL or into a HTTP header.</span></span> <span data-ttu-id="10f55-120">그런 다음 두 버전의 동시에 동일한 서비스 인스턴스 내의 서비스를 구현 하거나 각각 API의 버전을 처리 하는 서로 다른 인스턴스를 배포 간의 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-120">Then you can decide between implementing both versions of the service simultaneously within the same service instance, or deploying different instances that each handle a version of the API.</span></span> <span data-ttu-id="10f55-121">이 대 한 좋은 방법은 [중재자 패턴](https://en.wikipedia.org/wiki/Mediator_pattern) (예를 들어 [MediatR 라이브러리](https://github.com/jbogard/MediatR))를 다르게 구현 버전 독립 처리기에 분리 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-121">A good approach for this is the [Mediator pattern](https://en.wikipedia.org/wiki/Mediator_pattern) (for example, [MediatR library](https://github.com/jbogard/MediatR)) to decouple the different implementation versions into independent handlers.</span></span>

<span data-ttu-id="10f55-122">마지막으로 REST 아키텍처를 사용 하는 경우, [하이퍼미디어](https://www.infoq.com/articles/mark-baker-hypermedia) 버전 관리를 위한 가장 좋은 방법은 서비스 이며 evolvable Api를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10f55-122">Finally, if you are using a REST architecture, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) is the best solution for versioning your services and allowing evolvable APIs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="10f55-123">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="10f55-123">Additional resources</span></span>

-   <span data-ttu-id="10f55-124">**Scott Hanselman 합니다. ASP.NET Core RESTful 웹 API 버전 관리를 쉽게**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span><span class="sxs-lookup"><span data-stu-id="10f55-124">**Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
<http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx></span></span>

-   <span data-ttu-id="10f55-125">**버전 관리는 RESTful 웹 API**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span><span class="sxs-lookup"><span data-stu-id="10f55-125">**Versioning a RESTful web API**
[*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)</span></span>

-   <span data-ttu-id="10f55-126">**로 Fielding 합니다. 버전 관리, 하이퍼미디어, 및 REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning></span><span class="sxs-lookup"><span data-stu-id="10f55-126">**Roy Fielding. Versioning, Hypermedia, and REST**
<https://www.infoq.com/articles/roy-fielding-on-versioning></span></span>


>[!div class="step-by-step"]
<span data-ttu-id="10f55-127">[이전] (비동기-메시지-기반-communication.md) [다음] (microservices-주소 지정 기능-service-registry.md)</span><span class="sxs-lookup"><span data-stu-id="10f55-127">[Previous] (asynchronous-message-based-communication.md) [Next] (microservices-addressability-service-registry.md)</span></span>
