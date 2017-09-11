---
title: ".NET Core Docker 이미지 작성"
description: "Docker 이미지 및 .NET Core 이해"
keywords: .NET, .NET Core, Docker
author: spboyer
ms.author: shboyer
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.translationtype: HT
ms.sourcegitcommit: 9dc52f3a8c74c1aa575a83cb3bbd579b93fae9ae
ms.openlocfilehash: 0e679ffc22f52de5e2ce8194942efbb2f5299ee4
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---

#<a name="building-docker-images-for-net-core-applications"></a><span data-ttu-id="e739b-104">.NET Core 응용 프로그램에 대한 Docker 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="e739b-104">Building Docker Images for .NET Core Applications</span></span>

 
> [!IMPORTANT]
> <span data-ttu-id="e739b-105">.NET Core 2.0에 대한 업데이트 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-105">We are in the process of updating for .NET Core 2.0.</span></span> <span data-ttu-id="e739b-106">아래 지침은 만료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-106">The instructions below are out of date.</span></span> <span data-ttu-id="e739b-107">불편을 끼쳐드려서 죄송합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-107">We sincerely apologize for any inconvenience!</span></span>

<span data-ttu-id="e739b-108">.NET Core와 Docker를 함께 사용하는 방법을 이해하려면 먼저 제공되는 다양한 Docker 이미지와 올바른 사용 시기에 대해 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-108">In order to get an understanding of how to use .NET Core and Docker together, we must first get to know the different Docker images that are offered and when is the right use case for them.</span></span> <span data-ttu-id="e739b-109">여기서는 제공되는 변형 이미지를 살펴보고, ASP.NET Core Web API를 빌드하며, Yeoman Docker 도구를 사용하여 디버깅 가능한 컨테이너를 만들 뿐만 아니라 Visual Studio Code가 이 프로세스에 어떻게 도움이 되는지를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-109">Here we will walk through the variations offered, build an ASP.NET Core Web API, use the Yeoman Docker tools to create a debuggable container as well as peek at how Visual Studio Code can assist in the process.</span></span> 

## <a name="docker-image-optimizations"></a><span data-ttu-id="e739b-110">Docker 이미지 최적화</span><span class="sxs-lookup"><span data-stu-id="e739b-110">Docker Image Optimizations</span></span>

<span data-ttu-id="e739b-111">개발자를 위한 Docker 이미지를 작성할 때 다음 세 가지 주요 시나리오를 중점적으로 고려했습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-111">When building Docker images for developers, we focused on three main scenarios:</span></span>

- <span data-ttu-id="e739b-112">.NET Core 앱을 개발하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="e739b-112">Images used to develop .NET Core apps</span></span>
- <span data-ttu-id="e739b-113">.NET Core 앱을 빌드하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="e739b-113">Images used to build .NET Core apps</span></span>
- <span data-ttu-id="e739b-114">.NET Core 앱을 실행하는 데 사용되는 이미지</span><span class="sxs-lookup"><span data-stu-id="e739b-114">Images used to run .NET Core apps</span></span>

