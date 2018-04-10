---
title: Docker 기반 응용 프로그램에 대한 개발 프로세스
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Docker 기반 응용 프로그램에 대한 개발 프로세스
keywords: Docker, 마이크로 서비스, ASP.NET, 컨테이너
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dc91c7d5e2e27602afd6d583bf09adae3caea59e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="development-process-for-docker-based-applications"></a><span data-ttu-id="ea233-104">Docker 기반 응용 프로그램에 대한 개발 프로세스</span><span class="sxs-lookup"><span data-stu-id="ea233-104">Development Process for Docker-Based Applications</span></span>

<span data-ttu-id="ea233-105">*Visual Studio 및 Visual Studio Tools for Docker에 중점을 둔 IDE 또는 Docker CLI 및 Visual Studio Code에 중점을 둔 CLI/편집기 중 원하는 방식으로 컨테이너화된 .NET 응용 프로그램을 개발하세요.*</span><span class="sxs-lookup"><span data-stu-id="ea233-105">*Develop containerized .NET applications the way you like, either IDE focused with Visual Studio and Visual Studio tools for Docker or CLI/Editor focused with Docker CLI and Visual Studio Code.*</span></span>

## <a name="development-environment-for-docker-apps"></a><span data-ttu-id="ea233-106">Docker 앱을 위한 개발 환경</span><span class="sxs-lookup"><span data-stu-id="ea233-106">Development environment for Docker apps</span></span>

### <a name="development-tool-choices-ide-or-editor"></a><span data-ttu-id="ea233-107">개발 도구 선택: IDE 또는 편집기</span><span class="sxs-lookup"><span data-stu-id="ea233-107">Development tool choices: IDE or editor</span></span>

<span data-ttu-id="ea233-108">완전하고 강력한 IDE를 선호하든지 아니면 간단하고 민첩한 편집기를 선호하든지 상관없이 Microsoft는 Docker 응용 프로그램을 개발하는 데 사용할 수 있는 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-108">Whether you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has tools that you can use for developing Docker applications.</span></span>

<span data-ttu-id="ea233-109">**Visual Studio(Windows용)**.</span><span class="sxs-lookup"><span data-stu-id="ea233-109">**Visual Studio (for Windows)**.</span></span> <span data-ttu-id="ea233-110">Docker 기반 응용 프로그램을 개발하려면 이미 기본 제공되는 Docker용 도구와 함께 제공되는 Visual Studio 2017 이상 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-110">To develop Docker-based applications, use Visual Studio 2017 or later versions that comes with tools for Docker already built-in.</span></span> <span data-ttu-id="ea233-111">Docker용 도구를 통해 대상 Docker 환경에서 직접 응용 프로그램을 개발하고 실행할 수 있으며, 응용 프로그램의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-111">The tools for Docker let you develop, run, and validate your applications directly in the target Docker environment.</span></span> <span data-ttu-id="ea233-112">F5 키를 눌러 응용 프로그램(단일 컨테이너 또는 여러 컨테이너)을 Docker 호스트에 직접 실행 및 디버그하거나, Ctrl+F5를 눌러 컨테이너를 다시 빌드하지 않고도 응용 프로그램을 편집 및 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-112">You can press F5 to run and debug your application (single container or multiple containers) directly into a Docker host, or press CTRL+F5 to edit and refresh your application without having to rebuild the container.</span></span> <span data-ttu-id="ea233-113">이는 Docker 기반 앱을 위한 가장 강력한 개발 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-113">This is the most powerful development choice for Docker-based apps.</span></span>

<span data-ttu-id="ea233-114">**Mac용 Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="ea233-114">**Visual Studio for Mac**.</span></span> <span data-ttu-id="ea233-115">Xamarin Studio에서 진화한 IDE로, macOS에서 실행되고 Docker 기반 응용 프로그램 개발을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-115">It is an IDE, evolution of Xamarin Studio, that runs on macOS and supports Docker-based application development.</span></span> <span data-ttu-id="ea233-116">이는 Mac 컴퓨터에서 작업 중인 개발자로, 강력한 IDE도 사용하고자 하는 경우에 권장되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-116">This should be the preferred choice for developers working in Mac machines who also want to use a powerful IDE.</span></span>

