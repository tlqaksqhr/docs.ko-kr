---
title: "Docker 앱에 대 한 내부 루프 개발 워크플로"
description: "Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 632c04507c1478238a5dc2573542f8c88bae2a51
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="46123-104">Docker 앱에 대 한 내부 루프 개발 워크플로</span><span class="sxs-lookup"><span data-stu-id="46123-104">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="46123-105">전체 DevOps 스패닝 외부 반복 워크플로 트리거하기 전에 순환, 모든 정보가 각 개발자의 컴퓨터에서 응용 프로그램 자체가 해당 기본 설정된 언어 또는 플랫폼을 사용 하 여 코딩과 로컬로 테스트 (그림 4-14).</span><span class="sxs-lookup"><span data-stu-id="46123-105">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="46123-106">하겠지만 모든 경우에 매우 중요 한 점은 공통적으로 선택 하는 언어, 프레임 워크 또는 플랫폼에 관계 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-106">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="46123-107">이 특정 워크플로의 항상 개발 및 Docker 컨테이너를 로컬로 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-107">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="46123-108">그림 4-14: 내부 루프 개발 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="46123-108">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="46123-109">컨테이너 또는 Docker 이미지의 인스턴스는 이러한 구성 요소를 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-109">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="46123-110">운영 체제 선택 (예를 들어 Linux 배포 또는 Windows)</span><span class="sxs-lookup"><span data-stu-id="46123-110">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="46123-111">개발자 (예를 들어 응용 프로그램 이진 파일)가 추가 된 파일</span><span class="sxs-lookup"><span data-stu-id="46123-111">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="46123-112">구성 (예를 들어, 환경 설정 및 종속성)</span><span class="sxs-lookup"><span data-stu-id="46123-112">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="46123-113">Docker 실행을 처리 하는 것에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="46123-113">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="46123-114">(다음 섹션에서 설명) 프로세스로 Docker를 활용 하는 내부 루프 개발 워크플로를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-114">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="46123-115">한 번만 그렇게 해야 하기 때문에 환경을 설정 하는 초기 단계 포함 되어 있지 고려해 서 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-115">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="46123-116">Visual Studio Code 및 Docker CLI를 사용 하 여 Docker 컨테이너 내에서 단일 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="46123-116">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="46123-117">앱에서 사용자 고유의 서비스 추가 라이브러리 (종속성)로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-117">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="46123-118">그림 4-15에서는 일반적으로 각 단계에 자세히 설명 뒤 Docker 앱을 개발할 때 수행 해야 하는 기본 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46123-118">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="46123-119">그림 4-15: Docker CLI를 사용 하 여 Docker 컨테이너 화 가능한 응용 프로그램에 대 한 기간에 대 한 높은 수준의 워크플로</span><span class="sxs-lookup"><span data-stu-id="46123-119">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="46123-120">1 단계: Visual Studio Code에서 코딩을 시작 하 고 초기 응용 프로그램/서비스 기준 만들기</span><span class="sxs-lookup"><span data-stu-id="46123-120">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="46123-121">응용 프로그램을 개발 하는 방법은 Docker 없이 수행 하는 방법은 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-121">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="46123-122">에 차이가 있는지를 개발 하는 동안 배포 및 테스트 중인 응용 프로그램 또는 로컬 환경 (예: Linux VM 또는 Windows)에 배치 하는 Docker 컨테이너 내에서 실행 되는 서비스.</span><span class="sxs-lookup"><span data-stu-id="46123-122">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="46123-123">**로컬 환경 설정**</span><span class="sxs-lookup"><span data-stu-id="46123-123">**Setting up your local environment**</span></span>

