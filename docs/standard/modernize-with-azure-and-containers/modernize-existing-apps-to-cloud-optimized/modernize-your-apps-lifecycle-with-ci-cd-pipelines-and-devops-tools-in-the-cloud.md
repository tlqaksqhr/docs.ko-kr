---
title: 현대화 CI/CD 파이프라인 및 DevOps 도구로 클라우드에서 앱의 수명 주기
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | 현대화 CI/CD 파이프라인 및 DevOps 도구로 클라우드에서 앱의 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 63907a1911b4c95f0dbecb2af33964225cf3e7b1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="c8e61-103">현대화 CI/CD 파이프라인 및 DevOps 도구로 클라우드에서 앱의 수명 주기</span><span class="sxs-lookup"><span data-stu-id="c8e61-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="c8e61-104">오늘날의 비즈니스 경쟁 시장에 포함 되도록 빠른 속도로 혁신 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="c8e61-105">DevOps 도구와 프로세스 혁신 주기적으로이 구현 하는 데 중요 한 최신 응용 프로그램 필요 높은 품질을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="c8e61-106">오른쪽 DevOps 도구와 함께 개발자 연속 배포를 효율적이 고 사용자의 혁신적인 응용 프로그램에 보다 신속 하 게 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="c8e61-107">연속 통합 및 배포 사례는 잘 구성, 특히 다중 컨테이너 응용 프로그램을 사용 하 여 작업할 때 컨테이너의 도입 새로운 고려 사항을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="c8e61-108">Visual Studio Team Services에는 연속 통합 및 다양 한 공식 Team Services 배포 작업을 수행 하는 환경에 여러 컨테이너 응용 프로그램 배포를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-108">Visual Studio Team Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Team Services deployment tasks:</span></span>

-   <span data-ttu-id="c8e61-109">[독립 실행형 Docker 호스트 VM에 배포](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux 또는 Windows Server 2016 이상)</span><span class="sxs-lookup"><span data-stu-id="c8e61-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

-   [<span data-ttu-id="c8e61-110">서비스 패브릭에 배포</span><span class="sxs-lookup"><span data-stu-id="c8e61-110">Deploy to Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [<span data-ttu-id="c8e61-111">Azure 컨테이너 서비스 – Kubernetes에 배포</span><span class="sxs-lookup"><span data-stu-id="c8e61-111">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="c8e61-112">또한에 배포할 수 있지만 [docker는 Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) 또는 DC/Team Services 스크립트 기반 작업을 사용 하 여 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-112">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Team Services script-based tasks.</span></span>

<span data-ttu-id="c8e61-113">배포 민첩성을 촉진를 계속 하려면 이러한 도구는 다양 한 개발 및 CI/CD 솔루션으로 컨테이너 작업에 대 한 뛰어난 dev 테스트-에-프로덕션에 배포 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-113">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="c8e61-114">그림 4-12 Kubernetes 클러스터 컨테이너 서비스를 Azure에 배포 하는 연속 배포 파이프라인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8e61-114">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Visual Studio Team Services 연속 배포 파이프라인을 Kubernetes 클러스터에 배포](./media/image12.png)

> <span data-ttu-id="c8e61-116">**그림 4-12입니다.**</span><span class="sxs-lookup"><span data-stu-id="c8e61-116">**Figure 4-12.**</span></span> <span data-ttu-id="c8e61-117">Visual Studio Team Services 연속 배포 파이프라인을 Kubernetes 클러스터에 배포</span><span class="sxs-lookup"><span data-stu-id="c8e61-117">Visual Studio Team Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="c8e61-118">[이전](modernize-your-apps-with-monitoring-and-telemetry.md)
[다음](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="c8e61-118">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