<span data-ttu-id="e739b-115">왜 이 세 가지 이미지가 중요할까요?</span><span class="sxs-lookup"><span data-stu-id="e739b-115">Why three images?</span></span>
<span data-ttu-id="e739b-116">컨테이너화된 응용 프로그램을 개발, 빌드 및 실행할 때 서로 다른 우선 순위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-116">When developing, building and running containerized applications, we have different priorities.</span></span>
- <span data-ttu-id="e739b-117">**개발:**  얼마나 빨리 변경을 반복할 수 있는지 그리고 변경 내용을 디버그하는 기능이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-117">**Development:**  How fast can you iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="e739b-118">이미지의 크기는 중요하지 않으며 코드를 변경하고 변경 내용을 신속하게 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-118">The size of the image isn't as important, rather can you make changes to your code and see them quickly.</span></span> <span data-ttu-id="e739b-119">[yo docker](https://aka.ms/yodocker)와 같이 Visual Studio Code에서 사용하는 일부 도구에서 개발하는 동안 이 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-119">Some of our tools, like [yo docker](https://aka.ms/yodocker) for use in Visual Studio Code use this image during development time.</span></span> 
- <span data-ttu-id="e739b-120">**빌드:** 앱을 컴파일하는 데 무엇이 필요한지가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-120">**Build:** What's needed to compile your app.</span></span> <span data-ttu-id="e739b-121">여기에는 컴파일러와 이진 파일을 최적화하기 위한 다른 모든 종속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-121">This includes the compiler and any other dependencies to optimize the binaries.</span></span> <span data-ttu-id="e739b-122">이 이미지는 배포하는 이미지가 아니며, 프로덕션 이미지에 배치하는 콘텐츠를 빌드하는 데 사용되는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-122">This image isn't the image you deploy, rather it's an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="e739b-123">이 이미지는 연속 통합 또는 빌드 환경에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-123">This image would be used in your continuous integration, or build environment.</span></span> <span data-ttu-id="e739b-124">예를 들어 모든 종속성을 빌드 에이전트에 직접 설치하는 대신 빌드 에이전트는 빌드 이미지를 인스턴스화하여 이미지 내에 포함된 앱을 빌드하는 데 필요한 모든 종속성을 사용하여 응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-124">For instance, rather than installing all the dependencies directly on a build agent, the build agent would instance a build image to compile the application with all the dependencies required to build the app contained within the image.</span></span> <span data-ttu-id="e739b-125">빌드 에이전트는 이 Docker 이미지를 실행하는 방법만 알고 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-125">Your build agent only needs to know how to run this Docker image.</span></span> 
- <span data-ttu-id="e739b-126">**프로덕션:** 이미지를 배포하고 시작할 수 있는 속도가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-126">**Production:** How fast you can deploy and start your image.</span></span> <span data-ttu-id="e739b-127">이 이미지는 작기 때문에 Docker 레지스트리에서 Docker 호스트 사이의 네트워크를 신속하게 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-127">This image is small so it can quickly travel across the network from your Docker Registry to your Docker hosts.</span></span> <span data-ttu-id="e739b-128">콘텐츠를 실행할 준비가 되면 Docker 실행부터 결과 처리까지 가장 빠른 시간에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-128">The contents are ready to run enabling the fastest time from Docker run to processing results.</span></span> <span data-ttu-id="e739b-129">변경이 불가능한 Docker 모델에서는 코드를 동적으로 컴파일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-129">In the immutable Docker model, there's no need for dynamic compilation of code.</span></span> <span data-ttu-id="e739b-130">이 이미지에 배치되는 콘텐츠는 이진 파일과 응용 프로그램을 실행하는 데 필요한 콘텐츠로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-130">The content you place in this image would be limited to the binaries and content needed to run the application.</span></span> <span data-ttu-id="e739b-131">컴파일된 이진 파일, 이미지, .js 및 .css 파일을 포함하는 `dotnet publish`를 사용하는 게시된 출력을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-131">For example, the published output using `dotnet publish` which contains the compiled binaries, images, .js and .css files.</span></span> <span data-ttu-id="e739b-132">시간이 지남에 따라 미리 JIT 컴파일된 패키지를 포함하는 이미지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-132">Over time, you'll see images that contain pre-jitted packages.</span></span>  

<span data-ttu-id="e739b-133">여러 버전의 .NET Core 이미지가 있지만 모두 하나 이상의 레이어를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-133">Though there are multiple versions of the .NET Core image, they all share one or more layers.</span></span> <span data-ttu-id="e739b-134">모든 이미지가 동일한 기본 레이어와 잠재적으로 다른 레이어를 공유하기 때문에 저장하는 데 필요한 디스크 공간의 크기나 레지스트리에서 끌어오는 델타가 전체보다 훨씬 더 작습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-134">The amount of disk space needed to store or the delta to pull from your registry is much smaller than the whole because all of the images share the same base layer and potentially others.</span></span>  

