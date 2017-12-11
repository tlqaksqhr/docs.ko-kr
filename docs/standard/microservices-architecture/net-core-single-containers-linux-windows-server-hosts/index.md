---
title: "Linux 또는 Windows Nano 서버 호스트에 단일 컨테이너 기반 .NET Core 웹 응용 프로그램 배포"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Linux 또는 Windows Nano 서버 호스트에 단일 컨테이너 기반 .NET Core 웹 응용 프로그램 배포"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 73d733a45837d047319312ea7b2e558a02b39eba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a><span data-ttu-id="50237-104">Linux 또는 Windows Nano 서버 호스트에 단일 컨테이너 기반 .NET Core 웹 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="50237-104">Deploying Single-Container-Based .NET Core Web Applications on Linux or Windows Nano Server Hosts</span></span>

<span data-ttu-id="50237-105">*간단한 웹 응용 프로그램의 모놀리식 배포에 대해 Docker 컨테이너를 사용할 수 있습니다. 이를 통해 지속적인 통합 및 지속적인 배포 파이프라인이 개선되며 프로덕션에 배포할 수 있습니다. 더 이상 “내 컴퓨터에서는 되는데 프로덕션에서는 되지 않는” 문제가 발생하지 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="50237-105">*You can use Docker containers for monolithic deployment of simpler web applications. This improves continuous integration and continuous deployment pipelines and helps achieve deployment-to-production success. No more “It works in my machine, why does not work in production?”*</span></span>

<span data-ttu-id="50237-106">마이크로 서비스 기반 아키텍처에는 다양한 이점이 있지만 그에 따른 복잡성도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-106">A microservices-based architecture has many benefits, but those benefits come at a cost of increased complexity.</span></span> <span data-ttu-id="50237-107">이점보다 비용이 더 많이 들어서, 단일 컨테이너 또는 소수의 컨테이너에서 실행되는 모놀리식 배포 응용 프로그램을 사용하는 것이 더 나은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-107">In some cases, the costs outweigh the benefits, and you will be better served with a monolithic deployment application running in a single container or in just a few containers.</span></span> 

<span data-ttu-id="50237-108">모놀리식 응용 프로그램은 잘 분리된 마이크로 서비스로 쉽게 분할되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-108">A monolithic application might not be easily decomposable into well-separated microservices.</span></span> <span data-ttu-id="50237-109">앞서 언급한 대로, 마이크로 서비스는 기능별로 분할되어야 합니다. 마이크로 서비스는 독립적으로 작업을 수행하며 복원력이 우수한 응용 프로그램을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-109">You have learned that these should be partitioned by function: microservices should work independently of each other to provide a more resilient application.</span></span> <span data-ttu-id="50237-110">응용 프로그램의 기능 조각을 제공할 수 없는 경우 응용 프로그램을 분리하면 복잡성만 더할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="50237-110">If you cannot deliver feature slices of the application, separating it only adds complexity.</span></span>

<span data-ttu-id="50237-111">응용 프로그램의 기능을 독립적으로 확장할 필요가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-111">An application might not yet need to scale features independently.</span></span> <span data-ttu-id="50237-112">eShopOnContainers 참조 응용 프로그램의 수명 초기에, 트래픽 때문에 기능을 여러 마이크로 서비스로 분리할 필요가 없는 상황을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="50237-112">Let’s suppose that early in the life of our eShopOnContainers reference application, the traffic did not justify separating features into different microservices.</span></span> <span data-ttu-id="50237-113">트래픽은 매우 작기 때문에 대개 하나의 서비스에 리소스를 추가하면 모든 서비스에 리소스가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-113">Traffic was small enough that adding resources to one service typically meant adding resources to all services.</span></span> <span data-ttu-id="50237-114">추가로 응용 프로그램을 불연속 서비스로 분리해서 얻는 이점은 매우 적습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-114">The additional work to separate the application into discrete services provided minimal benefit.</span></span>