<span data-ttu-id="46123-124">Mac 및 Windows 용 Docker의 최신 버전으로 이전에 Docker 응용 프로그램을 개발 하는 보다 훨씬 더 쉽게 및 설치가 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-124">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="46123-125">**자세한 내용은** 이동에 대 한 지침은 Windows 용 Docker 설정, [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-125">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="46123-126">에 대 한 지침은 Mac 용 Docker 설정로 이동 <https://docs.docker.com/docker-for-mac/>합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-126">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="46123-127">또한 Docker CLI를 사용 하는 동안 응용 프로그램을 실제로 개발할 수 있도록 코드 편집기를 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-127">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="46123-128">Microsoft 제공 Mac, Windows 및 Linux에서 지원 되 고 있는 IntelliSense를 제공 하는 간단한 코드 편집기는 Visual Studio Code [여러 언어에 대 한 지원](https://code.visualstudio.com/docs/languages/overview) (JavaScript,.NET, 이동, Java, Ruby, Python 및 가장 최신 언어의 경우) [디버깅](https://code.visualstudio.com/Docs/editor/debugging), [Git와의 통합](https://code.visualstudio.com/Docs/editor/versioncontrol) 및 [extensions 지원](https://code.visualstudio.com/docs/extensions/overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-128">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="46123-129">이 편집기는 Mac 및 Linux 개발자를 위한 매우 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-129">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="46123-130">Windows에서 전체 Visual Studio 응용 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-130">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="46123-131">**자세한 내용은** 이동에 대 한 지침은 Visual Studio for Windows, Mac 또는 Linux를 설치, [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/)합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-131">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span></span>

