---
title: Docker에서 호스트되는 마이크로 서비스 - C#
description: Docker 컨테이너에서 실행되는 ASP.NET Core 서비스를 만드는 방법 알아보기
ms.date: 02/03/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: eacfa87e465e5f7737dbd2bfc4c6a77ffc5531c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="619b2-103">Docker에서 호스트되는 마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="619b2-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="619b2-104">이 자습서에서는 Docker 컨테이너에서 ASP.NET Core 마이크로 서비스를 빌드 및 배포하는 데 필요한 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="619b2-105">이 자습서를 진행하면서 다음을 익히게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="619b2-106">Yeoman를 사용하여 ASP.NET Core 응용 프로그램을 생성하는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-106">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="619b2-107">개발 Docker 환경을 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-107">How to create a development Docker environment</span></span>
* <span data-ttu-id="619b2-108">기존 이미지에 따라 Docker 이미지를 빌드하는 하는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="619b2-109">서비스를 Docker 컨테이너에 배포하는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="619b2-110">이러한 방법을 진행하면서 다음과 같은 일부 C# 언어 기능도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="619b2-111">C# 개체를 JSON 페이로드로 변환하는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="619b2-112">변경할 수 없는 데이터 전송 개체를 빌드하는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-112">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="619b2-113">들어오는 HTTP 요청을 처리하고 HTTP 응답을 생성하는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-113">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="619b2-114">null 허용 값 형식을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="619b2-114">How to work with nullable value types</span></span>

