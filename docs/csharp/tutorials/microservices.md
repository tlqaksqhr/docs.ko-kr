---
title: Docker에서 호스트되는 마이크로 서비스 - C#
description: Docker 컨테이너에서 실행되는 ASP.NET Core 서비스를 만드는 방법 알아보기
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 1f4b38243beb1210b1374bd701fac66b2fa72cc5
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106352"
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="33ea1-103">Docker에서 호스트되는 마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="33ea1-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="33ea1-104">이 자습서에서는 Docker 컨테이너에서 ASP.NET Core 마이크로 서비스를 빌드 및 배포하는 데 필요한 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="33ea1-105">이 자습서를 진행하면서 다음을 익히게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="33ea1-106">ASP.NET Core 응용 프로그램을 생성하는 방법</span><span class="sxs-lookup"><span data-stu-id="33ea1-106">How to generate an ASP.NET Core application.</span></span>
* <span data-ttu-id="33ea1-107">개발 Docker 환경을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="33ea1-107">How to create a development Docker environment.</span></span>
* <span data-ttu-id="33ea1-108">기존 이미지에 따라 Docker 이미지를 빌드하는 하는 방법</span><span class="sxs-lookup"><span data-stu-id="33ea1-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="33ea1-109">서비스를 Docker 컨테이너에 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="33ea1-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="33ea1-110">이러한 방법을 진행하면서 다음과 같은 일부 C# 언어 기능도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="33ea1-111">C# 개체를 JSON 페이로드로 변환하는 방법</span><span class="sxs-lookup"><span data-stu-id="33ea1-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="33ea1-112">변경할 수 없는 데이터 전송 개체를 빌드하는 방법.</span><span class="sxs-lookup"><span data-stu-id="33ea1-112">How to build immutable Data Transfer Objects.</span></span>
* <span data-ttu-id="33ea1-113">들어오는 HTTP 요청을 처리하고 HTTP 응답을 생성하는 방법.</span><span class="sxs-lookup"><span data-stu-id="33ea1-113">How to process incoming HTTP Requests and generate the HTTP Response.</span></span>
* <span data-ttu-id="33ea1-114">null 허용 값 형식을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="33ea1-114">How to work with nullable value types.</span></span>

