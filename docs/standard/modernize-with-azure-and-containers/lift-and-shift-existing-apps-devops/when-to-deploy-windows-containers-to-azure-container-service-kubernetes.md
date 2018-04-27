---
title: Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우
description: 컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cccf78ef5b7683a2eefa3efab50a7bbe1bffda18
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="e9a6b-103">Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우</span><span class="sxs-lookup"><span data-stu-id="e9a6b-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="e9a6b-104">Azure 컨테이너 서비스를 Azure에 맞게 인기 있는 오픈 소스 도구 및 기술 구성을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a6b-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="e9a6b-105">사용자 컨테이너 및 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기</span><span class="sxs-lookup"><span data-stu-id="e9a6b-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="e9a6b-106">Orchestrator 도구, 호스트, 수 및 크기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a6b-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="e9a6b-107">Azure 컨테이너 서비스를 인프라를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a6b-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="e9a6b-108">Kubernetes, docker는 Docker Swarm 또는 DC/OS와 같은 오픈 소스 orchestrators와 이미 작업 하는 경우에 기존 관리 명시할 컨테이너 작업을 클라우드로 이동할 수를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9a6b-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="e9a6b-109">이미 익숙한, 사용자가 선택한 orchestrator에 대 한 표준 API 끝점을 통해 연결 하는 응용 프로그램 관리 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a6b-109">Use the application management tools that you're already familiar with, and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="e9a6b-110">사용 하는 것 이지만, Linux Docker 컨테이너도 지원 Windows 컨테이너 2017 (이전와 최근 orchestrator에 따라)의으로 하는 경우 이러한 모든 orchestrators 완성도 높은 환경을 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9a6b-110">All these orchestrators are mature environments if you are using Linux Docker containers, but they also support Windows Containers as of 2017 (some earlier, some more recently, depending on the orchestrator).</span></span>

<span data-ttu-id="e9a6b-111">예를 들어 Kubernetes, 컨테이너에 대 한 지원은 Windows 컨테이너 Kubernetes에 사용 하 여 네이티브 (첫 번째 클래스 시민) 매우 효과적이 고 신뢰할 수 있는 이기도 (미리 보기 될 때까지 초기 대체 2017).</span><span class="sxs-lookup"><span data-stu-id="e9a6b-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also very effective and reliable (in preview until early fall 2017).</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e9a6b-112">[이전](when-to-deploy-windows-containers-to-service-fabric.md)
[다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="e9a6b-112">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