<span data-ttu-id="619b2-115">이 항목에 대한 [샘플 앱을 보거나 다운로드](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="619b2-116">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="619b2-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="619b2-117">Docker를 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="619b2-117">Why Docker?</span></span>

<span data-ttu-id="619b2-118">Docker를 사용하면 데이터 센터 또는 공용 클라우드에서 서비스를 호스트하는 표준 컴퓨터 이미지를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="619b2-119">Docker는 이미지를 구성하고, 필요할 때 이미지를 복제하여 응용 프로그램의 설치 크기를 조정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="619b2-120">이 자습서의 모든 코드는 모든 .NET Core 환경에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="619b2-121">Docker 설치를 위한 추가 작업은 ASP.NET Core 응용 프로그램에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="619b2-122">전제 조건</span><span class="sxs-lookup"><span data-stu-id="619b2-122">Prerequisites</span></span>
<span data-ttu-id="619b2-123">.NET Core를 실행하도록 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-123">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="619b2-124">[.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="619b2-125">Windows, Ubuntu Linux, macOS 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-125">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="619b2-126">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="619b2-127">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="619b2-128">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="619b2-129">또한 Docker 엔진을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="619b2-130">사용하는 플랫폼에 대한 지침을 보려면 [Docker 설치 페이지](http://www.docker.com/products/docker)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="619b2-130">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="619b2-131">Docker는 여러 Linux 배포판, macOS 또는 Windows에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="619b2-132">위에 참조된 페이지에는 사용 가능한 각 설치에 대한 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-132">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="619b2-133">설치할 대부분의 구성 요소는 패키지 관리자에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-133">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="619b2-134">node.js의 패키지 관리자 `npm`이 설치된 경우 이 단계를 건너뛰어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-134">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="619b2-135">그렇지 않은 경우 [nodejs.org](https://nodejs.org)에서 최신 NodeJs를 설치합니다. 그러면 npm 패키지 관리자가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-135">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="619b2-136">이제 ASP.NET Core 개발을 지원하는 다양한 명령줄 도구를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-136">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="619b2-137">명령줄 템플릿은 Yeoman, Bower, Grunt 및 Gulp를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-137">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="619b2-138">적절한 템플릿이 설치되어 있으면 즐겨 사용하는 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-138">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="619b2-139">`-g` 옵션은 전역 설치임을 나타내므로 해당 도구를 시스템 전체에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-139">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="619b2-140">(로컬 설치의 경우 패키지가 단일 프로젝트에 적용됨).</span><span class="sxs-lookup"><span data-stu-id="619b2-140">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="619b2-141">이러한 핵심 도구를 설치한 후 yeoman ASP.NET 템플릿 생성기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-141">Once you've installed those core tools, you need to install the yeoman ASP.NET template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="619b2-142">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="619b2-142">Create the Application</span></span>

<span data-ttu-id="619b2-143">이제 모든 도구를 설치했으므로 새로운 ASP.NET Core 응용 프로그램을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-143">Now that you've installed all the tools, create a new ASP.NET Core application.</span></span> <span data-ttu-id="619b2-144">명령줄 생성기를 사용하려면 즐겨 사용하는 셸에서 다음 yeoman 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-144">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="619b2-145">이 명령은 만들려는 응용 프로그램의 종류를 선택하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-145">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="619b2-146">이 마이크로 서비스에 대해 가능한 가장 간단하고 가장 경량의 웹 응용 프로그램에서 만들려고 하므로 '빈 웹 응용 프로그램'을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-146">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="619b2-147">템플릿은 이름을 묻는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-147">The template will prompt you for a name.</span></span> <span data-ttu-id="619b2-148">'WeatherMicroservice'를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-148">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="619b2-149">템플릿은 다음 8개의 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-149">The template creates eight files for you:</span></span>

* <span data-ttu-id="619b2-150">ASP.NET Core 응용 프로그램에 대해 사용자 지정된 .gitignore</span><span class="sxs-lookup"><span data-stu-id="619b2-150">A .gitignore, customized for ASP.NET Core applications.</span></span>
* <span data-ttu-id="619b2-151">Startup.cs 파일.</span><span class="sxs-lookup"><span data-stu-id="619b2-151">A Startup.cs file.</span></span> <span data-ttu-id="619b2-152">여기에는 응용 프로그램의 기본 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-152">This contains the basis of the application.</span></span>
* <span data-ttu-id="619b2-153">Program.cs 파일.</span><span class="sxs-lookup"><span data-stu-id="619b2-153">A Program.cs file.</span></span> <span data-ttu-id="619b2-154">여기에는 응용 프로그램의 진입점이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-154">This contains the entry point of the application.</span></span>
* <span data-ttu-id="619b2-155">WeatherMicroservice.csproj 파일.</span><span class="sxs-lookup"><span data-stu-id="619b2-155">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="619b2-156">응용 프로그램에 대한 빌드 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-156">This is the build file for the application.</span></span>
* <span data-ttu-id="619b2-157">Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="619b2-157">A Dockerfile.</span></span> <span data-ttu-id="619b2-158">이 스크립트는 응용 프로그램에 대한 Docker 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-158">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="619b2-159">README.md.</span><span class="sxs-lookup"><span data-stu-id="619b2-159">A README.md.</span></span> <span data-ttu-id="619b2-160">다른 ASP.NET Core 리소스에 대한 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-160">This contains links to other ASP.NET Core resources.</span></span>
* <span data-ttu-id="619b2-161">web.config 파일.</span><span class="sxs-lookup"><span data-stu-id="619b2-161">A web.config file.</span></span> <span data-ttu-id="619b2-162">기본 구성 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-162">This contains basic configuration information.</span></span>
* <span data-ttu-id="619b2-163">runtimeconfig.template.json 파일.</span><span class="sxs-lookup"><span data-stu-id="619b2-163">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="619b2-164">IDE에 사용되는 디버깅 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-164">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="619b2-165">이제 템플릿 생성 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-165">Now you can run the template generated application.</span></span> <span data-ttu-id="619b2-166">이 작업은 명령줄에서 일련의 도구를 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-166">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="619b2-167">`dotnet` 명령은 .NET 개발에 필요한 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-167">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="619b2-168">각 동사는 다른 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-168">Each verb executes a different command</span></span>

<span data-ttu-id="619b2-169">첫 번째 단계는 모든 종속성을 복원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-169">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="619b2-170">Dotnet은 NuGet 패키지 관리자를 사용하여 필요한 모든 패키지를 응용 프로그램 디렉터리에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-170">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="619b2-171">또한 project.json.lock 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-171">It also generates a project.json.lock file.</span></span> <span data-ttu-id="619b2-172">이 파일에는 참조되는 각 패키지에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-172">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="619b2-173">모든 종속성을 복원한 후 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-173">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="619b2-174">일단 응용 프로그램을 빌드한 후에는 명령줄에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-174">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="619b2-175">기본 구성은 `http://localhost:5000`을 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-175">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="619b2-176">브라우저를 열고 해당 페이지로 이동하면 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="619b2-176">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="619b2-177">반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-177">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="619b2-178">ASP.NET Core 응용 프로그램 분석</span><span class="sxs-lookup"><span data-stu-id="619b2-178">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="619b2-179">응용 프로그램을 빌드했으므로 기능이 구현되는 방식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-179">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="619b2-180">생성된 파일 중에서 이 시점에서 특히 흥미로운 2개의 파일은 project.json과 Startup.cs입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-180">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="619b2-181">Project.json에는 프로젝트에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-181">Project.json contains information about the project.</span></span> <span data-ttu-id="619b2-182">자주 사용하는 두 개의 노드는 '종속성'과 '프레임워크'입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-182">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="619b2-183">종속성 노드에는 이 응용 프로그램에 필요한 모든 패키지가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-183">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="619b2-184">현재 이 노드는 작으며 웹 서버를 실행하는 패키지만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-184">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="619b2-185">'프레임워크' 노드는 이 응용 프로그램을 실행하는 .NET Framework의 버전 및 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-185">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="619b2-186">응용 프로그램은 Startup.cs에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-186">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="619b2-187">이 파일에는 startup 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-187">This file contains the startup class.</span></span>

<span data-ttu-id="619b2-188">두 메서드는 ASP.NET Core 인프라에서 응용 프로그램을 구성 및 실행하기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-188">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="619b2-189">`ConfigureServices` 메서드는 이 응용 프로그램에 필요한 서비스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-189">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="619b2-190">Lean 마이크로 서비스를 빌드하는 경우 어떤 종속성도 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-190">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="619b2-191">`Configure` 메서드는 들어오는 HTTP 요청에 대한 처리기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-191">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="619b2-192">템플릿은 텍스트 'Hello World!'를 포함하는 모든 요청에 응답하는 간단한 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-192">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="619b2-193">마이크로 서비스 빌드</span><span class="sxs-lookup"><span data-stu-id="619b2-193">Build a microservice</span></span>

<span data-ttu-id="619b2-194">빌드하려는 서비스는 전 세계 어디에서든지 날씨 보고서를 전달할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-194">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="619b2-195">프로덕션 응용 프로그램에서는 날씨 데이터를 검색하기 위해 몇 가지 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-195">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="619b2-196">이 샘플에서는 임의 일기 예보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-196">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="619b2-197">임의 날씨 서비스를 구현하기 위해 수행해야 하는 많은 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-197">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="619b2-198">들어오는 요청을 구문 분석하여 위도와 경도를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-198">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="619b2-199">일부 임의 예보 데이터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-199">Generate some random forecast data.</span></span>
* <span data-ttu-id="619b2-200">C# 개체의 임의 예보 데이터를 JSON 패킷으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-200">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="619b2-201">사용자 서비스가 JSON을 다시 전송함을 나타내도록 응답 헤더를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-201">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="619b2-202">응답을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-202">Write the response.</span></span>

<span data-ttu-id="619b2-203">다음 섹션에서는 이러한 각 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-203">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="619b2-204">쿼리 문자열 구문 분석.</span><span class="sxs-lookup"><span data-stu-id="619b2-204">Parsing the Query String.</span></span>

<span data-ttu-id="619b2-205">먼저 쿼리 문자열을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-205">You'll begin by parsing the query string.</span></span> <span data-ttu-id="619b2-206">서비스는 다음 형식으로 쿼리 문자열의 'lat' 및 'long' 인수를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-206">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="619b2-207">수행해야 하는 모든 변경 내용은 람다 식에 startup 클래스의 `app.Run`에 대한 인수로 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-207">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="619b2-208">람다 식의 인수는 요청에 대한 `HttpContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-208">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="619b2-209">해당 속성 중 하나는 `Request` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-209">One of its properties is the `Request` object.</span></span> <span data-ttu-id="619b2-210">`Request` 개체는 요청에 대한 쿼리 문자열에 있는 모든 값의 사전을 포함하는 `Query` 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-210">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="619b2-211">첫 번째 추가 내용은 위도 및 경도 값을 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-211">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="619b2-212">쿼리 사전 값은 `StringValue` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-212">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="619b2-213">해당 형식에는 문자열 컬렉션이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-213">That type can contain a collection of strings.</span></span> <span data-ttu-id="619b2-214">날씨 서비스의 경우 각 값이 단일 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-214">For your weather service, each value is a single string.</span></span> <span data-ttu-id="619b2-215">이 때문에 위의 코드에서 `FirstOrDefault()`가 호출되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-215">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="619b2-216">다음에는 문자열을 double 값으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-216">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="619b2-217">문자열을 double로 변환하는 데 사용하는 메서드는 `double.TryParse()`입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-217">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="619b2-218">이 메서드는 C# out 매개 변수를 사용하여 입력 문자열을 double로 변환할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-218">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="619b2-219">문자열이 double에 대한 유효한 표현을 나타낼 경우 이 메서드는 true를 반환하고 `result` 인수는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-219">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="619b2-220">문자열이 유효한 double을 나타내지 않을 경우 이 메서드는 false를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-220">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="619b2-221">*null 허용 double*을 반환하는 *확장 메서드*를 사용하여 해당 API를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-221">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="619b2-222">*null 허용 값 형식*은 일부 값 형식을 나타내는 형식으로 누락된 값 또는 null 값을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-222">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="619b2-223">Null 허용 형식은 형식 선언에 `?` 문자를 추가하여 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-223">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="619b2-224">확장 메서드는 정적 메서드로 정의되지만 첫 번째 매개 변수에 `this` 한정자를 추가하여 마치 해당 클래스의 멤버인 것처럼 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-224">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="619b2-225">확장 메서드는 정적 클래스에서만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-225">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="619b2-226">구문 분석을 위한 확장 메서드를 포함하는 클래스의 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-226">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="619b2-227">`default(double?)` 식은 `double?` 형식의 기본값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-227">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="619b2-228">기본값은 null(또는 누락된) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-228">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="619b2-229">이 확장 메서드를 사용하여 쿼리 문자열 인수를 double 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-229">You can use this extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="619b2-230">구문 분석 코드를 쉽게 테스트하기 위해 인수 값을 포함하도록 응답을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-230">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="619b2-231">이제 웹 응용 프로그램을 실행하고 구문 분석 코드가 작동하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-231">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="619b2-232">브라우저에서 웹 요청에 값을 추가합니다. 그러면 업데이트된 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-232">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="619b2-233">임의 일기 예보 빌드</span><span class="sxs-lookup"><span data-stu-id="619b2-233">Build a random weather forecast</span></span>

<span data-ttu-id="619b2-234">다음 작업은 임의 일기 예보를 빌드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-234">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="619b2-235">일기 예보에 대해 원하는 값을 포함하는 데이터 컨테이너부터 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-235">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

<span data-ttu-id="619b2-236">다음에는 해당 값을 임의로 설정하는 생성자를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-236">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="619b2-237">이 생성자는 위도 및 경도 값을 사용하여 난수 생성기를 시드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-237">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="619b2-238">즉, 같은 위치에 대한 예보는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-238">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="619b2-239">위도 및 경도 대한 인수를 변경하면 다른 예보를 얻게 됩니다(다른 시드로 시작하므로).</span><span class="sxs-lookup"><span data-stu-id="619b2-239">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="619b2-240">이제 응답 메서드에서 5일 예보를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-240">You can now generate the 5-day forecast in your response method:</span></span>

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a><span data-ttu-id="619b2-241">JSON 응답을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-241">Build the JSON response.</span></span>

<span data-ttu-id="619b2-242">서버의 최종 코드 작업은 WeatherReport 배열을 JSON 패킷으로 변환하고 클라이언트에 다시 전송하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-242">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="619b2-243">먼저 JSON 패킷을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-243">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="619b2-244">종속성 목록에 NewtonSoft JSON Serializer를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-244">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="619b2-245">이 경우 `dotnet` CLI를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-245">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="619b2-246">그런 다음 `JsonConvert` 클래스를 사용하여 개체를 문자열에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-246">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="619b2-247">위의 코드는 예보 개체(`WeatherForecast` 개체 목록)를 JSON 패킷으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-247">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="619b2-248">응답 패킷을 생성한 다음 콘텐츠 형식을 `application/json`으로 설정하고 문자열을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-248">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="619b2-249">이제 응용 프로그램이 실행되고 임의 예보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-249">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="619b2-250">Docker 이미지 빌드</span><span class="sxs-lookup"><span data-stu-id="619b2-250">Build a Docker image</span></span>

<span data-ttu-id="619b2-251">마지막 작업은 Docker에서 응용 프로그램을 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-251">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="619b2-252">응용 프로그램을 나타내는 Docker 이미지를 실행하는 Docker 컨테이너를 만들 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-252">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="619b2-253">***Docker 이미지***는 응용 프로그램을 실행하기 위한 환경을 정의하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-253">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="619b2-254">***Docker 컨테이너***는 실행 중인 Docker 이미지 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-254">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="619b2-255">비유하자면 *Docker 이미지*를 *클래스*로, *Docker 컨테이너*를 개체 또는 해당 클래스의 인스턴스로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-255">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="619b2-256">ASP.NET 템플릿에서 만들어진 Dockerfile이 현재 작업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-256">The Dockerfile created by the ASP.NET template will serve for our purposes.</span></span> <span data-ttu-id="619b2-257">해당 내용을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-257">Let's go over its contents.</span></span>

<span data-ttu-id="619b2-258">첫 번째 줄은 소스 이미지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-258">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="619b2-259">Docker를 사용하여 소스 템플릿을 기준으로 컴퓨터 이미지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-259">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="619b2-260">시작할 때 컴퓨터의 모든 매개 변수를 제공할 필요는 없으며 변경 내용만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-260">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="619b2-261">여기서 변경은 응용 프로그램을 포함하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-261">The changes here will be to include our application.</span></span>

<span data-ttu-id="619b2-262">이 첫 번째 샘플에서는 `1.1-sdk-msbuild` 버전의 dotnet 이미지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-262">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="619b2-263">이것이 작업 Docker 환경을 만드는 가장 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-263">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="619b2-264">이 이미지는 dotnet core 런타임 및 dotnet SDK를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-264">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="619b2-265">이 이미지를 사용하면 보다 쉽게 시작하고 빌드할 수 있지만 더 큰 이미지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-265">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="619b2-266">다음 5개 줄은 응용 프로그램을 설정하고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-266">The next five lines setup and build your application:</span></span>

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroservice.csproj .
RUN dotnet restore 

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="619b2-267">현재 디렉터리의 프로젝트 파일에 Docker VM으로 복사되고 모든 패키지가 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-267">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="619b2-268">dotnet CLI를 사용하면 Docker 이미지에 .NET Core SDK가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-268">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="619b2-269">그런 다음 응용 프로그램의 나머지 부분이 복사되고 dotnet publish 명령이 응용 프로그램을 빌드하고 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-269">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="619b2-270">파일의 마지막 줄은 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-270">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="619b2-271">이 구성된 포트는 Dockerfile의 마지막 줄에 있는 `dotnet`에 대한 `--server.urls` 인수에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-271">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="619b2-272">`ENTRYPOINT` 명령은 서비스를 시작하는 명령 및 명령줄 옵션을 Docker에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-272">The `ENTRYPOINT` command informs Docker what command and command-line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="619b2-273">컨테이너에서 이미지 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="619b2-273">Building and running the image in a container.</span></span>

<span data-ttu-id="619b2-274">이미지를 빌드하고 Docker 컨테이너 내의 서비스를 실행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-274">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="619b2-275">로컬 디렉터리의 모든 파일을 이미지에 복사하려고 하지는 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-275">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="619b2-276">대신 컨테이너에서 응용 프로그램에 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-276">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="619b2-277">`.dockerignore` 파일을 만들고 이미지로 복사되지 않는 디렉토리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-277">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="619b2-278">빌드 자산은 복사하고 싶지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-278">You don't want any of the build assets copied.</span></span> <span data-ttu-id="619b2-279">빌드를 지정하고 디렉터리를 `.dockerignore` 파일에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-279">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="619b2-280">`docker build` 명령을 사용하여 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-280">You build the image using the `docker build` command.</span></span> <span data-ttu-id="619b2-281">코드를 포함하는 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-281">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="619b2-282">이 명령은 Dockerfile의 모든 정보를 기반으로 컨테이너 이미지를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-282">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="619b2-283">`-t` 인수는 이 컨테이너 이미지에 대한 태그 또는 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-283">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="619b2-284">위의 명령줄에서 Docker 컨테이너에 사용되는 태그는 `weather-microservice`입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-284">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="619b2-285">이 명령이 완료되면 컨테이너에서 새 서비스를 실행할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-285">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="619b2-286">다음 명령을 실행하여 컨테이너를 시작하고 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-286">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="619b2-287">`-d` 옵션은 현재 터미널에서 분리된 컨테이너를 실행하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-287">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="619b2-288">즉, 터미널에 명령 출력에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-288">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="619b2-289">`-p` 옵션은 서비스와 호스트 사이의 포트 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-289">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="619b2-290">여기서는 포트 80으로 들어오는 모든 요청이 컨테이너의 포트 5000으로 전달되어야 한다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-290">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="619b2-291">5000을 사용하면 서비스가 위의 Dockerfile에 지정된 명령줄 인수에서 수신을 대기하는 포트가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-291">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="619b2-292">`--name` 인수는 실행 중인 컨테이너의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-292">The `--name` argument names your running container.</span></span> <span data-ttu-id="619b2-293">해당 컨테이너 관련 작업을 수행할 때 사용할 수 있는 편리한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-293">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="619b2-294">다음 명령을 확인하여 이미지가 실행 중인지 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-294">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="619b2-295">컨테이너가 실행 중인 경우 실행 중인 프로세스에서 해당 컨테이너를 나열하는 줄이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-295">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="619b2-296">(하나만 있을 수 있음).</span><span class="sxs-lookup"><span data-stu-id="619b2-296">(It may be the only one).</span></span>

<span data-ttu-id="619b2-297">브라우저를 열고 localhost로 이동한 후 위도 및 경도를 지정하여 서비스를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-297">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="619b2-298">실행 중인 컨테이너에 연결</span><span class="sxs-lookup"><span data-stu-id="619b2-298">Attaching to a running container</span></span>

<span data-ttu-id="619b2-299">명령 창에서 서비스를 실행할 때는 각 요청에 대해 출력되는 진단 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-299">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="619b2-300">컨테이너가 분리 모드에서 실행 중인 경우에는 해당 정보가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-300">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="619b2-301">Docker attach 명령을 사용하면 실행 중인 컨테이너에 연결하여 로그 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-301">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="619b2-302">명령 창에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-302">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="619b2-303">`--sig-proxy=false` 인수는 `Ctrl-C` 명령이 컨테이너 프로세스에 전송되지 않고 오히려 `docker attach` 명령을 중지함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-303">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="619b2-304">마지막 인수는 `docker run` 명령에서 컨테이너에 지정된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-304">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="619b2-305">또한 Docker 할당 컨테이너 ID를 사용하여 컨테이너를 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-305">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="619b2-306">`docker run`에서 컨테이너의 이름을 지정하지 않은 경우 컨테이너 ID를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-306">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="619b2-307">브라우저를 열고 서비스로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-307">Open a browser and navigate to your service.</span></span> <span data-ttu-id="619b2-308">연결된 실행 중인 컨테이너에서 명령 창의 진단 메시지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-308">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="619b2-309">`Ctrl-C`를 눌러 연결 프로세스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-309">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="619b2-310">컨테이너 작업이 끝났으면 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-310">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="619b2-311">컨테이너와 이미지는 여전히 다시 시작하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-311">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="619b2-312">컴퓨터에서 컨테이너를 제거하려는 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-312">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="619b2-313">컴퓨터에서 사용하지 않은 이미지를 제거하려는 경우 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-313">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="619b2-314">결론</span><span class="sxs-lookup"><span data-stu-id="619b2-314">Conclusion</span></span> 

<span data-ttu-id="619b2-315">이 자습서에서는 ASP.NET Core 마이크로 서비스를 빌드하고 몇 가지 간단한 기능을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-315">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="619b2-316">해당 서비스에 대해 Docker 컨테이너 이미지를 빌드하고 컴퓨터에서 해당 컨테이너를 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-316">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="619b2-317">터미널 창을 서비스에 연결하고 서비스에서 진단 메시지를 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-317">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="619b2-318">그 과정에서 C# 언어의 일부 기능이 사용되는 것을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="619b2-318">Along the way, you saw several features of the C# language in action.</span></span>
