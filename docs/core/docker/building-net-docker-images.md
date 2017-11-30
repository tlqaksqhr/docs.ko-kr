---
title: ".NET Core Docker 이미지 작성"
description: "Docker 이미지 및 .NET Core 이해"
keywords: .NET, .NET Core, Docker
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
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="43ca0-104">.NET Core 응용 프로그램에 대한 Docker 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="43ca0-104">Building Docker Images for .NET Core Applications</span></span>

 <span data-ttu-id="43ca0-105">이 자습서에서는 Docker에서.NET Core를 사용 하는 방법에 집중 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-105">In this tutorial, We focus on how to use .NET Core on Docker.</span></span> <span data-ttu-id="43ca0-106">첫째, 살펴볼 제공 되며 Microsoft 및 사용 사례에서 유지 관리 하는 서로 다른 Docker 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-106">First, we explore the different Docker images offered and maintained by Microsoft, and use cases.</span></span> <span data-ttu-id="43ca0-107">에서는 빌드 및 ASP.NET Core 응용 프로그램 dockerize 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-107">We then learn how to build and dockerize an ASP.NET Core app.</span></span>

<span data-ttu-id="43ca0-108">이 자습서는 과정을 자세히 배울 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-108">During the course of this tutorial, you learn:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="43ca0-109">Microsoft.NET Core Docker 이미지에 대 한 자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="43ca0-109">Learn about Microsoft .NET Core Docker images</span></span> 
> * <span data-ttu-id="43ca0-110">ASP.NET Core Dockerize에 샘플 응용 프로그램 가져오기</span><span class="sxs-lookup"><span data-stu-id="43ca0-110">Get an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="43ca0-111">ASP.NET 샘플 앱을 로컬로 실행</span><span class="sxs-lookup"><span data-stu-id="43ca0-111">Run the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="43ca0-112">빌드 및 Linux 컨테이너에 대 한 Docker가 있는 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="43ca0-112">Build and run the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="43ca0-113">빌드 및 Windows 용 Docker 컨테이너와 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-113">Build and run the sample with Docker for Windows containers</span></span>

## <a name="docker-image-optimizations"></a><span data-ttu-id="43ca0-114">Docker 이미지 최적화</span><span class="sxs-lookup"><span data-stu-id="43ca0-114">Docker Image Optimizations</span></span>

<span data-ttu-id="43ca0-115">개발자를 위한 Docker 이미지를 작성할 때 다음 세 가지 주요 시나리오를 중점적으로 고려했습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-115">When building Docker images for developers, we focused on three main scenarios:</span></span>

* <span data-ttu-id="43ca0-116">.NET Core 앱을 개발하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-116">Images used to develop .NET Core apps</span></span>
* <span data-ttu-id="43ca0-117">.NET Core 앱을 빌드하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-117">Images used to build .NET Core apps</span></span>
* <span data-ttu-id="43ca0-118">.NET Core 앱을 실행하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-118">Images used to run .NET Core apps</span></span>

<span data-ttu-id="43ca0-119">왜 이 세 가지 이미지가 중요할까요?</span><span class="sxs-lookup"><span data-stu-id="43ca0-119">Why three images?</span></span>
<span data-ttu-id="43ca0-120">개발, 빌드 및 실행 중인 컨테이너 화 된 응용 프로그램 때 서로 다른 우선 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-120">When developing, building, and running containerized applications, we have different priorities.</span></span>

* <span data-ttu-id="43ca0-121">**개발:** 변경 내용 및 변경 내용을 디버깅 하는 기능에 신속 하 게 우선 순위 중점적 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-121">**Development:**  The priority focuses on quickly iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="43ca0-122">이미지의 크기를으로 중요 하지 않습니다, 그리고 대신 수 변경 코드를 신속 하 게 참조 하세요?</span><span class="sxs-lookup"><span data-stu-id="43ca0-122">The size of the image isn't as important, rather can you make changes to your code and see them quickly?</span></span>