<span data-ttu-id="46123-132">Docker CLI를 사용 하 고 다른 코드 편집기를 사용 하 여 코드를 작성 하지만 Dockerfile 작성자에 게 쉽게 및 docker compose.yml 파일 작업 영역에는 Visual Studio 코드를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="46123-132">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="46123-133">또한 아래 Docker CLI를 사용 하 여 상세 작업 실행 될 수 있는 스크립트 물어봅니다 IDE에서 Visual Studio 코드 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-133">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="46123-134">Visual Studio 코드를 설치 해야 하는 확장에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-134">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="46123-135">이렇게 하려면, 키를 눌러 Ctrl + Shift + P를 입력 **ext 설치**, 다음 확장을 실행 하 고: 설치 확장 명령을 마켓플레이스 확장 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-135">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="46123-136">그런 다음 입력 **docker** 결과 필터링 하 그림 4-16 표시 된 것 처럼 Dockerfile 및 Docker 구성 파일 (yml) 지원 확장을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-136">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="46123-137">그림 4-16: Visual Studio 코드에서 Docker 확장 설치</span><span class="sxs-lookup"><span data-stu-id="46123-137">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="46123-138">2 단계: 기존 이미지 (일반 운영 체제 또는.NET Core, Node.js, 및 Ruby와 같은 개발 환경)와 관련 된 DockerFile 만들기</span><span class="sxs-lookup"><span data-stu-id="46123-138">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="46123-139">DockerFile을 빌드해야 하는 사용자 지정 이미지 및 컨테이너를 배포 해야 합니다, 그리고 따라서 응용 프로그램은 하나의 사용자 지정 서비스 이루어진 경우 단일 DockerFile 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-139">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="46123-140">그러나 응용 프로그램은 여러 서비스 (예: microservices 아키텍처)으로 구성 된 경우에 서비스 당 하나의 Dockerfile 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-140">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="46123-141">DockerFile은 일반적으로 응용 프로그램 또는 서비스의 루트 폴더에 배치 하 고 해당 Docker를 설정 하 고 해당 응용 프로그램 또는 서비스를 실행 하는 방법을 알 수 있도록 필요한 명령이 포함 되어 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-141">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="46123-142">DockerFile을 만들고 코드와 함께 프로젝트에 추가할 수 있습니다 (node.js,.NET Core 등), 또는 환경을 처음 접하는 경우 다음 팁을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-142">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="46123-143">라는 명령줄 도구를 사용할 수 있습니다 [yo docker](https://github.com/Microsoft/generator-docker)는 스 캐 폴드에서 선택 하 고 필요한 Docker 구성 파일을 추가 하 여 언어의 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="46123-143">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="46123-144">기본적으로, 적절 한 DockerFile 생성을 지원 하기 위해 시작 하는 개발자가 docker-compose.yml 및 기타 관련된 스크립트 작성 하 고 Docker 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-144">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="46123-145">이 yeoman 생성기 선택한 개발 언어와 대상 컨테이너 호스트를 요청 하는 몇 가지 질문을 라는 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="46123-145">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![yo docker](./media/image21.png)

<span data-ttu-id="46123-147">Windows에서 및 Mac에서, 두 경우 모두 실행 yo docker를 생성 하는 샘플 코드 프로젝트 (현재.NET Core, Golang, 및 지원 되는 언어와 Node.js)에서 작동 하도록 이미 구성 되어 그림 4-17 터미널에서 두 가지 스크린샷입니다를 표시 하는 예를 들어, Docker의 맨 위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-147">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="46123-148">그림 4-17: yo docker 명령 창 (왼쪽)에서 고 Mac의 도구</span><span class="sxs-lookup"><span data-stu-id="46123-148">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="46123-149">그림 4-18를 사용 하는 예제 yo docker 다음 기존.NET Core 프로젝트에 스 캐 폴드 된 수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-149">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="46123-150">그림 4-18: yo 기존.NET core는 docker 프로젝트 준비</span><span class="sxs-lookup"><span data-stu-id="46123-150">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="46123-151">DockerFile에에서 (예: "보낸 사람 microsoft/dotnet:1.0.0-core" 사용) 사용 하 게 어떤 기본 Docker 이미지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-151">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="46123-152">일반적으로 사용자 지정 이미지에서 공식 모든 리포지토리에서 얻을 수 있는 기본 이미지를 기반으로 빌드됩니다는 [Docker 허브 레지스트리](https://hub.docker.com/) (같은 [.NET Core에 대 한 이미지](https://hub.docker.com/r/microsoft/dotnet/) 또는 한 개의 [Node.js용](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="46123-152">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="46123-153">***옵션 a: 기존 공식 Docker 이미지 사용***</span><span class="sxs-lookup"><span data-stu-id="46123-153">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="46123-154">언어 a c k의 공식 리포지토리를 사용 하 여 버전 번호를 가진 동일한 언어 기능을 모든 컴퓨터 (개발, 테스트 및 프로덕션 포함)에서 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-154">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="46123-155">다음은.NET Core 컨테이너에 대 한 샘플 DockerFile입니다.</span><span class="sxs-lookup"><span data-stu-id="46123-155">Following is a sample DockerFile for a .NET Core container:</span></span>

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="46123-156">이 경우 microsoft/aspnetcore:1.0.1 라는 Linux 용 공식 ASP.NET Core Docker 이미지의 버전 1.0.1 사용 중인 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-156">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="46123-157">자세한 내용은 참조는 [ASP.NET Core Docker 이미지 페이지](https://hub.docker.com/r/microsoft/aspnetcore/) 및 [.NET Core Docker 이미지 페이지](https://hub.docker.com/r/microsoft/dotnet/)합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-157">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="46123-158">사용자도 사용할 수 노드: 4와 같은 다른 비교 가능한 이미지-Node.js 또는에서 제공 되는 개발 언어에 대 한 다른 많은 미리 구성 된 이미지에 대 한 onbuild [Docker 허브](https://hub.docker.com/explore/)합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-158">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="46123-159">DockerFile의 Docker (예: 포트 80) 런타임 시 사용할 TCP 포트를 수신 하도록 지시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-159">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="46123-160">Docker에서 응용 프로그램을 실행 하는 방법을 알 수 있도록 언어/프레임 워크를 사용 하는 따라 DockerFile에 추가할 수 있는 구성의 다른 줄 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-160">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="46123-161">ENTRYPOINT 줄을 해야 하는 예를 들어, \["dotnet", "MyCustomMicroservice.dll"\] 작성 하 고 서비스를 실행 하는 방법에 따라 여러 변형을 추가할을 포함할 수는 있지만.NET Core 응용 프로그램에 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-161">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="46123-162">사용 중인 SDK 및 CLI dotnet 작성 하 고.NET 응용 프로그램을 실행 하는 경우 약간 다른 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46123-162">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="46123-163">결론입니다 ENTRYPOINT 줄 및 줄에서 응용 프로그램에 대해 선택한 언어/플랫폼에 따라 다른을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-163">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="46123-164">**자세한 내용은** .NET Core 응용 프로그램에 대 한 Docker 이미지를 작성 하는 방법에 대 한 정보로 이동 <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-164">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="46123-165">사용자 고유의 이미지를 작성 하는 방법에 대 한 자세한 내용은 이동 [https://docs.docker.com/engine/ \자습서/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/)합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-165">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="46123-166">**다중 플랫폼 이미지 리포지토리와**</span><span class="sxs-lookup"><span data-stu-id="46123-166">**Multiplatform image repositories**</span></span>

<span data-ttu-id="46123-167">Windows 컨테이너 점점 더 많이 사용 된, 단일 리포지토리에 플랫폼 변형 Linux 및 Windows 이미지 등을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-167">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="46123-168">이 단일 저장소와 같은 여러 플랫폼을 사용 하는 공급 업체에 대 한 가능 하 게 하는 Docker에 방문 하 고 새로운 기능 [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) DockerHub 레지스트리에서 사용할 수 있는 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="46123-168">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="46123-169">기능 활성화 되 면 서비스를 Windows 호스트에서이 이미지를 끌어오려면 끌어오고 Windows variant Linux variant 끌어오고 Linux 호스트에서 동일한 이미지 이름을 끌어오기 반면 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-169">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="46123-170">***처음부터 기본 이미지 b: 만들기 옵션***</span><span class="sxs-lookup"><span data-stu-id="46123-170">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="46123-171">이 항목에 설명 된 대로 처음부터 직접 Docker 기본 이미지를 만들 수 있습니다 [문서](https://docs.docker.com/engine/userguide/eng-image/baseimages/) Docker에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-171">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="46123-172">Docker로 시작 하는 경우에 가장 적합 한 되지 않았을 수 있는 시나리오 이지만 기본 이미지의 특정 비트를 설정 하려는 경우 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-172">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="46123-173">3 단계: 서비스를 포함 하 여 사용자 지정 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="46123-173">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="46123-174">응용 프로그램을 구성 하는 각 사용자 지정 서비스에 대해 관련된 이미지를 만드는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-174">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="46123-175">응용 프로그램 구성 된 단일 서비스 또는 웹 앱을 단일 이미지 방금 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-175">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="46123-176">계정 "외부 루프 DevOps"워크플로 고려 하는 경우 이미지에서 생성 됩니다는 자동화 된 빌드 프로세스에 의해 해당 글로벌 환경에서 이미지를 만들 수는 소스 코드 (연속 통합) Git 리포지토리에 푸시 될 때마다 사용자 소스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="46123-176">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="46123-177">하지만 해당 외부 반복 경로 생각 전에 Docker 응용 프로그램이 실제로 제대로 작동 하는지 (Git 등) 소스 제어 시스템에 제대로 작동 하지 않을 수 있는 코드를 푸시 하지 않도록 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-177">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="46123-178">따라서 각 개발자는 전체 내부 루프 프로세스 로컬 테스트 및 개발 완전 한 기능 하거나 소스 제어 시스템으로 변경 해야 할 때까지 계속 작업을 수행 해야 하는 먼저 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-178">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="46123-179">로컬 환경 및 DockerFile을 사용 하 여 이미지를 만들려면 사용할 수 있듯이 그림 4-19 docker 빌드 명령 (실행할 수 있습니다 docker 작성-를 몇 가지 컨테이너/서비스에 의해 구성 되는 응용 프로그램에 대 한 빌드).</span><span class="sxs-lookup"><span data-stu-id="46123-179">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="46123-180">그림 4-19: docker 빌드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-180">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="46123-181">필요에 따라 직접 docker를 실행 하는 대신 프로젝트의 폴더에서 빌드를 처음 실행된 dotnet를 사용 하 여 명령을 게시 하 고 docker 빌드를 실행 한 다음 필요한.NET 라이브러리와 함께 배포 가능한 폴더를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-181">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="46123-182">이 예제에서는이 Docker 이미지를 사용 하 여 만듭니다는 이름 cesardl/netcore-webapi-마이크로 서비스-docker: 첫 번째 (: 먼저가 한 개의 태그, 예: 특정 버전).</span><span class="sxs-lookup"><span data-stu-id="46123-182">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="46123-183">각 사용자 지정 이미지를 만들어야 할 여러 컨테이너를 사용 하 여 구성 된 Docker 응용 프로그램에 대해이 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-183">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="46123-184">명령을 찾을 수 있습니다 기존 이미지 로컬 저장소 (개발 컴퓨터)에서 docker를 사용 하 여 이미지, 그림 4-20을 보여 주는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-184">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="46123-185">그림 4-20: 보기 docker 이미지를 사용 하 여 기존 이미지</span><span class="sxs-lookup"><span data-stu-id="46123-185">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="46123-186">4 단계: (선택 사항) 정의에서 docker compose.yml 여러 서비스를 사용 하는 구성 된 Docker 응용 프로그램을 빌드할 때 서비스</span><span class="sxs-lookup"><span data-stu-id="46123-186">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="46123-187">Docker compose.yml 파일에서 다음 단계에에서 설명 된 배포 명령을 사용 하 여 구성 된 응용 프로그램으로 배포 될 관련된 서비스 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-187">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="46123-188">해당 프로그램 main에서 파일 또는 루트 솔루션 폴더를 만들어야 합니다. 유사 콘텐츠는 다음 docker compose.yml 파일에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-188">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

```yml
version: '2'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="46123-189">이 특별 한 경우에이 파일은 두 서비스를 정의 합니다. (사용자 지정 서비스) 웹 서비스 및 redis 서비스 (인기 있는 캐시 서비스).</span><span class="sxs-lookup"><span data-stu-id="46123-189">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="46123-190">각 서비스를 각각에 대 한 구체적인 Docker 이미지를 사용 해야 하므로 컨테이너 기능을 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-190">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="46123-191">이 특정 웹 서비스에 대 한 이미지는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-191">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="46123-192">현재 디렉터리에 DockerFile에서 빌드</span><span class="sxs-lookup"><span data-stu-id="46123-192">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="46123-193">노출 된 포트 80: 컨테이너 호스트 컴퓨터의 포트 81에 전달</span><span class="sxs-lookup"><span data-stu-id="46123-193">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="46123-194">프로젝트 디렉터리를 이미지를 다시 빌드하지 않고도 코드를 수정할 수 있도록 /code 컨테이너 내에 호스트에 탑재 하십시오.</span><span class="sxs-lookup"><span data-stu-id="46123-194">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="46123-195">웹 서비스는 redis 서비스에 연결</span><span class="sxs-lookup"><span data-stu-id="46123-195">Link the web service to the redis service</span></span>

<span data-ttu-id="46123-196">Redis 서비스에서 사용 하는 [최신 공용 redis 이미지](https://hub.docker.com/_/redis/) Docker 허브 레지스트리에서 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-196">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="46123-197">[redis](http://redis.io/) 는 서버 쪽 응용 프로그램을 위한 인기 있는 캐시 시스템.</span><span class="sxs-lookup"><span data-stu-id="46123-197">[redis](http://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="46123-198">5 단계: 빌드 및 Docker 앱 실행</span><span class="sxs-lookup"><span data-stu-id="46123-198">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="46123-199">응용 프로그램에 단일 컨테이너에만 있는 경우 (VM 또는 실제 서버) Docker 호스트에 배포 하 여 실행 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-199">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="46123-200">그러나 앱 여러 서비스 이루어진 경우 해야 *작성*도 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-200">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="46123-201">다양 한 옵션을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-201">Let's see the different options.</span></span>

<span data-ttu-id="46123-202">***A: 실행 단일 컨테이너 또는 서비스 옵션***</span><span class="sxs-lookup"><span data-stu-id="46123-202">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="46123-203">다음과 같이 명령을 실행 하는 docker를 사용 하 여 Docker 이미지를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-203">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="46123-204">Note를이 특정 배포에 대 한에서는 합니다 수 리디렉션 5000 내부 포트를 포트 80에 전송 된 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="46123-204">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="46123-205">이제 응용 프로그램은 외부 포트는 호스트 수준에서 80에서 수신 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-205">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="46123-206">***옵션 b: 작성 및 여러 컨테이너 응용 프로그램 실행***</span><span class="sxs-lookup"><span data-stu-id="46123-206">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="46123-207">대부분의 엔터프라이즈 시나리오에서 여러 서비스 Docker 응용 프로그램 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-207">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="46123-208">이러한 경우에는 명령을 실행할 수 있습니다 docker 작성를 (그림 4-21) 있으며에 이전에 만든 docker compose.yml 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-208">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="46123-209">이 명령을 실행의 관련된 컨테이너의 모든 구성 된 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-209">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="46123-210">그림 4-21: "docker-작성을" 명령을 실행 결과</span><span class="sxs-lookup"><span data-stu-id="46123-210">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="46123-211">Docker를 실행 한 후-를 작성, 그림 4-22에서 VM 표현에 표시 된 것 처럼 응용 프로그램 및 해당 관련된 컨테이너에 Docker 호스트에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-211">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="46123-212">배포 된 Docker 컨테이너를 사용 하 여 그림 4-22: VM</span><span class="sxs-lookup"><span data-stu-id="46123-212">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="46123-213">참고 docker-작성을 및 docker 실행 하면 컨테이너 개발 환경에서 테스트를 위해 충분 수도 있지만 있습니다 수 전혀 사용 하지 않는 해당 Docker 클러스터 작업을 하기를 기대 하 고 docker는 Docker Swarm, Mesosphere DC/OS 또는 Kubernetes orchestrators와 같은 경우 까지 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-213">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="46123-214">같은 클러스터를 사용 하 여 [docker는 Docker Swarm 모드](https://docs.docker.com/engine/swarm/) 배포 하 고 있는 경우 또는 단일 서비스에 대 한 docker 서비스 만들기와 같은 추가 명령을 사용 하 여 테스트 해야 (사용 가능 Docker에 대 한 Windows 및 Mac에서 1.12 버전 이후) 여러 컨테이너를 구성 하는 응용 프로그램을 배포, 번들 작성 docker를 사용 하 여 한 docker는 myBundleFile, 문서에 설명 된 대로 스택으로 구성 된 앱을 배포 하 여 배포 [분산 응용 프로그램 번들](https://blog.docker.com/2016/06/docker-app-bundle/) Docker에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-214">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="46123-215">에 대 한 [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) 및 [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) 다양 한 배포 명령 및 스크립트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-215">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="46123-216">6 단계: (로컬로 로컬 CD VM)에서 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="46123-216">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="46123-217">이 단계는 앱이 수행 하는 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="46123-217">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="46123-218">매우 간단한.NET Core Web API에서 "Hello World"로 단일 컨테이너 또는 서비스 배포를 DockerFile에 지정 된 TCP 포트를 제공 하 여 서비스에 액세스 해야만 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-218">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="46123-219">사용자가 서비스를 이동 하려면 localhost, 설정 되지 않은 경우는이 명령을 사용 하 여 컴퓨터에 대 한 IP 주소를 찾을:</span><span class="sxs-lookup"><span data-stu-id="46123-219">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="46123-220">docker 컴퓨터 ip *사용자 컨테이너 이름*</span><span class="sxs-lookup"><span data-stu-id="46123-220">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="46123-221">Docker 호스트에 브라우저를 열고 해당 사이트;로 이동 를 실행 하 여 응용 프로그램/서비스 그림 4-23에서와 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-221">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="46123-222">그림 4-23: localhost를 사용 하 여 로컬로 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="46123-222">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="46123-223">어떻게에 배포 된 docker run. 앞에서 설명한 대로 있기 때문에 포트 80을 사용 하지만 내부적으로 5000, 포트에 리디렉션되지가 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-223">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="46123-224">이 터미널에서 CURL을 사용 하 여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46123-224">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="46123-225">Windows에서 Docker 설치에서 기본 IP 그림 4-24 표시 된 것 처럼 10.0.75.1, 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46123-225">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="46123-226">그림 4-24: CURL을 사용 하 여 로컬로 Docker 응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="46123-226">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="46123-227">**Docker에서 실행 중인 컨테이너 디버깅**</span><span class="sxs-lookup"><span data-stu-id="46123-227">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="46123-228">Node.js 및.NET Core 컨테이너 등의 다른 플랫폼을 사용 하는 경우 visual Studio 코드 디버깅 Docker를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-228">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="46123-229">또한 디버그할 수.NET Core 컨테이너 Docker에서 Visual Studio를 사용 하는 경우 다음 섹션에 설명 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-229">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="46123-230">**추가 정보:** 이동 Node.js Docker 컨테이너를 디버깅 하는 방법에 대 한 자세한 내용은 <https://blog.docker.com/2016/07/live-debugging-docker/> 및 [https://blogs.msdn.microsoft.com/ \ \ 사용자\_ed/2016/02/27 / visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/)합니다.</span><span class="sxs-lookup"><span data-stu-id="46123-230">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="46123-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="46123-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span></span>
