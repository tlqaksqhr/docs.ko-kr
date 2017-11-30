---
title: "Docker 앱을 위한 개발 환경"
description: "Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 된 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: eedba16136ad394bda45cc871944f9b876c8ee38
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2017
---
# <a name="development-environment-for-docker-apps"></a><span data-ttu-id="0dc60-104">Docker 앱을 위한 개발 환경</span><span class="sxs-lookup"><span data-stu-id="0dc60-104">Development environment for Docker apps</span></span>

## <a name="development-tools-choices-ide-or-editor"></a><span data-ttu-id="0dc60-105">개발 도구에서 선택 항목: IDE 또는 편집기</span><span class="sxs-lookup"><span data-stu-id="0dc60-105">Development tools choices: IDE or editor</span></span>

<span data-ttu-id="0dc60-106">관계 없이 완전 하 고 강력한 IDE 또는 편집기를 간단 하 고 agile 선호 하는 경우 Microsoft에서는 Docker 응용 프로그램 개발에 있어 거둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-106">No matter if you prefer a full and powerful IDE or a lightweight and agile editor, Microsoft has you covered when it comes to developing Docker applications.</span></span>

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a><span data-ttu-id="0dc60-107">Visual Studio Code 및 Docker CLI (Mac, Linux 및 Windows 용 플랫폼 간 도구)</span><span class="sxs-lookup"><span data-stu-id="0dc60-107">Visual Studio Code and Docker CLI (cross-platform tools for Mac, Linux, and Windows)</span></span>

<span data-ttu-id="0dc60-108">모든 개발 언어를 지 원하는 플랫폼 간을 간단 하 고 편집기를 선호 하는 경우에 Visual Studio Code 및 Docker CLI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-108">If you prefer a lightweight, cross-platform editor supporting any development language, you can use Visual Studio Code and Docker CLI.</span></span> <span data-ttu-id="0dc60-109">이러한 제품은 개발자 워크플로 최적화 하기 위한 중요 한 단순 하면서도 강력한 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-109">These products provide a simple yet robust experience, which is critical for streamlining the developer workflow.</span></span> <span data-ttu-id="0dc60-110">"Docker에 대 한 Mac" 또는 "Docker에 대 한 Windows" (개발 환경)를 설치 하 여 Docker 개발자가 Windows 또는 Linux (런타임 환경)를 둘 다에 대 한 앱을 빌드할 수 단일 Docker CLI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-110">By installing "Docker for Mac" or "Docker for Windows" (development environment), Docker developers can use a single Docker CLI to build apps for both Windows or Linux (runtime environment).</span></span> <span data-ttu-id="0dc60-111">또한 Visual Studio Code 편집기에서 Docker 명령을 실행 하려면 Dockerfile 및 바로 가기 작업에 대 한 intellisense 기능을 갖춘 Docke에 대 한 확장을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-111">Plus, Visual Studio Code supports extensions for Docker with IntelliSense for Dockerfiles and shortcut-tasks to run Docker commands from the editor.</span></span>

> [!NOTE]
> <span data-ttu-id="0dc60-112">Visual Studio 코드를 다운로드 하려면로 이동 <https://code.visualstudio.com/download>합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-112">To download Visual Studio Code, go to <https://code.visualstudio.com/download>.</span></span>

<span data-ttu-id="0dc60-113">Mac 및 Windows 용 Docker을 다운로드 하려면로 이동 <http://www.docker.com/products/docker>합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-113">To download Docker for Mac and Windows, go to <http://www.docker.com/products/docker>.</span></span>

### <a name="visual-studio-with-docker-tools"></a><span data-ttu-id="0dc60-114">Docker 도구와 visual Studio</span><span class="sxs-lookup"><span data-stu-id="0dc60-114">Visual Studio with Docker Tools</span></span>

<span data-ttu-id="0dc60-115">Visual Studio 2015를 사용 하는 경우 "Visual Studio 용 Docker 도구입니다." 추가 기능 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-115">When you're using Visual Studio 2015 you can install the add-on tools "Docker Tools for Visual Studio."</span></span> <span data-ttu-id="0dc60-116">Visual Studio 2017 년에 대 한 Docker 도구 제공 내장 이미 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-116">For Visual Studio 2017, Docker Tools come built in already.</span></span> <span data-ttu-id="0dc60-117">두 경우 모두 개발할 수 있습니다 실행 하 고 선택한 Docker 환경에서 직접 응용 프로그램의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-117">In both cases you can develop, run, and validate your applications directly in the chosen Docker environment.</span></span> <span data-ttu-id="0dc60-118">F 5를 눌러 응용 프로그램 (단일 컨테이너 또는 여러 컨테이너)는 Docker에 직접 디버깅을 호스트 하거나 Ctrl + f 5를 편집 하 여 컨테이너를 다시 작성 하지 않고도 앱을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-118">F5 your application (single container or multiple containers) directly into a Docker host with debugging, or press Ctrl+F5 to edit and refresh your app without having to rebuild the container.</span></span> <span data-ttu-id="0dc60-119">이 Linux 또는 Windows 용 Docker 컨테이너를 만들고 Windows 개발자를 위한 가장 간단한 효율적이 고 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-119">This is the simplest and more powerful choice for Windows developers creating Docker containers for Linux or Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="0dc60-120">Visual Studio 용 Docker 도구를 다운로드 하려면로 이동 <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>합니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-120">To download Docker Tools for Visual Studio, go to <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.</span></span>

## <a name="language-and-framework-choices"></a><span data-ttu-id="0dc60-121">언어 및 프레임 워크 선택</span><span class="sxs-lookup"><span data-stu-id="0dc60-121">Language and framework choices</span></span>

<span data-ttu-id="0dc60-122">Docker 응용 프로그램 및 대부분의 언어와 Microsoft 도구를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-122">You can develop Docker applications and Microsoft tools with most modern languages.</span></span> <span data-ttu-id="0dc60-123">다음은 초기 목록을 하지만에 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-123">The following is an initial list, but you are not limited to it:</span></span>

-   <span data-ttu-id="0dc60-124">.NET core 및 ASP.NET 코어</span><span class="sxs-lookup"><span data-stu-id="0dc60-124">.NET Core and ASP.NET Core</span></span>

-   <span data-ttu-id="0dc60-125">Node.js</span><span class="sxs-lookup"><span data-stu-id="0dc60-125">Node.js</span></span>

-   <span data-ttu-id="0dc60-126">Golang</span><span class="sxs-lookup"><span data-stu-id="0dc60-126">Golang</span></span>

-   <span data-ttu-id="0dc60-127">Java</span><span class="sxs-lookup"><span data-stu-id="0dc60-127">Java</span></span>

-   <span data-ttu-id="0dc60-128">Ruby</span><span class="sxs-lookup"><span data-stu-id="0dc60-128">Ruby</span></span>

-   <span data-ttu-id="0dc60-129">Python</span><span class="sxs-lookup"><span data-stu-id="0dc60-129">Python</span></span>

<span data-ttu-id="0dc60-130">기본적으로, Linux 또는 Windows에서 Docker에서 지 원하는 다른 최신 언어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dc60-130">Basically, you can use any modern language supported by Docker in Linux or Windows.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="0dc60-131">[이전] (오케스트레이션-높은-확장성-availability.md) [다음] (docker-앱-내부-루프-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0dc60-131">[Previous] (orchestrate-high-scalability-availability.md) [Next] (docker-apps-inner-loop-workflow.md)</span></span>