* <span data-ttu-id="43ca0-123">**빌드:** 이 이미지는 컴파일러 및 이진 파일을 최적화 하기 위해 다른 종속성을 포함 하 여 응용 프로그램을 컴파일하는 데 필요한 모든 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-123">**Build:** This image contains everything needed to compile your app, which includes the compiler and any other dependencies to optimize the binaries.</span></span>  <span data-ttu-id="43ca0-124">이미지를 프로덕션에 배치 하는 자산을 만드는 빌드 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-124">You use the build image to create the assets you place into a production image.</span></span> <span data-ttu-id="43ca0-125">연속 통합 또는 빌드 환경에서 빌드 이미지를 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-125">The build image would be used for continuous integration, or in a build environment.</span></span> <span data-ttu-id="43ca0-126">이 방법은 빌드 에이전트를 컴파일하고 빌드 이미지 인스턴스에서 (모든 필수 종속성)이 있는 응용 프로그램을 빌드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-126">This approach allows a build agent to compile and build the application (with all the required dependencies) in a build image instance.</span></span> <span data-ttu-id="43ca0-127">빌드 에이전트는 이 Docker 이미지를 실행하는 방법만 알고 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-127">Your build agent only needs to know how to run this Docker image.</span></span>

* <span data-ttu-id="43ca0-128">**프로덕션:** 배포 하 고 이미지를 시작할 수 속도?</span><span class="sxs-lookup"><span data-stu-id="43ca0-128">**Production:** How fast you can deploy and start your image?</span></span> <span data-ttu-id="43ca0-129">이 이미지 Docker 호스트에 Docker 레지스트리에서 네트워크 성능을 최적화 하도록 작습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-129">This image is small so network performance from your Docker Registry to your Docker hosts is optimized.</span></span> <span data-ttu-id="43ca0-130">콘텐츠를 실행할 준비가 되면 Docker 실행부터 결과 처리까지 가장 빠른 시간에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-130">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="43ca0-131">동적 코드 컴파일에 Docker 모델에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-131">Dynamic code compilation isn't needed in the Docker model.</span></span> <span data-ttu-id="43ca0-132">이 이미지에 배치되는 콘텐츠는 이진 파일과 응용 프로그램을 실행하는 데 필요한 콘텐츠로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-132">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span>

    <span data-ttu-id="43ca0-133">예를 들어는 `dotnet publish` 출력에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-133">For example, the `dotnet publish` output contains:</span></span>

    * <span data-ttu-id="43ca0-134">컴파일된 이진 파일</span><span class="sxs-lookup"><span data-stu-id="43ca0-134">the compiled binaries</span></span>
    * <span data-ttu-id="43ca0-135">.css 및.js 파일</span><span class="sxs-lookup"><span data-stu-id="43ca0-135">.js and .css files</span></span>


<span data-ttu-id="43ca0-136">포함 하는 이유는 `dotnet publish` 프로덕션 이미지에서 명령 출력은 변경 하지 않으려면 해당 '는 최소 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-136">The reason to include the `dotnet publish` command output in your production image is to keep its' size to a minimum.</span></span>

<span data-ttu-id="43ca0-137">일부.NET Core 이미지 최신 태그를 다운로드 하는 것은 비교적 단순해 프로세스 않도록 다른 태그 간의 계층을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-137">Some .NET Core images share layers between different tags so downloading the latest tag is a relatively lightweight process.</span></span> <span data-ttu-id="43ca0-138">컴퓨터에 이전 버전이 이미 있는 경우이 아키텍처는 필요한 디스크 공간을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-138">If you already have an older version on your machine, this architecture decreases the needed disk space.</span></span>

<span data-ttu-id="43ca0-139">동일한 컴퓨터에 공용 이미지를 사용 하는 여러 응용 프로그램, 메모리 공용 이미지 간에 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-139">When multiple applications use common images on the same machine, memory is shared between the common images.</span></span> <span data-ttu-id="43ca0-140">이미지를 공유할 수 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-140">The images must be the same to be shared.</span></span>

