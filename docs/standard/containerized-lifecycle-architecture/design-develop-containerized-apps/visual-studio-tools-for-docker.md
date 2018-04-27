---
title: Visual Studio Tools를 사용 하 여 Docker (Visual Studio Windows에서)에 대 한
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7f000cfdaf9e750869ed6495b8198fd76e4c23b0
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a><span data-ttu-id="d1637-103">Visual Studio Tools를 사용 하 여 Docker (Visual Studio Windows에서)에 대 한</span><span class="sxs-lookup"><span data-stu-id="d1637-103">Using Visual Studio Tools for Docker (Visual Studio on Windows)</span></span>

<span data-ttu-id="d1637-104">Visual Studio Code 및 Docker CLI를 사용 하는 경우 한 Docker는 워크플로와 비슷하지만 대 한 Visual Studio 도구를 사용 하는 경우 개발자 워크플로 (실제로 동일한 Docker CLI)를 기반 있지만 보다 쉽게 시작할 수, 프로세스를 간소화 하 고 큰 제공 생산성 빌드에 대해 실행 하 고 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-104">The developer workflow when using Visual Studio Tools for Docker is similar to the workflow when using Visual Studio Code and Docker CLI (in fact, it is based on the same Docker CLI), but it is easier to get started, simplifies the process, and provides greater productivity for the build, run, and compose tasks.</span></span> <span data-ttu-id="d1637-105">실행 하 고 f5 키 또는 Ctrl + f 5를 눌러 Visual Studio에서와 같은 간단한 작업을 통해 사용자 컨테이너를 디버깅할 수 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-105">It's also able to execute and debug your containers via simple actions like F5 and Ctrl+F5 from Visual Studio.</span></span> <span data-ttu-id="d1637-106">더욱, 실행 하 고 단일 컨테이너를 디버깅할 수 있을 뿐만 아니라 Visual Studio 2017 년으로 실행 하 고 디버그할 수 컨테이너 (전체 솔루션)의 그룹 동시에 솔루션 수준에서 동일한 docker compose.yml 파일에서 정의 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="d1637-106">Even more, with Visual Studio 2017, in addition to being able to run and debug a single container, you also can run and debug a group of containers (a whole solution) at the same time if they are defined in the same docker-compose.yml file at the solution level.</span></span>

## <a name="configuring-your-local-environment"></a><span data-ttu-id="d1637-107">로컬 환경 구성</span><span class="sxs-lookup"><span data-stu-id="d1637-107">Configuring your local environment</span></span>

<span data-ttu-id="d1637-108">Windows 용 Docker의 최신 버전으로 이전에 Docker 응용 프로그램을 개발 다음 참조에 설명 된 대로 설치가 간단 하기 때문에 보다 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-108">With the latest versions of Docker for Windows, it is easier than ever to develop Docker applications because the setup is straightforward, as explained in the following references.</span></span>

<span data-ttu-id="d1637-109">**추가 정보:** 로 Windows 용 Docker를 설치 하는 방법에 대 한 자세한 내용은 <https://docs.docker.com/docker-for-windows/>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-109">**More info:** To learn more about installing Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>

<span data-ttu-id="d1637-110">Visual Studio 2015를 사용 하는 경우에 업데이트 3 또는 이후 버전와 Docker 용 Visual Studio Tools 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-110">If you're using Visual Studio 2015, you must have Update 3 or a later version plus the Visual Studio Tools for Docker.</span></span>

<span data-ttu-id="d1637-111">**추가 정보:** 알아보려면 Visual Studio를 설치 하는 방법에 지침은 [ https://www.visualstudio.com/\ 제품/vs-2015-제품-버전](https://www.visualstudio.com/products/vs-2015-product-editions)합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-111">**More info:** For instructions on installing Visual Studio, go to [https://www.visualstudio.com/\ products/vs-2015-product-editions](https://www.visualstudio.com/products/vs-2015-product-editions).</span></span>

<span data-ttu-id="d1637-112">Visual Studio Tools for Docker 설치에 대 한 확인을 이동 <http://aka.ms/vstoolsfordocker> 및 <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-112">To see more about installing Visual Studio Tools for Docker, go to <http://aka.ms/vstoolsfordocker> and <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.</span></span>

<span data-ttu-id="d1637-113">Visual Studio 2017를 사용 하 여 Docker 지원 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-113">If you're using Visual Studio 2017, Docker support is already included.</span></span>

## <a name="using-docker-tools-in-visual-studio-2015"></a><span data-ttu-id="d1637-114">Visual Studio 2015에서 Docker 도구를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d1637-114">Using Docker Tools in Visual Studio 2015</span></span>

<span data-ttu-id="d1637-115">Docker 용 Visual Studio Tools 개발 하 고 로컬로 유효성을 검사 Docker 컨테이너 linux에서 Linux Docker 호스트 또는 VM 또는 Windows에서 직접 Windows 컨테이너를 사용 하 여 일관 된 방식으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-115">The Visual Studio Tools for Docker provides a consistent way to develop and validate locally your Docker containers for Linux in a Linux Docker host or VM, or your Windows Containers directly on Windows.</span></span>

<span data-ttu-id="d1637-116">단일 컨테이너를 사용 하는 경우 가장 먼저 시작 해야.NET Core 프로젝트에 Docker 지원에 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-116">If you're using a single container, the first thing you need to begin is to turn on Docker support into your .NET Core project.</span></span> <span data-ttu-id="d1637-117">이렇게 하려면 그림 4-25에 나와 있는 것 처럼 프로젝트 파일을 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-117">To do this, right-click your project file, as shown in Figure 4-25.</span></span>

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/image/file/205468/1/add-docker-support.png](./media/image31.png)

