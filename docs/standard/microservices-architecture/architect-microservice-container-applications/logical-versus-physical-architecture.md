---
title: "논리적 아키텍처 대 물리적 아키텍처"
description: "컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | 논리적 아키텍처 대 물리적 아키텍처"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b08a5b8fb8f9df8a9a0a821fa85f1f6a94fce2d3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="logical-architecture-versus-physical-architecture"></a><span data-ttu-id="3935b-104">논리적 아키텍처 대 물리적 아키텍처</span><span class="sxs-lookup"><span data-stu-id="3935b-104">Logical architecture versus physical architecture</span></span>

<span data-ttu-id="3935b-105">이 시점에서 논리적 아키텍처와 물리적 아키텍처 사이의 차이점과 이것이 마이크로 서비스 기반 응용 프로그램의 디자인에 어떻게 적용되는지를 설명하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-105">It is useful at this point to stop and discuss the distinction between logical architecture and physical architecture, and how this applies to the design of microservice-based applications.</span></span>

<span data-ttu-id="3935b-106">시작하려면, 마이크로 서비스를 빌드하는데 특정 기술을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-106">To begin, building microservices does not require the use of any specific technology.</span></span> <span data-ttu-id="3935b-107">예를 들어, 마이크로 서비스 기반 아키텍처를 만들기 위해 Docker 컨테이너가 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-107">For instance, Docker containers are not mandatory in order to create a microservice-based architecture.</span></span> <span data-ttu-id="3935b-108">이러한 마이크로 서비스는 일반 프로세스로도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-108">Those microservices could also be run as plain processes.</span></span> <span data-ttu-id="3935b-109">마이크로 서비스는 논리적 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-109">Microservices is a logical architecture.</span></span>

<span data-ttu-id="3935b-110">또한, 마이크로 서비스가 물리적으로 단일 서비스, 프로세스 또는 컨테이너로 구현될 수 있는 경우에도(간단히 하기 위해, 이것이 [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)의 초기 버전에서 취한 접근법입니다.), 수십 또는 수백의 서비스로 구성된 크고 복잡한 응용 프로그램을 빌드할 때 비즈니스 마이크로 서비스와 물리적 서비스 또는 컨테이너 간의 패리티는 모든 경우에 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-110">Moreover, even when a microservice could be physically implemented as a single service, process, or container (for simplicity’s sake, that is the approach taken in the initial version of [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)), this parity between business microservice and physical service or container is not necessarily required in all cases when you build a large and complex application composed of many dozens or even hundreds of services.</span></span>

<span data-ttu-id="3935b-111">여기에 응용 프로그램의 논리적 아키텍처와 물리적 아키텍처 사이에 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-111">This is where there is a difference between an application’s logical architecture and physical architecture.</span></span> <span data-ttu-id="3935b-112">시스템의 논리적 아키텍처와 논리적 경계는 반드시 일대일로 물리적 또는 배포 아키텍처에 매핑되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-112">The logical architecture and logical boundaries of a system do not necessarily map one-to-one to the physical or deployment architecture.</span></span> <span data-ttu-id="3935b-113">그것은 발생할 수 있지만, 종종 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-113">It can happen, but it often does not.</span></span>

<span data-ttu-id="3935b-114">특정 비즈니스 마이크로 서비스 또는 경계 컨텍스트를 식별했을 수도 있지만, 비지니스 마이크로 서비스마다 하나의 서비스(예: ASP.NET Web API) 또는 단일 Docker 컨테이너를 만들어서 구현하는 것이 언제나 가장 좋은 방법이라는 것을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-114">Although you might have identified certain business microservices or Bounded Contexts, it does not mean that the best way to implement them is always by creating a single service (such as an ASP.NET Web API) or single Docker container for each business microservice.</span></span> <span data-ttu-id="3935b-115">각 비즈니스 마이크로 서비스가 단일 서비스 또는 컨테이너를 사용하여 구현되어야 한다는 규칙을 갖는 것은 너무 엄격합니다. </span><span class="sxs-lookup"><span data-stu-id="3935b-115">Having a rule saying each business microservice has to be implemented using a single service or container is too rigid.</span></span>