<span data-ttu-id="50237-115">또한 응용 프로그램의 개발 초기에는 자연적인 기능 경계를 명확하게 알지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-115">Also, early in the development of an application you might not have a clear idea where the natural functional boundaries are.</span></span> <span data-ttu-id="50237-116">최소 기능 제품을 개발할 때는 자연적인 분리가 아직 발생하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-116">As you develop a minimum viable product, the natural separation might not yet have emerged.</span></span>

<span data-ttu-id="50237-117">이러한 조건 중 일부는 일시적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-117">Some of these conditions might be temporary.</span></span> <span data-ttu-id="50237-118">모놀리식 응용 프로그램을 만들어 시작하고 나중에 일부 기능을 분리하여 마이크로 서비스로 개발하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-118">You might start by creating a monolithic application, and later separate some features to be developed and deployed as microservices.</span></span> <span data-ttu-id="50237-119">응용 프로그램의 문제 영역에는 다른 조건이 필요할 수 있습니다. 즉, 응용 프로그램은 여러 마이크로 서비스로 분리되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-119">Other conditions might be essential to the application’s problem space, meaning that the application might never be broken into multiple microservices.</span></span>

<span data-ttu-id="50237-120">응용 프로그램을 다수의 불연속 프로세스로 분리하면 오버헤드도 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-120">Separating an application into many discrete processes also introduces overhead.</span></span> <span data-ttu-id="50237-121">기능을 다른 프로세스로 분리하는 작업이 더 어려워지며</span><span class="sxs-lookup"><span data-stu-id="50237-121">There is more complexity in separating features into different processes.</span></span> <span data-ttu-id="50237-122">통신 프로토콜이 더 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="50237-122">The communication protocols become more complex.</span></span> <span data-ttu-id="50237-123">서비스 간에 메서드 호출 대신 비동기적인 통신을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-123">Instead of method calls, you must use asynchronous communications between services.</span></span> <span data-ttu-id="50237-124">마이크로 서비스 아키텍처로 이동하면 이벤트 버스 처리, 메시지 복원력 및 다시 시도, 최종 일관성 등 eShopOnContainers 응용 프로그램의 마이크로 서비스 버전에서 구현된 빌드 블록을 많이 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-124">As you move to a microservices architecture, you need to add many of the building blocks implemented in the microservices version of the eShopOnContainers application: event bus handling, message resiliency and retries, eventual consistency, and more.</span></span>

<span data-ttu-id="50237-125">한층 간소화된 버전의 eShopOnContainers([eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic)이라고 하며 동일한 GitHub 리포지토리에 포함됨)는 모놀리식 MVC 응용 프로그램으로 실행되며 설명한 바와 같이 이러한 디자인 선택에는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-125">A much-simplified version of eShopOnContainers (named [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) and included in the same GitHub repo) runs as a monolithic MVC application, and as just described, there are advantages offered by that design choice.</span></span> <span data-ttu-id="50237-126">GitHub에서 이 응용 프로그램에 대한 소스를 다운로드하고 로컬에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-126">You can download the source for this application from GitHub and run it locally.</span></span> <span data-ttu-id="50237-127">이 모놀리식 응용 프로그램도 컨테이너 환경에서의 배포를 통해 이점을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-127">Even this monolithic application benefits from being deployed in a container environment.</span></span>

<span data-ttu-id="50237-128">첫째, 컨테이너화된 배포는 응용 프로그램의 모든 인스턴스가 동일한 환경에서 실행되는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-128">For one, the containerized deployment means that every instance of the application runs in the same environment.</span></span> <span data-ttu-id="50237-129">여기에는 초기 테스트 및 개발이 이루어지는 개발자 환경이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-129">This includes the developer environment where early testing and development take place.</span></span> <span data-ttu-id="50237-130">개발 팀은 프로덕션 환경과 일치하는 컨테이너화된 환경에서 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-130">The development team can run the application in a containerized environment that matches the production environment.</span></span>

