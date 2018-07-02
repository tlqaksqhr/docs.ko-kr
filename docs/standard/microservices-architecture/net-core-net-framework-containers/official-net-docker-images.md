---
title: 공식 .NET Docker 이미지
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 공식 .NET Docker 이미지
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/06/2018
ms.openlocfilehash: bb2190a4fae6f8a26b220fd12ecb9f65ea6f4b96
ms.sourcegitcommit: 6c480773ae896f45af4671fb3e26611a50e4dd81
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2018
ms.locfileid: "35251118"
---
# <a name="official-net-docker-images"></a><span data-ttu-id="a70fd-103">공식 .NET Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="a70fd-103">Official .NET Docker images</span></span>

<span data-ttu-id="a70fd-104">공식 .NET Docker 이미지는 Microsoft에서 만들고 최적화된 Docker 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-104">The Official .NET Docker images are Docker images created and optimized by Microsoft.</span></span> <span data-ttu-id="a70fd-105">이러한 이미지는 [Docker 허브](https://hub.docker.com/u/microsoft/)의 Microsoft 리포지토리에서 공개적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-105">They are publicly available in the Microsoft repositories on [Docker Hub](https://hub.docker.com/u/microsoft/).</span></span> <span data-ttu-id="a70fd-106">각 리포지토리는 .NET 버전 및 OS와 버전(Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core 등)에 따라 여러 이미지를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-106">Each repository can contain multiple images, depending on .NET versions, and depending on the OS and versions (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etc.).</span></span>

<span data-ttu-id="a70fd-107">.NET Core 2.1 이후에는 ASP.NET Core 이미지를 포함한 모든 .NET Core 이미지를 [.NET Core 이미지 리포지토리](https://hub.docker.com/r/microsoft/dotnet/)의 Docker Hub에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-107">Since .NET Core 2.1, all the .NET Core images, including for ASP.NET Core are available at Docker Hub at the [.NET Core image repo](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="a70fd-108">이미지 리포지토리 대부분은 특정 프레임워크 버전뿐만 아니라 OS(Linux 배포 또는 Windows 버전)를 선택하는 데 도움이 되는 광범위한 태그 지정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-108">Most image repos provide extensive tagging to help you select not just a specific framework version, but also to choose an OS (Linux distro or Windows version).</span></span>


## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a><span data-ttu-id="a70fd-109">개발 및 프로덕션을 위한 .NET Core 및 Docker 이미지 최적화</span><span class="sxs-lookup"><span data-stu-id="a70fd-109">.NET Core and Docker image optimizations for development versus production</span></span>

<span data-ttu-id="a70fd-110">Microsoft에서는 개발자를 위한 Docker 이미지를 빌드할 때 다음과 같은 주요 시나리오를 중점적으로 고려했습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-110">When building Docker images for developers, Microsoft focused on the following main scenarios:</span></span>

-   <span data-ttu-id="a70fd-111">.NET Core 앱을 *개발*하고 빌드하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="a70fd-111">Images used to *develop* and build .NET Core apps.</span></span>

-   <span data-ttu-id="a70fd-112">.NET Core 앱을 *실행*하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="a70fd-112">Images used to *run* .NET Core apps.</span></span>

<span data-ttu-id="a70fd-113">여러 이미지인 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a70fd-113">Why multiple images?</span></span> <span data-ttu-id="a70fd-114">컨테이너화된 응용 프로그램을 개발, 빌드 및 실행할 때 일반적으로 다양한 우선 순위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-114">When developing, building, and running containerized applications, you usually have different priorities.</span></span> <span data-ttu-id="a70fd-115">Microsoft에서는 이러한 별도 작업에 다른 이미지를 제공하여 앱을 개발하고, 빌드하고, 배포하는 별도 프로세스를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-115">By providing different images for these separate tasks, Microsoft helps optimize the separate processes of developing, building, and deploying apps.</span></span>

### <a name="during-development-and-build"></a><span data-ttu-id="a70fd-116">개발 및 빌드 중</span><span class="sxs-lookup"><span data-stu-id="a70fd-116">During development and build</span></span>

<span data-ttu-id="a70fd-117">개발 중에 중요한 점은 변경 내용을 반복하는 신속성 및 변경 내용을 디버깅하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-117">During development, what is important is how fast you can iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="a70fd-118">이미지의 크기는 코드를 변경하고 변경 내용을 신속하게 확인하는 기능만큼 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-118">The size of the image is not as important as the ability to make changes to your code and see the changes quickly.</span></span> <span data-ttu-id="a70fd-119">일부 도구 및 “빌드 에이전트 컨테이너”는 개발 및 빌드 프로세스 중에 개발 ASP.NET Core 이미지(**microsoft/dotnet:2.1-sdk**)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-119">Some tools and "build-agent containers", use the development ASP.NET Core image (**microsoft/dotnet:2.1-sdk**) during development and build process.</span></span> <span data-ttu-id="a70fd-120">Docker 컨테이너 안에 빌드하는 경우 중요한 측면은 앱을 컴파일하기 위해 필요한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-120">When building inside a Docker container, the important aspects are the elements that are needed in order to compile your app.</span></span> <span data-ttu-id="a70fd-121">여기에는 컴파일러 및 다른 .NET 종속성 외에도 웹 개발 종속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-121">This includes the compiler and any other .NET dependencies, plus web development dependencies.</span></span>

<span data-ttu-id="a70fd-122">이러한 형식의 빌드 이미지가 중요한 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="a70fd-122">Why is this type of build image important?</span></span> <span data-ttu-id="a70fd-123">프로덕션에 이 이미지를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-123">You do not deploy this image to production.</span></span> <span data-ttu-id="a70fd-124">대신 프로덕션 이미지에 배치하는 콘텐츠를 빌드하는 데 사용되는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-124">Instead, it is an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="a70fd-125">이 이미지는 Docker 다단계 빌드를 사용할 경우 CI(지속적인 통합) 환경 또는 빌드 환경에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-125">This image would be used in your continuous integration (CI) environment or build environment when using Docker Multi-stage builds.</span></span>

### <a name="in-production"></a><span data-ttu-id="a70fd-126">프로덕션 내</span><span class="sxs-lookup"><span data-stu-id="a70fd-126">In production</span></span>

<span data-ttu-id="a70fd-127">프로덕션에서 중요한 점은 프로덕션 .NET Core 이미지를 기반으로 컨테이너를 배포하고 시작할 수 있는 신속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-127">What is important in production is how fast you can deploy and start your containers based on a production .NET Core image.</span></span> <span data-ttu-id="a70fd-128">따라서 네트워크를 통해 Docker 레지스트리에서 Docker 호스트로 빠르게 이동할 수 있도록 **microsoft/dotnet:2.1-aspnetcore-runtime**을 기반으로 한 런타임 전용 이미지는 소규모입니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-128">Therefore, the runtime-only image based on **microsoft/dotnet:2.1-aspnetcore-runtime** is small so that it can travel quickly across the network from your Docker registry to your Docker hosts.</span></span> <span data-ttu-id="a70fd-129">콘텐츠를 실행할 준비가 되면 컨테이너 시작부터 결과 처리까지 가장 빠른 시간에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-129">The contents are ready to run, enabling the fastest time from starting the container to processing results.</span></span> <span data-ttu-id="a70fd-130">Docker 모델에서 빌드 컨테이너를 사용할 때 dotnet 빌드 또는 dotnet 게시를 실행하므로 C\# 코드로 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-130">In the Docker model, there is no need for compilation from C\# code, as there is when you run dotnet build or dotnet publish when using the build container.</span></span>

<span data-ttu-id="a70fd-131">이 최적화된 이미지에 응용 프로그램을 실행하는 데 필요한 이진 파일 및 기타 콘텐츠를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-131">In this optimized image you put only the binaries and other content needed to run the application.</span></span> <span data-ttu-id="a70fd-132">예를 들어 dotnet 게시에서 만든 콘텐츠에는 컴파일된 .NET 이진 파일, 이미지, .js 및 .css 파일만이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-132">For example, the content created by dotnet publish contains only the compiled .NET binaries, images, .js, and .css files.</span></span> <span data-ttu-id="a70fd-133">시간이 지남에 따라 미리 JIT 컴파일된 패키지를 포함하는 이미지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-133">Over time, you will see images that contain pre-jitted packages.</span></span>

<span data-ttu-id="a70fd-134">여러 버전의 .NET Core 및 ASP.NET Core 이미지가 있지만 기본 계층을 비롯하여 모두 하나 이상의 계층을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-134">Although there are multiple versions of the .NET Core and ASP.NET Core images, they all share one or more layers, including the base layer.</span></span> <span data-ttu-id="a70fd-135">따라서 이미지를 저장하는 데 필요한 디스크 공간의 크기는 작고 사용자 지정 이미지와 해당 기본 이미지 간의 델타로만 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-135">Therefore, the amount of disk space needed to store an image is small; it consists only of the delta between your custom image and its base image.</span></span> <span data-ttu-id="a70fd-136">결과적으로 레지스트리에서 이미지를 빠르게 끌어옵니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-136">The result is that it is quick to pull the image from your registry.</span></span>

<span data-ttu-id="a70fd-137">Docker 허브에서 .NET 이미지 리포지토리를 탐색하는 경우 태그로 분류되거나 표시된 여러 이미지 버전을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-137">When you explore the .NET image repositories at Docker Hub, you will find multiple image versions classified or marked with tags.</span></span> <span data-ttu-id="a70fd-138">이러한 태그를 통해 다음 표와 같이 필요한 버전에 따라 사용할 항목을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a70fd-138">These tags help to decide which one to use, depending on the version you need, like those in the following table:</span></span>

-   <span data-ttu-id="a70fd-139">microsoft/dotnet:**2.1-aspnetcore-runtime**</span><span class="sxs-lookup"><span data-stu-id="a70fd-139">microsoft/dotnet:**2.1-aspnetcore-runtime**</span></span>

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   <span data-ttu-id="a70fd-140">microsoft/**dotnet:2.1-sdk**</span><span class="sxs-lookup"><span data-stu-id="a70fd-140">microsoft/**dotnet:2.1-sdk**</span></span>

        .NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
<span data-ttu-id="a70fd-141">[이전] (net-container-os-targets.md) [다음] (../architect-microservice-container-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="a70fd-141">[Previous] (net-container-os-targets.md) [Next] (../architect-microservice-container-applications/index.md)</span></span>
