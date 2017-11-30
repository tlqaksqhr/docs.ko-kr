---
title: ".NET 및 Docker 소개"
description: "이해 Docker 및.NET Core"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a><span data-ttu-id="b2255-104">.NET 및 Docker 소개</span><span class="sxs-lookup"><span data-stu-id="b2255-104">Introduction to .NET and Docker</span></span>

 <span data-ttu-id="b2255-105">이 문서를 소개 하 고 Docker에는.NET 작업의 배경 개념을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-105">This article provides an introduction and conceptual background to working with .NET on Docker.</span></span> 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a><span data-ttu-id="b2255-106">Docker: 배포 하 고 원하는 위치에 실행 하 여 앱 패키징</span><span class="sxs-lookup"><span data-stu-id="b2255-106">Docker: Packaging your apps to deploy and run anywhere</span></span>

<span data-ttu-id="b2255-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) 개발자와 관리자가 빌드할 수 있도록 하는 개방형 플랫폼은 [이미지](https://docs.docker.com/glossary/?term=image), 배송, 및 라는 느슨하게 격리 된 환경에서 배포 응용 프로그램을 실행 한 [컨테이너](https://www.docker.com/what-container).</span><span class="sxs-lookup"><span data-stu-id="b2255-107">[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) is an open platform that enables developers and administrators to build [images](https://docs.docker.com/glossary/?term=image), ship, and run distributed applications in a loosely isolated environment called a [container](https://www.docker.com/what-container).</span></span> <span data-ttu-id="b2255-108">이 방법을 개발, QA, 및 프로덕션 환경 간의 효율적인 응용 프로그램 수명 주기 관리를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-108">This approach enables efficient application lifecycle management between development, QA, and production environments.</span></span>
 
