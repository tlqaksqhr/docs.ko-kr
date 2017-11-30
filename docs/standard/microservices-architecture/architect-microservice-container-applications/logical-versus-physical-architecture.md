---
title: "물리적 아키텍처 또는 논리적 아키텍처"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 물리적 아키텍처 또는 논리적 아키텍처"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 635774a8fcd0cf1c0ede6a73c604071f538a37fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="logical-architecture-versus-physical-architecture"></a><span data-ttu-id="4ead4-104">물리적 아키텍처 또는 논리적 아키텍처</span><span class="sxs-lookup"><span data-stu-id="4ead4-104">Logical architecture versus physical architecture</span></span>

<span data-ttu-id="4ead4-105">이 시점에서 중지 하 고 논리적 아키텍처와 물리적 아키텍처가 마이크로 서비스 기반 응용 프로그램의 디자인에 적용 됩니다 하는 방법을 간의 차이 설명 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-105">It is useful at this point to stop and discuss the distinction between logical architecture and physical architecture, and how this applies to the design of microservice-based applications.</span></span>

<span data-ttu-id="4ead4-106">를 시작 하려면 microservices 작성 하지 않아도 모든 특정 기술 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-106">To begin, building microservices does not require the use of any specific technology.</span></span> <span data-ttu-id="4ead4-107">예를 들어, Docker 컨테이너 마이크로 서비스 기반 아키텍처를 만들기 위해 필수있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-107">For instance, Docker containers are not mandatory in order to create a microservice-based architecture.</span></span> <span data-ttu-id="4ead4-108">이러한 microservices 일반 프로세스로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-108">Those microservices could also be run as plain processes.</span></span> <span data-ttu-id="4ead4-109">Microservices는 논리적 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="4ead4-109">Microservices is a logical architecture.</span></span>

<span data-ttu-id="4ead4-110">또한, 경우에 단일 서비스, 프로세스 또는 컨테이너로는 마이크로 서비스를 물리적으로 구현할 수 있습니다 (의 초기 버전에 적용 되는 방법을 단순성을 [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)),이 간의 패리티 비즈니스 마이크로 서비스 및 물리적 서비스 또는 컨테이너 필요 하지 않습니다 반드시 모든 경우에에서는 많은 수십 또는 수백 서비스의 구성 하는 대규모 또는 복잡 한 응용 프로그램을 빌드할 때.</span><span class="sxs-lookup"><span data-stu-id="4ead4-110">Moreover, even when a microservice could be physically implemented as a single service, process, or container (for simplicity’s sake, that is the approach taken in the initial version of [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)), this parity between business microservice and physical service or container is not necessarily required in all cases when you build a large and complex application composed of many dozens or even hundreds of services.</span></span>

<span data-ttu-id="4ead4-111">여기에 응용 프로그램의 논리 아키텍처와 물리적 아키텍처 사이 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-111">This is where there is a difference between an application’s logical architecture and physical architecture.</span></span> <span data-ttu-id="4ead4-112">논리 아키텍처 및 시스템의 논리적 경계 반드시 매핑되지 않는 일대일로 물리적 컴퓨터 또는 배포 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="4ead4-112">The logical architecture and logical boundaries of a system do not necessarily map one-to-one to the physical or deployment architecture.</span></span> <span data-ttu-id="4ead4-113">이 오류가 발생할 수 있습니다 하지만 자주 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-113">It can happen, but it often does not.</span></span>

<span data-ttu-id="4ead4-114">수를 식별 한 특정 비즈니스 microservices 또는 경계가 지정 된 컨텍스트에 있지만를 구현 하는 가장 좋은 방법은 단일 서비스 (예: ASP.NET 웹 API) 또는 각 비즈니스 마이크로 서비스에 대 한 단일 Docker 컨테이너를 만들 때 항상 의미 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-114">Although you might have identified certain business microservices or Bounded Contexts, it does not mean that the best way to implement them is always by creating a single service (such as an ASP.NET Web API) or single Docker container for each business microservice.</span></span> <span data-ttu-id="4ead4-115">단일 서비스를 사용 하 여 구현 해야 하는 각 비즈니스 마이크로 서비스를 말하는 규칙 필요 없거나 컨테이너가 융통성이 부족.</span><span class="sxs-lookup"><span data-stu-id="4ead4-115">Having a rule saying each business microservice has to be implemented using a single service or container is too rigid.</span></span>