<span data-ttu-id="33ea1-115">이 항목에 대한 [샘플 앱을 보거나 다운로드](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="33ea1-116">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33ea1-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="why-docker"></a><span data-ttu-id="33ea1-117">Docker를 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="33ea1-117">Why Docker?</span></span>

<span data-ttu-id="33ea1-118">Docker를 사용하면 데이터 센터 또는 공용 클라우드에서 서비스를 호스트하는 표준 컴퓨터 이미지를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="33ea1-119">Docker는 이미지를 구성하고, 필요할 때 이미지를 복제하여 응용 프로그램의 설치 크기를 조정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="33ea1-120">이 자습서의 모든 코드는 모든 .NET Core 환경에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="33ea1-121">Docker 설치를 위한 추가 작업은 ASP.NET Core 응용 프로그램에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="33ea1-122">전제 조건</span><span class="sxs-lookup"><span data-stu-id="33ea1-122">Prerequisites</span></span>

<span data-ttu-id="33ea1-123">.NET Core를 실행하도록 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-123">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="33ea1-124">[.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="33ea1-125">Windows, Linux, macOS 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-125">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="33ea1-126">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="33ea1-127">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="33ea1-128">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="33ea1-129">또한 Docker 엔진을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="33ea1-130">사용하는 플랫폼에 대한 지침을 보려면 [Docker 설치 페이지](http://www.docker.com/products/docker)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33ea1-130">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="33ea1-131">Docker는 여러 Linux 배포판, macOS 또는 Windows에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="33ea1-132">위에 참조된 페이지에는 사용 가능한 각 설치에 대한 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-132">The page referenced above contains sections to each of the available installations.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="33ea1-133">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="33ea1-133">Create the Application</span></span>

<span data-ttu-id="33ea1-134">이제 모든 도구를 설치했으므로 즐겨찾기 셸에서 다음 명령을 실행하여 "WeatherMicroservice"라는 디렉터리에서 새 ASP.NET Core 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-134">Now that you've installed all the tools, create a new ASP.NET Core application in a directory called "WeatherMicroservice" by executing the following command in your favorite shell:</span></span>

```console
dotnet new web -o WeatherMicroservice
```

<span data-ttu-id="33ea1-135">`dotnet` 명령은 .NET 개발에 필요한 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-135">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="33ea1-136">각 동사는 다른 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-136">Each verb executes a different command.</span></span>

<span data-ttu-id="33ea1-137">`dotnet new` 명령은 .Net Core 프로젝트를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-137">The `dotnet new` command is used to create .Net Core projects.</span></span>

<span data-ttu-id="33ea1-138">`dotnet new` 명령 이후의 `-o WeatherMicroservice` 옵션을 사용하여 ASP.NET Core application.응용 프로그램을 만들 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-138">The `-o WeatherMicroservice` option after the `dotnet new` command is used to give the location to create the ASP.NET Core application.</span></span>

<span data-ttu-id="33ea1-139">이 마이크로 서비스에는 가능한 가장 간단하고 가벼운 웹 응용 프로그램이 필요하기 때문에 "빈 ASP.NET Core " 템플릿에 `web`이라는 짧은 이름을 지정하여 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-139">For this microservice, we want the simplest, most lightweight web application possible, so we used the "ASP.NET Core Empty" template, by specifying its short name, `web`.</span></span>

<span data-ttu-id="33ea1-140">이 템플릿은 다음 4개 파일을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-140">The template creates four files for you:</span></span>

* <span data-ttu-id="33ea1-141">Startup.cs 파일.</span><span class="sxs-lookup"><span data-stu-id="33ea1-141">A Startup.cs file.</span></span> <span data-ttu-id="33ea1-142">여기에는 응용 프로그램의 기본 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-142">This contains the basis of the application.</span></span>
* <span data-ttu-id="33ea1-143">Program.cs 파일.</span><span class="sxs-lookup"><span data-stu-id="33ea1-143">A Program.cs file.</span></span> <span data-ttu-id="33ea1-144">여기에는 응용 프로그램의 진입점이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-144">This contains the entry point of the application.</span></span>
* <span data-ttu-id="33ea1-145">WeatherMicroservice.csproj 파일.</span><span class="sxs-lookup"><span data-stu-id="33ea1-145">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="33ea1-146">응용 프로그램에 대한 빌드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-146">This is the build file for the application.</span></span>
* <span data-ttu-id="33ea1-147">Properties/launchSettings.json 파일.</span><span class="sxs-lookup"><span data-stu-id="33ea1-147">A Properties/launchSettings.json file.</span></span> <span data-ttu-id="33ea1-148">IDE에 사용되는 디버깅 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-148">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="33ea1-149">이제 템플릿 생성 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-149">Now you can run the template generated application:</span></span>

```console
dotnet run
```

<span data-ttu-id="33ea1-150">이 명령은 먼저 응용 프로그램을 빌드하는 데 필요한 종속성을 복원한 다음, 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-150">This command will first restore dependencies required to build the application and then it will build the application.</span></span>

<span data-ttu-id="33ea1-151">기본 구성은 `http://localhost:5000`을 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-151">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="33ea1-152">브라우저를 열고 해당 페이지로 이동하면 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="33ea1-152">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="33ea1-153">반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-153">message.</span></span>

<span data-ttu-id="33ea1-154">작업이 완료되면 <kbd>Ctrl</kbd>+<kbd>C</kbd>를 눌러 응용 프로그램을 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-154">When you're done, you can shut down the application by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="33ea1-155">ASP.NET Core 응용 프로그램 분석</span><span class="sxs-lookup"><span data-stu-id="33ea1-155">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="33ea1-156">응용 프로그램을 빌드했으므로 기능이 구현되는 방식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-156">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="33ea1-157">생성된 파일 중에서 이 시점에서 특히 흥미로운 2개의 파일은 WeatherMicroservice.csproj와 Startup.cs입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-157">There are two of the generated files that are particularly interesting at this point: WeatherMicroservice.csproj and Startup.cs.</span></span> 

<span data-ttu-id="33ea1-158">.csproj 파일에는 프로젝트에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-158">The .csproj file contains information about the project.</span></span>
<span data-ttu-id="33ea1-159">가장 흥미로운 두 노드는 `<TargetFramework>` 및 `<PackageReference>`입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-159">The two nodes that are most interesting are `<TargetFramework>` and `<PackageReference>`.</span></span>

<span data-ttu-id="33ea1-160">`<TargetFramework>` 노드는 이 응용 프로그램을 실행할 .NET 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-160">The `<TargetFramework>` node specifies the version of .NET that will run this application.</span></span>

<span data-ttu-id="33ea1-161">각 `<PackageReference>` 노드는 이 응용 프로그램에 필요한 패키지를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-161">Each `<PackageReference>` node is used to specify a package that is needed for this application.</span></span>

<span data-ttu-id="33ea1-162">응용 프로그램은 Startup.cs에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-162">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="33ea1-163">이 파일에는 startup 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-163">This file contains the startup class.</span></span>

<span data-ttu-id="33ea1-164">두 메서드는 ASP.NET Core 인프라에서 응용 프로그램을 구성 및 실행하기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-164">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="33ea1-165">`ConfigureServices` 메서드는 이 응용 프로그램에 필요한 서비스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-165">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="33ea1-166">Lean 마이크로 서비스를 빌드하는 경우 어떤 종속성도 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-166">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="33ea1-167">`Configure` 메서드는 들어오는 HTTP 요청에 대한 처리기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-167">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="33ea1-168">템플릿은 텍스트 'Hello World!'를 포함하는 모든 요청에 응답하는 간단한 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-168">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="33ea1-169">마이크로 서비스 빌드</span><span class="sxs-lookup"><span data-stu-id="33ea1-169">Build a microservice</span></span>

<span data-ttu-id="33ea1-170">빌드하려는 서비스는 전 세계 어디에서든지 날씨 보고서를 전달할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-170">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="33ea1-171">프로덕션 응용 프로그램에서는 날씨 데이터를 검색하기 위해 몇 가지 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-171">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="33ea1-172">이 샘플에서는 임의 일기 예보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-172">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="33ea1-173">임의 날씨 서비스를 구현하기 위해 수행해야 하는 많은 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-173">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="33ea1-174">들어오는 요청을 구문 분석하여 위도와 경도를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-174">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="33ea1-175">일부 임의 예보 데이터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-175">Generate some random forecast data.</span></span>
* <span data-ttu-id="33ea1-176">C# 개체의 임의 예보 데이터를 JSON 패킷으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-176">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="33ea1-177">사용자 서비스가 JSON을 다시 전송함을 나타내도록 응답 헤더를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-177">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="33ea1-178">응답을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-178">Write the response.</span></span>

<span data-ttu-id="33ea1-179">다음 섹션에서는 이러한 각 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-179">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="33ea1-180">쿼리 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="33ea1-180">Parsing the Query String</span></span>

<span data-ttu-id="33ea1-181">먼저 쿼리 문자열을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-181">You'll begin by parsing the query string.</span></span> <span data-ttu-id="33ea1-182">서비스는 다음 형식으로 쿼리 문자열의 'lat' 및 'long' 인수를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-182">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

<span data-ttu-id="33ea1-183">수행해야 하는 모든 변경 내용은 람다 식에 startup 클래스의 `app.Run`에 대한 인수로 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-183">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="33ea1-184">람다 식의 인수는 요청에 대한 `HttpContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-184">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="33ea1-185">해당 속성 중 하나는 `Request` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-185">One of its properties is the `Request` object.</span></span> <span data-ttu-id="33ea1-186">`Request` 개체는 요청에 대한 쿼리 문자열에 있는 모든 값의 사전을 포함하는 `Query` 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-186">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="33ea1-187">첫 번째 추가 내용은 위도 및 경도 값을 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-187">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="33ea1-188">`Query` 사전 값은 `StringValue` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-188">The `Query` dictionary values are `StringValue` type.</span></span> <span data-ttu-id="33ea1-189">해당 형식에는 문자열 컬렉션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-189">That type can contain a collection of strings.</span></span> <span data-ttu-id="33ea1-190">날씨 서비스의 경우 각 값이 단일 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-190">For your weather service, each value is a single string.</span></span> <span data-ttu-id="33ea1-191">이 때문에 위의 코드에서 `FirstOrDefault()`가 호출되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-191">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="33ea1-192">다음에는 문자열을 double 값으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-192">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="33ea1-193">문자열을 double로 변환하는 데 사용하는 메서드는 `double.TryParse()`입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-193">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="33ea1-194">이 메서드는 C# out 매개 변수를 사용하여 입력 문자열을 double로 변환할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-194">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="33ea1-195">문자열이 double에 대한 유효한 표현을 나타낼 경우 이 메서드는 true를 반환하고 `result` 인수는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-195">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="33ea1-196">문자열이 유효한 double을 나타내지 않을 경우 이 메서드는 false를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-196">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="33ea1-197">*null 허용 double*을 반환하는 *확장 메서드*를 사용하여 해당 API를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-197">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="33ea1-198">*null 허용 값 형식*은 일부 값 형식을 나타내는 형식으로 누락된 값 또는 null 값을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-198">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="33ea1-199">Null 허용 형식은 형식 선언에 `?` 문자를 추가하여 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-199">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="33ea1-200">확장 메서드는 정적 메서드로 정의되지만 첫 번째 매개 변수에 `this` 한정자를 추가하여 마치 해당 클래스의 멤버인 것처럼 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-200">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="33ea1-201">확장 메서드는 정적 클래스에서만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-201">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="33ea1-202">구문 분석을 위한 확장 메서드를 포함하는 클래스의 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-202">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="33ea1-203">확장 메서드를 호출하기 전에 현재 문화권을 고정으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-203">Before calling the extension method, change the current culture to invariant:</span></span>

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

<span data-ttu-id="33ea1-204">이렇게 하면 응용 프로그램이 기본 문화권에 관계없이 모든 서버에서 번호를 동일하게 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-204">This ensures that your application parses numbers the same on any server, regardless of its default culture.</span></span>

<span data-ttu-id="33ea1-205">이제 확장 메서드를 사용하여 쿼리 문자열 인수를 double 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-205">Now you can use the extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="33ea1-206">구문 분석 코드를 쉽게 테스트하기 위해 인수 값을 포함하도록 응답을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-206">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="33ea1-207">이제 웹 응용 프로그램을 실행하고 구문 분석 코드가 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-207">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="33ea1-208">브라우저에서 웹 요청에 값을 추가합니다. 그러면 업데이트된 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-208">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="33ea1-209">임의 일기 예보 빌드</span><span class="sxs-lookup"><span data-stu-id="33ea1-209">Build a random weather forecast</span></span>

<span data-ttu-id="33ea1-210">다음 작업은 임의 일기 예보를 빌드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-210">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="33ea1-211">일기 예보에 대해 원하는 값을 포함하는 데이터 컨테이너부터 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-211">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

<span data-ttu-id="33ea1-212">다음에는 해당 값을 임의로 설정하는 생성자를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-212">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="33ea1-213">이 생성자는 위도 및 경도 값을 사용하여 `Random` 숫자 생성기를 시드합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-213">This constructor uses the values for the latitude and longitude to seed the `Random` number generator.</span></span> <span data-ttu-id="33ea1-214">즉, 같은 위치에 대한 예보는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-214">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="33ea1-215">위도 및 경도 대한 인수를 변경하면 다른 시드로 시작하므로 다른 예보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-215">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed).</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="33ea1-216">이제 응답 메서드에서 5일 예보를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-216">You can now generate the 5-day forecast in your response method:</span></span>

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a><span data-ttu-id="33ea1-217">JSON 응답 빌드</span><span class="sxs-lookup"><span data-stu-id="33ea1-217">Build the JSON response</span></span>

<span data-ttu-id="33ea1-218">서버의 최종 코드 작업은 `WeatherReport` 목록을 JSON 문서로 변환하고 클라이언트에 다시 전송하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-218">The final code task on the server is to convert the `WeatherReport` list into JSON document, and send that back to the client.</span></span> <span data-ttu-id="33ea1-219">먼저 JSON 문서를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-219">Let's start by creating the JSON document.</span></span> <span data-ttu-id="33ea1-220">종속성 목록에 Newtonsoft JSON serializer를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-220">You'll add the Newtonsoft JSON serializer to the list of dependencies.</span></span> <span data-ttu-id="33ea1-221">다음 `dotnet` 명령을 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-221">You can do that using the following `dotnet` command:</span></span>

```console
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="33ea1-222">그런 다음 `JsonConvert` 클래스를 사용하여 개체를 문자열에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-222">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="33ea1-223">위의 코드는 예보 개체(`WeatherForecast` 개체 목록)를 JSON 문서로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-223">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON document.</span></span> <span data-ttu-id="33ea1-224">응답 문서를 생성한 다음, 콘텐츠 형식을 `application/json`으로 설정하고 문자열을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-224">After you've constructed the response document, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="33ea1-225">이제 응용 프로그램이 실행되고 임의 예보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-225">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="33ea1-226">Docker 이미지 빌드</span><span class="sxs-lookup"><span data-stu-id="33ea1-226">Build a Docker image</span></span>

<span data-ttu-id="33ea1-227">마지막 작업은 Docker에서 응용 프로그램을 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-227">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="33ea1-228">응용 프로그램을 나타내는 Docker 이미지를 실행하는 Docker 컨테이너를 만들 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-228">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="33ea1-229">***Docker 이미지***는 응용 프로그램을 실행하기 위한 환경을 정의하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-229">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="33ea1-230">***Docker 컨테이너***는 실행 중인 Docker 이미지 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-230">A ***Docker Container*** represents a running instance of a Docker Image.</span></span>

<span data-ttu-id="33ea1-231">비유하자면 *Docker 이미지*를 *클래스*로, *Docker 컨테이너*를 개체 또는 해당 클래스의 인스턴스로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-231">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="33ea1-232">이를 위해 다음 Dockerfile이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-232">The following Dockerfile will serve for our purposes:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="33ea1-233">해당 내용을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-233">Let's go over its contents.</span></span>

<span data-ttu-id="33ea1-234">첫 번째 줄은 응용 프로그램을 빌드하는 데 사용되는 소스 이미지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-234">The first line specifies the source image used for building the application:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
```

<span data-ttu-id="33ea1-235">Docker를 사용하여 소스 템플릿을 기준으로 컴퓨터 이미지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-235">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="33ea1-236">시작할 때 컴퓨터의 모든 매개 변수를 제공할 필요는 없으며 변경 내용만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-236">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="33ea1-237">여기서 변경은 응용 프로그램을 포함하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-237">The changes here will be to include our application.</span></span>

<span data-ttu-id="33ea1-238">이 샘플에서는 `dotnet` 이미지의 `2.1-sdk` 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-238">In this sample, we'll use the `2.1-sdk` version of the `dotnet` image.</span></span> <span data-ttu-id="33ea1-239">이것이 작업 Docker 환경을 만드는 가장 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-239">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="33ea1-240">이 이미지는 .NET Core 런타임 및 .NET Core SDK를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-240">This image includes the .NET Core runtime, and the .NET Core SDK.</span></span>
<span data-ttu-id="33ea1-241">이렇게 하면 쉽게 시작하고 빌드할 수 있지만 더 큰 이미지가 생성되므로, 이 이미지로 응용 프로그램을 빌드하고 다른 이미지로 이미지를 실행하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-241">That makes it easier to get started and build, but does create a larger image, so we'll use this image for building the application and a different image to run it.</span></span>

<span data-ttu-id="33ea1-242">다음 줄은 응용 프로그램을 설정하고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-242">The next lines setup and build your application:</span></span>

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="33ea1-243">현재 디렉터리의 프로젝트 파일에 Docker VM으로 복사되고 모든 패키지가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-243">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="33ea1-244">dotnet CLI를 사용하면 Docker 이미지에 .NET Core SDK가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-244">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="33ea1-245">그런 다음, 응용 프로그램의 나머지 부분이 복사되고 `dotnet
publish` 명령이 응용 프로그램을 빌드하고 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-245">After that, the rest of your application gets copied, and the `dotnet
publish` command builds and packages your application.</span></span>

<span data-ttu-id="33ea1-246">마지막으로, 응용 프로그램을 실행하는 두 번째 Docker 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-246">Finally, we create a second Docker image that runs the application:</span></span>

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="33ea1-247">이 이미지는 `dotnet` 이미지의 `2.1-aspnetcore-runtime` 버전을 사용합니다. 이 이미지에는 ASP.NET Core 응용 프로그램을 실행하는 데 필요한 모든 항목이 포함되지만.NET Core SDK는 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-247">This image uses the `2.1-aspnetcore-runtime` version of the `dotnet` image, which contains everything necessary to run ASP.NET Core applications, but does not include the .NET Core SDK.</span></span> <span data-ttu-id="33ea1-248">즉, 이 이미지는 .NET Core 응용 프로그램을 빌드하는 데 사용할 수 없지만 최종 이미지를 더 작게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-248">This means this image can't be used to build .NET Core applications, but it also makes the final image smaller.</span></span>

<span data-ttu-id="33ea1-249">이 작업을 수행하기 위해 빌드된 응용 프로그램을 첫 번째 이미지에서 두 번째 이미지로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-249">To make this work, we copy the built application from the first image to the second one.</span></span>

<span data-ttu-id="33ea1-250">`ENTRYPOINT` 명령은 서비스를 시작하는 명령을 Docker에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-250">The `ENTRYPOINT` command informs Docker what command starts the service.</span></span>

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="33ea1-251">컨테이너에서 이미지 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="33ea1-251">Building and running the image in a container</span></span>

<span data-ttu-id="33ea1-252">이미지를 빌드하고 Docker 컨테이너 내의 서비스를 실행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-252">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="33ea1-253">로컬 디렉터리의 모든 파일을 이미지에 복사하려고 하지는 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-253">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="33ea1-254">대신 컨테이너에서 응용 프로그램에 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-254">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="33ea1-255">`.dockerignore` 파일을 만들고 이미지로 복사되지 않는 디렉토리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-255">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="33ea1-256">빌드 자산은 복사하고 싶지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-256">You don't want any of the build assets copied.</span></span> <span data-ttu-id="33ea1-257">빌드를 지정하고 디렉터리를 `.dockerignore` 파일에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-257">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="33ea1-258">`docker build` 명령을 사용하여 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-258">You build the image using the `docker build` command.</span></span> <span data-ttu-id="33ea1-259">코드를 포함하는 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-259">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="33ea1-260">이 명령은 Dockerfile의 모든 정보를 기반으로 컨테이너 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-260">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="33ea1-261">`-t` 인수는 이 컨테이너 이미지에 대한 태그 또는 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-261">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="33ea1-262">위의 명령줄에서 Docker 컨테이너에 사용되는 태그는 `weather-microservice`입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-262">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="33ea1-263">이 명령이 완료되면 컨테이너에서 새 서비스를 실행할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-263">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="33ea1-264">다음 명령을 실행하여 컨테이너를 시작하고 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-264">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

<span data-ttu-id="33ea1-265">`-d` 옵션은 현재 터미널에서 분리된 컨테이너를 실행하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-265">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="33ea1-266">즉, 터미널에 명령 출력에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-266">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="33ea1-267">`-p` 옵션은 서비스와 호스트 사이의 포트 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-267">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="33ea1-268">여기서는 포트 80으로 들어오는 모든 요청이 컨테이너의 포트 80으로 전달되어야 한다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-268">Here it says that any incoming request on port 80 should be forwarded to port 80 on the container.</span></span> <span data-ttu-id="33ea1-269">포트 80은 서비스가 수신 대기 중인 포트와 일치합니다. 이 포트는 프로덕션 응용 프로그램의 기본 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-269">Using 80 matches the port your service is listening on, which is the default port for production applications.</span></span> <span data-ttu-id="33ea1-270">`--name` 인수는 실행 중인 컨테이너의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-270">The `--name` argument names your running container.</span></span> <span data-ttu-id="33ea1-271">해당 컨테이너 관련 작업을 수행할 때 사용할 수 있는 편리한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-271">It's a convenient name you can use to work with that container.</span></span>

<span data-ttu-id="33ea1-272">다음 명령을 확인하여 이미지가 실행 중인지 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-272">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="33ea1-273">컨테이너가 실행 중인 경우 실행 중인 프로세스에서 해당 컨테이너를 나열하는 줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-273">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="33ea1-274">(하나만 있을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="33ea1-274">(It may be the only one.)</span></span>

<span data-ttu-id="33ea1-275">브라우저를 열고 localhost로 이동한 후 위도 및 경도를 지정하여 서비스를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-275">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="33ea1-276">실행 중인 컨테이너에 연결</span><span class="sxs-lookup"><span data-stu-id="33ea1-276">Attaching to a running container</span></span>

<span data-ttu-id="33ea1-277">명령 창에서 서비스를 실행할 때는 각 요청에 대해 출력되는 진단 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-277">When you ran your service in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="33ea1-278">컨테이너가 분리 모드에서 실행 중인 경우에는 해당 정보가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-278">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="33ea1-279">Docker attach 명령을 사용하면 실행 중인 컨테이너에 연결하여 로그 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-279">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="33ea1-280">명령 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-280">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="33ea1-281">`--sig-proxy=false` 인수는 <kbd>Ctrl</kbd>+<kbd>C</kbd> 명령이 컨테이너 프로세스에 전송되지 않고 오히려 `docker attach` 명령을 중지함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-281">The `--sig-proxy=false` argument means that <kbd>Ctrl</kbd>+<kbd>C</kbd> commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="33ea1-282">마지막 인수는 `docker run` 명령에서 컨테이너에 지정된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-282">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="33ea1-283">또한 Docker 할당 컨테이너 ID를 사용하여 컨테이너를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-283">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="33ea1-284">`docker run`에서 컨테이너의 이름을 지정하지 않은 경우 컨테이너 ID를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-284">If you didn't specify a name for your container in `docker run` you must use the container ID.</span></span>

<span data-ttu-id="33ea1-285">브라우저를 열고 서비스로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-285">Open a browser and navigate to your service.</span></span> <span data-ttu-id="33ea1-286">연결된 실행 중인 컨테이너에서 명령 창의 진단 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-286">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="33ea1-287"><kbd>Ctrl</kbd>+<kbd>C</kbd>를 눌러 연결 프로세스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-287">Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop the attach process.</span></span>

<span data-ttu-id="33ea1-288">컨테이너 작업이 끝났으면 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-288">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="33ea1-289">컨테이너와 이미지는 여전히 다시 시작하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-289">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="33ea1-290">컴퓨터에서 컨테이너를 제거하려는 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-290">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="33ea1-291">컴퓨터에서 사용하지 않은 이미지를 제거하려는 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-291">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="33ea1-292">결론</span><span class="sxs-lookup"><span data-stu-id="33ea1-292">Conclusion</span></span> 

<span data-ttu-id="33ea1-293">이 자습서에서는 ASP.NET Core 마이크로 서비스를 빌드하고 몇 가지 간단한 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-293">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="33ea1-294">해당 서비스에 대해 Docker 컨테이너 이미지를 빌드하고 컴퓨터에서 해당 컨테이너를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-294">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="33ea1-295">터미널 창을 서비스에 연결하고 서비스에서 진단 메시지를 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-295">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="33ea1-296">그 과정에서 C# 언어의 일부 기능이 사용되는 것을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="33ea1-296">Along the way, you saw several features of the C# language in action.</span></span>