## <a name="docker-image-variations"></a><span data-ttu-id="e739b-135">Docker 이미지 변형</span><span class="sxs-lookup"><span data-stu-id="e739b-135">Docker image variations</span></span>

<span data-ttu-id="e739b-136">위의 목표를 달성하기 위해 [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/)에서 이미지 변형을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-136">To achieve the goals above, we provide image variants under [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

- <span data-ttu-id="e739b-137">`microsoft/dotnet:<version>-sdk`: 즉, **microsoft/dotnet:1.0.0-preview2-sdk**로, 이 이미지는 .NET Core 및 CLI(명령줄 도구)가 포함된 .NET Core SDK를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-137">`microsoft/dotnet:<version>-sdk` : that is **microsoft/dotnet:1.0.0-preview2-sdk**, this image contains the .NET Core SDK which includes the .NET Core and Command Line Tools (CLI).</span></span> <span data-ttu-id="e739b-138">이 이미지는 **개발 시나리오**에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-138">This image maps to the **development scenario**.</span></span> <span data-ttu-id="e739b-139">로컬 개발, 디버깅 및 단위 테스트에 이 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-139">You would use this image for local development, debugging and unit testing.</span></span> <span data-ttu-id="e739b-140">예를 들어 코드 체크 인 전의 모든 개발 작업에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-140">For example, all the development you do, before you check in your code.</span></span> <span data-ttu-id="e739b-141">이 이미지는 **빌드** 시나리오에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-141">This image can also be used for your **build** scenarios.</span></span>

- <span data-ttu-id="e739b-142">`microsoft/dotnet:<version>-core`: 즉, **microsoft/dotnet:1.0.0-core**로, [이식 가능한 .NET Core 응용 프로그램](../deploying/index.md)을 실행하는 이미지이며 **프로덕션**에서 응용 프로그램을 실행하는 데 맞게 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-142">`microsoft/dotnet:<version>-core` : that is **microsoft/dotnet:1.0.0-core**, image which runs [portable .NET Core applications](../deploying/index.md) and it is optimized for running your application in **production**.</span></span> <span data-ttu-id="e739b-143">SDK를 포함하지 않으며 `dotnet publish`의 최적화된 출력을 수행하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-143">It does not contain the SDK, and is meant to take the optimized output of `dotnet publish`.</span></span> <span data-ttu-id="e739b-144">이식 가능한 런타임은 실행 중인 여러 컨테이너에서 공유 이미지 레이어를 활용하는 경우 Docker 컨테이너 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-144">The portable runtime is well suited for Docker container scenarios as running multiple containers benefit from shared image layers.</span></span>  

## <a name="alternative-images"></a><span data-ttu-id="e739b-145">대체 이미지</span><span class="sxs-lookup"><span data-stu-id="e739b-145">Alternative images</span></span>

<span data-ttu-id="e739b-146">개발, 빌드 및 프로덕션에 최적화된 시나리오 외에도 추가 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-146">In addition to the optimized scenarios of development, build and production, we provide additional images:</span></span>