## <a name="docker-image-variations"></a><span data-ttu-id="43ca0-141">Docker 이미지 변형</span><span class="sxs-lookup"><span data-stu-id="43ca0-141">Docker image variations</span></span>

<span data-ttu-id="43ca0-142">목표를 달성 하기 위, 아래 이미지 변형 제공 [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/)합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-142">To achieve the goals above, we provide image variants under [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

* <span data-ttu-id="43ca0-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`)이이 이미지는.NET Core 및 명령줄 도구 (CLI)을 포함 하는.NET Core SDK를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-143">`microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) This image contains the .NET Core SDK, which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="43ca0-144">이 이미지는 **개발 시나리오**에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-144">This image maps to the **development scenario**.</span></span> <span data-ttu-id="43ca0-145">이 이미지를 사용 하 여 로컬 개발, 디버깅 및 단위 테스트에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-145">You use this image for local development, debugging, and unit testing.</span></span> <span data-ttu-id="43ca0-146">이 이미지는 **빌드** 시나리오에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-146">This image can also be used for your **build** scenarios.</span></span> <span data-ttu-id="43ca0-147">사용 하 여 `microsoft/dotnet:sdk` 항상 최신 버전을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-147">Using `microsoft/dotnet:sdk` always gives you the latest version.</span></span>

> [!TIP]
> <span data-ttu-id="43ca0-148">사용 하려는 경우 확실 하지 않은 사용자의 요구에 대 한,는 `microsoft/dotnet:<version>-sdk` 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-148">If you are unsure about your needs, you want to use the `microsoft/dotnet:<version>-sdk` image.</span></span> <span data-ttu-id="43ca0-149">Throw가으로 사용할 수 있도록 설계 했습니다 "사실상" 이미지로 트래버스하여 컨테이너 (소스 코드를 탑재 및 응용 프로그램을 시작 컨테이너 시작) 및 다른 이미지를 작성 하는 기본 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-149">As the "de facto" image, it's designed to be used as a throw away container (mount your source code and start the container to start your app), and as the base image to build other images from.</span></span>

* <span data-ttu-id="43ca0-150">`microsoft/dotnet:<version>-runtime`:이 이미지.NET Core (런타임 및 라이브러리)을 포함 하 고 실행 중인.NET Core 응용 프로그램에 최적화 되어 **프로덕션**합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-150">`microsoft/dotnet:<version>-runtime`: This image contains the .NET Core (runtime and libraries) and is optimized for running .NET Core apps in **production**.</span></span>

## <a name="alternative-images"></a><span data-ttu-id="43ca0-151">대체 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-151">Alternative images</span></span>

<span data-ttu-id="43ca0-152">개발, 빌드 및 프로덕션에 최적화된 시나리오 외에도 추가 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-152">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

* <span data-ttu-id="43ca0-153">`microsoft/dotnet:<version>-runtime-deps`: **런타임 deps** 이미지.NET Core에서 필요한 네이티브 종속성의 모든 운영 체제를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-153">`microsoft/dotnet:<version>-runtime-deps`: The **runtime-deps** image contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="43ca0-154">이 이미지에 대 한는 [자체 포함 된 응용 프로그램](https://docs.microsoft.com/dotnet/core/deploying/index)합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-154">This image is for [self-contained applications](https://docs.microsoft.com/dotnet/core/deploying/index).</span></span>

<span data-ttu-id="43ca0-155">각 변형의 최신 버전:</span><span class="sxs-lookup"><span data-stu-id="43ca0-155">Latest versions of each variant:</span></span>

* <span data-ttu-id="43ca0-156">`microsoft/dotnet`또는 `microsoft/dotnet:latest` (SDK 이미지에 대 한 별칭)</span><span class="sxs-lookup"><span data-stu-id="43ca0-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (alias for the SDK image)</span></span>
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a><span data-ttu-id="43ca0-157">탐색 하는 샘플</span><span class="sxs-lookup"><span data-stu-id="43ca0-157">Samples to explore</span></span>

* <span data-ttu-id="43ca0-158">[이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) 프로덕션에 대 한 앱 ASP.NET Core 용 Docker 이미지를 구성 하기 위한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-158">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="43ca0-159">샘플은 Windows와 Linux 컨테이너에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-159">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="43ca0-160">이.NET Core Docker 샘플에 대 한 모범 사례 패턴 [프로덕션에 대 한.NET Core 응용 프로그램에 대 한 Docker 이미지를 작성 합니다.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="43ca0-160">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span>

## <a name="your-first-aspnet-core-docker-app"></a><span data-ttu-id="43ca0-161">첫 번째 ASP.NET Core Docker 앱</span><span class="sxs-lookup"><span data-stu-id="43ca0-161">Your first ASP.NET Core Docker app</span></span>

<span data-ttu-id="43ca0-162">이 자습서에서는 dockerize 하고자 하는 앱에 대 한 ASP.NET Core Docker 샘플 응용 프로그램을 사용 하 여 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-162">For this tutorial, lets use an ASP.NET Core Docker sample application for the app we want to dockerize.</span></span> <span data-ttu-id="43ca0-163">ASP.NET Core Docker 샘플 응용 프로그램에이 프로덕션에 대 한 앱 ASP.NET Core 용 Docker 이미지를 구성 하기 위한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-163">This ASP.NET Core Docker sample application demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="43ca0-164">샘플은 Windows와 Linux 컨테이너에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-164">The sample works with both Linux and Windows containers.</span></span>

<span data-ttu-id="43ca0-165">Dockerfile 샘플 ASP.NET Core 런타임 Docker 기본 이미지 기반으로 ASP.NET Core 응용 프로그램 Docker 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-165">The sample Dockerfile creates an ASP.NET Core application Docker image based off of the ASP.NET Core Runtime Docker base image.</span></span>

<span data-ttu-id="43ca0-166">사용 하 여는 [여러 단계로 이루어진 Docker 빌드 기능](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) 에:</span><span class="sxs-lookup"><span data-stu-id="43ca0-166">It uses the [Docker multi-stage build feature](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) to:</span></span>

* <span data-ttu-id="43ca0-167">에 따라 컨테이너에서 샘플을 빌드하는 **큰** ASP.NET Core 빌드 Docker 기본 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-167">build the sample in a container based on the **larger** ASP.NET Core Build Docker base image</span></span> 
* <span data-ttu-id="43ca0-168">최종 빌드 결과에 따라 Docker 이미지를에 복사는 **더 작은** ASP.NET Core Docker 런타임 기본 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-168">copies the final build result into a Docker image based on the **smaller** ASP.NET Core Docker Runtime base image</span></span>

> [!Note]
> <span data-ttu-id="43ca0-169">빌드 이미지 런타임 이미지는 손실 응용 프로그램을 빌드하는 필요한 도구를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-169">The build image contains required tools to build applications while the runtime image does not.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="43ca0-170">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="43ca0-170">Prerequisites</span></span>

<span data-ttu-id="43ca0-171">빌드하고 실행 하려면 다음 항목을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-171">To build and run, install the following items:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="43ca0-172">.NET core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="43ca0-172">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="43ca0-173">설치 [.NET Core SDK 2.0](https://www.microsoft.com/net/core)합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-173">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

* <span data-ttu-id="43ca0-174">아직 없는 경우, 즐겨 찾는 코드 편집기를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-174">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="43ca0-175">코드 편집기를 설치 해야?</span><span class="sxs-lookup"><span data-stu-id="43ca0-175">Need to install a code editor?</span></span> <span data-ttu-id="43ca0-176">시도 [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="43ca0-176">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="43ca0-177">Docker 클라이언트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-177">Installing Docker Client</span></span>

<span data-ttu-id="43ca0-178">설치 [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) Docker 클라이언트의 이상.</span><span class="sxs-lookup"><span data-stu-id="43ca0-178">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="43ca0-179">에 Docker 클라이언트를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-179">The Docker client can be installed in:</span></span>

* <span data-ttu-id="43ca0-180">Linux 배포</span><span class="sxs-lookup"><span data-stu-id="43ca0-180">Linux distributions</span></span>

   * [<span data-ttu-id="43ca0-181">CentOS</span><span class="sxs-lookup"><span data-stu-id="43ca0-181">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="43ca0-182">Debian</span><span class="sxs-lookup"><span data-stu-id="43ca0-182">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="43ca0-183">Fedora</span><span class="sxs-lookup"><span data-stu-id="43ca0-183">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="43ca0-184">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="43ca0-184">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="43ca0-185">macOS</span><span class="sxs-lookup"><span data-stu-id="43ca0-185">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="43ca0-186">[Windows](https://docs.docker.com/docker-for-windows/)합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-186">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

#### <a name="installing-git-for-sample-repository"></a><span data-ttu-id="43ca0-187">샘플 저장소에 대 한 Git 설치</span><span class="sxs-lookup"><span data-stu-id="43ca0-187">Installing Git for sample repository</span></span>

* <span data-ttu-id="43ca0-188">설치 [git](https://git-scm.com/download) 리포지토리 복제 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="43ca0-188">Install [git](https://git-scm.com/download) if you wish to clone the repository.</span></span>

### <a name="getting-the-sample-application"></a><span data-ttu-id="43ca0-189">샘플 응용 프로그램 가져오기</span><span class="sxs-lookup"><span data-stu-id="43ca0-189">Getting the sample application</span></span>

<span data-ttu-id="43ca0-190">복제 하 여이 샘플을 가져오는 가장 쉬운 방법은 [샘플 리포지토리](https://github.com/dotnet/dotnet-docker-samples) git에서 다음 지침을 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="43ca0-190">The easiest way to get the sample is by cloning the [samples repository](https://github.com/dotnet/dotnet-docker-samples) with git, using the following instructions:</span></span> 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

<span data-ttu-id="43ca0-191">또한.NET Core Docker 샘플 리포지토리에서 zip으로 (에 작은) 저장소를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-191">You can also download the repository (it is small) as a zip from the .NET Core Docker samples repository.</span></span>

### <a name="run-the-aspnet-app-locally"></a><span data-ttu-id="43ca0-192">ASP.NET 응용 프로그램을 로컬로 실행</span><span class="sxs-lookup"><span data-stu-id="43ca0-192">Run the ASP.NET app locally</span></span>

<span data-ttu-id="43ca0-193">참조 지점으로 응용 프로그램을 컨테이너화하기 전에 먼저 로컬로 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-193">For a reference point, before we containerize the application, first run the application locally.</span></span>

<span data-ttu-id="43ca0-194">작성 하 고 (지침에서는 저장소의 루트를 가정 하는 데 사용) 다음 명령을 사용 하 여.NET Core 2.0 SDK와 함께 응용 프로그램을 로컬로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-194">You can build and run the application locally with the .NET Core 2.0 SDK using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
dotnet run
```

