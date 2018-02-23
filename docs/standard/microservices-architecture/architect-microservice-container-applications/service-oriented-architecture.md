---
title: "서비스 지향 아키텍처"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 서비스 지향 아키텍처"
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
ms.openlocfilehash: 6a5f0f53f4208c9944adea33fe1aa3f35fed81ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="8ee68-104">서비스 지향 아키텍처</span><span class="sxs-lookup"><span data-stu-id="8ee68-104">Service-oriented architecture</span></span> 

<span data-ttu-id="8ee68-105">SOA(서비스 지향 아키텍처)라는 용어는 남용되었으며 사람들 사이에서 여러 의미로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="8ee68-106">하지만 한 가지 공통 분모가 있으니, SOA는 응용 프로그램을 하위 시스템 또는 계층 같은 다양한 유형으로 분류할 수 있는 여러 서비스로 구성 해제하여(가장 일반적으로 HTTP 서비스) 응용 프로그램을 만든다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="8ee68-107">이제 이러한 서비스는 모든 종속성이 컨테이너 이미지에 포함되므로 배포 문제를 해결하는 Docker 컨테이너로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="8ee68-108">그러나 SOA 응용 프로그램을 강화해야 하는데, 단일 Docker 호스트를 기반으로 배포하는 경우 확장성 및 가용성 문제에 직면할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="8ee68-109">이때 Docker 클러스터링 소프트웨어 또는 오케스트레이터가 도움이 되며, 이에 대한 내용은 뒷부분에 나오는 마이크로 서비스에 대한 배포 접근 방식을 설명하는 섹션에서 다루겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="8ee68-110">Docker 컨테이너는 기존의 서비스 지향 아키텍처와 보다 발전된 마이크로 서비스 아키텍처 모두에 유용합니다(하지만 필수는 아님).</span><span class="sxs-lookup"><span data-stu-id="8ee68-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="8ee68-111">마이크로 서비스가 SOA에서 파생되지만, SOA는 마이크로 서비스 아키텍처와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="8ee68-112">대형 중앙 브로커, 조직 수준의 중앙 오케스트레이터, [ESB(Enterprise Service Bus)](https://en.wikipedia.org/wiki/Enterprise_service_bus) 같은 기능은 SOA에서 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="8ee68-113">하지만 대부분의 경우 이러한 기능은 마이크로 서비스 커뮤니티의 안티패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="8ee68-114">사실, 일부 사람들은 "마이크로 서비스 아키텍처는 SOA를 제대로 만든 것"이라고 주장합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="8ee68-115">SOA 접근 방식은 마이크로 서비스 아키텍처에 사용되는 요구 사항 및 기술보다 덜 규범적이므로 이 가이드에서는 마이크로 서비스를 집중적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="8ee68-116">마이크로 서비스 기반 응용 프로그램을 빌드하는 방법을 알고 있는 분들은 그보다 더 간단한 서비스 지향 응용 프로그램을 빌드하는 방법도 알고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee68-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="8ee68-117">[이전] (docker-application-state-data.md) [다음] (microservices-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="8ee68-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