<span data-ttu-id="3935b-116">따라서 비즈니스 마이크로 서비스 또는 경계 컨텍스트는 물리적 아키텍처와 일치하거나 또는 그렇지 않을 수도 있는 논리적 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-116">Therefore, a business microservice or Bounded Context is a logical architecture that might coincide (or not) with physical architecture.</span></span> <span data-ttu-id="3935b-117">중요한 점은 비즈니스 마이크로 서비스 또는 경계 컨텍스트는 코드와 상태를 독립적으로 버전 관리, 배포 및 크기를 조정할 수 있도록 자율적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-117">The important point is that a business microservice or Bounded Context must be autonomous by allowing code and state to be independently versioned, deployed, and scaled.</span></span>

<span data-ttu-id="3935b-118">그림 4-8에서 볼 수 있듯이, 카탈로그 비즈니스 마이크로 서비스는 여러 서비스 또는 프로세스로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-118">As Figure 4-8 shows, the catalog business microservice could be composed of several services or processes.</span></span> <span data-ttu-id="3935b-119">이들은 여러 ASP.NET Web API 서비스 또는 HTTP 또는 다른 프로토콜을 사용하는 다른 종류의 서비스일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-119">These could be multiple ASP.NET Web API services or any other kind of services using HTTP or any other protocol.</span></span> <span data-ttu-id="3935b-120">더 중요한 것은, 이들 서비스가 동일한 비즈니스 도메인과 관련하여 응집력을 갖는 한 동일한 데이터를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-120">More importantly, the services could share the same data, as long as these services are cohesive with respect to the same business domain.</span></span>

![](./media/image8.png)

<span data-ttu-id="3935b-121">**그림 4-8**.</span><span class="sxs-lookup"><span data-stu-id="3935b-121">**Figure 4-8**.</span></span> <span data-ttu-id="3935b-122">여러 물리적 서비스가 있는 비즈니스 마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="3935b-122">Business microservice with several physical services</span></span>

<span data-ttu-id="3935b-123">웹 API 서비스가 Search 서비스와 동일한 데이터를 대상으로 하기 때문에 예제의 서비스는 동일한 데이터 모델을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-123">The services in the example share the same data model because the Web API service targets the same data as the Search service.</span></span> <span data-ttu-id="3935b-124">따라서 비즈니스 마이크로 서비스의 실제 구현에서는 해당 기능을 분리하여 필요에 따라 각 내부 서비스를 확장 또는 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-124">So, in the physical implementation of the business microservice, you are splitting that functionality so you can scale each of those internal services up or down as needed.</span></span> <span data-ttu-id="3935b-125">아마도 웹 API 서비스는 일반적으로 검색보다 많은 인스턴스가 필요하거나 또는 그 반대일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-125">Maybe the Web API service usually needs more instances than the Search service, or vice versa.)</span></span>

<span data-ttu-id="3935b-126">즉, 마이크로 서비스의 논리적 아키텍처가 항상 물리적 배포 아키텍처와 일치하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-126">In short, the logical architecture of microservices does not always have to coincide with the physical deployment architecture.</span></span> <span data-ttu-id="3935b-127">이 가이드에서는 마이크로 서비스에 대해 언급할 때마다 하나 이상의 서비스에 매핑될 수 있는 비즈니스 또는 논리적 마이크로 서비스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-127">In this guide, whenever we mention a microservice, we mean a business or logical microservice that could map to one or more services.</span></span> <span data-ttu-id="3935b-128">대부분의 사례에서 이것은 단일 서비스이지만 더 많을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3935b-128">In most cases, this will be a single service, but it might be more.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="3935b-129">[이전](data-sovereignty-per-microservice.md) [다음](distributed-data-management.md)</span><span class="sxs-lookup"><span data-stu-id="3935b-129">[Previous] (data-sovereignty-per-microservice.md) [Next] (distributed-data-management.md)</span></span>