<span data-ttu-id="50237-131">둘째, 저렴한 비용으로 컨테이너화된 응용 프로그램을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-131">In addition, containerized applications scale out at lower cost.</span></span> <span data-ttu-id="50237-132">앞서 살펴본 것처럼 컨테이너 환경에서는 기존의 VM 환경에서보다 더 많은 리소스를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-132">As you saw earlier, the container environment enables greater resource sharing than traditional VM environments.</span></span>

<span data-ttu-id="50237-133">마지막으로, 응용 프로그램을 컨테이너화하면 비즈니스 논리와 저장소 서버 사이에서 강제 분할이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-133">Finally, containerizing the application forces a separation between the business logic and the storage server.</span></span> <span data-ttu-id="50237-134">응용 프로그램이 확장되면 여러 컨테이너는 모두 단일 실제 저장소 매체를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-134">As the application scales out, the multiple containers will all rely on a single physical storage medium.</span></span> <span data-ttu-id="50237-135">일반적으로 SQL Server 데이터베이스를 실행하는 고가용성의 서버가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-135">This would typically be a high-availability server running a SQL Server database.</span></span>

## <a name="application-tour"></a><span data-ttu-id="50237-136">응용 프로그램 둘러보기</span><span class="sxs-lookup"><span data-stu-id="50237-136">Application tour</span></span>

<span data-ttu-id="50237-137">[eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) 응용 프로그램은 모놀리식 응용 프로그램으로 실행되는 eShopOnContainers 응용 프로그램인 .NET Core에서 실행되는 ASP.NET Core MVC 기반 응용 프로그램의 일부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="50237-137">The [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) application represents some of the eShopOnContainers application running as a monolithic application—an ASP.NET Core MVC based application running on .NET Core.</span></span> <span data-ttu-id="50237-138">이 응용 프로그램은 이전 섹션에서 설명했던 카탈로그 검색 기능을 주로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-138">It mainly provides the catalog browsing capabilities that we described in earlier sections.</span></span>

<span data-ttu-id="50237-139">이 응용 프로그램은 카탈로그 저장소에 대해 SQL Server 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-139">The application uses a SQL Server database for the catalog storage.</span></span> <span data-ttu-id="50237-140">컨테이너 기반 배포에서 이 모놀리식 응용 프로그램은 마이크로 서비스 기반 응용 프로그램과 동일한 데이터 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-140">In container-based deployments, this monolithic application can access the same data store as the microservices-based application.</span></span> <span data-ttu-id="50237-141">이 응용 프로그램은 모놀리식 응용 프로그램과 함께 컨테이너에서 SQL Server를 실행할 수 있도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-141">The application is configured to run SQL Server in a container alongside the monolithic application.</span></span> <span data-ttu-id="50237-142">프로덕션 환경에서 SQL Server는 Docker 호스트 외부의 고가용성 컴퓨터에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-142">In a production environment, SQL Server would run on a high-availability machine, outside of the Docker host.</span></span> <span data-ttu-id="50237-143">편의를 위해 개발 또는 테스트 환경에서는 자체 컨테이너에서 SQL Server를 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-143">For convenience in a dev or test environment, we recommend running SQL Server in its own container.</span></span>