<span data-ttu-id="4ead4-116">따라서 비즈니스 마이크로 서비스 또는 경계가 지정 된 컨텍스트는 수행할지 일치 수 하는 논리적 아키텍처와 물리적 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="4ead4-116">Therefore, a business microservice or Bounded Context is a logical architecture that might coincide (or not) with physical architecture.</span></span> <span data-ttu-id="4ead4-117">중요 한 점은 이어야 한다는 것뿐입니다 비즈니스 마이크로 서비스 또는 경계가 지정 된 컨텍스트 자치 코드와 상태를 독립적으로 버전을 배포 하 고 크기가 조정 함으로써 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-117">The important point is that a business microservice or Bounded Context must be autonomous by allowing code and state to be independently versioned, deployed, and scaled.</span></span>

<span data-ttu-id="4ead4-118">그림 4-8에서 볼 수 있듯이 카탈로그 비즈니스 마이크로 서비스는 여러 서비스 또는 프로세스 구성 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-118">As Figure 4-8 shows, the catalog business microservice could be composed of several services or processes.</span></span> <span data-ttu-id="4ead4-119">여러 ASP.NET Web API 서비스 또는 다른 종류의 HTTP 또는 다른 프로토콜을 사용 하 여 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-119">These could be multiple ASP.NET Web API services or any other kind of services using HTTP or any other protocol.</span></span> <span data-ttu-id="4ead4-120">무엇 보다도 이러한 서비스는 동일한 비즈니스 도메인에 대해 일관 된 상태로 서비스 동일한 데이터를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-120">More importantly, the services could share the same data, as long as these services are cohesive with respect to the same business domain.</span></span>

![](./media/image8.png)

<span data-ttu-id="4ead4-121">**그림 4-8**합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-121">**Figure 4-8**.</span></span> <span data-ttu-id="4ead4-122">여러 개의 물리적 서비스를 비즈니스 마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="4ead4-122">Business microservice with several physical services</span></span>

<span data-ttu-id="4ead4-123">이 예제에서 서비스 웹 API 서비스는 검색 서비스와 동일한 데이터를 대상으로 하기 때문에 동일한 데이터 모델을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-123">The services in the example share the same data model because the Web API service targets the same data as the Search service.</span></span> <span data-ttu-id="4ead4-124">따라서 비즈니스 마이크로 서비스의 실제 구현에서 분할 하는 기능을 하는 확장할 수 있습니다 각 내부 서비스의 위로 또는 아래로 필요에 따라 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-124">So, in the physical implementation of the business microservice, you are splitting that functionality so you can scale each of those internal services up or down as needed.</span></span> <span data-ttu-id="4ead4-125">이전 웹 API 서비스 필요 일반적으로 더 인스턴스에 보다 검색 서비스 또는 그 반대로입니다.)</span><span class="sxs-lookup"><span data-stu-id="4ead4-125">Maybe the Web API service usually needs more instances than the Search service, or vice versa.)</span></span>

<span data-ttu-id="4ead4-126">즉, microservices의 논리적 아키텍처 항상 않아도 실제 배포 아키텍처와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-126">In short, the logical architecture of microservices does not always have to coincide with the physical deployment architecture.</span></span> <span data-ttu-id="4ead4-127">이 가이드에는 마이크로 서비스 언급 때마다 의미 비즈니스 또는 하나 이상의 서비스에 매핑할 수 있는 논리 마이크로 서비스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-127">In this guide, whenever we mention a microservice, we mean a business or logical microservice that could map to one or more services.</span></span> <span data-ttu-id="4ead4-128">대부분의 경우에서이 이름은 단일 서비스 이지만 더 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ead4-128">In most cases, this will be a single service, but it might be more.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="4ead4-129">[이전] (데이터-sovereignty-당-microservice.md) [다음] (distributed-데이터-management.md)</span><span class="sxs-lookup"><span data-stu-id="4ead4-129">[Previous] (data-sovereignty-per-microservice.md) [Next] (distributed-data-management.md)</span></span>
