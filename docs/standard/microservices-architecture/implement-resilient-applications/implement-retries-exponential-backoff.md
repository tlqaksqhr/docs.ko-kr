---
title: 지수 백오프를 사용하여 다시 시도 구현
description: 컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | 지수 백오프를 사용하여 다시 시도 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 7f909c6f81abce80bfdf118112271f1f87254793
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="f12fd-103">지수 백오프를 사용하여 다시 시도 구현</span><span class="sxs-lookup"><span data-stu-id="f12fd-103">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="f12fd-104">[ *지수 백오프를 사용하여 다시 시도*](https://docs.microsoft.com/azure/architecture/patterns/retry)는 최대 다시 시도 횟수에 도달할 때까지 대기 시간이 기하급수적으로 증가하면서 다시 시도하려고 하는 기술입니다([지수 백오프](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="f12fd-104">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="f12fd-105">이 기술은 클라우드 리소스가 어떤 이유로든 몇 초간 일시적으로 사용할 수 없다는 팩트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f12fd-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="f12fd-106">예를 들어 오케스트레이터는 클러스터에서 부하 분산을 위해 컨테이너를 다른 노드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f12fd-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="f12fd-107">이 시간 동안 일부 요청이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f12fd-107">During that time, some requests might fail.</span></span> <span data-ttu-id="f12fd-108">또 다른 예로 SQL Azure와 같은 데이터베이스를 들 수 있습니다. SQL Azure에서는 부하 분산을 위해 데이터베이스를 다른 서버로 옮길 수 있으므로 데이터베이스를 몇 초간 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f12fd-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="f12fd-109">지수 백오프를 사용하여 다시 시도 논리를 구현하는 많은 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f12fd-109">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f12fd-110">[이전] (partial-failure-strategies.md) [다음] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="f12fd-110">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