<span data-ttu-id="b2255-109">[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform) 사용 하 여는 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine) 을 신속 하 게 빌드하고로 앱을 패키지할 [Docker images](https://docs.docker.com/glossary/?term=image) 로 작성 된 파일을 사용 하 여 만든는 [Dockerfile ](https://docs.docker.com/glossary/?term=Dockerfile) 형식이 다음 되어 배포에서 실행 한 [컨테이너 계층화](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image) created using files written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format that then is deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

<span data-ttu-id="b2255-110">만들거나 사용자 고유의 [이미지 계층화](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) dockerfile 또는 기존 업체에서 사용 하 여 한 [레지스트리](https://docs.docker.com/glossary/?term=registry)처럼 [Docker 허브](https://docs.docker.com/glossary/?term=Docker%20Hub)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-110">You can either create your own [layered images](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) as dockerfiles or use existing ones from a [registry](https://docs.docker.com/glossary/?term=registry), like [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).</span></span>

<span data-ttu-id="b2255-111">[Docker 컨테이너, 이미지 및 레지스트리 간의 관계](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) 은 중요 한 개념 때 [설계 하 고 구축 응용 프로그램 또는 microservices 컨테이너 화 된](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-111">The [relationship between Docker containers, images, and registries](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) is an important concept when [architecting and building containerized applications or microservices](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/).</span></span> <span data-ttu-id="b2255-112">이 방법은 개발 및 배포 사이의 시간을 크게 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-112">This approach greatly shortens the time between development and deployment.</span></span>

### <a name="further-reading-and-watching"></a><span data-ttu-id="b2255-113">추가 정보 (및 보고)</span><span class="sxs-lookup"><span data-stu-id="b2255-113">Further reading (and watching)</span></span>

* [<span data-ttu-id="b2255-114">Windows 기반 컨테이너: 엔터프라이즈급 컨트롤이 있는 최신 웹 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-114">Windows-based containers: Modern app development with enterprise-grade control.</span></span>](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [<span data-ttu-id="b2255-115">Docker 개요</span><span class="sxs-lookup"><span data-stu-id="b2255-115">Docker overview</span></span>](https://docs.docker.com/engine/docker-overview/)
* [<span data-ttu-id="b2255-116">Windows 컨테이너의 Dockerfile</span><span class="sxs-lookup"><span data-stu-id="b2255-116">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="b2255-117">Dockerfile을 작성 하기 위한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="b2255-117">Best practices for writing Dockerfiles</span></span>](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [<span data-ttu-id="b2255-118">.NET Core 응용 프로그램에 대 한 빌딩 Docker 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-118">Building Docker Images for .NET Core applications</span></span>](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a><span data-ttu-id="b2255-119">.NET Docker 이미지 가져오기</span><span class="sxs-lookup"><span data-stu-id="b2255-119">Getting .NET Docker Images</span></span>

<span data-ttu-id="b2255-120">공식.NET Docker 이미지 생성 및 Microsoft에 의해 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-120">The Official .NET Docker images are created and optimized by Microsoft.</span></span> <span data-ttu-id="b2255-121">서로 공개적으로 사용할 수 있는 것은 Docker 허브에서 Microsoft 저장소에서입니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-121">They are publicly available in the Microsoft repositories on Docker Hub.</span></span> <span data-ttu-id="b2255-122">각 저장소는 OS 버전 및.NET 버전에 따라 여러 이미지를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-122">Each repository can contain multiple images, depending on .NET versions, and on OS versions.</span></span> <span data-ttu-id="b2255-123">대부분 이미지 리포지토리 특정 프레임 워크 버전 및 OS (Linux 배포판 또는 Windows 버전)를 모두 선택할 수 있도록 광범위 한 태그를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-123">Most image repos provide extensive tagging to help you select both a specific framework version and an OS (Linux distro or Windows version).</span></span>

## <a name="scenario-based-guidance"></a><span data-ttu-id="b2255-124">시나리오 기반 지침</span><span class="sxs-lookup"><span data-stu-id="b2255-124">Scenario Based Guidance</span></span>

<span data-ttu-id="b2255-125">.NET 저장소에 대 한 Microsoft의 용도 세부적인 이어서 초점을 맞추고 리포지토리 있으며 특정 시나리오 나 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-125">Microsoft’s intent for .NET repositories is to have granular and focused repos, which represent a specific scenario or workload.</span></span>

<span data-ttu-id="b2255-126">`microsoft/aspnetcore` 컨테이너 더 빠르게 시작할 수 있습니다, Docker에 대 한 ASP.NET Core 응용 프로그램에 대해 이미지 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-126">The `microsoft/aspnetcore` images are optimized for ASP.NET Core apps on Docker, so containers can start faster.</span></span>

<span data-ttu-id="b2255-127">.NET Core 이미지 (`microsoft/dotnet`)은.NET Core를 기반으로 하는 콘솔 앱을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-127">The .NET Core images (`microsoft/dotnet`) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="b2255-128">예를 들어 일괄 처리, Azure WebJobs 및 기타 콘솔 시나리오는 최적화 된.NET Core 이미지를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-128">For example, batch processes, Azure WebJobs, and other console scenarios should use optimized .NET Core images.</span></span>

<span data-ttu-id="b2255-129">Docker 및.NET 응용 프로그램을 사용 하는 가장 확실 한 가로 시나리오는 프로덕션 배포 및 호스팅에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-129">The most obvious horizontal scenario for using Docker and .NET applications is for production deployment and hosting.</span></span> <span data-ttu-id="b2255-130">사실은 프로덕션 시나리오 하나는 및의 다른 요소는 동일 하 게 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-130">It turns out that production is just one scenario and the other ones are equally useful.</span></span> <span data-ttu-id="b2255-131">이러한 시나리오는.NET에 한정 되지 않는 있지만 대부분의 개발자 플랫폼에 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-131">These scenarios are not specific to .NET, but should apply to most developer platforms.</span></span>

* <span data-ttu-id="b2255-132">**낮은 마찰 설치** -로컬 설치 없이.NET 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-132">**Low friction install** — You can try out .NET without a local install.</span></span> <span data-ttu-id="b2255-133">방금에.net Docker 이미지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-133">Just download a Docker image with .NET in it.</span></span>

* <span data-ttu-id="b2255-134">**컨테이너에서 개발한** -개발 및 프로덕션 환경을 (개발자 컴퓨터에서 전역 상태와 같은 문제를 방지) 유사 하 게 만드는 일관 된 환경에서 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-134">**Develop in a container** — You can develop in a consistent environment, making development and production environments similar (avoiding issues like global state on developer machines).</span></span> <span data-ttu-id="b2255-135">도 Docker 용 visual Studio Tools를 사용 하는 컨테이너 Visual Studio에서 직접 시작 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-135">Visual Studio Tools for Docker even enable you to start a container directly from Visual Studio.</span></span>

* <span data-ttu-id="b2255-136">**컨테이너에서 테스트** -마지막 테스트에서 남아 있는 기타 변경 내용 또는 잘못 구성 된 환경으로 인 한 실패를 줄이는 한 컨테이너에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-136">**Test in a container** — You can test in a container, reducing failures due to incorrectly configured environments or other changes left behind from the last test.</span></span>

* <span data-ttu-id="b2255-137">**컨테이너에 빌드** -올바르게 여러 환경에 대 한 공유 빌드 컴퓨터를 구성 하지만 대신 "BYOC" 이동 필요가 없도록는 컨테이너의 코드를 작성할 수 있습니다 (사용자 고유의 컨테이너 bring) 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-137">**Build in a container** — You can build code in a container, avoiding the need to correctly configure shared build machines for multiple environments but instead move to a “BYOC” (bring your own container) approach.</span></span>

* <span data-ttu-id="b2255-138">**모든 환경에서 배포** -사용자 환경의 모든 이미지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-138">**Deployment in all environments** — You can deploy an image through all of your environments.</span></span> <span data-ttu-id="b2255-139">이 방법은 일반적으로 외부 구성 (예를 들어 삽입 된 환경 변수)를 통해 이미지 동작을 변경 하는 구성 차이로 인 한 오류를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-139">This approach reduces failures due to configuration differences, typically changing the image behavior via external configuration (for example, injected environment variables).</span></span>

<span data-ttu-id="b2255-140">[일반적인 지침](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) Docker 컨테이너 개발을 위한.NET Core와.NET Framework 중에서 결정 하는 것에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-140">[General guidance](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) for deciding between .NET Core and .NET Framework for Docker container development.</span></span>

### <a name="common-docker-development-scenarios"></a><span data-ttu-id="b2255-141">일반적인 Docker 개발 시나리오</span><span class="sxs-lookup"><span data-stu-id="b2255-141">Common Docker development scenarios</span></span>

#### <a name="net-core"></a><span data-ttu-id="b2255-142">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2255-142">.NET Core</span></span>

<span data-ttu-id="b2255-143">**.NET core 리소스**</span><span class="sxs-lookup"><span data-stu-id="b2255-143">**.NET Core resources**</span></span>

 <span data-ttu-id="b2255-144">관심 있는 시나리오에 맞는.NET Core 샘플을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-144">Pick the .NET Core samples that fit your scenarios of interest.</span></span> <span data-ttu-id="b2255-145">모든 샘플 지침 Windows, Linux 또는 macOS 호스트에서 Windows 또는 Linux Docker 이미지를 대상으로 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-145">All sample instructions describe how to target Windows or Linux Docker images from Windows, Linux, or macOS hosts.</span></span>

<span data-ttu-id="b2255-146">샘플은.NET Core 2.0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-146">The samples use .NET Core 2.0.</span></span> <span data-ttu-id="b2255-147">Docker를 사용 [여러 단계로 이루어진 빌드](https://github.com/dotnet/announcements/issues/18) 및 [다중 아치 태그](https://github.com/dotnet/announcements/issues/14) 해당 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="b2255-147">They use Docker [multi-stage build](https://github.com/dotnet/announcements/issues/18) and [multi-arch tags](https://github.com/dotnet/announcements/issues/14) where appropriate.</span></span>

* [<span data-ttu-id="b2255-148">DockerHub에서.NET core 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-148">.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="b2255-149">.NET Core 응용 프로그램 dockerize</span><span class="sxs-lookup"><span data-stu-id="b2255-149">Dockerize a .NET Core application</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)

* <span data-ttu-id="b2255-150">이.NET Core Docker 샘플에서는 설명 하는 방법을 [.NET Core 개발 프로세스에서 Docker를 사용 하 여](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-150">This .NET Core Docker sample demonstrates how to [use Docker in your .NET Core development process](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev).</span></span> <span data-ttu-id="b2255-151">샘플은 Windows와 Linux 컨테이너에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-151">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="b2255-152">이.NET Core Docker 샘플에 대 한 모범 사례 패턴 [프로덕션에 대 한.NET Core 응용 프로그램에 대 한 Docker 이미지를 작성 합니다.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span><span class="sxs-lookup"><span data-stu-id="b2255-152">This .NET Core Docker sample demonstrates a best practice pattern for [building Docker images for .NET Core apps for production.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)</span></span> <span data-ttu-id="b2255-153">샘플은 Windows와 Linux 컨테이너에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-153">The sample works with both Linux and Windows containers.</span></span>

* <span data-ttu-id="b2255-154">이 [.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) Docker 이미지를 구축 하기 위한 모범 사례 패턴을 보여 줍니다 [자체 포함 된.NET Core 응용 프로그램](https://docs.microsoft.com/dotnet/core/deploying/)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-154">This [.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) demonstrates a best practice pattern for building Docker images for [self-contained .NET Core applications](https://docs.microsoft.com/dotnet/core/deploying/).</span></span> <span data-ttu-id="b2255-155">이점을 활용 하지 않고 작은 프로덕션 컨테이너에 사용 되는 [컨테이너 간의 기본 이미지를 공유](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-155">Used for the smallest production container without a benefit from [sharing base images between containers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).</span></span> <span data-ttu-id="b2255-156">그러나 하위 Docker 계층을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-156">However, lower Docker layers could be shared.</span></span>

#### <a name="arm32--raspberry-pi"></a><span data-ttu-id="b2255-157">ARM32 라스베리 Pi /</span><span class="sxs-lookup"><span data-stu-id="b2255-157">ARM32 / Raspberry Pi</span></span>

* [<span data-ttu-id="b2255-158">.NET core 런타임 ARM32 빌드 알림</span><span class="sxs-lookup"><span data-stu-id="b2255-158">.NET Core Runtime ARM32 builds announcement</span></span>](https://github.com/dotnet/announcements/issues/29)

* [<span data-ttu-id="b2255-159">ARM32 DockerHub에 라스베리 Pi.NET Core 이미지 /</span><span class="sxs-lookup"><span data-stu-id="b2255-159">ARM32 / Raspberry Pi .NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/dotnet/)

* [<span data-ttu-id="b2255-160">ARM32 GitHub에서 샘플을.NET Core Docker 라즈베리 Pi /</span><span class="sxs-lookup"><span data-stu-id="b2255-160">ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub</span></span>](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a><span data-ttu-id="b2255-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b2255-161">.NET Framework</span></span>

* <span data-ttu-id="b2255-162">[DockerHub에서.NET framework 이미지](https://hub.docker.com/r/microsoft/dotnet-framework/) 이 리포지토리에 다양 한.NET Framework Docker 구성을 보여 주는 샘플이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-162">[.NET Framework images on DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) This repo contain samples that demonstrate various .NET Framework Docker configurations.</span></span> <span data-ttu-id="b2255-163">사용자 고유의 Docker 이미지의 기반으로 이러한 이미지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-163">You can use these images as the basis of your own Docker images.</span></span>

<span data-ttu-id="b2255-164">**.NET framework 4.7**</span><span class="sxs-lookup"><span data-stu-id="b2255-164">**.NET Framework 4.7**</span></span>

<span data-ttu-id="b2255-165">[는 [dotnet-프레임 워크: 4.7 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) 의 기본 "hello world" 사용법을 보여 줍니다는 [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-165">[The [dotnet-framework:4.7 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) demonstrates basic "hello world" usage of the [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47).</span></span> <span data-ttu-id="b2255-166">빌드에 의존 하는 앱을 배포 하는 방법을 표시 하는 [.NET Framework 4.7 docker 이미지](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-166">It shows you how you can build and deploy the app relying on the [.NET Framework 4.7 docker image](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).</span></span>

<span data-ttu-id="b2255-167">**.NET framework 4.6.2**</span><span class="sxs-lookup"><span data-stu-id="b2255-167">**.NET Framework 4.6.2**</span></span>

<span data-ttu-id="b2255-168">[dotnet-프레임 워크: 4.6.2 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) 의 기본 "hello world" 사용법을 보여 줍니다는 [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-168">The [dotnet-framework:4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) demonstrates basic "hello world" usage of the [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462).</span></span> <span data-ttu-id="b2255-169">빌드에 의존 하는 앱을 배포 하는 방법을 표시 하는 [.NET Framework 4.6.2 docker 이미지](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-169">It shows you how you can build and deploy the app relying on the [.NET Framework 4.6.2 docker image](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).</span></span>

<span data-ttu-id="b2255-170">**.NET framework 3.5**</span><span class="sxs-lookup"><span data-stu-id="b2255-170">**.NET Framework 3.5**</span></span>

 <span data-ttu-id="b2255-171">[dotnet-프레임 워크: 3.5 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) 의 기본 "hello world" 사용법을 보여 줍니다 [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-171">The [dotnet-framework:3.5 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) demonstrates basic "hello world" usage of [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5).</span></span> <span data-ttu-id="b2255-172">표시 빌드 Docker에서.NET Framework 3.5에 의존 하는 프로젝트를 배포 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="b2255-172">It shows you how you can build and deploy a project relying on .NET Framework 3.5 in Docker.</span></span>

#### <a name="aspnet-core"></a><span data-ttu-id="b2255-173">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2255-173">ASP.NET Core</span></span>

* <span data-ttu-id="b2255-174">[이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) 프로덕션에 대 한 앱 ASP.NET Core 용 Docker 이미지를 구성 하기 위한 모범 사례 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-174">[This ASP.NET Core Docker sample](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) demonstrates a best practice pattern for building Docker images for ASP.NET Core apps for production.</span></span> <span data-ttu-id="b2255-175">샘플은 Windows와 Linux 컨테이너에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-175">The sample works with both Linux and Windows containers.</span></span>

* [<span data-ttu-id="b2255-176">DockerHub에서 ASP.NET Core 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-176">ASP.NET Core images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [<span data-ttu-id="b2255-177">GitHub에서 ASP.NET Core 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-177">ASP.NET Core images on GitHub</span></span>](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a><span data-ttu-id="b2255-178">ASP.NET 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="b2255-178">ASP.NET Framework</span></span> 

* [<span data-ttu-id="b2255-179">DockerHub에서 ASP.NET 프레임 워크 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-179">ASP.NET Framework images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnet/)

* [<span data-ttu-id="b2255-180">ASP.NET Web Forms 응용 프로그램에서.NET Framework 4.6.2 샘플에 액세스</span><span class="sxs-lookup"><span data-stu-id="b2255-180">ASP.NET Web Forms app on .NET Framework 4.6.2 sample</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a><span data-ttu-id="b2255-181">Windows Communication Framework (WCF)</span><span class="sxs-lookup"><span data-stu-id="b2255-181">Windows Communication Framework (WCF)</span></span>

* [<span data-ttu-id="b2255-182">DockerHub에서 프레임 워크 WCF (Windows Communication) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-182">Windows Communication Framework (WCF) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/wcf/)

* [<span data-ttu-id="b2255-183">GitHub의 Windows Communication Framework (WCF) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-183">Windows Communication Framework (WCF) images on GitHub</span></span>](https://github.com/microsoft/iis-docker)

* [<span data-ttu-id="b2255-184">.NET Full Framework 4.6.2를 사용 하 여 Windows Communication Framework (WCF) Docker 예제</span><span class="sxs-lookup"><span data-stu-id="b2255-184">Windows Communication Framework (WCF) Docker samples using .NET Full Framework 4.6.2</span></span>](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a><span data-ttu-id="b2255-185">Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="b2255-185">Internet Information Server (IIS)</span></span>

* [<span data-ttu-id="b2255-186">DockerHub에서 인터넷 정보 서버 (IIS) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-186">Internet Information Server (IIS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/iis/)

* [<span data-ttu-id="b2255-187">GitHub의 인터넷 정보 서버 (IIS) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-187">Internet Information Server (IIS) images on GitHub</span></span>](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a><span data-ttu-id="b2255-188">다른 Microsoft 스택 컨테이너 이미지와 상호 작용</span><span class="sxs-lookup"><span data-stu-id="b2255-188">Interact with other Microsoft stack container images</span></span>

#### <a name="microsoft-sql-server"></a><span data-ttu-id="b2255-189">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2255-189">Microsoft SQL Server</span></span>

* [<span data-ttu-id="b2255-190">Docker 빠른 시작으로 2017 Linux 컨테이너 이미지를 위한 Microsoft SQL Server 실행</span><span class="sxs-lookup"><span data-stu-id="b2255-190">Run the Microsoft SQL Server for Linux 2017 container image with Docker Quickstart</span></span>](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [<span data-ttu-id="b2255-191">DockerHub에 Linux 이미지에 대 한 Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2255-191">Microsoft SQL Server for Linux images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="b2255-192">DockerHub에서 Windows 컨테이너에 대 한 Microsoft SQL Server 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-192">Microsoft SQL Server for Windows Containers images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [<span data-ttu-id="b2255-193">DockerHub에 Windows 컨테이너에 대 한 Microsoft SQL Server Express Edition 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-193">Microsoft SQL Server Express Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [<span data-ttu-id="b2255-194">DockerHub에 Windows 컨테이너에 대 한 Microsoft SQL Server Developer Edition 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-194">Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub</span></span>](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a><span data-ttu-id="b2255-195">Visual Studio Team Services (VSTS) 에이전트</span><span class="sxs-lookup"><span data-stu-id="b2255-195">Visual Studio Team Services (VSTS) agent</span></span>

* [<span data-ttu-id="b2255-196">DockerHub에서 visual Studio Team Services (VSTS) 에이전트 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-196">Visual Studio Team Services (VSTS) agent images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/)

* [<span data-ttu-id="b2255-197">GitHub에서 visual Studio Team Services (VSTS) 에이전트 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-197">Visual Studio Team Services (VSTS) agent images on GitHub</span></span>](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a><span data-ttu-id="b2255-198">Operations Management Suite (OMS) Linux 에이전트</span><span class="sxs-lookup"><span data-stu-id="b2255-198">Operations Management Suite (OMS) Linux agent</span></span>

* [<span data-ttu-id="b2255-199">Operations Management Suite (OMS) Linux 에이전트 개요</span><span class="sxs-lookup"><span data-stu-id="b2255-199">Operations Management Suite (OMS) Linux agent overview</span></span>](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [<span data-ttu-id="b2255-200">DockerHub에 operations Management Suite (OMS) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-200">Operations Management Suite (OMS) images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [<span data-ttu-id="b2255-201">GitHub에 operations Management Suite (OMS) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-201">Operations Management Suite (OMS) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a><span data-ttu-id="b2255-202">Microsoft Azure 명령줄 인터페이스 (CLI)</span><span class="sxs-lookup"><span data-stu-id="b2255-202">Microsoft Azure Command Line Interface (CLI)</span></span>

* [<span data-ttu-id="b2255-203">DockerHub에서 Microsoft Azure 명령줄 인터페이스 (CLI) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-203">Microsoft Azure Command Line Interface (CLI) images on DockerHub</span></span>](Docker image for Microsoft Azure Command Line Interface) 

* [<span data-ttu-id="b2255-204">GitHub의 Microsoft Azure 명령줄 인터페이스 (CLI) 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-204">Microsoft Azure Command Line Interface (CLI) images on GitHub</span></span>](https://github.com/Microsoft/OMS-docker)

> [!Note]
> <span data-ttu-id="b2255-205">Azure 구독이 없는 경우 [바로 등록할](https://azure.microsoft.com/free/?b=16.48) 무료 30 일 계정 및 Azure 서비스의 조합을 사용해 Azure 크레딧에서 get $200에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-205">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a><span data-ttu-id="b2255-206">Microsoft Azure DB Cosmos 에뮬레이터 (Windows 컨테이너에만 해당)</span><span class="sxs-lookup"><span data-stu-id="b2255-206">Microsoft Azure Cosmos DB Emulator (Windows Containers only)</span></span>

* [<span data-ttu-id="b2255-207">DockerHub에서 Microsoft Azure Cosmos DB 에뮬레이터 이미지</span><span class="sxs-lookup"><span data-stu-id="b2255-207">Microsoft Azure Cosmos DB Emulator images on DockerHub</span></span>](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [<span data-ttu-id="b2255-208">로컬 개발 및 테스트에 대 한 Azure Cosmos DB 에뮬레이터를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="b2255-208">Use the Azure Cosmos DB Emulator for local development and testing</span></span>](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a><span data-ttu-id="b2255-209">풍부한 Docker 개발 생태계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-209">Exploring the rich Docker development ecosystem</span></span>

<span data-ttu-id="b2255-210">Docker 플랫폼 및 다른 Docker 이미지에 대해 배웠습니다, 했으므로 풍부한 Docker 생태계를 탐색 하는 다음 단계가입니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-210">Now that you have learned about the Docker platform and different Docker images, the next step is to explore the rich Docker ecosystem.</span></span> <span data-ttu-id="b2255-211">다음 링크는 Microsoft 도구 컨테이너 개발을 보완 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2255-211">The following links show you how the Microsoft tools complement container development.</span></span>

* [<span data-ttu-id="b2255-212">.NET 및 Docker를 함께 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="b2255-212">Using .NET and Docker together</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [<span data-ttu-id="b2255-213">디자인 하 고 여러 컨테이너 및 마이크로 서비스 기반.NET 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="b2255-213">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [<span data-ttu-id="b2255-214">Visual Studio 코드 Docker 확장</span><span class="sxs-lookup"><span data-stu-id="b2255-214">Visual Studio Code Docker extension</span></span>](https://code.visualstudio.com/docs/languages/dockerfile) 
* [<span data-ttu-id="b2255-215">Azure Service Fabric을 사용 하는 방법에 알아봅니다</span><span class="sxs-lookup"><span data-stu-id="b2255-215">Learn how to use Azure Service Fabric</span></span>](https://docs.microsoft.com/azure/service-fabric/) 
* [<span data-ttu-id="b2255-216">서비스 패브릭 Getting Started 샘플</span><span class="sxs-lookup"><span data-stu-id="b2255-216">Service Fabric Getting Started Sample</span></span>](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [<span data-ttu-id="b2255-217">Windows 컨테이너의 이점</span><span class="sxs-lookup"><span data-stu-id="b2255-217">Benefits of Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [<span data-ttu-id="b2255-218">Visual Studio Docker 도구 사용</span><span class="sxs-lookup"><span data-stu-id="b2255-218">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="b2255-219">Azure 컨테이너 인스턴스를 Azure 컨테이너 레지스트리에서 Docker 이미지 배포</span><span class="sxs-lookup"><span data-stu-id="b2255-219">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [<span data-ttu-id="b2255-220">Visual Studio 코드를 사용 하 여 디버깅</span><span class="sxs-lookup"><span data-stu-id="b2255-220">Debugging with Visual Studio Code</span></span>](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [<span data-ttu-id="b2255-221">가져오기 손에 Visual Studio와 함께 Mac, 컨테이너 및 서버 없이 코드에 대 한 클라우드</span><span class="sxs-lookup"><span data-stu-id="b2255-221">Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud</span></span>](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [<span data-ttu-id="b2255-222">Mac 랩 용 Docker 및 Visual Studio 시작</span><span class="sxs-lookup"><span data-stu-id="b2255-222">Getting Started with Docker and Visual Studio for Mac Lab</span></span>](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a><span data-ttu-id="b2255-223">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b2255-223">Next Steps</span></span>

* [<span data-ttu-id="b2255-224">.NET core Docker 기본 사항 알아보기</span><span class="sxs-lookup"><span data-stu-id="b2255-224">Learn Docker Basics with .NET Core</span></span>](../docker/docker-basics-dotnet-core.md)
* [<span data-ttu-id="b2255-225">.NET Core Docker 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="b2255-225">Building .NET Core Docker Images</span></span>](../docker/building-net-docker-images)