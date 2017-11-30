---
title: "지 수 백오프 함께 다시 시도 구현합니다."
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 지 수 백오프 함께 다시 시도 구현합니다."
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8ad8c6363ddff59915efc076161fe6b76074bbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-retries-with-exponential-backoff"></a><span data-ttu-id="46b45-104">지 수 백오프 함께 다시 시도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="46b45-104">Implementing retries with exponential backoff</span></span>

<span data-ttu-id="46b45-105">[*지 수 백오프 하 여 다시 시도* ](https://docs.microsoft.com/azure/architecture/patterns/retry) 는 최대 재시도 횟수에 도달할 때까지 기하급수적으로 증가 함에 따라 대기 시간이 작업을 다시 시도 하려고 하는 방법 (의 [지 수 백오프](https://en.wikipedia.org/wiki/Exponential_backoff)).</span><span class="sxs-lookup"><span data-stu-id="46b45-105">[*Retries with exponential backoff*](https://docs.microsoft.com/azure/architecture/patterns/retry) is a technique that attempts to retry an operation, with an exponentially increasing wait time, until a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="46b45-106">이 기술은 클라우드 리소스 일시적으로 사용할 수 없습니다 어떤 이유로 든 몇 초간 팩트를 수용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b45-106">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="46b45-107">예를 들어는 orchestrator를 부하 분산에 대 한 클러스터의 다른 노드로 컨테이너를 이동 될을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b45-107">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="46b45-108">이 시간 동안 일부 요청이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b45-108">During that time, some requests might fail.</span></span> <span data-ttu-id="46b45-109">또 다른 예로 데이터베이스 수 이동할 다른 서버에 부하 분산, 되어 데이터베이스의 몇 초 동안 사용할 수 없게 되는 SQL Azure와 같은 데이터베이스를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b45-109">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="46b45-110">지 수 백오프와 재시도 논리를 구현 하는 방법은 여러 가지.</span><span class="sxs-lookup"><span data-stu-id="46b45-110">There are many approaches to implement retries logic with exponential backoff.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="46b45-111">[이전] (부분-실패-strategies.md) [다음] (implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="46b45-111">[Previous] (partial-failure-strategies.md) [Next] (implement-resilient-entity-framework-core-sql-connections.md)</span></span>
