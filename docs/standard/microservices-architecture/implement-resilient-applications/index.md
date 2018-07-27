---
title: 복원력 있는 응용 프로그램 구현
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 복원력 있는 응용 프로그램 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: dc0db8f0cdfa77bcca467c3c632b3d93de8851d8
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37875126"
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="43a69-103">복원력 있는 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="43a69-103">Implementing Resilient Applications</span></span>

<span data-ttu-id="43a69-104">*마이크로 서비스와 클라우드 기반 응용 프로그램에서는 결국 발생하게 되는 부분 오류를 수용해야 합니다. 부분 오류에 탄력적으로 대처할 수 있도록 응용 프로그램을 디자인해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="43a69-104">*Your microservice and cloud-based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="43a69-105">복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-105">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="43a69-106">이는 오류를 방지하는 기능이 아닌 오류가 발생할 수 있다는 사실을 받아들이고 가동 중지 시간 또는 데이터 손실을 방지할 수 있도록 해당 오류에 응답하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-106">It is not about avoiding failures but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="43a69-107">복원력의 목표는 오류 발생 후 응용 프로그램을 완전히 작동 중인 상태로 되돌리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-107">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="43a69-108">마이크로 서비스 기반 응용 프로그램을 디자인하고 배포하기는 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-108">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="43a69-109">그러나 일부 오류가 명확히 발생하는 환경에서 응용 프로그램을 계속 실행하는 작업도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-109">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="43a69-110">따라서 응용 프로그램에 복원력이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-110">Therefore, your application should be resilient.</span></span> <span data-ttu-id="43a69-111">응용 프로그램은 클라우드에서의 네트워크 중단 또는 노드 또는 VM 충돌과 같은 부분 오류에 대처할 수 있도록 디자인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-111">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="43a69-112">클러스터 내에서 다른 노드로 이동한 마이크로 서비스(컨테이너)도 응용 프로그램에서 일시적 단기 오류를 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-112">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="43a69-113">응용 프로그램의 여러 개별 구성 요소도 상태 모니터링 기능과 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-113">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="43a69-114">이 장의 지침을 따라 가동 중지 시간 또는 복잡한 클라우드 기반 배포의 일반적인 문제가 발생하는 환경에서도 원활하게 작동하는 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43a69-114">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="43a69-115">[이전](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[다음](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="43a69-115">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>
