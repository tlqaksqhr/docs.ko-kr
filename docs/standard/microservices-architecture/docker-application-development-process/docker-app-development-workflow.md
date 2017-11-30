---
title: "Docker 앱에 대 한 개발 워크플로"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker 앱에 대 한 개발 워크플로"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="9fbae-104">Docker 앱에 대 한 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="9fbae-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="9fbae-105">응용 프로그램 개발 수명 주기는 개발자가 기본 설정된 언어를 사용 하 여 응용 프로그램 코드와 로컬로 테스트 여기서 각 개발자의 컴퓨터에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-105">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="9fbae-106">어떤 언어, 프레임 워크 및이 워크플로에 개발자가 선택 되는 플랫폼에 관계 없이 개발자가 항상 개발 및 테스트, Docker 컨테이너 하지만 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-106">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="9fbae-107">각 컨테이너 (Docker 이미지의 인스턴스)는 다음 구성 요소가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-107">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="9fbae-108">(예를 들어 Linux 배포판, Windows Nano Server 또는 Windows Server Core)는 운영 체제 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-108">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="9fbae-109">(응용 프로그램 이진 파일 등)은 개발자가 추가 되는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-109">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="9fbae-110">구성 정보 (환경 설정 및 종속성)입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-110">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="9fbae-111">Docker 컨테이너 기반 응용 프로그램을 개발 하기 위한 워크플로</span><span class="sxs-lookup"><span data-stu-id="9fbae-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="9fbae-112">이 섹션에 설명 된 *내부 루프* Docker 컨테이너 기반 응용 프로그램에 대 한 개발 워크플로에 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="9fbae-113">내부 루프 워크플로 사용 하지 계정으로 보다 광범위 한 DevOps 워크플로 및 개발자의 컴퓨터에서 수행 되는 개발 작업에만 중점을 두고 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-113">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="9fbae-114">한 번만 완료 된 후에 환경을 설정 하는 초기 단계, 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-114">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="9fbae-115">응용 프로그램 서비스과 추가 라이브러리 (종속성)으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="9fbae-116">일반적으로 수행 하는 Docker 응용 프로그램을 빌드하는 경우 그림 5-1을 보여 주는 것 처럼 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="9fbae-117">**그림 5-1입니다.**</span><span class="sxs-lookup"><span data-stu-id="9fbae-117">**Figure 5-1.**</span></span> <span data-ttu-id="9fbae-118">Docker 컨테이너 화 가능한 응용 프로그램을 개발 하기 위한 단계별 워크플로</span><span class="sxs-lookup"><span data-stu-id="9fbae-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="9fbae-119">이 가이드에서이 전체 프로세스를 자세히 설명 하 고 모든 주요 단계는 Visual Studio 환경 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="9fbae-120">편집기/CLI 개발 방법 (예를 들어 Visual Studio 코드와 macOS에서 Docker CLI 또는 Windows)를 사용 하는 경우 모든 단계를 일반적으로 Visual Studio를 사용 하는 경우 보다 더 자세히 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="9fbae-121">CLI 환경에서 작업 하는 방법에 대 한 자세한 내용은 전자책 참조 [Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 가능한 응용 프로그램 수명 주기](http://aka.ms/dockerlifecycleebook/)합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-121">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="9fbae-122">Visual Studio 2015 또는 Visual Studio 2017을 사용 하는 경우 이러한 단계 대부분의 생산성을 크게 향상 되는 자동으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-122">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="9fbae-123">Visual Studio 2017 사용 하면서 다중 컨테이너 응용 프로그램을 대상으로 할 때 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="9fbae-124">예를 들어, 하나만 마우스 클릭으로 Visual Studio는 Dockerfile 및 docker compose.yml 파일 프로젝트를 추가 응용 프로그램에 대 한 구성 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-124">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="9fbae-125">Docker 이미지를 작성 및 Docker에서 직접 여러 컨테이너 응용 프로그램을 실행 합니다. Visual Studio에서 응용 프로그램을 실행 하는 경우 도 한 번에 여러 컨테이너를 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="9fbae-126">이러한 기능에는 개발 속도 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-126">These features will boost your development speed.</span></span>

<span data-ttu-id="9fbae-127">그러나 Visual Studio에서는 이러한 단계가 자동 해 서 의미가 어떻게 진행 되 고 알 필요가 없습니다 Docker가 있는 on 아래 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-127">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="9fbae-128">따라서 아래 지침에 모든 단계를 자세히 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-128">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="9fbae-129">1단계:</span><span class="sxs-lookup"><span data-stu-id="9fbae-129">Step 1.</span></span> <span data-ttu-id="9fbae-130">코딩을 시작 하 고 초기 응용 프로그램 또는 서비스 기준을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9fbae-130">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="9fbae-131">Docker 응용 프로그램을 개발 하는 것은 Docker 없는 응용 프로그램을 개발 하는 방법은 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-131">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="9fbae-132">다른 점은 Docker를 개발 하는 동안 배포 및 테스트 중인 응용 프로그램 또는 로컬 환경에서 Docker 컨테이너 내에서 실행 되는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-132">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="9fbae-133">Linux 컨테이너 또는 Windows 컨테이너는 컨테이너 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-133">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="9fbae-134">Visual Studio와 함께 로컬 환경 설정</span><span class="sxs-lookup"><span data-stu-id="9fbae-134">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="9fbae-135">를 시작 하려면 했는지 확인 [Docker Community Edition (CE)](https://www.docker.com/community-edition) 경우 다음 지침에에서 설명 된 대로 설치 하는 Windows 용:</span><span class="sxs-lookup"><span data-stu-id="9fbae-135">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="9fbae-136">Windows 용 Docker CE 시작</span><span class="sxs-lookup"><span data-stu-id="9fbae-136">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="9fbae-137">또한 Visual Studio 2017 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-137">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="9fbae-138">이것은 것이 좋습니다 Visual Studio 2015는 Visual Studio tools for Docker 추가 기능을 통해 Visual Studio 2017 컨테이너 디버깅에 대 한 지원 같은 Docker에 대 한 지원을 고급 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-138">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="9fbae-139">Visual Studio 2017을 선택한 경우 Docker에 대 한 도구에 포함 되어는 **.NET Core 및 Docker** 그림 5-2와 같이 설치 하는 동안 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-139">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="9fbae-140">**그림 5-2**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-140">**Figure 5-2**.</span></span> <span data-ttu-id="9fbae-141">선택 하 고 **.NET Core 및 Docker** Visual Studio 2017 설치 하는 동안 작업</span><span class="sxs-lookup"><span data-stu-id="9fbae-141">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="9fbae-142">응용 프로그램에서 Docker를 사용 하도록 설정 하 고 배포 및 Docker에서 테스트 하기 전에 응용 프로그램 (일반적으로.NET Core 컨테이너를 사용 하려는 경우)에 일반.net 코딩을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-142">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="9fbae-143">그러나 Docker에서 가능한 한 빨리 실제 환경 수 있는 모든 문제를 가능한 한 빨리 검색 하기 때문에 작업을 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="9fbae-144">Visual Studio를 사용 하면 Docker는 거의 마치 투명 하 게 사용 하는 것이 쉽지 때문에이 방법은 권장-Visual Studio에서 여러 컨테이너 응용 프로그램을 디버깅 하는 경우 가장 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9fbae-145">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9fbae-145">Additional resources</span></span>

-   <span data-ttu-id="9fbae-146">**Windows 용 Docker CE 시작**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="9fbae-146">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="9fbae-147">**Visual Studio 2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span><span class="sxs-lookup"><span data-stu-id="9fbae-147">**Visual Studio 2017**
[*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="9fbae-148">2단계.</span><span class="sxs-lookup"><span data-stu-id="9fbae-148">Step 2.</span></span> <span data-ttu-id="9fbae-149">기존.NET 기본 이미지와 관련 된 Dockerfile 만들기</span><span class="sxs-lookup"><span data-stu-id="9fbae-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="9fbae-150">Dockerfile; 빌드 하려는 각 사용자 지정 이미지 필요 Visual Studio 또는 Docker CLI를 사용 하 여 수동으로에서 자동으로 배포 여부를 각 컨테이너에 대 한 배포를 Dockerfile을 또한 해야 (실행 docker 및 docker-명령을 작성).</span><span class="sxs-lookup"><span data-stu-id="9fbae-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="9fbae-151">응용 프로그램은 하나의 사용자 지정 서비스를 포함 하는 경우 단일 Dockerfile 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="9fbae-152">응용 프로그램 (예: microservices 아키텍처)는 여러 서비스를 포함 하는 경우 각 서비스에 대 한 Dockerfile 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="9fbae-153">Dockerfile은 응용 프로그램 또는 서비스의 루트 폴더에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="9fbae-154">Docker를 설정 하 고 컨테이너에 응용 프로그램 또는 서비스를 실행 하는 방법을 지시 하는 명령이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="9fbae-155">수동으로 코드에서 Dockerfile을 만들 하 고.NET 종속성과 함께 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="9fbae-156">Visual Studio 및 Docke에 대 한 도구와이 작업에는 몇 가지 마우스 클릭 해야합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-156">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="9fbae-157">명명 된 하는 옵션은 Visual Studio 2017에 새 프로젝트를 만들 때 **컨테이너를 사용 하도록 설정 (Docker) 지원**그림 5-3에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-157">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="9fbae-158">**그림 5-3**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-158">**Figure 5-3**.</span></span> <span data-ttu-id="9fbae-159">Visual Studio 2017에서 새 프로젝트를 만들 때 Docker 지원을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9fbae-159">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="9fbae-160">Visual Studio에서 프로젝트 파일을 마우스 오른쪽 단추로 클릭 하 고 옵션을 선택 하 여 새 프로젝트나 기존 프로젝트에서 Docker 지원을 설정할 수도 있습니다 **추가 Docker 프로젝트 지원**그림 5-4에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-160">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="9fbae-161">**그림 5-4**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-161">**Figure 5-4**.</span></span> <span data-ttu-id="9fbae-162">기존 Visual Studio 2017 프로젝트에서 Docker 지원을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="9fbae-162">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="9fbae-163">이 작업 (예: ASP.NET 웹 응용 프로그램 또는 웹 API 서비스) 프로젝트에 필요한 구성으로 프로젝트를 Dockerfile을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-163">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="9fbae-164">또한 전체 솔루션에 대 한 docker compose.yml 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-164">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="9fbae-165">다음 섹션에서는 이러한 각 파일에 입력 되는 정보가 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-165">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="9fbae-166">Visual Studio,이 작업을 수행할 수 있지만 Dockerfile에 포함할 항목을 이해 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-166">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="9fbae-167">옵션 a: 기존 공식.NET Docker 이미지를 사용 하 여 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9fbae-167">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="9fbae-168">일반적으로 기본 이미지에는 공식 저장소에서 가져올 수를 기반으로 컨테이너에 대해 사용자 지정 이미지를 만들기는 [Docker 허브](https://hub.docker.com/) 레지스트리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-168">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="9fbae-169">하는 방법을 보여 줍니다 정확 하 게 내부적 Visual Studio에서 Docker 지원 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-169">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="9fbae-170">Dockerfile 기존 aspnetcore 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-170">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="9fbae-171">이전에서는 설명는 Docker 이미지 리포지토리 프레임 워크와 선택한 운영 체제에 따라 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-171">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="9fbae-172">예를 들어, ASP.NET Core (Linux 또는 Windows)를 사용 하려는 경우 사용할 이미지는 microsoft / aspnetcore:2.0 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-172">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="9fbae-173">따라서 컨테이너에 대해 사용할 어떤 기본 Docker 이미지를 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-173">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="9fbae-174">Microsoft에서 추가 하 여 그렇게 / aspnetcore:2.0 Dockerfile에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-174">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="9fbae-175">이 자동으로 수행 됩니다 Visual Studio가 있지만이 값을 업데이트, 버전을 업데이트 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="9fbae-175">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="9fbae-176">Docker 허브에서 공식.NET 이미지 리포지토리를 사용 하 여 버전 번호는 동일한 언어 기능은 모든 컴퓨터 (개발, 테스트 및 프로덕션 포함)에서 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-176">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="9fbae-177">다음 예제에서는 ASP.NET Core 컨테이너에 대 한 Dockerfile 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-177">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="9fbae-178">이 경우 컨테이너 공식 ASP.NET Core Docker 이미지 (Linux 및 Windows 용 다중 arch)의 버전 2.0은 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-178">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="9fbae-179">이 값은 설정 `FROM microsoft/aspnetcore:2.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-179">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="9fbae-180">(이 기본 이미지에 대 한 자세한 내용은 참조는 [ASP.NET Core Docker 이미지](https://hub.docker.com/r/microsoft/aspnetcore/) 페이지 및 [.NET Core Docker 이미지](https://hub.docker.com/r/microsoft/dotnet/) 페이지입니다.) Dockerfile의 Docker (이 경우 포트 80 노출 설정으로 구성 된 대로)에서 런타임에 사용할 TCP 포트에서 수신 대기 하도록 지시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-180">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="9fbae-181">언어 및 사용 하는 프레임 워크에 따라 Dockerfile의 추가 구성 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-181">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="9fbae-182">예를 들어, ENTRYPOINT 줄을 \["dotnet", "MySingleContainerWebApp.dll"\] .NET Core 응용 프로그램을 실행 하는 Docker를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-182">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="9fbae-183">을 사용 중인 SDK 및.NET Core CLI (dotnet CLI) 작성 하 고.NET 응용 프로그램을 실행 하는 경우이 설정은 다른 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-183">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="9fbae-184">결론입니다 ENTRYPOINT 줄 및 기타 설정에서 응용 프로그램에 대해 선택한 언어 및 플랫폼에 따라 달라을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-184">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9fbae-185">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9fbae-185">Additional resources</span></span>

-   <span data-ttu-id="9fbae-186">**.NET Core 응용 프로그램에 대 한 Docker 이미지를 작성**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span><span class="sxs-lookup"><span data-stu-id="9fbae-186">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span></span>

-   <span data-ttu-id="9fbae-187">**사용자 고유의 이미지를 작성할**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-187">**Build your own image**.</span></span> <span data-ttu-id="9fbae-188">공식 Docker 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-188">In the official Docker documentation.</span></span>
    [<span data-ttu-id="9fbae-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span><span class="sxs-lookup"><span data-stu-id="9fbae-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span></span>](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="9fbae-190">다중 아치 이미지 저장소를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="9fbae-190">Using multi-arch image repositories</span></span>

<span data-ttu-id="9fbae-191">단일 리포지토리 플랫폼 변형 Linux 이미지 등 Windows 이미지를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-191">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="9fbae-192">이 기능에는 Microsoft (기본 이미지 작성자)와 같은 공급 업체를 (즉, Linux 및 Windows)는 여러 플랫폼을 처리 하려면 단일 리포지토리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-192">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="9fbae-193">예를 들어는 [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) Docker 허브 레지스트리에서 사용할 수 있는 저장소 같은 리포지토리 이름을 사용 하 여 Linux 및 Windows Nano Server에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-193">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="9fbae-194">다음과 같은 경우에는 다음과 같은 명시적 되는 플랫폼을 대상으로 하는 태그를 지정 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="9fbae-194">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="9fbae-195">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="9fbae-195">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="9fbae-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="9fbae-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="9fbae-197">그러나 이것이 2017 중순 이후 새로운 지정 하는 경우 같은 태그 된 경우에 동일한 이미지 이름, (예: 여러 아키텍처를 지 원하는 aspnetcore 이미지) 새 다중 아치 이미지에서 배포 하는 Docker 호스트 운영 체제에 따라 Linux 또는 Windows 버전을 사용 하 고 를 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="9fbae-197">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="9fbae-198">**microsoft / aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="9fbae-198">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="9fbae-199">이러한 방식으로 Windows 호스트에서 이미지를 가져올 때, Windows variant 끌어오고 것 및 Linux 호스트에서 동일한 이미지 이름을 끌어오기은 Linux 변형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-199">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="9fbae-200">옵션 b: 처음부터 기본 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="9fbae-200">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="9fbae-201">처음부터 직접 Docker 기본 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-201">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="9fbae-202">이 시나리오는 적합 하지 않습니다 Docker로 시작 하는 사람 있지만 사용자 고유의 기본 이미지의 특정 비트를 설정 하려는 경우 그렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-202">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9fbae-203">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9fbae-203">Additional resources</span></span>

-   <span data-ttu-id="9fbae-204">**다중 아치.NET Core 이미지**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-204">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="9fbae-205">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="9fbae-205">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="9fbae-206">**기본 이미지를 만들**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-206">**Create a base image**.</span></span> <span data-ttu-id="9fbae-207">공식 Docker 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-207">Official Docker documentation.</span></span>
    [<span data-ttu-id="9fbae-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span><span class="sxs-lookup"><span data-stu-id="9fbae-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span></span>](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="9fbae-209">3단계.</span><span class="sxs-lookup"><span data-stu-id="9fbae-209">Step 3.</span></span> <span data-ttu-id="9fbae-210">사용자 지정 Docker 이미지를 만들고 여기에 응용 프로그램 또는 서비스 포함</span><span class="sxs-lookup"><span data-stu-id="9fbae-210">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="9fbae-211">응용 프로그램에서 각 서비스에 대해 관련된 이미지를 만드는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-211">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="9fbae-212">응용 프로그램은 하나의 서비스 또는 웹 응용 프로그램의 구성 된, 경우 하기만 하면 단일 이미지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-212">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="9fbae-213">Docker 이미지는 자동으로 사용자에 대 한 Visual Studio에서 작성 하는 참고 사항</span><span class="sxs-lookup"><span data-stu-id="9fbae-213">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="9fbae-214">다음 단계는만 편집기/CLI 워크플로에 필요 하 고 쉽게 구별할 수 있도록 아래 수행 되는 작업에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-214">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="9fbae-215">개발자 해야 개발 하 고 로컬로 푸시할은 완료 될 때까지 테스트 기능 또는 소스 제어 시스템 (예를 들어 GitHub에서)로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-215">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="9fbae-216">이 Docker 이미지를 만들려면 및 (Windows 또는 Linux VM) 로컬 Docker 호스트에 컨테이너를 배포 및 실행, 테스트 및 로컬 해당 컨테이너에 대 한 디버그 해야 할 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-216">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="9fbae-217">Docker CLI 및 Dockerfile을 사용 하 여 로컬 환경에서 사용자 지정 이미지를 만들려면, docker 빌드 명령을 그림 5-5와 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-217">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="9fbae-218">**그림 5-5**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-218">**Figure 5-5**.</span></span> <span data-ttu-id="9fbae-219">사용자 지정 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="9fbae-219">Creating a custom Docker image</span></span>

<span data-ttu-id="9fbae-220">필요에 따라 docker 빌드 프로젝트 폴더에서를 직접 실행 하는 대신 먼저 필요한.NET 라이브러리와 함께 배포 가능한 폴더를 생성할 수 있습니다 게시 하 고 dotnet를 실행 하 여 이진 파일을 다음 docker 빌드 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-220">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="9fbae-221">이렇게 하면 만들어지고 Docker 이미지의 이름 cesardl/netcore-webapi-마이크로 서비스-docker: 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-221">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="9fbae-222">이 경우: 먼저는 특정 버전을 나타내는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-222">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="9fbae-223">구성 된 Docker 응용 프로그램에 대해 만들어야 할 각 사용자 지정 이미지에 대해이 단계를 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-223">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="9fbae-224">응용 프로그램의 여러 컨테이너 만들어질 때 (즉,이 다중 컨테이너 응용 프로그램)를 사용할 수도 있습니다는-관련의 노출 된 메타 데이터를 사용 하 여 하나의 명령으로 모든 관련된 이미지를 만들려면 빌드 명령을를 docker 구성 docker compose.yml 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-224">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="9fbae-225">명령을 찾을 수 있습니다 기존 이미지 로컬 저장소에서 docker를 사용 하 여 이미지, 그림 5-6에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-225">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="9fbae-226">**그림 5-6입니다.**</span><span class="sxs-lookup"><span data-stu-id="9fbae-226">**Figure 5-6.**</span></span> <span data-ttu-id="9fbae-227">Docker 이미지 명령을 사용 하 여 보기 기존 이미지</span><span class="sxs-lookup"><span data-stu-id="9fbae-227">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="9fbae-228">Visual Studio를 사용 하 여 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="9fbae-228">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="9fbae-229">프로젝트를 만들려면 Docker 지 원하는 Visual Studio를 사용 하면 명시적으로 만들지 마십시오 이미지.</span><span class="sxs-lookup"><span data-stu-id="9fbae-229">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="9fbae-230">대신, 이미지가 만들어집니다 dockerized 응용 프로그램이 나 서비스를 실행 하 고 F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-230">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="9fbae-231">이 단계는 Visual Studio에서 자동 및 발생 표시 되지 것입니다 이지만 진행 상황을 파악 하는 것에 아래 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-231">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="9fbae-232">4단계.</span><span class="sxs-lookup"><span data-stu-id="9fbae-232">Step 4.</span></span> <span data-ttu-id="9fbae-233">다중 컨테이너 Docker 응용 프로그램을 빌드할 때 docker compose.yml 서비스 정의</span><span class="sxs-lookup"><span data-stu-id="9fbae-233">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="9fbae-234">[docker compose.yml](https://docs.docker.com/compose/compose-file/) 파일로 배포 명령 사용 하 여 구성 된 응용 프로그램으로 배포 될 관련된 서비스의 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-234">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="9fbae-235">Docker compose.yml 파일을 사용 하려면 다음 예제에서와 비슷한 콘텐츠로 프로그램 main에서 파일 또는 루트 솔루션 폴더를 만드는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-235">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

<span data-ttu-id="9fbae-236">Docker compose.yml 파일 단순화 되 고 병합 된 버전을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-236">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="9fbae-237">(예: 이름 사용자 지정 이미지의)을 배포 환경 연결 문자열과 같은 종속 된 구성 정보 및 항상 적용 하는 각 컨테이너에 대 한 정적 구성 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-237">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="9fbae-238">이후 섹션에서 배웁니다 어떻게 docker compose.yml 구성을 여러도 분할할 수 있습니다 docker 구성 파일 및 환경 및 실행 유형 (디버그 또는 릴리스)에 따라 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-238">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="9fbae-239">Docker compose.yml 파일 예제에서는 5 개의 서비스 정의: webmvc 서비스 (웹 응용 프로그램), 두 microservices (catalog.api 및 ordering.api) 및 하나 이상의 데이터 원본 컨테이너를 sql.data, 컨테이너를 실행 하는 Linux 용 SQL Server에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-239">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="9fbae-240">각 서비스는 Docker 이미지를 각각에 대 한 필요 않도록 컨테이너 기능을 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-240">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="9fbae-241">Docker compose.yml 파일에는 어떤 컨테이너가 사용 하 여을 뿐 아니라 개별적으로 구성 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-241">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="9fbae-242">예를 들어, webmvc 컨테이너에에서 있는 정의.yml 파일:</span><span class="sxs-lookup"><span data-stu-id="9fbae-242">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="9fbae-243">미리 작성 된 eshop를 사용 하 여 / 웹: 최신 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-243">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="9fbae-244">그러나 이미지의 일부로 작성도 구성할 수는 docker 구성 빌드를 기반으로 하는 추가 구성을 실행: docker-compose 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-244">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="9fbae-245">두 개의 환경 변수를 (CatalogUrl 및 OrderingUrl)를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-245">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="9fbae-246">호스트 컴퓨터의 외부 포트 80 컨테이너에는 80 노출 된 포트를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-246">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="9fbae-247">웹 응용 프로그램 카탈로그 및 서비스를 순서에 연결 된 종속\_설정에 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-247">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="9fbae-248">이렇게 하면 해당 서비스가 시작 될 때까지 대기 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-248">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="9fbae-249">이후 섹션에서 docker compose.yml 파일 microservices 및 다중 컨테이너 응용 프로그램을 구현 하는 방법을 다룰 때 다시 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-249">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="9fbae-250">Visual Studio 2017에 docker compose.yml 작업</span><span class="sxs-lookup"><span data-stu-id="9fbae-250">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="9fbae-251">그림 5-7에 표시 된 것 처럼 서비스 프로젝트는 Visual Studio 솔루션에 Docker 솔루션 지원을 추가 하면 Visual Studio 프로젝트에 Dockerfile을 추가 하 고 docker compose.yml 파일과 함께 서비스 섹션 (프로젝트) 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-251">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="9fbae-252">여러 컨테이너 솔루션 작성을 시작 하는 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-252">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="9fbae-253">그런 다음 docker compose.yml 파일 열고 추가 기능으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-253">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="9fbae-254">**그림 5-7**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-254">**Figure 5-7**.</span></span> <span data-ttu-id="9fbae-255">ASP.NET Core 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 Visual Studio 2017에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="9fbae-255">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="9fbae-256">Visual Studio에서 Docker 지원을 추가 Dockerfile을 프로젝트에 추가 하는 뿐 아니라 솔루션 수준에서 설정 된 여러 개의 전역 docker compose.yml 파일에 구성 정보를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-256">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="9fbae-257">Visual Studio에서 솔루션에 Docker 지원을 추가 하면 그림 5-8에 나와 있는 것 처럼 추가 docker compose.yml 파일을 포함 하는 솔루션 탐색기에서 새 노드는 docker compose.dcproj 프로젝트 파일에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-257">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="9fbae-258">**그림 5-8**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-258">**Figure 5-8**.</span></span> <span data-ttu-id="9fbae-259">**docker 작성** 추가 Visual Studio 2017 솔루션 탐색기에서 트리 노드</span><span class="sxs-lookup"><span data-stu-id="9fbae-259">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="9fbae-260">사용 하 여 단일 docker compose.yml 파일 다중 컨테이너 응용 프로그램을 배포할 수 있습니다는 docker 명령을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-260">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="9fbae-261">환경 (프로덕션 및 개발) 및 실행에 따라 값을 재정의할 수 있도록 Visual Studio 그중에서 그룹을 추가 하는 반면 유형 (디버그와 릴리스).</span><span class="sxs-lookup"><span data-stu-id="9fbae-261">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="9fbae-262">이 기능은 이후 섹션에서 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-262">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="9fbae-263">5단계.</span><span class="sxs-lookup"><span data-stu-id="9fbae-263">Step 5.</span></span> <span data-ttu-id="9fbae-264">Docker 응용 프로그램 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="9fbae-264">Build and run your Docker application</span></span>

<span data-ttu-id="9fbae-265">응용 프로그램에 단일 컨테이너에 있는 경우 (VM 또는 실제 서버) Docker 호스트에 배포 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-265">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="9fbae-266">그러나 응용 프로그램에 여러 서비스 있으면 배포할 수 있습니다는 구성 된 응용 프로그램으로 단일 CLI 명령을 사용 하 여 (docker-작성 위로), 또는 Visual Studio와 함께 있으며 내부적 해당 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-266">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="9fbae-267">다양 한 옵션에 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-267">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="9fbae-268">Docker CLI를 단일 컨테이너를 실행 하는 옵션 a:</span><span class="sxs-lookup"><span data-stu-id="9fbae-268">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="9fbae-269">Docker run 명령, 그림 5-9와 같이 사용 하 여 Docker 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-269">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="9fbae-270">**그림 5-9**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-270">**Figure 5-9**.</span></span> <span data-ttu-id="9fbae-271">Docker run 명령을 사용 하 여 Docker 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-271">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="9fbae-272">이 경우 명령은 호스트 컴퓨터의 포트 80 컨테이너의 내부 포트 5000에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-272">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="9fbae-273">즉, 호스트 포트 80에서 수신 대기 하 고 포트 5000 컨테이너에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-273">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="9fbae-274">다중 컨테이너 응용 프로그램을 실행 하는 옵션 b:</span><span class="sxs-lookup"><span data-stu-id="9fbae-274">Option B: Running a multi-container application</span></span>

<span data-ttu-id="9fbae-275">대부분의 엔터프라이즈 시나리오에서 Docker 응용 프로그램 구성 됩니다 여러 서비스 그림 5-10에서와 같이 여러 컨테이너 응용 프로그램을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-275">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="9fbae-276">**그림 5-10**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-276">**Figure 5-10**.</span></span> <span data-ttu-id="9fbae-277">배포 된 Docker 컨테이너를 사용 하 여 VM</span><span class="sxs-lookup"><span data-stu-id="9fbae-277">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="9fbae-278">Docker CLI와 다중 컨테이너 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-278">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="9fbae-279">Docker를 실행할 수를 Docker CLI 사용 다중 컨테이너 응용 프로그램을 실행 하려면-명령을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-279">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="9fbae-280">포함 되는 다중 컨테이너 응용 프로그램을 배포 하려면 솔루션 수준에서이 명령 사용 하 여 docker compose.yml 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-280">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="9fbae-281">그림 5-11 docker compose.yml 파일이 포함 된 기본 프로젝트 디렉터리에서 명령을 실행할 때 결과 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-281">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="9fbae-282">**그림 5-11**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-282">**Figure 5-11**.</span></span> <span data-ttu-id="9fbae-283">실행 하는 경우 결과 예는 명령을 docker 구성</span><span class="sxs-lookup"><span data-stu-id="9fbae-283">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="9fbae-284">Docker 후-명령 실행을 작성, VM 표시 그림 5-10에서에서 보여 주는 것 처럼 응용 프로그램 및 해당 관련된 컨테이너 Docker 호스트에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-284">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="9fbae-285">실행 하 고 Visual Studio와 함께 여러 컨테이너 응용 프로그램 디버깅</span><span class="sxs-lookup"><span data-stu-id="9fbae-285">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="9fbae-286">Visual Studio 2017을 사용 하 여 다중 컨테이너 응용 프로그램을 실행 하는 것은 간단 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-286">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="9fbae-287">수만 실행 하면 여러 컨테이너 응용 프로그램 있지만 일반적인 중단점을 설정 하 여 Visual Studio에서 직접 모든 해당 컨테이너 디버깅 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-287">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="9fbae-288">솔루션 내의 프로젝트를 솔루션 지원 Docker를 추가할 때마다 전에 언급 했 듯이 실행 하거나 전체 솔루션을 한 번에 디버그할 수 있는 글로벌 (솔루션 수준의) docker compose.yml 파일에서 해당 프로젝트 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-288">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="9fbae-289">Visual Studio Docker 솔루션 지원이 활성화 되는 각 프로젝트에 대 한 컨테이너를 시작 되며 모든 내부 단계를 수행 하면 (dotnet 게시, docker 빌드 등.).</span><span class="sxs-lookup"><span data-stu-id="9fbae-289">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="9fbae-290">여기서 중요 한 점은, 그림 5-12, 표시 된 것 처럼 Visual Studio 2017에 있다는 점입니다 추가 **Docker** F5 키 작업에 대 한 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-290">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="9fbae-291">이 옵션을 사용 하 여 실행 하거나 솔루션 수준에서 docker compose.yml 파일에 정의 된 모든 컨테이너를 실행 하 여 다중 컨테이너 응용 프로그램을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-291">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="9fbae-292">여러 컨테이너 솔루션을 디버깅 하는 기능 (컨테이너)를 다른 프로젝트에 중단점을 여러 개, 각 중단점을 설정할 수 있습니다 및에서 실행 하 고 다른 프로젝트에 정의 된 중단점에서 중지 됩니다 Visual Studio에서 디버깅 하는 동안 의미 다른 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-292">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="9fbae-293">**그림 5-12**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-293">**Figure 5-12**.</span></span> <span data-ttu-id="9fbae-294">Visual Studio 2017에 실행 중인 다중 컨테이너 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9fbae-294">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9fbae-295">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9fbae-295">Additional resources</span></span>

-   <span data-ttu-id="9fbae-296">**원격 Docker 호스트에는 ASP.NET 컨테이너를 배포**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="9fbae-296">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="9fbae-297">테스트 및 orchestrators 사용 하 여 배포에 대 한 메모</span><span class="sxs-lookup"><span data-stu-id="9fbae-297">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="9fbae-298">docker 작성 하 고 docker 실행 명령을 (또는 실행 및 디버깅을 Visual Studio에서 컨테이너)는 개발 환경에서 컨테이너를 테스트 하기에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-298">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="9fbae-299">하지만 Docker 클러스터를 대상으로 하 고 docker는 Docker Swarm, Mesosphere DC/OS 또는 Kubernetes orchestrators 형식 하는 경우이 방법을 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-299">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="9fbae-300">같은 클러스터를 사용 하는 경우 [docker는 Docker Swarm 모드](https://docs.docker.com/engine/swarm/) 배포 및와 같은 추가 명령을 사용 하 여 테스트 해야 할 (사용 가능 Windows 용 Docker CE 및 Mac 1.12 버전부터), [docker 서비스를 만들](https://docs.docker.com/engine/reference/commandline/service_create/) 에 대 한 단일 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-300">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="9fbae-301">사용 하면 여러 컨테이너를 구성 하는 응용 프로그램을 배포 하는 경우 [docker 번들 작성](https://docs.docker.com/compose/reference/bundle/) 및 [docker 배포 myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) 으로 구성 된 응용 프로그램을 배포 하는 *스택*.</span><span class="sxs-lookup"><span data-stu-id="9fbae-301">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="9fbae-302">자세한 내용은 블로그 게시물을 참조 하십시오. [실험적 분산 응용 프로그램 번들 소개](https://blog.docker.com/2016/06/docker-app-bundle/) Docker 설명서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-302">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="9fbae-303">Docker 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-303">on the Docker site.</span></span>

<span data-ttu-id="9fbae-304">에 대 한 [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) 및 [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) 다양 한 배포 명령 및 스크립트에도 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-304">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="9fbae-305">6단계.</span><span class="sxs-lookup"><span data-stu-id="9fbae-305">Step 6.</span></span> <span data-ttu-id="9fbae-306">로컬 Docker 호스트를 사용 하 여 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="9fbae-306">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="9fbae-307">이 단계는 응용 프로그램이 수행 하는 작업에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-307">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="9fbae-308">간단한.NET Core 웹 응용 프로그램에서 단일 컨테이너 또는 서비스로 배포 된 Docker 호스트에서 브라우저를 열고 그림 5-13에 표시 된 것 처럼 해당 사이트로 이동 하는 서비스를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-308">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="9fbae-309">(Dockerfile의 구성 컨테이너의 포트 80 이외의 값이 설정 되어 있는 호스트에 매핑되면, 후 호스트를 URL에 포함 합니다.)</span><span class="sxs-lookup"><span data-stu-id="9fbae-309">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host post in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="9fbae-310">**그림 5-13**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-310">**Figure 5-13**.</span></span> <span data-ttu-id="9fbae-311">Localhost를 사용 하 여 로컬로 Docker 응용 프로그램 테스트의 예</span><span class="sxs-lookup"><span data-stu-id="9fbae-311">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="9fbae-312">Localhost Docker를 가리키지 않습니다 경우 호스트 IP (기본적으로 Docker CE를 사용 하는 경우, 것)으로 서비스를 탐색 하려면 해당 컴퓨터의 네트워크 카드의 IP 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-312">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="9fbae-313">참고가이 URL은 브라우저에서 설명 하는 특정 컨테이너 예제에 대 한 포트 80을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-313">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="9fbae-314">그러나 내부적으로 요청으로 리디렉션됩니다 port 5000, 기 때문에 해당 방법을 배포 된 docker run 명령, 이전 단계에서 설명한 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-314">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="9fbae-315">그림 5-14에 나와 있는 것 처럼는 터미널에서 curl을 사용 하 여 응용 프로그램을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-315">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="9fbae-316">Windows에서 Docker 설치에서 기본 Docker 호스트 IP는 항상 컴퓨터의 실제 IP 주소와 함께 10.0.75.1 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-316">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="9fbae-317">**그림 5-14**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-317">**Figure 5-14**.</span></span> <span data-ttu-id="9fbae-318">Curl을 사용 하 여 로컬로 Docker 응용 프로그램 테스트의 예</span><span class="sxs-lookup"><span data-stu-id="9fbae-318">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="9fbae-319">테스트 및 Visual Studio 2017을 사용 하 여 컨테이너 디버깅</span><span class="sxs-lookup"><span data-stu-id="9fbae-319">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="9fbae-320">실행 되 고 Visual Studio 2017을 사용 하 여 컨테이너 디버깅, 컨테이너 없이 실행 되는 때와 거의 동일한 방법으로.NET 응용 프로그램을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-320">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="9fbae-321">테스트 및 Visual Studio가 없는 디버깅</span><span class="sxs-lookup"><span data-stu-id="9fbae-321">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="9fbae-322">편집기/CLI 방식을 사용 하 여를 개발 하는 경우 컨테이너를 디버깅 하는 것이 더 어렵기 및 추적을 생성 하 여 디버그 하려는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-322">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9fbae-323">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9fbae-323">Additional resources</span></span>

-   <span data-ttu-id="9fbae-324">**로컬 Docker 컨테이너에서 앱 디버깅**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="9fbae-324">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="9fbae-325">**Steve Lasker 합니다. 빌드, 디버그, Docker 사용 하 여 ASP.NET Core 앱을 배포 합니다.**</span><span class="sxs-lookup"><span data-stu-id="9fbae-325">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="9fbae-326">비디오입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-326">Video.</span></span>
    [<span data-ttu-id="9fbae-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span><span class="sxs-lookup"><span data-stu-id="9fbae-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span></span>](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="9fbae-328">Visual Studio를 사용 하 여 컨테이너를 개발할 때 간소화 된 워크플로</span><span class="sxs-lookup"><span data-stu-id="9fbae-328">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="9fbae-329">효과적으로, Visual Studio를 사용 하는 경우 워크플로 편집기/CLI 방식을 사용 하는 경우 보다 훨씬 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-329">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="9fbae-330">대부분의 Docker에 필요한 단계는 Dockerfile과 관련 docker compose.yml 파일 숨겨져 있거나 그림 5-15에 나와 있는 것 처럼 Visual Studio를 통해 보다 간단해 집니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-330">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="9fbae-331">**그림 5-15**합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-331">**Figure 5-15**.</span></span> <span data-ttu-id="9fbae-332">Visual Studio와 함께 개발 하는 경우 간소화 된 워크플로</span><span class="sxs-lookup"><span data-stu-id="9fbae-332">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="9fbae-333">또한 (프로젝트에 추가 Docker 지원) 2 단계를 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-333">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="9fbae-334">따라서.NET 다른 개발 작업을 사용 하는 경우 워크플로 일반적인 개발 작업 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-334">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="9fbae-335">실행 중인 내부적 (이미지 빌드 프로세스, 어떤 사용 하는 기본 이미지, 컨테이너 등의 배포) 하 고 경우에 따라 동작을 사용자 지정 하려면 Dockerfile 또는 docker compose.yml 파일을 편집 해야 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-335">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="9fbae-336">하지만 대부분의 작업은 훨씬 더 생산적 있게 되므로 Visual Studio를 사용 하 여 크게 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-336">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9fbae-337">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9fbae-337">Additional resources</span></span>

-   <span data-ttu-id="9fbae-338">**Steve Lasker 합니다. Visual Studio 2017 함께.NET docker 개발**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="9fbae-338">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="9fbae-339">**Jeffrey 화 Fritz 합니다. Visual Studio에 대 한 새로운 Docker 도구를 사용 하 여 컨테이너에서.NET Core 앱 배치**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="9fbae-339">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="9fbae-340">Dockerfile의 PowerShell 명령을 사용 하 여 Windows 컨테이너를 설정</span><span class="sxs-lookup"><span data-stu-id="9fbae-340">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="9fbae-341">[Windows 컨테이너](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) Docker 이미지를 기존 Windows 응용 프로그램을 변환 하 고 Docker 생태계의 나머지 부분과 동일한 도구와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-341">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="9fbae-342">Windows 컨테이너를 사용 하려면 다음 예에서 같이 Dockerfile의 PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-342">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="9fbae-343">이 경우 Windows Server Core 기본 이미지 (FROM 설정) 하 고 PowerShell 명령 (실행 설정)를 사용 하 여 IIS를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-343">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="9fbae-344">유사한 방식 ASP.NET 4.x,.NET 4.6 또는 다른 Windows 소프트웨어와 같은 추가 구성 요소를 설정 하려면 PowerShell 명령을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-344">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="9fbae-345">예를 들어 ASP.NET 4.5를 Dockerfile에 다음 명령을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-345">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="9fbae-346">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9fbae-346">Additional resources</span></span>

-   <span data-ttu-id="9fbae-347">**Dockerfile aspnet docker/입니다.**</span><span class="sxs-lookup"><span data-stu-id="9fbae-347">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="9fbae-348">Windows 기능을 포함 하도록 dockerfile에서 실행 되도록 예제 Powershell 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbae-348">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [<span data-ttu-id="9fbae-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span><span class="sxs-lookup"><span data-stu-id="9fbae-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span></span>](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="9fbae-350">[이전] [다음]을 (index.md) (... / net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="9fbae-350">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
