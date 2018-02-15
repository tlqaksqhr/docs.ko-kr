---
title: "Docker는 무엇입니까?"
description: "Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c75b2fa87e5aad93693c76c3bbd135044b36525f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="what-is-docker"></a><span data-ttu-id="7688e-104">Docker는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="7688e-104">What is Docker?</span></span>

<span data-ttu-id="7688e-105">[Docker](https://www.docker.com/) 는 [오픈 소스 프로젝트](https://github.com/docker/docker) 클라우드 또는 온-프레미스에서 실행할 수 있는 휴대용, 스페이스인 컨테이너로 응용 프로그램의 배포를 자동화 하는 데 (참조 그림 1-2).</span><span class="sxs-lookup"><span data-stu-id="7688e-105">[Docker](https://www.docker.com/) is an [open-source project](https://github.com/docker/docker) for automating the deployment of applications as portable, self-sufficient containers that can run in the cloud or on-premises (see Figure 1-2).</span></span> <span data-ttu-id="7688e-106">Docker 이기도 한 [회사](https://www.docker.com/) 장려 하 고이 기술은 클라우드, Linux 및 Windows 공급 업체를 비롯 하 여 Microsoft와의 공동 작업에서 작업을 개발 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-106">Docker is also a [company](https://www.docker.com/) that promotes and develops this technology, working in collaboration with cloud, Linux, and Windows vendors, including Microsoft.</span></span>

![](./media/image2.png)

<span data-ttu-id="7688e-107">Docker 그림 1-2: 하이브리드 클라우드의 모든 계층에서 컨테이너를 배포</span><span class="sxs-lookup"><span data-stu-id="7688e-107">Figure 1-2: Docker deploys containers at all layers of the hybrid cloud</span></span>

<span data-ttu-id="7688e-108">Linux와 Windows에서 docker 이미지 컨테이너 고유 하 게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-108">Docker image containers can run natively on Linux and Windows.</span></span> <span data-ttu-id="7688e-109">그러나 Windows 이미지는 Windows 호스트에 대해서만 실행할 수 있습니다 및 Linux 이미지 Linux 호스트를 호스트 서버 또는 VM에 대해서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-109">However, Windows images can run only on Windows hosts and Linux images can run only on Linux hosts, meaning a host server or a VM.</span></span>

<span data-ttu-id="7688e-110">개발자는 Windows, Linux 또는 macOS에서 개발 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-110">Developers can use development environments on Windows, Linux, or macOS.</span></span> <span data-ttu-id="7688e-111">개발 컴퓨터에서 개발자는 docker 이미지 배포 응용 프로그램 및 해당 종속성을 포함 하 여 Docker 호스트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-111">On the development computer, the developer runs a Docker host to which Docker images are deployed, including the app and its dependencies.</span></span> <span data-ttu-id="7688e-112">Linux 기반, Docker 호스트를 사용 하 여 linux 또는 Mac에서 작업 하는 개발자 및 Linux 컨테이너에 대 한 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-112">Developers who work on Linux or on the Mac use a Docker host that is Linux based, and they can create images only for Linux containers.</span></span> <span data-ttu-id="7688e-113">(Mac에서 작업 하는 개발자 코드를 편집 하거나 Docker 명령줄 인터페이스를 실행할 수 \[CLI\] 컨테이너에서 macOS 등 했지만,이 문서의 작성일, macOS에서 직접 실행 되지 않습니다.) Windows에서 작업 하는 개발자는 Linux 또는 Windows 컨테이너에 대 한 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-113">(Developers working on the Mac can edit code or run the Docker command-line interface \[CLI\] from macOS, but, as of this writing, containers do not run directly on macOS.) Developers who work on Windows can create images for either Linux or Windows Containers.</span></span>

<span data-ttu-id="7688e-114">Docker 컨테이너 개발 환경에서 호스팅하고 개발자를 위한 추가 도구를 제공, 제공 [Docker Community Edition (CE)](https://www.docker.com/community-edition) macOS 또는 Windows에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-114">To host containers in development environments and provide additional developer tools, Docker ships [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows or for macOS.</span></span> <span data-ttu-id="7688e-115">이러한 제품에 필요한 VM (Docker 호스트)를 사용 하는 컨테이너 호스트 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-115">These products install the necessary VM (the Docker host) to host the containers.</span></span> <span data-ttu-id="7688e-116">Docker도 사용할 수 있도록 [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), 엔터프라이즈 개발을 위해 설계 하 고 작성 하는 IT 팀에서 사용 하는, 배송, 및 프로덕션 환경에서 큰 업무에 중요 한 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-116">Docker also makes available [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), which is designed for enterprise development and is used by IT teams who build, ship, and run large business-critical applications in production.</span></span>

<span data-ttu-id="7688e-117">실행 하려면 [Windows 컨테이너](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview), 두 가지 방법으로 런타임:</span><span class="sxs-lookup"><span data-stu-id="7688e-117">To run [Windows Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview), there are two types of runtimes:</span></span>

-   <span data-ttu-id="7688e-118">**Windows Server 컨테이너** 이 런타임 프로세스 및 네임 스페이스 격리 기술을 통해 응용 프로그램 격리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-118">**Windows Server Container** This runtime provides application isolation through process and namespace isolation technology.</span></span> <span data-ttu-id="7688e-119">Windows Server 컨테이너 호스트에서 실행 되는 모든 컨테이너와 컨테이너 호스트와 커널을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-119">A Windows Server Container shares a kernel with the container host and with all containers running on the host.</span></span>

-   <span data-ttu-id="7688e-120">**Hyper-v 컨테이너** 이 각 컨테이너를 고도로 최적화 된 VM에서 실행 하 여 Windows Server 컨테이너에서 제공 하는 격리를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-120">**Hyper-V Container** This expands on the isolation provided by Windows Server Containers by running each container in a highly optimized VM.</span></span> <span data-ttu-id="7688e-121">이 구성에서는 컨테이너 호스트의 커널은 더 나은 격리를 제공 하는 Hyper-v 컨테이너와 공유 되지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-121">In this configuration, the kernel of the container host is not shared with the Hyper-V Containers, providing better isolation.</span></span>

<span data-ttu-id="7688e-122">이러한 컨테이너에 대 한 이미지에 동일한 방식으로 만들어지며 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-122">The images for these containers are created in the same way and function the same.</span></span> <span data-ttu-id="7688e-123">차이점은 컨테이너 이미지에서 만들어지는 방법을-추가 매개 변수가 필요한 Hyper-v 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-123">The difference is in how the container is created from the image—running a Hyper-V Container requires an extra parameter.</span></span> <span data-ttu-id="7688e-124">자세한 내용은 참조 [Hyper-v 컨테이너](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-124">For details, see [Hyper-V Containers](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).</span></span>

## <a name="comparing-docker-containers-with-vms"></a><span data-ttu-id="7688e-125">Vm 사용 하 여 Docker 컨테이너 비교</span><span class="sxs-lookup"><span data-stu-id="7688e-125">Comparing Docker containers with VMs</span></span>

<span data-ttu-id="7688e-126">그림 1-3 Vm 및 Docker 간의 비교를 보여 줍니다. 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-126">Figure 1-3 shows a comparison between VMs and Docker containers.</span></span>

<span data-ttu-id="7688e-127">컨테이너에 훨씬 더 적은 리소스가 필요 하기 때문에 (예를 들어 필요 하지 않은 전체 OS)를 쉽게 배포 하 고 빠른 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-127">Because containers require far fewer resources (for example, they do not need a full OS), they are easy to deploy and they start fast.</span></span> <span data-ttu-id="7688e-128">이렇게 하면 동일한 하드웨어 단위 줄여 비용에 더 많은 서비스를 실행할 수 있는지를 의미 하는 높은 밀도 받아 주세요.</span><span class="sxs-lookup"><span data-stu-id="7688e-128">This makes it possible for you to have higher density, meaning that you can run more services on the same hardware unit, thereby reducing costs.</span></span>

<span data-ttu-id="7688e-129">동일한 커널을에서 실행의 부작용을으로 Vm 보다 적은 격리를 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-129">As a side effect of running on the same kernel, you achieve less isolation than VMs.</span></span>

<span data-ttu-id="7688e-130">이미지의 주요 목표는 수행 하는 환경 (종속성) 동일한 다른 배포에서입니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-130">The main goal of an image is that it makes the environment (dependencies) the same across different deployments.</span></span> <span data-ttu-id="7688e-131">이 컴퓨터에서 디버깅 하 고 보장 환경으로 다른 컴퓨터에 배포할 수 있는 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-131">This means that you can debug it on your machine and then deploy it to another machine with the same environment guaranteed.</span></span>

<span data-ttu-id="7688e-132">컨테이너 이미지는 응용 프로그램 또는 서비스를 패키지 하는 신뢰할 수 있는 고 재현 가능한 방식으로 배포 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-132">A container image is a way to package an app or service and deploy it in a reliable and reproducible manner.</span></span> <span data-ttu-id="7688e-133">이런 점에서 Docker가 아닙니다.만 하는 기술 이기도 한 철학 및 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-133">In this respect, Docker is not only a technology, it's also a philosophy and a process.</span></span>

<span data-ttu-id="7688e-134">Docker를 사용 하면 예를 들어 개발자를 들, "바로 가기 작동 제 컴퓨터에서 안 되는 이유 프로덕션 환경에서?"</span><span class="sxs-lookup"><span data-stu-id="7688e-134">When using Docker, you will not hear developers say, "It works on my machine, why not in production?"</span></span> <span data-ttu-id="7688e-135">수 단순히 이제, "Docker에서 실행" 때문에 모든 지원 되는 Docker 환경에서 패키지 Docker 응용 프로그램을 실행할 수 있으며 모든 배포 대상 (개발, QA, 스테이징 등 프로덕션.)에서 원래 방식으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688e-135">They can simply say, "It runs on Docker," because the packaged Docker application can be run on any supported Docker environment, and it will run the way it was intended to on all deployment destinations (Dev, QA, staging, production, etc.).</span></span>

![](./media/image3.png)

<span data-ttu-id="7688e-136">Docker 컨테이너에 기존 Vm의 그림 1-3: 비교</span><span class="sxs-lookup"><span data-stu-id="7688e-136">Figure 1-3: Comparison of traditional VMs to Docker containers</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7688e-137">[이전] [다음] (docker terminology.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="7688e-137">[Previous] (index.md) [Next] (docker-terminology.md)</span></span>