<span data-ttu-id="50237-144">초기 기능 집합에서는 카탈로그 검색 기능만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-144">The initial feature set only enables browsing the catalog.</span></span> <span data-ttu-id="50237-145">업데이트하면 컨테이너화된 응용 프로그램의 전체 기능 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-145">Updates would enable the full feature set of the containerized application.</span></span> <span data-ttu-id="50237-146">고급 모놀리식 웹 응용 프로그램 아키텍처는 [ASP.NET 웹 응용 프로그램 아키텍처 사례](https://aka.ms/webappebook) 전자책과 관련 [eShopOnWeb 응용 프로그램 예제](http://aka.ms/WebAppArchitecture)에 설명되어 있습니다. 단, 이 경우에는 해당 시나리오가 ASP.NET Core를 사용한 일반 웹 개발에 집중하므로 Docker 컨테이너에서 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-146">A more advanced monolithic web application architecture is described in the [ASP.NET Web Application architecture practices](https://aka.ms/webappebook) e-book and related [eShopOnWeb sample application](http://aka.ms/WebAppArchitecture), although in that case it is not running on Docker containers because that scenario focuses on plain web development with ASP.NET Core.</span></span>

<span data-ttu-id="50237-147">그러나 eShopOnContainers(eShopWeb)에서 사용할 수 있는 단순화된 버전은 Docker 컨테이너에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-147">However, the simplified version available in eShopOnContainers (eShopWeb) runs in a Docker container.</span></span>

## <a name="docker-support"></a><span data-ttu-id="50237-148">Docker 지원</span><span class="sxs-lookup"><span data-stu-id="50237-148">Docker support</span></span>

<span data-ttu-id="50237-149">eShopOnWeb 프로젝트는.NET Core에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-149">The eShopOnWeb project runs on .NET Core.</span></span> <span data-ttu-id="50237-150">따라서 Linux 기반 또는 Windows 기반 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-150">Therefore, it can run in either Linux-based or Windows-based containers.</span></span> <span data-ttu-id="50237-151">Docker 배포에서는 SQL Server에 대해서 동일한 호스트 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-151">Note that for Docker deployment, you want to use the same host type for SQL Server.</span></span> <span data-ttu-id="50237-152">사람들은 Linux 기반 컨테이너를 선호하며 여기에서는 더 작은 공간을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-152">Linux-based containers allow a smaller footprint and are preferred.</span></span>

<span data-ttu-id="50237-153">Visual Studio는 Docker에 대한 지원을 솔루션에 추가하는 프로젝트 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-153">Visual Studio provides a project template that adds support for Docker to a solution.</span></span> <span data-ttu-id="50237-154">프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭하면 **Docker 지원**이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-154">You right-click the project, click **Add** followed by **Docker Support**.</span></span> <span data-ttu-id="50237-155">템플릿은 Dockerfile을 기존 프로젝트와 시작 docker-compose.yml 파일을 제공하는 새 **docker-compose** 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-155">The template adds a Dockerfile to your project, and a new **docker-compose** project that provides a starter docker-compose.yml file.</span></span> <span data-ttu-id="50237-156">이 단계는 GitHub에서 다운로드한 eShopOnWeb 프로젝트에서 이미 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-156">This step has already been done in the eShopOnWeb project downloaded from GitHub.</span></span> <span data-ttu-id="50237-157">그림 6-1에 표시된 것처럼 솔루션에 **eShopOnWeb** 프로젝트와 **docker-compose** 프로젝트가 포함되었음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-157">You will see that the solution contains the **eShopOnWeb** project and the **docker-compose** project as shown in Figure 6-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="50237-158">**그림 6-1**.</span><span class="sxs-lookup"><span data-stu-id="50237-158">**Figure 6-1**.</span></span> <span data-ttu-id="50237-159">단일 컨테이너 웹 응용 프로그램의 **docker-compose** 프로젝트</span><span class="sxs-lookup"><span data-stu-id="50237-159">The **docker-compose** project in a single-container web application</span></span>

<span data-ttu-id="50237-160">이러한 파일은 모든 Docker 프로젝트와 일치하는 표준 docker-compose 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="50237-160">These files are standard docker-compose files, consistent with any Docker project.</span></span> <span data-ttu-id="50237-161">Visual Studio 또는 명령줄에서 해당 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-161">You can use them with Visual Studio or from the command line.</span></span> <span data-ttu-id="50237-162">이 응용 프로그램은 .NET Core에서 실행되며 Linux 컨테이너를 사용하므로 Mac 또는 Linux 컴퓨터에서 응용 프로그램을 코딩, 빌드 및 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-162">This application runs on .NET Core and uses Linux containers, so you can also code, build, and run on a Mac or on a Linux machine.</span></span>

<span data-ttu-id="50237-163">Docker compose.yml 파일에는 빌드할 이미지 및 시작할 컨테이너에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-163">The docker-compose.yml file contains information about what images to build and what containers to launch.</span></span> <span data-ttu-id="50237-164">템플릿은 eshopweb 이미지를 빌드하고 응용 프로그램의 컨테이너를 시작하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-164">The templates specify how to build the eshopweb image and launch the application’s containers.</span></span> <span data-ttu-id="50237-165">컨테이너를 빌드하고 시작하려면 이미지(예: mssql-server-linux)를 포함하여 SQL Server에서 종속성을 추가하고 Docker의 sql.data 이미지에 대한 서비스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-165">You need to add the dependency on SQL Server by including an image for it (for example, mssql-server-linux), and a service for the sql.data image for Docker to build and launch that container.</span></span> <span data-ttu-id="50237-166">이러한 설정이 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-166">These settings are shown in the following example:</span></span>

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web
    build:
    context: ./eShopWeb
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  sql.data:
    image: microsoft/mssql-server-linux
```

<span data-ttu-id="50237-167">depends\_on 지시문은 eShopWeb 이미지가 sql.data 이미지에 종속된다는 사실을 Docker에게 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50237-167">The depends\_on directive tells Docker that the eShopWeb image depends on the sql.data image.</span></span> <span data-ttu-id="50237-168">해당 지시문 아래 줄은 microsoft/mssql-server-linux 이미지를 사용하여 이미지가 태그된 sql.data를 빌드하기 위한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="50237-168">Lines below that are the instructions to build an image tagged sql.data using the microsoft/mssql-server-linux image.</span></span>

<span data-ttu-id="50237-169">**docker-compose** 프로젝트는 기본 docker-compose.yml 노드에서 다른 docker-compose 파일을 표시하여 해당 파일과 관련된 시각적 표시를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-169">The **docker-compose** project displays the other docker-compose files under the main docker-compose.yml node to provide a visual indication that these files are related.</span></span> <span data-ttu-id="50237-170">docker-compose-override.yml 파일에는 연결 문자열 및 다른 응용 프로그램 설정과 같은 두 서비스 모두에 대한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-170">The docker-compose-override.yml file contains settings for both services, such as connection strings and other application settings.</span></span>

<span data-ttu-id="50237-171">다음 예제에서는 Visual Studio의 디버깅에 사용되는 설정이 포함된 docker-compose.vs.debug.yml 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50237-171">The following example shows the docker-compose.vs.debug.yml file, which contains settings used for debugging in Visual Studio.</span></span> <span data-ttu-id="50237-172">해당 파일에서는 eshopweb 이미지에 개발 태그가 추가되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-172">In that file, the eshopweb image has the dev tag appended to it.</span></span> <span data-ttu-id="50237-173">개발 태그가 릴리스 이미지에서 디버그를 분리하는 작업을 도와주어 실수로 디버그 정보를 프로덕션 환경에 배포하는 문제가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-173">That helps separate debug from release images so that you do not accidentally deploy the debug information to a production environment:</span></span>

```yml
version: '2'
  
services:
  eshopweb:
    image: eshop/web:dev
    build:
    args:
    source: ${DOCKER_BUILD_SOURCE}
    environment:
      - DOTNET_USE_POLLING_FILE_WATCHER=1
    volumes:
      - ./eShopWeb:/app
      - ~/.nuget/packages:/root/.nuget/packages:ro
      - ~/clrdbg:/clrdbg:ro
    entrypoint: tail -f /dev/null
    labels:
      - "com.microsoft.visualstudio.targetoperatingsystem=linux"
```

<span data-ttu-id="50237-174">추가된 마지막 파일은 docker-compose.ci.build.yml입니다.</span><span class="sxs-lookup"><span data-stu-id="50237-174">The last file added is docker-compose.ci.build.yml.</span></span> <span data-ttu-id="50237-175">이 파일은 CI 서버에서 프로젝트를 빌드하기 위해 명령줄에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-175">This would be used from the command line to build the project from a CI server.</span></span> <span data-ttu-id="50237-176">이 compose 파일은 응용 프로그램에 필요한 이미지를 빌드하는 Docker 컨테이너를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-176">This compose file starts a Docker container that builds the images needed for your application.</span></span> <span data-ttu-id="50237-177">다음 예제에서는 docker-compose.ci.build.yml 파일의 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50237-177">The following example shows the contents of the docker-compose.ci.build.yml file.</span></span>

```yml
version: '2'
  
services:
  ci-build:
    image: microsoft/aspnetcore-build:1.0-1.1
    volumes:
      - .:/src
    working_dir: /src
  command: /bin/bash -c "dotnet restore ./eShopWeb.sln && dotnet publish  ./eShopWeb.sln -c Release -o ./obj/Docker/publish"
```

<span data-ttu-id="50237-178">**참고**: .NET Core 2.0부터는 dotnet publish가 실행되면 자동으로 dotnet restore 명령이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-178">**Note**: Starting with .NET Core 2.0, the dotnet restore command executes automatically when dotnet publish is executed.</span></span>

<span data-ttu-id="50237-179">이 이미지는 ASP.NET Core 빌드 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="50237-179">Notice that the image is an ASP.NET Core build image.</span></span> <span data-ttu-id="50237-180">해당 이미지에는 응용 프로그램을 빌드하고 필수 이미지를 만들기 위한 SDK와 빌드 도구가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-180">That image includes the SDK and build tools to build your application and create the required images.</span></span> <span data-ttu-id="50237-181">이 파일을 사용하여 **docker-compose** 프로젝트를 실행하면 이미지에서 컨테이너가 빌드된 후 해당 컨테이너에서 응용 프로그램의 이미지가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-181">Running the **docker-compose** project using this file starts the build container from the image, then builds your application’s image in that container.</span></span> <span data-ttu-id="50237-182">docker-compose 파일을 명령줄의 일부로 지정하여 Docker 컨테이너에서 응용 프로그램을 빌드한 다음 시작하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-182">You specify that docker-compose file as part of the command line to build your application in a Docker container, then launch it.</span></span>

<span data-ttu-id="50237-183">다른 응용 프로그램을 실행할 때와 같이 Visual Studio에서 **docker-compose** 프로젝트를 시작 프로젝트로 선택한 다음 Ctrl+F5(디버그하려면 F5 키)를 눌러 Docker 컨테이너에서 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-183">In Visual Studio, you can run your application in Docker containers by selecting the **docker-compose** project as the startup project, and then pressing Ctrl+F5 (F5 to debug), as you can with any other application.</span></span> <span data-ttu-id="50237-184">**docker-compose** 프로젝트를 시작하면 Visual Studio는 docker-compose.yml 파일, docker-compose.override.yml 파일 및 docker-compose.vs.\* 파일 중 하나를 사용하여 **docker-compose**를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-184">When you start the **docker-compose** project, Visual Studio runs **docker-compose** using the docker-compose.yml file, the docker-compose.override.yml file, and one of the docker-compose.vs.\* files.</span></span> <span data-ttu-id="50237-185">응용 프로그램이 시작되면 Visual Studio에서는 브라우저가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-185">Once the application has started, Visual Studio launches the browser for you.</span></span>

<span data-ttu-id="50237-186">디버거에서 응용 프로그램을 시작한 경우 Visual Studio는 Docker에서 실행 중인 응용 프로그램을 첨부합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-186">If you launch the application in the debugger, Visual Studio will attach to the running application in Docker.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="50237-187">문제 해결</span><span class="sxs-lookup"><span data-stu-id="50237-187">Troubleshooting</span></span>

<span data-ttu-id="50237-188">이 섹션에서는 로컬에서 컨테이너를 실행할 때 발생할 수 있는 몇 가지 문제를 설명하고 일부 해결 방법을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-188">This section describes a few issues that might arise when your run containers locally and suggests some fixes.</span></span>

### <a name="stopping-docker-containers"></a><span data-ttu-id="50237-189">Docker 컨테이너 중지</span><span class="sxs-lookup"><span data-stu-id="50237-189">Stopping Docker containers</span></span> 

<span data-ttu-id="50237-190">컨테이너화된 응용 프로그램을 시작한 후 디버깅을 중지했음에도 컨테이너가 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="50237-190">After you launch the containerized application, the containers continue to run, even after you have stopped debugging.</span></span> <span data-ttu-id="50237-191">명령줄에서 docker ps 명령을 실행하여 실행 중인 컨테이너를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-191">You can run the docker ps command from the command line to see which containers are running.</span></span> <span data-ttu-id="50237-192">그림 6-2에 표시된 것처럼 docker stop 명령은 실행 중인 컨테이너를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-192">The docker stop command stops a running container, as shown in Figure 6-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="50237-193">**그림 6-2**.</span><span class="sxs-lookup"><span data-stu-id="50237-193">**Figure 6-2**.</span></span> <span data-ttu-id="50237-194">docker ps 및 docker stop CLI 명령을 사용하여 컨테이너 목록 표시 및 중지</span><span class="sxs-lookup"><span data-stu-id="50237-194">Listing and stopping containers with the docker ps and docker stop CLI commands</span></span>

<span data-ttu-id="50237-195">서로 다른 구성 간에 전환할 때는 실행 중인 프로세스를 중지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-195">You might need to stop running processes when you switch between different configurations.</span></span> <span data-ttu-id="50237-196">그러지 않으면 웹 응용 프로그램을 실행 중인 컨테이너에서 응용 프로그램에 대한 포트(이 예에서는 5106)를 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-196">Otherwise, the container that is running the web application is using the port for your application (5106 in this example).</span></span>

### <a name="adding-docker-to-your-projects"></a><span data-ttu-id="50237-197">프로젝트에 Docker 추가</span><span class="sxs-lookup"><span data-stu-id="50237-197">Adding Docker to your projects</span></span>

<span data-ttu-id="50237-198">Docker 지원을 추가하는 마법사는 실행 중인 Docker 프로세스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-198">The wizard that adds Docker support communicates with the running Docker process.</span></span> <span data-ttu-id="50237-199">마법사를 시작할 때 Docker가 실행되고 있지 않은 경우 마법사가 올바르게 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50237-199">The wizard will not run correctly if Docker is not running when you start the wizard.</span></span> <span data-ttu-id="50237-200">또한 마법사는 올바른 Docker 지원을 추가하기 위해 현재 선택한 컨테이너를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-200">In addition, the wizard examines your current container choice to add the correct Docker support.</span></span> <span data-ttu-id="50237-201">Windows 컨테이너에 대한 지원을 추가하려는 경우 구성된 Windows 컨테이너를 통해 Docker가 실행되는 동안 마법사를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-201">If you want to add support for Windows Containers, you need to run the wizard while you have Docker running with Windows Containers configured.</span></span> <span data-ttu-id="50237-202">Linux 컨테이너에 대한 지원을 추가하려는 경우 구성된 Linux 컨테이너를 통해 Docker가 실행되는 동안 마법사를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50237-202">If you want to add support for Linux containers, run the wizard while you have Docker running with Linux containers configured.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="50237-203">[이전] (../docker-application-development-process/docker-app-development-workflow.md) [다음] (../containerize-net-framework-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="50237-203">[Previous] (../docker-application-development-process/docker-app-development-workflow.md) [Next] (../containerize-net-framework-applications/index.md)</span></span>
