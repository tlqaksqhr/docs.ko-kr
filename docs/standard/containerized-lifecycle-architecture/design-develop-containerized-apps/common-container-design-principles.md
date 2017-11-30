---
title: "공용 컨테이너 디자인 원칙"
description: "Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 된 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d7186ae3b768384fe5c6b269578de8db5ef6064c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="common-container-design-principles"></a><span data-ttu-id="5fa5e-104">공용 컨테이너 디자인 원칙</span><span class="sxs-lookup"><span data-stu-id="5fa5e-104">Common container design principles</span></span>

<span data-ttu-id="5fa5e-105">앞의 개발 프로세스에 있는 경우 관련 하 여 컨테이너를 사용 하는 방법을 알면 몇 가지 기본 개념</span><span class="sxs-lookup"><span data-stu-id="5fa5e-105">Ahead of getting into the development process there are a few basic concepts worth mentioning with regard to how you use containers.</span></span>

## <a name="container-equals-a-process"></a><span data-ttu-id="5fa5e-106">컨테이너는 프로세스를 같음</span><span class="sxs-lookup"><span data-stu-id="5fa5e-106">Container equals a process</span></span>

<span data-ttu-id="5fa5e-107">컨테이너 모델의 컨테이너는 단일 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-107">In the container model, a container represents a single process.</span></span> <span data-ttu-id="5fa5e-108">컨테이너 프로세스 경계를 정의 하면 눈금 또는 일괄 처리 오프, 프로세스에 사용 되는 기본 형식을 만드는 데 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-108">By defining a container as a process boundary, you begin to create the primitives used to scale, or batch-off, processes.</span></span> <span data-ttu-id="5fa5e-109">Docker 컨테이너를 실행 하면 표시 됩니다는 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-109">When you run a Docker container, you'll see an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) definition.</span></span> <span data-ttu-id="5fa5e-110">프로세스 및 컨테이너의 수명을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-110">This defines the process and the lifetime of the container.</span></span> <span data-ttu-id="5fa5e-111">프로세스가 완료 되 면 컨테이너 수명 주기에 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-111">When the process completes, the container life cycle ends.</span></span> <span data-ttu-id="5fa5e-112">웹 서버 및 Microsoft Azure로 구현 했을 수 있는 일괄 처리 작업, 수명이 짧은 프로세스와 같은 장기 실행 프로세스는 [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-112">There are long-running processes, such as web servers, and short-lived processes, such as batch jobs, which might have been implemented as Microsoft Azure [WebJobs](https://azure.microsoft.com/en-us/documentation/articles/websites-webjobs-resources/).</span></span> <span data-ttu-id="5fa5e-113">프로세스에 실패할 경우 컨테이너가 종료되며 조정자가 이어서 프로세스를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-113">If the process fails, the container ends, and the orchestrator takes over.</span></span> <span data-ttu-id="5fa5e-114">Orchestrator를 실행 하는 5 개의 인스턴스를 유지 하도록 지정 된 하나에 오류가 발생 하는 경우 orchestrator 오류가 발생 한 프로세스를 바꾸려면 다른 컨테이너로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-114">If the orchestrator was instructed to keep five instances running and one fails, the orchestrator will create another container to replace the failed process.</span></span> <span data-ttu-id="5fa5e-115">일괄 작업에서 프로세스는 매개 변수와 함께 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-115">In a batch job, the process is started with parameters.</span></span> <span data-ttu-id="5fa5e-116">프로세스가 완료되면 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-116">When the process completes, the work is complete.</span></span>

<span data-ttu-id="5fa5e-117">여러 프로세스를 단일 컨테이너에서 실행 하려는 시나리오를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-117">You might find a scenario in which you want multiple processes running in a single container.</span></span> <span data-ttu-id="5fa5e-118">아키텍처 문서의 되지 않습니다는 "사용 안 함," 없고 항상는 "항상"입니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-118">In any architecture document, there's never a "never," nor is there always an "always."</span></span> <span data-ttu-id="5fa5e-119">사용 하는 일반적인 패턴은 여러 프로세스를 요구 하는 시나리오에 대 한 [감독자](http://supervisord.org/)합니다.</span><span class="sxs-lookup"><span data-stu-id="5fa5e-119">For scenarios requiring multiple processes, a common pattern is to use [Supervisor](http://supervisord.org/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="5fa5e-120">[이전] (디자인-docker-applications.md) [다음] (모놀리식 applications.md)</span><span class="sxs-lookup"><span data-stu-id="5fa5e-120">[Previous] (design-docker-applications.md) [Next] (monolithic-applications.md)</span></span>
