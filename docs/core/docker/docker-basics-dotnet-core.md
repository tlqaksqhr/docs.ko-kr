---
title: ".NET core Docker 기본 사항 알아보기"
description: "Docker 및.NET Core 기본 자습서"
keywords: ".NET,.NET core, Docker, 자습서"
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="16e47-104">.NET core Docker 기본 사항 알아보기</span><span class="sxs-lookup"><span data-stu-id="16e47-104">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="16e47-105">이 자습서에서는 Docker 컨테이너를 빌드 및.NET Core 응용 프로그램에 대 한 작업을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-105">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="16e47-106">이 자습서는 과정을 자세히 배울 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="16e47-107">Dockerfile 파일을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="16e47-107">How to create a Dockerfile</span></span>
> * <span data-ttu-id="16e47-108">.NET Core 응용 프로그램을 만드는 방법.</span><span class="sxs-lookup"><span data-stu-id="16e47-108">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="16e47-109">Docker 컨테이너에 앱을 배포 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-109">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="16e47-110">[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform) 사용 하 여는 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine) 을 신속 하 게 빌드하고로 앱을 패키지할 [Docker images](https://docs.docker.com/glossary/?term=image)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-110">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="16e47-111">이러한 이미지 작성는 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 형식 수 배포에서 실행 하는 [컨테이너 계층에](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-111">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="16e47-112">.NET core: 가장 쉬운 방법은 시작 하려면</span><span class="sxs-lookup"><span data-stu-id="16e47-112">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="16e47-113">Docker 이미지를 만들기 전에 응용 프로그램을 컨테이너 화할 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-113">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="16e47-114">Windows, Linux 또는 MacOS 등에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-114">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="16e47-115">작업을 수행 하는 빠르고 쉬운 방법을.NET Core를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-115">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="16e47-116">.NET Core CLI 도구 집합에 익숙하지 않은 경우 [.NET Core SDK 개요](../tools/index.md)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="16e47-116">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="16e47-117">사용 하 여 Windows와 Linux 컨테이너를 빌드할 수 [다중 arch 기반 태그](https://github.com/dotnet/announcements/issues/14)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-117">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="16e47-118">첫 번째.NET Core Docker 앱</span><span class="sxs-lookup"><span data-stu-id="16e47-118">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="16e47-119">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="16e47-119">Prerequisites</span></span>

<span data-ttu-id="16e47-120">이 자습서를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-120">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="16e47-121">.NET core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="16e47-121">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="16e47-122">설치 [.NET Core SDK 2.0](https://www.microsoft.com/net/core)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-122">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="16e47-123">지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16e47-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="16e47-124">아직 없는 경우, 즐겨 찾는 코드 편집기를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-124">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="16e47-125">코드 편집기를 설치 해야?</span><span class="sxs-lookup"><span data-stu-id="16e47-125">Need to install a code editor?</span></span> <span data-ttu-id="16e47-126">시도 [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="16e47-126">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="16e47-127">Docker 클라이언트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-127">Installing Docker Client</span></span>

<span data-ttu-id="16e47-128">설치 [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) Docker 클라이언트의 이상.</span><span class="sxs-lookup"><span data-stu-id="16e47-128">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="16e47-129">에 Docker 클라이언트를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-129">The Docker client can be installed in:</span></span>

* <span data-ttu-id="16e47-130">Linux 배포</span><span class="sxs-lookup"><span data-stu-id="16e47-130">Linux distributions</span></span>

   * [<span data-ttu-id="16e47-131">CentOS</span><span class="sxs-lookup"><span data-stu-id="16e47-131">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="16e47-132">Debian</span><span class="sxs-lookup"><span data-stu-id="16e47-132">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="16e47-133">Fedora</span><span class="sxs-lookup"><span data-stu-id="16e47-133">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="16e47-134">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="16e47-134">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="16e47-135">macOS</span><span class="sxs-lookup"><span data-stu-id="16e47-135">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="16e47-136">[Windows](https://docs.docker.com/docker-for-windows/)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-136">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="16e47-137">Dockerization에 대 한.NET Core 2.0 콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="16e47-137">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="16e47-138">명령 프롬프트를 열고 *Hello*라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-138">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="16e47-139">사용자가 만든 폴더를 찾아 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-139">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="16e47-140">이제 간단한 연습을 해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-140">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="16e47-141">[`dotnet new`](../tools/dotnet-new.md)는 콘솔 앱을 빌드하는 데 필요한 종속성이 있는 최신 `Hello.csproj` 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-141">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="16e47-142">응용 프로그램에 대한 진입점을 포함하는 기본 파일인 `Program.cs`도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-142">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="16e47-143">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="16e47-143">`Hello.csproj`:</span></span>

   <span data-ttu-id="16e47-144">프로젝트 파일은 종속성을 복원하고 프로그램을 빌드하는 데 필요한 모든 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-144">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="16e47-145">`OutputType` 태그에서는 실행 파일, 즉 콘솔 응용 프로그램을 빌드하고 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-145">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="16e47-146">`TargetFramework` 태그에서는 대상으로 하는 .NET 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-146">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="16e47-147">고급 시나리오에서는 여러 대상 프레임 워크를 지정 하 고 단일 작업에서 지정 된 프레임 워크를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-147">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="16e47-148">이 자습서에서는.NET Core 2.0에 대 한 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-148">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="16e47-149">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="16e47-149">`Program.cs`:</span></span>

   <span data-ttu-id="16e47-150">프로그램을 시작 하 여 `using System`합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-150">The program starts by `using System`.</span></span> <span data-ttu-id="16e47-151">이 문구는 의미 "의 모든 항목으로 전환한는 `System` 이 파일에 대 한 범위로 네임 스페이스입니다."</span><span class="sxs-lookup"><span data-stu-id="16e47-151">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="16e47-152">`System` 네임스페이스에는 `string` 또는 숫자 형식과 같은 기본 구문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-152">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="16e47-153">그런 다음 `Hello`라는 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-153">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="16e47-154">네임 스페이스를 원하는 대로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-154">You can change namespace to anything you want.</span></span> <span data-ttu-id="16e47-155">`Program`이라는 클래스는 해당 네임스페이스 내에서 인수로 문자열 배열을 사용하는 `Main` 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-155">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="16e47-156">이 배열에는 컴파일된 프로그램을 호출할 때 전달된 인수 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-156">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="16e47-157">예제에서는 프로그램만 쓴 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="16e47-157">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="16e47-158">표시합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-158">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="16e47-159">.NET Core에서는 2.x **dotnet 새** 실행 되는 [ `dotnet restore` ](../tools/dotnet-restore.md) 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-159">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="16e47-160">**Dotnet 복원** 복원와 종속성 트리는 [NuGet](https://www.nuget.org/)(.NET 패키지 관리자) 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-160">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="16e47-161">NuGet에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-161">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="16e47-162">분석 하는 *Hello.csproj* 파일</span><span class="sxs-lookup"><span data-stu-id="16e47-162">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="16e47-163">파일 다운로드 종속성 (또는 컴퓨터 캐시에서 가져와)</span><span class="sxs-lookup"><span data-stu-id="16e47-163">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="16e47-164">기록 된 *obj/project.assets.json* 파일</span><span class="sxs-lookup"><span data-stu-id="16e47-164">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="16e47-165">*project.assets.json* 파일은 NuGet 종속성 그래프, 바인딩 해상도 및 다른 응용 프로그램 메타 데이터의 전체 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-165">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="16e47-166">이 필수와 같은 다른 도구에서 사용은 파일 [ `dotnet build` ](../tools/dotnet-build.md) 및 [ `dotnet run` ](../tools/dotnet-run.md), 소스 코드를 올바르게 처리 하려면.</span><span class="sxs-lookup"><span data-stu-id="16e47-166">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="16e47-167">[`dotnet run`](../tools/dotnet-run.md)호출 [ `dotnet build` ](../tools/dotnet-build.md) 성공적인 빌드를 차례로 호출을 확인 하려면 `dotnet <assembly.dll>` 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-167">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="16e47-168">고급 시나리오에 대 한 참조 [.NET Core 응용 프로그램 배포](../deploying/index.md) 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-168">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="16e47-169">.NET Core 응용 프로그램 dockerize</span><span class="sxs-lookup"><span data-stu-id="16e47-169">Dockerize the .NET Core application</span></span>

<span data-ttu-id="16e47-170">Hello.NET Core 콘솔 앱 성공적으로 로컬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-170">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="16e47-171">이제 보겠습니다 더 나아가 단계를 빌드 및 Docker에서 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-171">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="16e47-172">첫 번째 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="16e47-172">Your first Dockerfile</span></span>

<span data-ttu-id="16e47-173">텍스트 편집기를 열고 시작 해 보겠습니다!</span><span class="sxs-lookup"><span data-stu-id="16e47-173">Open your text editor and let's get started!</span></span> <span data-ttu-id="16e47-174">응용 프로그램에 구축 Hello 디렉터리에서 계속 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-174">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="16e47-175">어느 Linux에 대 한 다음 Docker 명령을 추가 또는 [Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/) 새 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-175">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="16e47-176">완료 되 면으로 Hello 디렉터리의 루트에 저장 **Dockerfile**을 확장명이 없는 (파일 형식으로 설정 해야 `All types (*.*)` 또는 이와 유사한).</span><span class="sxs-lookup"><span data-stu-id="16e47-176">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="16e47-177">Dockerfile에 순서 대로 실행 되는 Docker 빌드 명령이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-177">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="16e47-178">첫 번째 명령 이어야 [ **FROM**](https://docs.docker.com/engine/reference/builder/#from)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-178">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="16e47-179">이 명령은 새 빌드 단계를 초기화 하 고 나머지 지시에 대 한 기본 이미지를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-179">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="16e47-180">다중 아치 태그 Windows 용 Docker에 따라 Windows 또는 Linux 컨테이너를 끌어오도록 [컨테이너 모드](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-180">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="16e47-181">이 샘플에 대 한 기본 이미지는 microsoft/dotnet 리포지토리에서 2.0 sdk 이미지</span><span class="sxs-lookup"><span data-stu-id="16e47-181">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="16e47-182">[ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) 명령 작업 디렉터리 설정 모든 나머지 실행, CMD, ENTRYPOINT, 복사 및 추가 Dockerfile에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-182">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="16e47-183">디렉터리가 존재 하지 않는 경우 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-183">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="16e47-184">이 경우 WORKDIR 앱 디렉터리로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-184">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="16e47-185">[ **복사** ](https://docs.docker.com/engine/reference/builder/#copy) 명령 원본 경로에서 새 파일 또는 디렉터리를 복사 하 고 대상 컨테이너 파일 시스템에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-185">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="16e47-186">이 명령으로 C# 프로젝트 파일 컨테이너에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-186">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="16e47-187">[ **실행** ](https://docs.docker.com/engine/reference/builder/#run) 명령 현재 이미지를 기반으로 새 계층의 모든 명령을 실행 하 고 결과 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-187">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="16e47-188">결과 커밋된 이미지는 Dockerfile의 다음 단계에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-188">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="16e47-189">실행 중인 **dotnet 복원** C# 프로젝트 파일의 필요한 종속성을 가져오려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-189">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="16e47-190">이 **복사** 복사 하는 명령 파일의 나머지 부분에이 컨테이너에 새 [레이어](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-190">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="16e47-191">이 응용 프로그램 게시 **실행** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-191">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="16e47-192">[ **dotnet 게시** ](../tools/dotnet-publish.md) 명령은 응용 프로그램을 컴파일하고, 프로젝트 파일에 지정 된 종속성을 읽는다는 및 디렉터리에 파일의 결과 집합을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-192">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="16e47-193">앱과 함께 게시 되는 **릴리스** 구성 및 기본 디렉터리에 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-193">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="16e47-194">[ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) 명령 실행 파일로 실행할 컨테이너 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-194">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="16e47-195">Dockerfile 이제입니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-195">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="16e47-196">앱 이미지 복사</span><span class="sxs-lookup"><span data-stu-id="16e47-196">copies your app to the image</span></span>
* <span data-ttu-id="16e47-197">이미지에 대 한 응용 프로그램의 종속성</span><span class="sxs-lookup"><span data-stu-id="16e47-197">your app's dependencies to the image</span></span>
* <span data-ttu-id="16e47-198">앱이 실행 파일로 실행 되도록 작성</span><span class="sxs-lookup"><span data-stu-id="16e47-198">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="16e47-199">Hello.NET Core 2.0 앱 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="16e47-199">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="16e47-200">필수 Docker 명령</span><span class="sxs-lookup"><span data-stu-id="16e47-200">Essential Docker commands</span></span>

<span data-ttu-id="16e47-201">필수 이러한 Docker 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-201">These Docker commands are essential:</span></span>

* [<span data-ttu-id="16e47-202">docker 빌드</span><span class="sxs-lookup"><span data-stu-id="16e47-202">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="16e47-203">docker 실행</span><span class="sxs-lookup"><span data-stu-id="16e47-203">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="16e47-204">docker ps</span><span class="sxs-lookup"><span data-stu-id="16e47-204">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="16e47-205">docker stop</span><span class="sxs-lookup"><span data-stu-id="16e47-205">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="16e47-206">docker rm</span><span class="sxs-lookup"><span data-stu-id="16e47-206">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="16e47-207">docker rmi</span><span class="sxs-lookup"><span data-stu-id="16e47-207">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="16e47-208">docker 이미지</span><span class="sxs-lookup"><span data-stu-id="16e47-208">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="16e47-209">빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="16e47-209">Build and run</span></span>

<span data-ttu-id="16e47-210">Dockerfile; 작성 했습니다. 이제 Docker는 응용 프로그램을 작성 하 고 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-210">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="16e47-211">출력을는 `docker build` 명령 콘솔 출력은 다음과 같은 형태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-211">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="16e47-212">출력에서 보시 Docker 엔진 사용 Dockerfile이 컨테이너를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-212">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="16e47-213">출력을는 `docker run` 명령 콘솔 출력은 다음과 같은 형태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-213">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="16e47-214">지금까지</span><span class="sxs-lookup"><span data-stu-id="16e47-214">Congratulations!</span></span> <span data-ttu-id="16e47-215">바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-215">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="16e47-216">로컬.NET Core 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="16e47-216">Created a local .NET Core app</span></span>
> * <span data-ttu-id="16e47-217">만든 첫 번째 컨테이너를 만들려는 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="16e47-217">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="16e47-218">빌드되고 Dockerized 앱 실행</span><span class="sxs-lookup"><span data-stu-id="16e47-218">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="16e47-219">다음 단계</span><span class="sxs-lookup"><span data-stu-id="16e47-219">Next Steps</span></span>

<span data-ttu-id="16e47-220">수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-220">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="16e47-221">.NET Docker 이미지 비디오 소개</span><span class="sxs-lookup"><span data-stu-id="16e47-221">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="16e47-222">Visual Studio, Docker 및 Azure 컨테이너 인스턴스 시너지 효과!</span><span class="sxs-lookup"><span data-stu-id="16e47-222">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="16e47-223">Azure Quickstarts 용 docker</span><span class="sxs-lookup"><span data-stu-id="16e47-223">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="16e47-224">Azure에 대 한 Docker에서 앱 배포</span><span class="sxs-lookup"><span data-stu-id="16e47-224">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="16e47-225">Azure 구독이 없는 경우 [바로 등록할](https://azure.microsoft.com/free/?b=16.48) 무료 30 일 계정 및 Azure 서비스의 조합을 사용해 Azure 크레딧에서 get $200에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e47-225">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="16e47-226">이 샘플에 사용 되는 docker 이미지</span><span class="sxs-lookup"><span data-stu-id="16e47-226">Docker Images used in this sample</span></span>

<span data-ttu-id="16e47-227">이 예제에 사용 된 다음 Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="16e47-227">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="16e47-228">관련 참고 자료</span><span class="sxs-lookup"><span data-stu-id="16e47-228">Related Resources</span></span>

* [<span data-ttu-id="16e47-229">.NET core Docker 샘플</span><span class="sxs-lookup"><span data-stu-id="16e47-229">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="16e47-230">Windows 컨테이너의 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="16e47-230">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="16e47-231">.NET framework Docker 샘플</span><span class="sxs-lookup"><span data-stu-id="16e47-231">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="16e47-232">DockerHub에서 ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="16e47-232">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="16e47-233">.NET Core 응용 프로그램-Docker 자습서 dockerize</span><span class="sxs-lookup"><span data-stu-id="16e47-233">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="16e47-234">Visual Studio Docker 도구 사용</span><span class="sxs-lookup"><span data-stu-id="16e47-234">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="16e47-235">Azure 컨테이너 인스턴스를 Azure 컨테이너 레지스트리에서 Docker 이미지 배포</span><span class="sxs-lookup"><span data-stu-id="16e47-235">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)