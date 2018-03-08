---
title: "Docker 앱에 대한 개발 워크플로"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Docker 앱에 대한 개발 워크플로"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8537b1db27f512ec0bfc2f23589efe8199ca3287
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="83602-104">Docker 앱에 대한 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="83602-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="83602-105">응용 프로그램 개발 수명 주기는 각 개발자의 컴퓨터에서 시작되며, 개발자는 자신의 컴퓨터에서 선호하는 언어를 사용하여 로컬로 응용 프로그램 코드를 작성하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-105">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="83602-106">개발자가 어떤 언어, 프레임워크, 플랫폼을 선택하든 이 워크플로를 사용하면 개발자는 항상 Docker 컨테이너를 로컬로 개발하고 테스트하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-106">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="83602-107">각 컨테이너(Docker 이미지의 인스턴스)는 다음 구성 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-107">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="83602-108">운영 체제 선택(예: Linux 배포판, Windows Nano Server 또는 Windows Server Core).</span><span class="sxs-lookup"><span data-stu-id="83602-108">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="83602-109">개발자가 추가한 파일(응용 프로그램 이진 파일 등).</span><span class="sxs-lookup"><span data-stu-id="83602-109">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="83602-110">구성 정보(환경 설정 및 종속성).</span><span class="sxs-lookup"><span data-stu-id="83602-110">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="83602-111">Docker 컨테이너 기반 응용 프로그램을 개발하기 위한 워크플로</span><span class="sxs-lookup"><span data-stu-id="83602-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="83602-112">이 섹션에서는 Docker 컨테이너 기반 응용 프로그램에 대한 *내부 루프* 개발 워크플로를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="83602-113">내부 루프 워크플로란 광범위한 DevOps 워크플로를 고려하지 않고 개발자의 컴퓨터에서 수행되는 개발 작업에만 집중한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-113">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="83602-114">환경을 설정하는 초기 단계는 한 번만 수행되므로 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-114">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="83602-115">응용 프로그램은 개발자 고유의 서비스와 추가 라이브러리(종속성)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="83602-116">다음은 그림 5-1처럼 일반적으로 Docker 응용 프로그램을 빌드할 때 수행하는 기본 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="83602-117">**그림 5-1.**</span><span class="sxs-lookup"><span data-stu-id="83602-117">**Figure 5-1.**</span></span> <span data-ttu-id="83602-118">Docker 컨테이너화된 앱 개발을 위한 단계별 워크플로</span><span class="sxs-lookup"><span data-stu-id="83602-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="83602-119">이 가이드에서는 전체 프로세스를 자세히 설명하고 모든 주요 단계는 Visual Studio 환경을 중심으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="83602-120">편집기/CLI 개발 접근 방식을 사용하는 경우(예: macOS 또는 Windows에서 Visual Studio Code와 Docker CLI 사용) 일반적으로 Visual Studio를 사용할 때보다 모든 단계를 더 자세히 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="83602-121">CLI 환경에서 작업하는 방법에 대한 자세한 내용은 전자책 [컨테이너화된 Docker 응용 프로그램 수명 주기와 Microsoft 플랫폼 및 도구](http://aka.ms/dockerlifecycleebook/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83602-121">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="83602-122">Visual Studio 2015 또는 Visual Studio 2017을 사용하는 경우 이러한 단계의 상당 부분이 자동으로 처리되므로 생산성이 대폭 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-122">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="83602-123">Visual Studio 2017을 사용하고 다중 컨테이너 응용 프로그램을 대상으로 하는 경우에 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="83602-124">예를 들어 마우스 클릭 한 번이면 Visual Studio가 응용 프로그램의 구성을 사용하여 Dockerfile 및 docker-compose.yml 파일을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-124">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="83602-125">Visual Studio에서 응용 프로그램을 실행하면 Visual Studio가 Docker 이미지를 작성하고 Docker에서 바로 다중 컨테이너 응용 프로그램을 실행하며, 심지어 여러 컨테이너를 한꺼번에 디버깅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="83602-126">이러한 기능은 개발 속도를 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-126">These features will boost your development speed.</span></span>

<span data-ttu-id="83602-127">그러나 Visual Studio가 이러한 단계를 자동으로 처리한다고 해서 Docker 내부에서 발생하는 일에 대해 전혀 몰라도 된다는 뜻은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="83602-127">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="83602-128">따라서 이어지는 지침에서 모든 단계를 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-128">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="83602-129">1단계:</span><span class="sxs-lookup"><span data-stu-id="83602-129">Step 1.</span></span> <span data-ttu-id="83602-130">코딩을 시작하고 초기 응용 프로그램 또는 서비스 기준 만들기</span><span class="sxs-lookup"><span data-stu-id="83602-130">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="83602-131">Docker 응용 프로그램 개발은 Docker 없이 응용 프로그램을 개발하는 방법과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-131">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="83602-132">다른 점은 Docker를 개발하는 동안 로컬 환경의 Docker 컨테이너 내에서 실행되는 응용 프로그램을 배포하고 테스트한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-132">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="83602-133">컨테이너는 Linux 컨테이너일 수도 있고 Windows 컨테이너일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-133">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="83602-134">Visual Studio를 사용하여 로컬 환경 설정</span><span class="sxs-lookup"><span data-stu-id="83602-134">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="83602-135">시작하려면 다음 지침에 설명된 대로 Windows용 [Docker CE(Community Edition)](https://www.docker.com/community-edition)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-135">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="83602-136">Windows용 Docker CE 시작</span><span class="sxs-lookup"><span data-stu-id="83602-136">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="83602-137">또한 Visual Studio 2017을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-137">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="83602-138">Visual Studio 2017은 컨테이너 디버깅 등 더 많은 Docker 관련 기능을 지원하므로 Visual Studio 2015에 Visual Studio Tools for Docker 추가 기능을 사용하는 것보다 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-138">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="83602-139">그림 5-2처럼 설치 과정에서 **.NET Core 및 Docker** 워크로드를 선택하면 Visual Studio 2017에 Docker용 도구가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-139">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="83602-140">**그림 5-2**.</span><span class="sxs-lookup"><span data-stu-id="83602-140">**Figure 5-2**.</span></span> <span data-ttu-id="83602-141">Visual Studio 2017을 설치하는 동안 **.NET Core 및 Docker** 워크로드 선택</span><span class="sxs-lookup"><span data-stu-id="83602-141">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="83602-142">심지어 응용 프로그램에서 Docker를 사용하도록 설정하고 Docker에 배포 및 테스트하기 전에도 일반 .NET에서 응용 프로그램 코딩을 시작할 수 있습니다(컨테이너를 사용하려는 경우 일반적으로 .NET Core).</span><span class="sxs-lookup"><span data-stu-id="83602-142">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="83602-143">하지만 되도록이면 빨리 Docker에서 작업을 시작하는 것이 좋습니다. 실제로 사용하게 될 환경이고 문제를 최대한 신속하게 검색할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="83602-144">이렇게 하도록 권장하는 이유는 Visual Studio를 사용하면 거의 투명한 것처럼 느껴지는 Docker를 손쉽게 작업할 수 있기 때문입니다. 가장 대표적인 예로 Visual Studio에서 다중 컨테이너 응용 프로그램을 디버깅하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="83602-145">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="83602-145">Additional resources</span></span>

-   <span data-ttu-id="83602-146">**Windows용 Docker CE 시작**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="83602-146">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="83602-147">**Visual Studio 2017**
    [*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span><span class="sxs-lookup"><span data-stu-id="83602-147">**Visual Studio 2017**
[*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="83602-148">2단계.</span><span class="sxs-lookup"><span data-stu-id="83602-148">Step 2.</span></span> <span data-ttu-id="83602-149">기존 .NET 기본 이미지와 관련된 Dockerfile 만들기</span><span class="sxs-lookup"><span data-stu-id="83602-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="83602-150">Visual Studio에서 자동으로 배포하든 아니면 Docker CLI(docker run 및 docker-compose 명령)를 사용하여 수동으로 배포하든, 빌드하려는 각 사용자 지정 이미지에 대한 Dockerfile과 배포할 각 컨테이너에 대한 Dockerfile이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="83602-151">응용 프로그램이 단일 사용자 지정 서비스를 포함하는 경우 단일 Dockerfile이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="83602-152">응용 프로그램이 여러 서비스를 포함하는 경우(마이크로 서비스 아키텍처처럼) 서비스마다 하나의 Dockerfile이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="83602-153">Dockerfile은 응용 프로그램 또는 서비스의 루트 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="83602-154">컨테이너의 응용 프로그램 또는 서비스를 설정하고 실행하는 방법을 Docker에 알려주는 명령을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="83602-155">코드를 사용하여 수동으로 Dockerfile을 만들어서 .NET 종속성과 함께 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="83602-156">Visual Studio와 Docker용 도구를 사용하면 마우스 클릭 몇 번으로 이 작업을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-156">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="83602-157">Visual Studio 2017에서 새 프로젝트를 만들 때 그림 5-3처럼 **컨테이너(Docker) 지원 사용**이라는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-157">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="83602-158">**그림 5-3**.</span><span class="sxs-lookup"><span data-stu-id="83602-158">**Figure 5-3**.</span></span> <span data-ttu-id="83602-159">Visual Studio 2017에서 새 프로젝트를 만들 때 Docker 지원을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="83602-159">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="83602-160">그림 5-4처럼 Visual Studio에서 프로젝트 파일을 마우스 오른쪽 단추로 클릭하고 **Docker 프로젝트 지원 추가** 옵션을 선택하여 새 프로젝트 또는 기존 프로젝트에서 Docker 지원을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-160">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="83602-161">**그림 5-4**.</span><span class="sxs-lookup"><span data-stu-id="83602-161">**Figure 5-4**.</span></span> <span data-ttu-id="83602-162">기존 Visual Studio 2017 프로젝트에서 Docker 지원을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="83602-162">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="83602-163">프로젝트에서 수행하는 이 작업(ASP.NET 웹 응용 프로그램 또는 웹 API 서비스 같은)은 필요한 구성을 사용하여 Dockerfile을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-163">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="83602-164">또한 전체 솔루션에 대한 docker compose.yml 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-164">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="83602-165">다음 섹션에서는 이러한 각 파일에 입력되는 정보를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-165">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="83602-166">Visual Studio에서 이 작업을 자동으로 수행할 수 있지만, Dockerfile에 어떤 정보가 들어가는지 알아두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-166">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="83602-167">옵션 A: 기존의 공식 .NET Docker 이미지를 사용하여 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="83602-167">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="83602-168">일반적으로 [Docker Hub](https://hub.docker.com/) 레지스트리의 공식 리포지토리에서 얻을 수 있는 기본 이미지를 기반으로 컨테이너에 대한 사용자 지정 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-168">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="83602-169">Visual Studio에서 Docker 지원을 사용하도록 설정하면 내부에서 이와 같은 일이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-169">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="83602-170">Dockerfile은 기존 aspnetcore 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-170">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="83602-171">앞에서 선택하는 프레임워크 및 운영 체제에 따라 어떤 Docker 이미지와 리포지토리를 사용할 수 있는지 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-171">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="83602-172">예를 들어 ASP.NET Core(Linux 또는 Windows)를 사용하려는 경우 사용할 이미지는 microsoft/aspnetcore:2.0입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-172">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="83602-173">따라서 컨테이너에 사용할 기본 Docker 이미지만 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-173">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="83602-174">그 방법은 Dockerfile에 FROM microsoft/aspnetcore:2.0을 추가하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-174">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="83602-175">이 작업은 Visual Studio가 자동으로 수행하지만, 버전을 업데이트하려면 직접 이 값을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-175">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="83602-176">버전 번호가 있는 Docker Hub의 공식 .NET 이미지 리포지토리를 사용하면 모든 컴퓨터에서(개발, 테스트 및 프로덕션 포함) 동일한 언어 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-176">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="83602-177">다음 예제에서는 ASP.NET Core 컨테이너에 대한 샘플 Dockerfile을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="83602-177">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="83602-178">이 예에서 컨테이너는 공식 ASP.NET Core Docker 버전 2.0 이미지(Linux 및 Windows용 다중 아키텍처)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-178">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="83602-179">이것은 설정 `FROM microsoft/aspnetcore:2.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-179">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="83602-180">(이 기본 이미지에 대한 자세한 내용은 [ASP.NET Core Docker 이미지](https://hub.docker.com/r/microsoft/aspnetcore/) 페이지 및 [.NET Core Docker 이미지](https://hub.docker.com/r/microsoft/dotnet/) 페이지를 참조하세요.) 또한 Dockerfile에서, 런타임에 사용할 TCP 포트(이 예에서는 EXPOSE 설정을 사용하여 구성한 대로 포트 80)에서 수신 대기하라고 Docker에 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-180">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="83602-181">사용하는 언어 및 프레임워크에 따라 Dockerfile에서 추가 구성 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-181">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="83602-182">예를 들어 \["dotnet", "MySingleContainerWebApp.dll"\]이 포함된 ENTRYPOINT 줄은 Docker에 .NET Core 응용 프로그램을 실행하라고 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="83602-182">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="83602-183">SDK 및 .NET Core CLI(dotnet CLI)를 사용하여 .NET 응용 프로그램을 빌드하고 실행하는 경우 이 설정이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="83602-183">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="83602-184">결론적으로 ENTRYPOINT 줄 및 기타 설정은 개발자가 응용 프로그램에 대해 선택하는 언어 및 플랫폼에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="83602-184">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="83602-185">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="83602-185">Additional resources</span></span>

-   <span data-ttu-id="83602-186">**.NET Core 응용 프로그램에 대한 Docker 이미지 빌드**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="83602-186">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)</span></span>

-   <span data-ttu-id="83602-187">**고유의 이미지 빌드**.</span><span class="sxs-lookup"><span data-stu-id="83602-187">**Build your own image**.</span></span> <span data-ttu-id="83602-188">공식 Docker 설명서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-188">In the official Docker documentation.</span></span>
    [<span data-ttu-id="83602-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span><span class="sxs-lookup"><span data-stu-id="83602-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span></span>](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="83602-190">다중 아키텍처 이미지 리포지토리 사용</span><span class="sxs-lookup"><span data-stu-id="83602-190">Using multi-arch image repositories</span></span>

<span data-ttu-id="83602-191">단일 리포지토리는 Linux 이미지 및 Windows 이미지 같은 플랫폼 변형을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-191">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="83602-192">이 기능을 통해 Microsoft 같은 공급업체(기본 이미지 작성자)는 여러 플랫폼(즉, Linux 및 Windows)을 처리하는 단일 리포지토리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-192">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="83602-193">예를 들어 Docker Hub 레지스트리에서 제공되는 [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) 리포지토리는 동일한 리포지토리 이름을 사용하여 Linux 및 Windows Nano Server에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-193">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="83602-194">태그를 지정하는 경우 다음과 같이 명시적인 플랫폼을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-194">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="83602-195">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="83602-195">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="83602-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="83602-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="83602-197">그러나 이것은 2017년 중순 이후에 나온 새 기능이며, 동일한 이미지 이름을 지정하고 동일한 태그를 지정하는 경우 새로운 다중 아키텍처 이미지(예: 다중 아키텍처를 지원하는 aspnetcore 이미지)는 다음 예제와 같이 개발자가 배포하는 Docker 호스트 OS에 따라 Linux 또는 Windows 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-197">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="83602-198">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="83602-198">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="83602-199">이와 같이, Windows 호스트에서 이미지를 끌어오면 Windows 변형을 끌어오고, Linux 호스트에서 동일한 이미지 이름을 끌어오면 Linux 변형을 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="83602-199">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="83602-200">옵션 B: 기본 이미지를 처음부터 새로 만들기</span><span class="sxs-lookup"><span data-stu-id="83602-200">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="83602-201">개발자 고유의 Docker 기본 이미지를 처음부터 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-201">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="83602-202">이 시나리오는 Docker를 시작하는 분들에게는 권장하지 않지만, 자신만의 고유한 기본 이미지 비트를 설정하고 싶은 분들은 그렇게 하셔도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-202">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="83602-203">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="83602-203">Additional resources</span></span>

-   <span data-ttu-id="83602-204">**다중 아키텍처 .NET Core 이미지**.</span><span class="sxs-lookup"><span data-stu-id="83602-204">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="83602-205">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="83602-205">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="83602-206">**기본 이미지 만들기**.</span><span class="sxs-lookup"><span data-stu-id="83602-206">**Create a base image**.</span></span> <span data-ttu-id="83602-207">공식 Docker 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-207">Official Docker documentation.</span></span>
    [<span data-ttu-id="83602-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span><span class="sxs-lookup"><span data-stu-id="83602-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span></span>](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="83602-209">3단계.</span><span class="sxs-lookup"><span data-stu-id="83602-209">Step 3.</span></span> <span data-ttu-id="83602-210">고유의 사용자 지정 Docker 이미지를 만들고 그 안에 응용 프로그램 또는 서비스 포함</span><span class="sxs-lookup"><span data-stu-id="83602-210">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="83602-211">응용 프로그램의 서비스마다 관련 이미지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-211">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="83602-212">응용 프로그램이 단일 서비스 또는 웹 응용 프로그램으로 구성된 경우 단일 이미지만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-212">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="83602-213">Docker 이미지는 Visual Studio에서 자동으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-213">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="83602-214">다음 단계는 편집기/CLI 워크플로에만 필요하며 내부적으로 발생하는 동작에 대한 이해를 돕기 위해 설명되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-214">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="83602-215">개발자는 완료된 기능 또는 변경 내용을 소스 제어 시스템(예: GitHub)으로 푸시할 때까지 로컬로 개발 및 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-215">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="83602-216">즉, Docker 이미지를 만들고 로컬 Docker 호스트(Windows 또는 Linux VM)에 컨테이너를 배포한 후 로컬 컨테이너에 대해 실행, 테스트 및 디버그해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-216">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="83602-217">로컬 환경에서 Docker CLI 및 Dockerfile을 사용하여 사용자 지정 이미지를 만들려면 그림 5-5처럼 docker build 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-217">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="83602-218">**그림 5-5**.</span><span class="sxs-lookup"><span data-stu-id="83602-218">**Figure 5-5**.</span></span> <span data-ttu-id="83602-219">사용자 지정 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="83602-219">Creating a custom Docker image</span></span>

<span data-ttu-id="83602-220">필요에 따라 프로젝트 폴더에서 직접 docker 빌드를 실행하는 대신, 먼저 dotnet publish를 실행하여 필수 .NET 라이브러리와 이진 파일로 배포 가능 폴더를 생성한 후 docker build 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-220">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="83602-221">이렇게 하면 cesardl/netcore-webapi-microservice-docker:first라는 이름의 Docker 이미지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="83602-221">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="83602-222">이 경우 첫 번째는 특정 버전을 나타내는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-222">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="83602-223">구성된 Docker 응용 프로그램에 대해 만들어야 하는 사용자 지정 이미지마다 이 단계를 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-223">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="83602-224">또한 응용 프로그램이 여러 컨테이너로 구성된 경우(즉, 다중 컨테이너 응용 프로그램인 경우) docker-compose up --build 명령을 사용하여 관련 docker-compose.yml 파일에 노출된 메타데이터를 통해 단일 명령으로 모든 관련 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-224">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="83602-225">그림 5-6처럼 docker images 명령을 사용하여 로컬 리포지토리에서 기존 이미지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-225">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="83602-226">**그림 5-6.**</span><span class="sxs-lookup"><span data-stu-id="83602-226">**Figure 5-6.**</span></span> <span data-ttu-id="83602-227">docker images 명령을 사용하여 기존 이미지 보기</span><span class="sxs-lookup"><span data-stu-id="83602-227">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="83602-228">Visual Studio로 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="83602-228">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="83602-229">Visual Studio를 사용하여 Docker가 지원되는 프로젝트를 만드는 경우 이미지를 명시적으로 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="83602-229">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="83602-230">그 대신, F5 키를 눌러 Docker화된 응용 프로그램 또는 서비스를 실행하면 자동으로 이미지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="83602-230">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="83602-231">이 단계는 Visual Studio에서 자동으로 실행되며 사용자에게는 보이지 않습니다. 하지만 내부적으로 어떤 일이 발생하는지 알아두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-231">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="83602-232">4단계.</span><span class="sxs-lookup"><span data-stu-id="83602-232">Step 4.</span></span> <span data-ttu-id="83602-233">다중 컨테이너 Docker 응용 프로그램을 빌드할 때 docker compose.yml 파일에서 서비스 정의</span><span class="sxs-lookup"><span data-stu-id="83602-233">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="83602-234">[docker compose.yml](https://docs.docker.com/compose/compose-file/) 파일을 사용하여 배포 명령을 통해 구성된 응용 프로그램으로 배포할 관련 서비스 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-234">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="83602-235">docker-compose.yml 파일을 사용하려면 기본 또는 루트 솔루션 폴더에 다음 예제와 비슷한 콘텐츠가 있는 파일을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-235">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

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

<span data-ttu-id="83602-236">이 docker-compose.yml 파일은 단순화되고 병합된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-236">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="83602-237">항상 적용되는 각 컨테이너에 대한 정적인 구성 데이터(사용자 지정 이미지처럼)와 연결 문자열처럼 배포 환경에 종속된 구성 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-237">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="83602-238">이후 섹션에서는 환경 및 실행 유형(디버그 또는 릴리스)에 따라 docker-compose.yml 구성을 여러 docker-compose 파일로 분할하고 값을 재정의하는 방법을 알아보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-238">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="83602-239">docker-compose.yml 파일 예제에서는 컨테이너로 실행되는 SQL Server for Linux를 기반으로 webmvc 서비스(웹 응용 프로그램), 2개의 마이크로 서비스(catalog.api 및 ordering.api), 1개의 데이터 원본 컨테이너, sql.data의 총 5개 서비스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-239">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="83602-240">각 서비스는 컨테이너로 배포되므로 각 서비스에 Docker 이미지가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-240">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="83602-241">docker-compose.yml 파일은 사용되는 컨테이너뿐 아니라 개별적으로 구성되는 방법까지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-241">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="83602-242">예를 들어 .yml 파일의 webmvc 컨테이너 정의는 다음과 같은 일을 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-242">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="83602-243">미리 빌드된 eshop/web:latest 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-243">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="83602-244">그러나 docker-compose 파일의 빌드: 섹션을 기반으로 한 추가 구성을 사용하여 docker-compose 실행의 일부로 빌드되도록 이미지를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-244">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="83602-245">두 환경 변수(CatalogUrl 및 OrderingUrl)를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-245">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="83602-246">컨테이너에 노출된 포트 80을 호스트 컴퓨터의 포트 80으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-246">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="83602-247">depends\_on 설정을 사용하여 웹앱을 카탈로그 및 주문 서비스와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-247">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="83602-248">이렇게 하면 서비스는 이러한 서비스가 시작될 때까지 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-248">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="83602-249">이후 섹션에서 마이크로 서비스 및 다중 컨테이너 앱을 구현하는 방법을 알아볼 때 docker-compose.yml 파일을 다시 한 번 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-249">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="83602-250">Visual Studio 2017에서 docker-compose.yml 파일 작업</span><span class="sxs-lookup"><span data-stu-id="83602-250">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="83602-251">그림 5-7처럼 Visual Studio 솔루션에서 서비스 프로젝트에 Docker 솔루션 지원을 추가하면 Visual Studio는 프로젝트에 Dockerfile을 추가하고 Dockerfile은 docker-compose.yml 파일을 통해 솔루션에서 서비스 섹션(프로젝트)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-251">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="83602-252">다중 컨테이너 솔루션 구성을 시작하는 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-252">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="83602-253">그런 다음, docker-compose.yml 파일을 열고 추가 기능을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-253">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="83602-254">**그림 5-7**.</span><span class="sxs-lookup"><span data-stu-id="83602-254">**Figure 5-7**.</span></span> <span data-ttu-id="83602-255">ASP.NET Core 프로젝트를 마우스 오른쪽 단추로 클릭하여 Visual Studio 2017에 Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="83602-255">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="83602-256">Visual Studio에 Docker 지원을 추가하면 프로젝트에 Dockerfile이 추가될 뿐 아니라 솔루션 수준에서 설정된 docker-compose.yml 파일에 구성 정보가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-256">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="83602-257">Visual Studio에서 솔루션에 Docker 지원을 추가하면 그림 5-8처럼 추가된 docker-compose.yml 파일을 포함하는 새 노드(docker-compose.dcproj 프로젝트 파일에 있는)가 솔루션 탐색기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-257">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="83602-258">**그림 5-8**.</span><span class="sxs-lookup"><span data-stu-id="83602-258">**Figure 5-8**.</span></span> <span data-ttu-id="83602-259">Visual Studio 2017 솔루션 탐색기에 추가된 **docker-compose** 트리 노드</span><span class="sxs-lookup"><span data-stu-id="83602-259">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="83602-260">docker-compose up 명령을 사용하여 단일 docker-compose.yml 파일이 있는 다중 컨테이너 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-260">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="83602-261">그러나 Visual Studio에서 그룹으로 추가하므로 개발자는 환경(개발 또는 프로덕션) 및 실행 형식(릴리스 또는 디버그)에 따라 값을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-261">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="83602-262">이 기능에 대한 내용은 이후 섹션에서 설명하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-262">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="83602-263">5단계.</span><span class="sxs-lookup"><span data-stu-id="83602-263">Step 5.</span></span> <span data-ttu-id="83602-264">Docker 응용 프로그램을 빌드하고 실행</span><span class="sxs-lookup"><span data-stu-id="83602-264">Build and run your Docker application</span></span>

<span data-ttu-id="83602-265">응용 프로그램에 단일 컨테이너만 있는 경우 응용 프로그램을 Docker 호스트(VM 또는 실제 서버)에 배포하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-265">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="83602-266">그러나 응용 프로그램에 여러 서비스가 있는 경우에는 단일 CLI 명령(docker-compose up)을 사용하여 또는 이 명령을 내부적으로 실행하는 Visual Studio를 사용하여 구성된 응용 프로그램으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-266">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="83602-267">다양한 옵션을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-267">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="83602-268">옵션 A: Docker CLI로 단일 컨테이너 실행</span><span class="sxs-lookup"><span data-stu-id="83602-268">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="83602-269">그림 5-9처럼 docker run 명령을 사용하여 Docker 컨테이너를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-269">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="83602-270">**그림 5-9**.</span><span class="sxs-lookup"><span data-stu-id="83602-270">**Figure 5-9**.</span></span> <span data-ttu-id="83602-271">docker run 명령을 사용하여 Docker 컨테이너 실행</span><span class="sxs-lookup"><span data-stu-id="83602-271">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="83602-272">이 경우 이 명령은 컨테이너의 내부 포트 5000을 호스트 컴퓨터의 포트 80에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-272">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="83602-273">즉, 호스트가 포트 80에서 수신 대기하고 컨테이너의 포트 5000에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-273">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="83602-274">옵션 B: 다중 컨테이너 응용 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="83602-274">Option B: Running a multi-container application</span></span>

<span data-ttu-id="83602-275">대부분의 엔터프라이즈 시나리오에서 Docker 응용 프로그램은 여러 서비스로 구성되며, 따라서 그림 5-10처럼 다중 컨테이너 응용 프로그램을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-275">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="83602-276">**그림 5-10**.</span><span class="sxs-lookup"><span data-stu-id="83602-276">**Figure 5-10**.</span></span> <span data-ttu-id="83602-277">Docker 컨테이너가 배포된 VM</span><span class="sxs-lookup"><span data-stu-id="83602-277">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="83602-278">Docker CLI를 사용하여 다중 컨테이너 응용 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="83602-278">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="83602-279">Docker CLI를 사용하여 다중 컨테이너 응용 프로그램을 실행하려면 docker-compose up 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-279">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="83602-280">이 명령은 솔루션 수준에서 docker-compose.yml 파일을 사용하여 다중 컨테이너 응용 프로그램을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-280">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="83602-281">그림 5-11은 기본 프로젝트 디렉터리에서 명령을 실행할 때의 결과를 보여주며, docker-compose.yml 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-281">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="83602-282">**그림 5-11**.</span><span class="sxs-lookup"><span data-stu-id="83602-282">**Figure 5-11**.</span></span> <span data-ttu-id="83602-283">docker-compose up 명령을 실행할 때의 결과 예제</span><span class="sxs-lookup"><span data-stu-id="83602-283">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="83602-284">docker-compose up 명령을 실행하면 그림 5-10에 보이는 VM처럼 응용 프로그램 및 관련 컨테이너가 Docker 호스트에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-284">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="83602-285">Visual Studio로 다중 컨테이너 응용 프로그램 실행 및 디버깅</span><span class="sxs-lookup"><span data-stu-id="83602-285">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="83602-286">Visual Studio 2017을 사용하여 다중 컨테이너 응용 프로그램을 실행하는 방법이 더 이상 간단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-286">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="83602-287">다중 컨테이너 응용 프로그램을 실행할 수 있을 뿐 아니라, 일반적인 중단점을 설정하여 Visual Studio에서 직접 모든 컨테이너를 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-287">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="83602-288">앞서 언급했듯이, 솔루션 내의 프로젝트에 Docker 솔루션 지원을 추가할 때마다 해당 프로젝트가 전역(솔루션 수준) docker-compose.yml 파일에서 구성되며, 따라서 전체 솔루션을 한꺼번에 실행 또는 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-288">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="83602-289">Visual Studio는 Docker 솔루션 지원이 사용되는 각 프로젝트에 대해 하나의 컨테이너를 시작하고, 모든 내부 단계(dotnet 게시, dotnet 빌드 등)를 자동으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-289">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="83602-290">여기서 중요한 점은, 그림 5-12처럼 Visual Studio 2017에는 F5 키 작업에 대한 추가 **Docker** 명령이 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-290">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="83602-291">이 옵션을 통해 솔루션 수준에서 docker-compose.yml 파일에 정의된 모든 컨테이너를 실행하여 다중 컨테이너 응용 프로그램을 디버깅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-291">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="83602-292">다중 컨테이너 솔루션을 디버그하는 기능이 있다는 것은 서로 다른 프로젝트(컨테이너)마다 하나씩 여러 중단점을 지정할 수 있으며, Visual Studio에서 디버깅할 때 여러 프로젝트에서 정의되어 여러 컨테이너에서 실행되는 중단점에서 중지된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-292">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="83602-293">**그림 5-12**.</span><span class="sxs-lookup"><span data-stu-id="83602-293">**Figure 5-12**.</span></span> <span data-ttu-id="83602-294">Visual Studio 2017에서 다중 컨테이너 앱 실행</span><span class="sxs-lookup"><span data-stu-id="83602-294">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="83602-295">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="83602-295">Additional resources</span></span>

-   <span data-ttu-id="83602-296">**원격 Docker 호스트에 ASP.NET 컨테이너 배포**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="83602-296">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="83602-297">오케스트레이터를 사용하여 테스트 및 배포하는 내용에 대한 메모</span><span class="sxs-lookup"><span data-stu-id="83602-297">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="83602-298">docker-compose up 및 docker run 명령(또는 Visual Studio에서 컨테이너를 실행하고 디버깅)은 개발 환경에서 컨테이너를 테스트하기에 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-298">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="83602-299">하지만 Docker Swarm, Mesosphere DC/OS 또는 Kubernetes 같은 Docker 클러스터와 오케스트레이터를 대상으로 하는 경우에는 이 방법을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-299">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="83602-300">[Docker Swarm 모드](https://docs.docker.com/engine/swarm/)(Windows용 및 Mac용 Docker CE 버전 1.12부터 사용 가능) 같은 클러스터를 사용하는 경우 단일 서비스에 대한 [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) 같은 추가 명령을 사용하여 배포하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-300">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="83602-301">여러 컨테이너로 구성된 응용 프로그램을 배포하는 경우 [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) 및 [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/)을 사용하여 구성된 응용 프로그램을 *스택*으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-301">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="83602-302">자세한 내용은 Docker 설명서의 블로그 게시물 [실험적 분산 응용 프로그램 번들 소개](https://blog.docker.com/2016/06/docker-app-bundle/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83602-302">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="83602-303">Docker 사이트에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-303">on the Docker site.</span></span>

<span data-ttu-id="83602-304">[DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) 및 [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/)의 경우 다양한 배포 명령 및 스크립트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-304">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="83602-305">6단계.</span><span class="sxs-lookup"><span data-stu-id="83602-305">Step 6.</span></span> <span data-ttu-id="83602-306">로컬 Docker 호스트를 사용하여 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="83602-306">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="83602-307">이 단계는 응용 프로그램에서 하는 일에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="83602-307">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="83602-308">단일 컨테이너 또는 서비스로 배포되는 간단한 .NET Core 웹 응용 프로그램에서는 그림 5-13처럼 Docker 호스트에서 브라우저를 열고 해당 사이트로 이동하여 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-308">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="83602-309">(Dockerfile의 구성이 컨테이너를 호스트에 있는 80 이외의 포트로 매핑하는 경우 호스트 게시물을 URL에 포함합니다.)</span><span class="sxs-lookup"><span data-stu-id="83602-309">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host post in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="83602-310">**그림 5-13**.</span><span class="sxs-lookup"><span data-stu-id="83602-310">**Figure 5-13**.</span></span> <span data-ttu-id="83602-311">localhost를 사용하여 로컬로 Docker 응용 프로그램을 테스트하는 예제</span><span class="sxs-lookup"><span data-stu-id="83602-311">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="83602-312">localhost가 Docker 호스트 IP를 가리키지 않는 경우(Docker CE를 사용하는 경우 기본적으로 Docker 호스트 IP를 가리켜야 함) 서비스를 탐색하려면 컴퓨터 네트워크 카드의 IP 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-312">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="83602-313">브라우저에서 이 URL은 우리가 살펴보고 있는 특정 컨테이너 예제에 대한 포트 80을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-313">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="83602-314">그러나 내부적으로는 요청이 포트 5000으로 리디렉션됩니다. 왜냐하면 이전 단계에서 설명했듯이 docker run 명령을 사용하여 이와 같은 방법으로 배포되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-314">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="83602-315">그림 5-14처럼 터미널에서 curl을 사용하여 응용 프로그램을 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-315">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="83602-316">Windows에 설치된 Docker에서 기본 Docker 호스트 IP는 컴퓨터의 실제 IP 주소와는 별개로 항상 10.0.75.1입니다.</span><span class="sxs-lookup"><span data-stu-id="83602-316">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="83602-317">**그림 5-14**.</span><span class="sxs-lookup"><span data-stu-id="83602-317">**Figure 5-14**.</span></span> <span data-ttu-id="83602-318">curl을 사용하여 로컬로 Docker 응용 프로그램을 테스트하는 예제</span><span class="sxs-lookup"><span data-stu-id="83602-318">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="83602-319">Visual Studio 2017을 사용하여 컨테이너 테스트 및 디버깅</span><span class="sxs-lookup"><span data-stu-id="83602-319">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="83602-320">Visual Studio 2017을 사용하여 컨테이너를 실행하고 디버깅할 때 컨테이너 없이 실행할 때와 거의 동일한 방법으로 .NET 응용 프로그램을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-320">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="83602-321">Visual Studio 없이 디버깅 및 테스트</span><span class="sxs-lookup"><span data-stu-id="83602-321">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="83602-322">편집기/CLI 방식을 사용하여 개발하는 경우 컨테이너를 디버깅하기가 훨씬 어려우며 추적을 생성하여 디버그하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-322">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="83602-323">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="83602-323">Additional resources</span></span>

-   <span data-ttu-id="83602-324">**로컬 Docker 컨테이너에서 앱 디버깅**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="83602-324">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="83602-325">**Steve Lasker. Docker를 사용하여 ASP.NET Core 앱 빌드, 디버그, 배포.**</span><span class="sxs-lookup"><span data-stu-id="83602-325">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="83602-326">비디오.</span><span class="sxs-lookup"><span data-stu-id="83602-326">Video.</span></span>
    [<span data-ttu-id="83602-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span><span class="sxs-lookup"><span data-stu-id="83602-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span></span>](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="83602-328">Visual Studio를 사용하여 컨테이너를 개발할 때의 간소화된 워크플로</span><span class="sxs-lookup"><span data-stu-id="83602-328">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="83602-329">Visual Studio를 사용하면 편집기/CLI 방식을 사용할 때보다 워크플로가 훨씬 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-329">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="83602-330">Dockerfile 및 docker-compose.yml 파일과 관련하여 Docker에 필요한 대부분의 단계는 그림 5-15처럼 숨겨져 있거나 Visual Studio를 통해 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-330">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="83602-331">**그림 5-15**.</span><span class="sxs-lookup"><span data-stu-id="83602-331">**Figure 5-15**.</span></span> <span data-ttu-id="83602-332">Visual Studio를 사용하여 배포할 때의 간소화된 워크플로</span><span class="sxs-lookup"><span data-stu-id="83602-332">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="83602-333">또한 2단계(프로젝트에 Docker 지원 추가)를 한 번만 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-333">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="83602-334">따라서 다른 개발에서 .NET을 사용하여 수행하는 일반적인 개발 작업과 워크플로가 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-334">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="83602-335">내부에서 어떤 동작이 발생하는지(이미지 빌드 프로세스, 사용하는 기본 이미지, 컨테이너 배포 등) 알아야 하며, 때로는 Dockerfile 또는 docker-compose.yml 파일을 편집하여 동작을 사용자 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-335">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="83602-336">하지만 Visual Studio를 사용하여 대부분의 작업이 대폭 간소화되므로 개발자의 생산성이 크게 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="83602-336">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="83602-337">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="83602-337">Additional resources</span></span>

-   <span data-ttu-id="83602-338">**Steve Lasker. Visual Studio 2017을 사용하여 .NET Docker 개발**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="83602-338">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="83602-339">**Jeffrey T. Fritz. 새로운 Visual Studio용 Docker 도구를 사용하여 컨테이너에 .NET Core 앱 배포**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="83602-339">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="83602-340">DockerFile에서 PowerShell 명령을 사용하여 Windows 컨테이너 설정</span><span class="sxs-lookup"><span data-stu-id="83602-340">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="83602-341">[Windows 컨테이너](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview)를 사용하면 Docker 생태계의 나머지 부분과 동일한 도구로 기존 Windows 응용 프로그램을 Docker 이미지로 변환하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-341">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="83602-342">Windows 컨테이너를 사용하려면 다음 예제와 같이 Dockerfile에서 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-342">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="83602-343">이 예에서는 PowerShell 명령(RUN 설정)을 통해 Windows Server Core 기본 이미지(FROM 설정)를 사용하고 IIS를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-343">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="83602-344">비슷한 방법으로 PowerShell 명령을 사용하여 ASP.NET 4.x, .NET 4.6 또는 다른 Windows 소프트웨어 같은 추가 구성 요소를 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83602-344">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="83602-345">예를 들어 Dockerfile의 다음 명령은 ASP.NET 4.5를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="83602-345">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="83602-346">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="83602-346">Additional resources</span></span>

-   <span data-ttu-id="83602-347">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="83602-347">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="83602-348">Windows 기능을 포함하도록 dockerfile에서 실행되는 Powershell 명령 예제.</span><span class="sxs-lookup"><span data-stu-id="83602-348">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [<span data-ttu-id="83602-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span><span class="sxs-lookup"><span data-stu-id="83602-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span></span>](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="83602-350">[이전] (index.md) [다음] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="83602-350">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