- <span data-ttu-id="e739b-147">`microsoft/dotnet:<version>-onbuild`: 즉, **microsoft/dotnet:1.0.0-preview2-onbuild**로, [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) 트리거를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-147">`microsoft/dotnet:<version>-onbuild` : that is **microsoft/dotnet:1.0.0-preview2-onbuild**, contains [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) triggers.</span></span> <span data-ttu-id="e739b-148">빌드는 응용 프로그램을 [COPY](https://docs.docker.com/engine/reference/builder/#/copy)하고, `dotnet restore`를 실행하며, Docker 이미지가 실행될 때 응용 프로그램을 실행하는 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` 명령을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-148">The build will [COPY](https://docs.docker.com/engine/reference/builder/#/copy) your application, run `dotnet restore` and create an [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` instruction to run the application when the Docker image is run.</span></span> <span data-ttu-id="e739b-149">프로덕션에 최적화된 이미지는 아니지만 단순히 소스 코드를 이미지에 복사하여 실행할 때 유용한 경우는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-149">While not an optimized image for production, some may find it useful to simply copy their source code into an image and run it.</span></span> 

- <span data-ttu-id="e739b-150">`microsoft/dotnet:<version>-core-deps`: 즉, **microsoft/dotnet:1.0.0-core-deps**로, 자체 포함 응용 프로그램을 실행하려는 경우 이 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-150">`microsoft/dotnet:<version>-core-deps` : that is **microsoft/dotnet:1.0.0-core-deps**, if you wish to run self-contained applications use this image.</span></span> <span data-ttu-id="e739b-151">.NET Core에 필요한 모든 기본 종속성과 함께 운영 체제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-151">It contains the operating system with all of the native dependencies needed by .NET Core.</span></span> <span data-ttu-id="e739b-152">이 이미지는 고유한 사용자 지정 CoreFX 또는 CoreCLR 빌드에 대한 기본 이미지로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-152">This image can also be used as a base image for your own custom CoreFX or CoreCLR builds.</span></span> <span data-ttu-id="e739b-153">**onbuild** 변형이 단순히 코드를 이미지에 배치하고 실행하도록 최적화된 반면, 이 이미지는 .NET 런타임이 응용 프로그램과 함께 패키지로 제공되는 .NET Core 앱을 실행하는 데 필요한 운영 체제 종속성만 갖도록 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-153">While the **onbuild** variant is optimized to simply place your code in an image and run it, this image is optimized to have only the operating system dependencies required to run .NET Core apps that have the .NET runtime packaged with the application.</span></span> <span data-ttu-id="e739b-154">각 이미지가 응용 프로그램 내에서 .NET Core 런타임을 전달하기 때문에 이 이미지는 일반적으로 동일한 호스트에서 여러 .NET Core 컨테이너를 실행하는 데 최적화되어 있지 않으며 이미지 레이어를 활용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-154">This image isn't generally optimized for running multiple .NET Core containers on the same host, as each image carries the .NET Core runtime within the application, and you will not benefit from image layering.</span></span>   

<span data-ttu-id="e739b-155">각 변형의 최신 버전:</span><span class="sxs-lookup"><span data-stu-id="e739b-155">Latest versions of each variant:</span></span>

- <span data-ttu-id="e739b-156">`microsoft/dotnet` 또는 `microsoft/dotnet:latest`(SDK 포함)</span><span class="sxs-lookup"><span data-stu-id="e739b-156">`microsoft/dotnet` or `microsoft/dotnet:latest` (includes SDK)</span></span>
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

<span data-ttu-id="e739b-157">다음은 개발 컴퓨터에서 다양한 크기를 보여 주는 `docker pull <imagename>` 다음의 이미지 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-157">Here is a list of the images after a `docker pull <imagename>` on a development machine to show the various sizes.</span></span> <span data-ttu-id="e739b-158">개발/빌드 변형인 `microsoft/dotnet:1.0.0-preview2-sdk`는 응용 프로그램을 개발하고 빌드하는 SDK를 포함하기 때문에 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-158">Notice, the development/build variant, `microsoft/dotnet:1.0.0-preview2-sdk` is larger as it contains the SDK to develop and build your application.</span></span> <span data-ttu-id="e739b-159">프로덕션 변형인 `microsoft/dotnet:core`는 .NET Core 런타임만 포함하기 때문에 더 작습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-159">The production variant, `microsoft/dotnet:core` is smaller, as it only contains the .NET Core runtime.</span></span> <span data-ttu-id="e739b-160">Linux에서 사용할 수 있는 최소 이미지인 `core-deps`는 훨씬 더 작지만 응용 프로그램에서 이 이미지를 사용하여 .NET 런타임의 개인 복사본을 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-160">The minimal image capable of being used on Linux, `core-deps`, is quite smaller, however your application will need to copy a private copy of the .NET runtime with it.</span></span> <span data-ttu-id="e739b-161">컨테이너가 이미 개인 격리 장벽이기 때문에 여러 dotnet 기반 컨테이너를 실행할 경우 최적화가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-161">Since containers are already private isolation barriers, you will lose that optimization when running multiple dotnet based containers.</span></span> 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a><span data-ttu-id="e739b-162">필수 조건</span><span class="sxs-lookup"><span data-stu-id="e739b-162">Prerequisites</span></span>

<span data-ttu-id="e739b-163">빌드하고 실행하려면 다음과 같은 몇 가지 항목을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-163">To build and run, you'll need a few things installed:</span></span>

- [<span data-ttu-id="e739b-164">.NET Core</span><span class="sxs-lookup"><span data-stu-id="e739b-164">.NET Core</span></span>](http://dot.net)
- <span data-ttu-id="e739b-165">Docker 컨테이너를 로컬로 실행하기 위한 [Docker](https://www.docker.com/products/docker)</span><span class="sxs-lookup"><span data-stu-id="e739b-165">[Docker](https://www.docker.com/products/docker) to run your Docker containers locally</span></span>
- [<span data-ttu-id="e739b-166">Node.js</span><span class="sxs-lookup"><span data-stu-id="e739b-166">Node.js</span></span>](https://nodejs.org/)
- <span data-ttu-id="e739b-167">Web API 응용 프로그램을 만들기 위한 [ASP.NET용 Yeoman 생성기](https://github.com/omnisharp/generator-aspnet)</span><span class="sxs-lookup"><span data-stu-id="e739b-167">[Yeoman generator for ASP.NET](https://github.com/omnisharp/generator-aspnet) for creating the Web API application</span></span>
- <span data-ttu-id="e739b-168">Microsoft의 [Docker용 Yeoman 생성기](http://aka.ms/yodocker)</span><span class="sxs-lookup"><span data-stu-id="e739b-168">[Yeoman generator for Docker](http://aka.ms/yodocker) from Microsoft</span></span>

<span data-ttu-id="e739b-169">npm을 사용하여 ASP.NET Core 및 Docker용 Yeoman 생성기 설치</span><span class="sxs-lookup"><span data-stu-id="e739b-169">Install the Yeoman generators for ASP.NET Core and Docker using npm</span></span> 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> <span data-ttu-id="e739b-170">이 샘플에서는 [Visual Studio Code](http://code.visualstudio.com)를 편집기에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-170">This sample will be using [Visual Studio Code](http://code.visualstudio.com) for the editor.</span></span>

## <a name="creating-the-web-api-application"></a><span data-ttu-id="e739b-171">Web API 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="e739b-171">Creating the Web API application</span></span>

<span data-ttu-id="e739b-172">참조 지점으로 응용 프로그램을 컨테이너화하기 전에 먼저 로컬로 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-172">For a reference point, before we containerize the application, first run the application locally.</span></span> 

<span data-ttu-id="e739b-173">완성된 응용 프로그램은 [GitHub의 dotnet/docs 리포지토리](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-173">The finished application is located in the [dotnet/docs repository on GitHub](https://github.com/dotnet/docs/tree/master/samples/core/docker/building-net-docker-images).</span></span> <span data-ttu-id="e739b-174">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e739b-174">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="e739b-175">응용 프로그램에 대한 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-175">Create a directory for your application.</span></span>

<span data-ttu-id="e739b-176">해당 디렉터리에서 명령 또는 터미널 세션을 열고 다음을 입력하여 ASP.NET Yeoman 생성기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-176">Open a command or terminal session in that directory and use the ASP.NET Yeoman generator by typing the following:</span></span>
```
yo aspnet
```

<span data-ttu-id="e739b-177">**Web API 응용 프로그램**을 선택하고 앱의 이름으로 **api**를 입력한 다음 <Enter> 키를 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-177">Select **Web API Application** and type **api** for the name of the app and tap enter.</span></span>  <span data-ttu-id="e739b-178">응용 프로그램이 스캐폴드되면 `/api` 디렉터리로 변경하고 `dotnet restore`를 사용하여 NuGet 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-178">Once the application is scaffolded, change to the `/api` directory and restore the NuGet dependencies using `dotnet restore`.</span></span>

```
cd api
dotnet restore
```

<span data-ttu-id="e739b-179">`dotnet run`을 사용하고 **http://localhost:5000/api/values** 로 이동하여 응용 프로그램을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-179">Test the application using `dotnet run` and browsing to **http://localhost:5000/api/values**</span></span>

```javascript
[
    "value1",
    "value2"
]
```

<span data-ttu-id="e739b-180">`Ctrl+C`를 사용하여 응용 프로그램을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-180">Use `Ctrl+C` to stop the application.</span></span>

## <a name="adding-docker-support"></a><span data-ttu-id="e739b-181">Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="e739b-181">Adding Docker support</span></span>

<span data-ttu-id="e739b-182">Microsoft용 Yeoman 생성기를 사용하여 프로젝트에 Docker 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-182">Adding Docker support to the project is achieved using the Yeoman generator from Microsoft.</span></span> <span data-ttu-id="e739b-183">현재 컨테이너 내에서 프로젝트를 빌드하고 실행하는 데 도움이 되는 Dockerfile 및 스크립트를 만들어 .NET Core, Node.js 및 Go 프로젝트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-183">It currently supports .NET Core, Node.js and Go projects by creating a Dockerfile and scripts that help build and run projects inside containers.</span></span> <span data-ttu-id="e739b-184">편집기 디버깅 및 명령 팔레트를 지원하기 위해 Visual Studio Code 관련 파일(launch.json, tasks.json)도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-184">Visual Studio Code specific files are also added (launch.json, tasks.json) for editor debugging and command palette support.</span></span>

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js
```

- <span data-ttu-id="e739b-185">`.NET Core`를 프로젝트 형식으로 선택</span><span class="sxs-lookup"><span data-stu-id="e739b-185">Select `.NET Core` as the project type</span></span>
- <span data-ttu-id="e739b-186">`rtm`: .NET Core의 버전</span><span class="sxs-lookup"><span data-stu-id="e739b-186">`rtm` for the version of .NET Core</span></span>
- <span data-ttu-id="e739b-187">`Y`: 프로젝트에서 웹 서버 사용</span><span class="sxs-lookup"><span data-stu-id="e739b-187">`Y` the project uses a web server</span></span>
- <span data-ttu-id="e739b-188">`5000`: Web API 응용 프로그램에서 수신 대기하는 포트(http://localhost:5000)</span><span class="sxs-lookup"><span data-stu-id="e739b-188">`5000` is the port the Web API application is listening on (http://localhost:5000)</span></span>
- <span data-ttu-id="e739b-189">`api`: 이미지 이름</span><span class="sxs-lookup"><span data-stu-id="e739b-189">`api` for the image name</span></span>
- <span data-ttu-id="e739b-190">`api`: 서비스 이름</span><span class="sxs-lookup"><span data-stu-id="e739b-190">`api` for the service name</span></span>
- <span data-ttu-id="e739b-191">`api`: 작성 프로젝트</span><span class="sxs-lookup"><span data-stu-id="e739b-191">`api` for the compose project</span></span> 
- <span data-ttu-id="e739b-192">`Y`: 현재 Dockerfile 덮어쓰기</span><span class="sxs-lookup"><span data-stu-id="e739b-192">`Y` to overwrite the current Dockerfile</span></span>

<span data-ttu-id="e739b-193">생성기가 완료되면 다음 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-193">When the generator is complete, the following files are added to the project</span></span>

- <span data-ttu-id="e739b-194">.vscode/launch.json</span><span class="sxs-lookup"><span data-stu-id="e739b-194">.vscode/launch.json</span></span>
- <span data-ttu-id="e739b-195">Dockerfile.debug</span><span class="sxs-lookup"><span data-stu-id="e739b-195">Dockerfile.debug</span></span>
- <span data-ttu-id="e739b-196">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="e739b-196">Dockerfile</span></span>
- <span data-ttu-id="e739b-197">docker-compose.debug.yml</span><span class="sxs-lookup"><span data-stu-id="e739b-197">docker-compose.debug.yml</span></span>
- <span data-ttu-id="e739b-198">docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="e739b-198">docker-compose.yml</span></span>
- <span data-ttu-id="e739b-199">dockerTask.ps1</span><span class="sxs-lookup"><span data-stu-id="e739b-199">dockerTask.ps1</span></span>
- <span data-ttu-id="e739b-200">dockerTask.sh</span><span class="sxs-lookup"><span data-stu-id="e739b-200">dockerTask.sh</span></span>
- <span data-ttu-id="e739b-201">.vscode/tasks.json</span><span class="sxs-lookup"><span data-stu-id="e739b-201">.vscode/tasks.json</span></span>

<span data-ttu-id="e739b-202">생성자는 두 개의 Dockerfile을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-202">The generator creates two Dockerfiles.</span></span>

<span data-ttu-id="e739b-203">**Dockerfile.debug** - 이 파일은 이미지 변형 목록에서 확인할 경우 SDK, CLI 및 .NET Core를 포함하고 개발 및 디버깅(F5)에 사용되는 이미지인 **microsoft/dotnet:1.0.0-preview2-sdk** 이미지를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-203">**Dockerfile.debug** - this file is based on the **microsoft/dotnet:1.0.0-preview2-sdk** image which if you note from the list of image variants, includes the SDK, CLI and .NET Core and will be the image used for development and debugging (F5).</span></span> <span data-ttu-id="e739b-204">이러한 모든 구성 요소를 포함하면 약 540MB의 더 큰 이미지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-204">Including all of these components produces a larger image with a size roughly of 540MB.</span></span>

<span data-ttu-id="e739b-205">**Dockerfile** - 이 이미지는 **microsoft/dotnet:1.0.0-core**를 기반으로 하는 릴리스 이미지이며 프로덕션에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-205">**Dockerfile** - this image is the release image based on **microsoft/dotnet:1.0.0-core** and should be used for production.</span></span> <span data-ttu-id="e739b-206">빌드할 때 이 이미지는 약 253MB입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-206">This image when built is approximately 253 MB.</span></span>

### <a name="creating-the-docker-images"></a><span data-ttu-id="e739b-207">Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="e739b-207">Creating the Docker images</span></span>
<span data-ttu-id="e739b-208">`dockerTask.sh` 또는 `dockerTask.ps1` 스크립트를 사용하여 특정 환경에서 **api** 응용 프로그램에 대한 이미지 및 컨테이너를 빌드하거나 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-208">Using the `dockerTask.sh` or `dockerTask.ps1` script, we can build or compose the image and container for the **api** application for a specific environment.</span></span> <span data-ttu-id="e739b-209">다음 명령을 실행하여 **debug** 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-209">Build the **debug** image by running the following command.</span></span>

```bash
./dockerTask.sh build debug
```

<span data-ttu-id="e739b-210">이 이미지는 ASP.NET 응용 프로그램을 빌드하고 `dotnet restore`를 실행하며 디버거를 이미지에 추가하고 `ENTRYPOINT`를 설정한 다음 마지막으로 이미지에 앱을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-210">The image will build the ASP.NET application, run `dotnet restore`, add the debugger to the image, set an `ENTRYPOINT` and finally copy the app to the image.</span></span> <span data-ttu-id="e739b-211">결과는 `TAG`가 *debug*인 *api*라는 Docker 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-211">The result is a Docker image named *api* with a `TAG` of *debug*.</span></span>  <span data-ttu-id="e739b-212">`docker images`를 사용하여 컴퓨터의 이미지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e739b-212">See the images on the machine using `docker images`.</span></span>

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

<span data-ttu-id="e739b-213">이미지를 생성하고 Docker 컨테이너 내에서 응용 프로그램을 실행하는 또 다른 방법은 Visual Studio Code에서 응용 프로그램을 열고 디버깅 도구를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-213">Another way to generate the image and run the application within the Docker container is to open the application in Visual Studio Code and use the debugging tools.</span></span> 

<span data-ttu-id="e739b-214">Visual Studio Code의 왼쪽에 있는 보기 표시줄에서 디버깅 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-214">Select the debugging icon in the View Bar on the left side of Visual Studio Code.</span></span>

![vscode 디버깅 아이콘](./media/building-net-docker-images/debugging_debugicon.png)

<span data-ttu-id="e739b-216">그런 다음 재생 아이콘이나 <F5> 키를 탭하여 이미지를 생성하고 컨테이너 내에서 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-216">Then tap the play icon or F5 to generate the image and start the application within the container.</span></span> <span data-ttu-id="e739b-217">Web API가 http://localhost:5000에서 기본 웹 브라우저를 사용하여 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-217">The Web API will be launched using your default web browser at http://localhost:5000.</span></span>

![VSCode Docker 도구 디버그](./media/building-net-docker-images/docker-tools-vscode-f5.png)

<span data-ttu-id="e739b-219">마치 응용 프로그램이 컨테이너 내부가 아닌 개발 컴퓨터에서 로컬로 실행되는 것처럼 응용 프로그램에서 중단점을 설정하고 단계별로 실행하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-219">You may set break points in your application, step through, etc. just as if the application was running locally on your development machine as opposed to inside the container.</span></span> <span data-ttu-id="e739b-220">컨테이너 내에서 디버깅하는 장점은 프로덕션 환경에 배포되는 것과 동일한 이미지가 사용된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-220">The benefit to debugging within the container is this is the same image that would be deployed to a production environment.</span></span>

<span data-ttu-id="e739b-221">릴리스 또는 프로덕션 이미지를 만들려면 `release` 환경 이름을 전달하여 터미널에서 명령을 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-221">Creating the release or production image requires simply running the command from the terminal passing the `release` environment name.</span></span>

```bash
./dockerTask build release
```

<span data-ttu-id="e739b-222">이 명령은 더 작은 **microsoft/dotnet:core** 기본 이미지를 기반으로 이미지를 만들고, 포트 5000을 [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) `dotnet api.dll`에 대한 [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) 설정하며, `/app` 디렉터리에 이 이미지를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-222">The command creates the image based on the smaller **microsoft/dotnet:core** base image, [EXPOSE](https://docs.docker.com/engine/reference/builder/#/expose) port 5000, sets the [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) for `dotnet api.dll` and copies it to the `/app` directory.</span></span> <span data-ttu-id="e739b-223">훨씬 더 작은 이미지를 생성하는 디버거, SDK 또는 `dotnet restore`가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-223">There is no debugger, SDK or `dotnet restore` resulting in a much smaller image.</span></span> <span data-ttu-id="e739b-224">이미지 이름은 `TAG`가 **latest**인 **api**입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-224">The image is named **api** with a `TAG` of **latest**.</span></span>

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a><span data-ttu-id="e739b-225">요약</span><span class="sxs-lookup"><span data-stu-id="e739b-225">Summary</span></span>

<span data-ttu-id="e739b-226">Docker 생성기를 사용하여 Web API 응용 프로그램에 필요한 파일을 추가하면 이미지의 개발 및 프로덕션 버전을 만드는 프로세스가 간단해집니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-226">Using the Docker generator to add the necessary files to our Web API application made the process simple to create the development and production versions of the images.</span></span>  <span data-ttu-id="e739b-227">도구는 컨테이너 내에서 응용 프로그램의 단계별 실행 디버깅을 제공하는 Windows 및 Visual Studio Code 통합에서 동일한 결과를 얻도록 하는 PowerShell 스크립트도 제공하여 플랫폼 간 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-227">The tooling is cross platform by also providing a PowerShell script to accomplish the same results on Windows and Visual Studio Code integration providing step through debugging of the application within the container.</span></span> <span data-ttu-id="e739b-228">이미지 변형 및 대상 시나리오를 이해하면 프로덕션 배포에 최적화된 이미지를 얻는 동시에 내부 루프 개발 프로세스를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e739b-228">By understanding the image variants and the target scenarios, you can optimize your inner-loop development process, while achieving optimized images for production deployments.</span></span>  