<span data-ttu-id="d1637-118">그림 4-25: Visual Studio 프로젝트에 대 한 Docker 지원을 설정</span><span class="sxs-lookup"><span data-stu-id="d1637-118">Figure 4-25: Turning on Docker support for your Visual Studio project</span></span>

## <a name="using-docker-tools-in-visual-studio-2017"></a><span data-ttu-id="d1637-119">Visual Studio 2017에 Docker 도구를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="d1637-119">Using Docker Tools in Visual Studio 2017</span></span>

<span data-ttu-id="d1637-120">솔루션에서 서비스 프로젝트에 Docker 지원의 추가 하는 경우 (그림 4-26 참조) Visual Studio DockerFile 파일을 프로젝트에만 추가 되지 않습니다, 것도 추가 서비스 섹션 솔루션의 docker compose.yml 파일 (또는 이러한 하지 않은 경우 파일을 만드는 중 존재).</span><span class="sxs-lookup"><span data-stu-id="d1637-120">When you add Docker support to a service project in your solution (see Figure 4-26), Visual Studio is not just adding a DockerFile file to your project, it also is adding a service section in your solution's docker-compose.yml files (or creating the files if they didn't exist).</span></span> <span data-ttu-id="d1637-121">Multicontainer 솔루션; 작성을 시작 하는 쉬운 방법 다음 docker compose.yml 파일을 열 있고 추가 기능으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-121">It's an easy way to begin composing your multicontainer solution; you then can open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image32.png)

<span data-ttu-id="d1637-122">그림 4-26: Visual Studio 2017 프로젝트에서 Docker 솔루션 지원을 설정</span><span class="sxs-lookup"><span data-stu-id="d1637-122">Figure 4-26: Turning on Docker Solution support in a Visual Studio 2017 project</span></span>

<span data-ttu-id="d1637-123">이 작업을 뿐만 아니라 DockerFile 프로젝트에 추가, 또한 솔루션 수준에서 설정 된 전역 docker compose.yml에 필요한 구성 코드 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-123">This action not only adds the DockerFile to your project, it also adds the required configuration lines of code to a global docker-compose.yml set at the solution level.</span></span>

<span data-ttu-id="d1637-124">또한 켤 수 있습니다 Docker 지원 Visual Studio 2017 년에서 ASP.NET Core 프로젝트를 만들 때 그림 4-27에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-124">You also can turn on Docker support when creating an ASP.NET Core project in Visual Studio 2017, as shown in Figure 4-27.</span></span>

![](./media/image33.png)

<span data-ttu-id="d1637-125">프로젝트를 만들 때 Docker 지원을 그림 4-27: 설정</span><span class="sxs-lookup"><span data-stu-id="d1637-125">Figure 4-27: Turning on Docker support when creating a project</span></span>

<span data-ttu-id="d1637-126">Visual Studio에서 솔루션에 Docker 지원을 추가 하면 또한 나타납니다 추가 된 docker compose.yml 파일을 솔루션 탐색기에서 새 노드 트리 그림 4-28 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-126">After you add Docker support to your solution in Visual Studio, you also will see a new node tree in Solution Explorer with the added docker-compose.yml files, as depicted in Figure 4-28.</span></span>

![](./media/image34.PNG)

<span data-ttu-id="d1637-127">그림 4-28: docker compose.yml 파일 이제 솔루션 탐색기에 표시.</span><span class="sxs-lookup"><span data-stu-id="d1637-127">Figure 4-28: docker-compose.yml files now display in Solution Explorer</span></span>

<span data-ttu-id="d1637-128">multicontainer를 배포할 수 응용 프로그램을 실행할 때 단일 docker compose.yml 파일을 사용 하 여 docker-작성. 환경 (프로덕션 및 개발) 및 실행에 따라 값을 재정의할 수 있도록 Visual Studio, 그룹을 추가 하는 반면 유형 (디버그와 릴리스).</span><span class="sxs-lookup"><span data-stu-id="d1637-128">You could deploy a multicontainer application by using a single docker-compose.yml file when you run docker-compose up; however, Visual Studio adds a group of them, so you can override values depending on the environment (development versus production) and the execution type (release versus debug).</span></span> <span data-ttu-id="d1637-129">뒷부분에서이 기능을 더 잘 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1637-129">This capability will be better explained in later chapters.</span></span>

<span data-ttu-id="d1637-130">**추가 정보:** 서비스 구현 및 Docke에 대 한 Visual Studio Tools의 사용에 관한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1637-130">**More info:** For further details on the services implementation and use of Visual Studio Tools for Docker, read the following articles:</span></span>

<span data-ttu-id="d1637-131">빌드, 디버그, 업데이트 및 새로 고침 로컬 Docker 컨테이너에는 앱: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="d1637-131">Build, debug, update, and refresh apps in a local Docker container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

<span data-ttu-id="d1637-132">원격 Docker 호스트에는 ASP.NET 컨테이너를 배포 합니다. [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="d1637-132">Deploy an ASP.NET container to a remote Docker host: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="d1637-133">[이전] (docker-앱-내부-루프-workflow.md) [다음] (set-up-windows-containers-with-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d1637-133">[Previous] (docker-apps-inner-loop-workflow.md) [Next] (set-up-windows-containers-with-powershell.md)</span></span>
