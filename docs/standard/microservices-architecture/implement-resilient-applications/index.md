---
title: 복원력 있는 응용 프로그램 구현
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 복원력 있는 응용 프로그램 구현
keywords: Docker, 마이크로 서비스, ASP.NET, 컨테이너
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 93e5435b402cc1a8ff049f25465de0f719516f31
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="0c467-104">복원력 있는 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="0c467-104">Implementing Resilient Applications</span></span>

<span data-ttu-id="0c467-105">*마이크로 서비스와 클라우드 기반 응용 프로그램에서는 결국 발생하게 되는 부분 오류를 수용해야 합니다. 부분 오류에 탄력적으로 대처할 수 있도록 응용 프로그램을 디자인해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="0c467-105">*Your microservice and cloud based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="0c467-106">복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="0c467-107">이는 오류를 방지하는 기능이 아닌 오류가 발생할 수 있다는 사실을 받아들이고 가동 중지 시간 또는 데이터 손실을 방지할 수 있도록 해당 오류에 응답하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-107">It is not about avoiding failures, but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="0c467-108">복원력의 목표는 오류 발생 후 응용 프로그램을 완전히 작동 중인 상태로 되돌리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="0c467-109">마이크로 서비스 기반 응용 프로그램을 디자인하고 배포하기는 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-109">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="0c467-110">그러나 일부 오류가 명확히 발생하는 환경에서 응용 프로그램을 계속 실행하는 작업도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-110">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="0c467-111">따라서 응용 프로그램에 복원력이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-111">Therefore, your application should be resilient.</span></span> <span data-ttu-id="0c467-112">응용 프로그램은 클라우드에서의 네트워크 중단 또는 노드 또는 VM 충돌과 같은 부분 오류에 대처할 수 있도록 디자인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-112">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="0c467-113">클러스터 내에서 다른 노드로 이동한 마이크로 서비스(컨테이너)도 응용 프로그램에서 일시적 단기 오류를 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-113">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="0c467-114">응용 프로그램의 여러 개별 구성 요소도 상태 모니터링 기능과 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-114">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="0c467-115">이 장의 지침을 따라 가동 중지 시간 또는 복잡한 클라우드 기반 배포의 일반적인 문제가 발생하는 환경에서도 원활하게 작동하는 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c467-115">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="0c467-116">[이전] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [다음] (handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="0c467-116">[Previous] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Next] (handle-partial-failure.md)</span></span>