<span data-ttu-id="43ca0-195">응용 프로그램이 시작 된 후 방문 **http://localhost:5000** 웹 브라우저에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-195">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a><span data-ttu-id="43ca0-196">빌드 및 Linux 컨테이너에 대 한 Docker가 있는 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="43ca0-196">Build and run the sample with Docker for Linux containers</span></span>

<span data-ttu-id="43ca0-197">빌드하고 수 있습니다 (지침에서는 저장소의 루트를 가정 하는 데 사용) 다음 명령을 사용 하 여 Linux 컨테이너를 사용 하 여 Docker에서 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-197">You can build and run the sample in Docker using Linux containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] <span data-ttu-id="43ca0-198">`docker run` '-p' 인수 지도 포트 컨테이너에는 80으로 로컬 컴퓨터에서 5000 포트 (포트 매핑 폼이 `host:container`).</span><span class="sxs-lookup"><span data-stu-id="43ca0-198">The `docker run` '-p' argument maps port 5000 on your local machine to port 80 in the container (the port mapping form is `host:container`).</span></span> <span data-ttu-id="43ca0-199">자세한 내용은 참조는 [docker 실행](https://docs.docker.com/engine/reference/commandline/exec/) 명령줄 매개 변수에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-199">For more information, see the [docker run](https://docs.docker.com/engine/reference/commandline/exec/) reference on command-line parameters.</span></span>

<span data-ttu-id="43ca0-200">응용 프로그램이 시작 된 후 방문 **http://localhost:5000** 웹 브라우저에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-200">After the application starts, visit **http://localhost:5000** in your web browser.</span></span>

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a><span data-ttu-id="43ca0-201">빌드 및 Windows 용 Docker 컨테이너와 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-201">Build and run the sample with Docker for Windows containers</span></span>

<span data-ttu-id="43ca0-202">빌드하고 수 있습니다 (지침에서는 저장소의 루트를 가정 하는 데 사용) 다음 명령을 사용 하 여 Windows 컨테이너를 사용 하 여 Docker에서 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-202">You can build and run the sample in Docker using Windows containers using the following commands (The instructions assume the root of the repository):</span></span>

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> <span data-ttu-id="43ca0-203">이동 해야 합니다는 **컨테이너 IP 주소** (http://localhost) 대비 직접 브라우저에서 Windows 컨테이너를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="43ca0-203">You must navigate to the **container IP address** (as opposed to http://localhost) in your browser directly when using Windows containers.</span></span> <span data-ttu-id="43ca0-204">다음 단계를 컨테이너의 IP 주소를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-204">You can get the IP address of your container with the following steps:</span></span>

* <span data-ttu-id="43ca0-205">다른 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-205">Open up another command prompt.</span></span>
* <span data-ttu-id="43ca0-206">실행 `docker ps` 프로그램 실행 중인 컨테이너를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-206">Run `docker ps` to see your running containers.</span></span> <span data-ttu-id="43ca0-207">"Aspnetcore_sample" 컨테이너가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-207">The "aspnetcore_sample" container should be there.</span></span>
* <span data-ttu-id="43ca0-208">`docker exec aspnetcore_sample ipconfig`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-208">Run `docker exec aspnetcore_sample ipconfig`.</span></span>
* <span data-ttu-id="43ca0-209">컨테이너 IP 주소를 복사 하 고 (예를 들어 172.29.245.43) 브라우저에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-209">Copy the container IP address and paste into your browser (for example, 172.29.245.43).</span></span>

> [!Note]
> <span data-ttu-id="43ca0-210">Docker exec 식별 컨테이너의 이름이 나 해시를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-210">Docker exec supports identifying containers with name or hash.</span></span> <span data-ttu-id="43ca0-211">이름 (aspnetcore_sample) 예에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-211">The name (aspnetcore_sample) is used in our example.</span></span>

<span data-ttu-id="43ca0-212">다음 예제에서는 실행 중인 Windows 컨테이너의 IP 주소를 얻어야 하는 방법의를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="43ca0-212">See the following example of how to get the IP address of a running Windows container.</span></span>

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!Note]
> <span data-ttu-id="43ca0-213">Docker exec 실행 중인 컨테이너에 새 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-213">Docker exec runs a new command in a running container.</span></span> <span data-ttu-id="43ca0-214">자세한 내용은 참조는 [docker exec 참조](https://docs.docker.com/engine/reference/commandline/exec/) 에 명령줄 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-214">For more information, see the [docker exec reference](https://docs.docker.com/engine/reference/commandline/exec/) on command-line parameters.</span></span>

<span data-ttu-id="43ca0-215">사용 하 여 로컬로 프로덕션 배포를 준비 하는 응용 프로그램을 만들 수 있습니다는 [dotnet 게시](../tools/dotnet-publish.md) 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-215">You can produce an application that is ready to deploy to production locally using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span>

```console
dotnet publish -c release -o published
```

> [!Note]
> <span data-ttu-id="43ca0-216">-C 릴리스 인수 (기본값은 디버그 모드) 릴리스 모드에서 응용 프로그램을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-216">The -c release argument builds the application in release mode (the default is debug mode).</span></span> <span data-ttu-id="43ca0-217">자세한 내용은 참조는 [dotnet run 참조](../tools/dotnet-run.md) 명령줄 매개 변수에 대.</span><span class="sxs-lookup"><span data-stu-id="43ca0-217">For more information, see the [dotnet run reference](../tools/dotnet-run.md) on command-line parameters.</span></span>

<span data-ttu-id="43ca0-218">응용 프로그램을 실행할 수 있습니다 **Windows** 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-218">You can run the application on **Windows** using the following command.</span></span>

```console
dotnet published\aspnetapp.dll
```

<span data-ttu-id="43ca0-219">응용 프로그램을 실행할 수 있습니다 **Linux** 또는 **macOS** 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-219">You can run the application on **Linux** or **macOS** using the following command.</span></span>

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="43ca0-220">이 샘플에 사용 되는 docker 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-220">Docker Images used in this sample</span></span>

<span data-ttu-id="43ca0-221">이 예제에 사용 된 다음 Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="43ca0-221">The following Docker images are used in this sample</span></span>

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

<span data-ttu-id="43ca0-222">지금까지</span><span class="sxs-lookup"><span data-stu-id="43ca0-222">Congratulations!</span></span> <span data-ttu-id="43ca0-223">바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-223">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="43ca0-224">Microsoft.NET Core Docker 이미지에 대 한 학습</span><span class="sxs-lookup"><span data-stu-id="43ca0-224">Learned about Microsoft .NET Core Docker images</span></span>
> * <span data-ttu-id="43ca0-225">ASP.NET Core Dockerize에 샘플 응용 프로그램을 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-225">Got an ASP.NET Core sample app to Dockerize</span></span>
> * <span data-ttu-id="43ca0-226">ASP.NET 샘플 앱을 로컬로 실행</span><span class="sxs-lookup"><span data-stu-id="43ca0-226">Ran the ASP.NET sample app locally</span></span>
> * <span data-ttu-id="43ca0-227">빌드 및 Linux 컨테이너에 대 한 Docker가 있는 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="43ca0-227">Built and ran the sample with Docker for Linux containers</span></span>
> * <span data-ttu-id="43ca0-228">빌드 및 Windows 용 Docker 컨테이너와 샘플을 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-228">Built and ran the sample with Docker for Windows containers</span></span>


<span data-ttu-id="43ca0-229">**다음 단계**</span><span class="sxs-lookup"><span data-stu-id="43ca0-229">**Next Steps**</span></span>

<span data-ttu-id="43ca0-230">수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-230">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="43ca0-231">Visual Studio Docker 도구 사용</span><span class="sxs-lookup"><span data-stu-id="43ca0-231">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="43ca0-232">Azure 컨테이너 인스턴스를 Azure 컨테이너 레지스트리에서 Docker 이미지 배포</span><span class="sxs-lookup"><span data-stu-id="43ca0-232">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="43ca0-233">Visual Studio 코드를 사용 하 여 디버깅</span><span class="sxs-lookup"><span data-stu-id="43ca0-233">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="43ca0-234">가져오기 손에 Visual Studio와 함께 Mac, 컨테이너 및 서버 없이 코드에 대 한 클라우드</span><span class="sxs-lookup"><span data-stu-id="43ca0-234">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="43ca0-235">Mac 랩 용 Docker 및 Visual Studio 시작</span><span class="sxs-lookup"><span data-stu-id="43ca0-235">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> <span data-ttu-id="43ca0-236">Azure 구독이 없는 경우 [바로 등록할](https://azure.microsoft.com/free/?b=16.48) 무료 30 일 계정 및 Azure 서비스의 조합을 사용해 Azure 크레딧에서 get $200에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ca0-236">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
