---
title: SOA 응용 프로그램
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5f60ff2fb1567d08b9e51e14ce5660a8e42f54aa
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="soa-applications"></a><span data-ttu-id="6650f-103">SOA 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="6650f-103">SOA applications</span></span>

<span data-ttu-id="6650f-104">SOA 과도 한 용어 되었으며 다른 사람에 게 많은 다른 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="6650f-105">하지만 (가장 일반적으로 HTTP 서비스)와 다른 형식으로 분류할 수 있는 여러 서비스에서 분해 하 여 응용 프로그램의 아키텍처 구조 하는 하위 시스템에는 최소한와 공통 분모, SOA, 또는 서비스 방향, 평균 등의 또는 계층으로 다른 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="6650f-106">오늘으로 배포할 수 있습니다 이러한 서비스를, Docker 컨테이너 종속성의 모든 컨테이너 이미지 내에 포함 되어 있으므로 배포 관련 문제를 해결 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="6650f-107">그러나 확장 Soa 해야 할 경우에 따라 단일 인스턴스를 배포 하는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="6650f-108">여기서 클러스터링 소프트웨어 또는 orchestrator Docker를 통해 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="6650f-109">살펴보게이 다음 섹션에서 자세히 microservices 접근 방식을 살펴볼 때는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="6650f-110">일의 끝 컨테이너 클러스터링 솔루션은 각 마이크로 서비스는 해당 데이터 모델을 소유 하는 고급 microservices 아키텍처 또는 기존의 SOA 아키텍처에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="6650f-111">및, 여러 데이터베이스를 통해 있습니다도 수 확장 SOA 서비스에서 공유 되는 모놀리식 데이터베이스와 함께 작업 하지 않고 데이터 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="6650f-112">그러나 데이터를 분할 하는 방법에 대 한 토론 순수 하 게에 대 한 아키텍처 및 디자인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6650f-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6650f-113">[이전] [다음] (오케스트레이션-높은-확장성-availability.md) (state-and-data-in-docker-applications.md)</span><span class="sxs-lookup"><span data-stu-id="6650f-113">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>