<span data-ttu-id="ea233-117">**Visual Studio Code 및 Docker CLI**.</span><span class="sxs-lookup"><span data-stu-id="ea233-117">**Visual Studio Code and Docker CLI**.</span></span> <span data-ttu-id="ea233-118">개발 언어를 지원하는 간단한 플랫폼 간 편집기를 선호하는 경우 Microsoft VS Code(Visual Studio Code) 및 Docker CLI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-118">If you prefer a lightweight and cross-platform editor that supports any development language, you can use Microsoft Visual Studio Code (VS Code) and the Docker CLI.</span></span> <span data-ttu-id="ea233-119">이는 Mac, Linux 및 Windows에 대한 플랫폼 간 개발 접근법입니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-119">This is a cross-platform development approach for Mac, Linux, and Windows.</span></span>

<span data-ttu-id="ea233-120">[Docker CE(Community Edition)](https://www.docker.com/community-edition) 도구를 설치하면 단일 Docker CLI를 사용하여 Windows용 앱과 Linux용 앱을 모두 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-120">By installing [Docker Community Edition (CE)](https://www.docker.com/community-edition) tools, you can use a single Docker CLI to build apps for both Windows and Linux.</span></span> <span data-ttu-id="ea233-121">또한 Visual Studio Code는 Dockerfile용 IntelliSense와 같은 Docker용 확장을 지원하고 편집기에서 Docker 명령을 실행하는 바로 가기 작업도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-121">Additionally, Visual Studio Code supports extensions for Docker such as IntelliSense for Dockerfiles and shortcut tasks to run Docker commands from the editor.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ea233-122">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="ea233-122">Additional resources</span></span>

-   <span data-ttu-id="ea233-123">**Visual Studio Tools for Docker**
    [*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span><span class="sxs-lookup"><span data-stu-id="ea233-123">**Visual Studio Tools for Docker**
[*https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker*](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>

-   <span data-ttu-id="ea233-124">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="ea233-124">**Visual Studio Code**.</span></span> <span data-ttu-id="ea233-125">공식 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-125">Official site.</span></span>
    [<span data-ttu-id="ea233-126">*https://code.visualstudio.com/download*</span><span class="sxs-lookup"><span data-stu-id="ea233-126">*https://code.visualstudio.com/download*</span></span>](https://code.visualstudio.com/download)

-   <span data-ttu-id="ea233-127">**Mac 및 Windows용 Docker CE(Community Edition)**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span><span class="sxs-lookup"><span data-stu-id="ea233-127">**Docker Community Edition (CE) for Mac and Windows**
[*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)</span></span>

## <a name="net-languages-and-frameworks-for-docker-containers"></a><span data-ttu-id="ea233-128">Docker 컨테이너를 위한 .NET 언어 및 프레임워크</span><span class="sxs-lookup"><span data-stu-id="ea233-128">.NET languages and frameworks for Docker containers</span></span>

<span data-ttu-id="ea233-129">이 가이드의 이전 섹션에서 언급했듯이 Docker 컨테이너화된 .NET 응용 프로그램을 개발할 때 .NET Framework, .NET Core 또는 오픈 소스 Mono 프로젝트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-129">As mentioned in earlier sections of this guide, you can use .NET Framework, .NET Core, or the open-source Mono project when developing Docker containerized .NET applications.</span></span> <span data-ttu-id="ea233-130">Linux 또는 Windows 컨테이너를 대상으로 할 때 사용 중인 .NET Framework에 따라 C\#, F\# 또는 Visual Basic으로 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea233-130">You can develop in C\#, F\#, or Visual Basic when targeting Linux or Windows Containers, depending on which .NET framework is in use.</span></span> <span data-ttu-id="ea233-131">.NET 언어에 대한 자세한 내용은 블로그 게시물, [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/)(.NET 언어 전략)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea233-131">For more details about.NET languages, see the blog post [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ea233-132">[이전](../architect-microservice-container-applications/using-azure-service-fabric.md) [다음](docker-app-development-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ea233-132">[Previous] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Next] (docker-app-development-workflow.md)</span></span>
