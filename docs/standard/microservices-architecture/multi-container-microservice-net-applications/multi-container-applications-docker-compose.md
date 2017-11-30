---
title: "Docker compose.yml로 다중 컨테이너 응용 프로그램 정의"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker compose.yml로 다중 컨테이너 응용 프로그램 정의"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="635ac-104">Docker compose.yml로 다중 컨테이너 응용 프로그램 정의</span><span class="sxs-lookup"><span data-stu-id="635ac-104">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="635ac-105">이 가이드에는 [docker compose.yml](https://docs.docker.com/compose/compose-file/) 파일 섹션에 도입 된 [4 단계. 다중 컨테이너 Docker 응용 프로그램을 빌드할 때 docker compose.yml 서비스 정의](#step4_define_svcs_in_docker_compose_yml)합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-105">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="635ac-106">그러나 더 자세히 살펴볼 있는 docker-compose 파일을 사용 하는 다른 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-106">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="635ac-107">예를 들어 docker compose.yml 파일에 여러 컨테이너 응용 프로그램을 배포 하려는 방법을 명시적으로 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-107">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="635ac-108">필요에 따라 사용자 지정 Docker 이미지를 작성 하는 방법을 설명할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-108">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="635ac-109">(사용자 지정 Docker 이미지 수 Docker CLI를 사용 하 여 빌드한도)입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-109">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="635ac-110">기본적으로, 각에 배포 하려면 컨테이너와 각 컨테이너 배포에 대 한 특정 특성 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-110">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="635ac-111">다중 컨테이너 배포 설명 파일을 사용 하는 후에 의해 오케스트레이션에서는 단일 작업에서 전체 솔루션을 배포할 수 있습니다는 [를 docker 작성](https://docs.docker.com/compose/overview/) CLI 명령 또는 있습니다에서 배포할 수 투명 하 게 Visual Studio입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-111">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="635ac-112">그렇지 않은 경우 명령을 실행 하 여 명령줄에서 docker를 사용 하 여 여러 단계에서 컨테이너에서 컨테이너를 배포 하는 Docker CLI를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-112">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="635ac-113">Docker compose.yml에 정의 된 각 서비스 정확히 하나의 이미지를 지정 하거나 작성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-113">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="635ac-114">다른 키, 사항이 며 해당 docker 실행 명령줄 함수와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-114">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="635ac-115">다음 YAML 코드 eShopOnContainers 샘플에 대 한 가능한 글로벌 하지만 단일 docker-compose.yml 파일의 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-115">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="635ac-116">EShopOnContainers에서 실제 docker-compose 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-116">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="635ac-117">가장 하지 않는 단일 파일로 통합된 단순화 된 버전 대신 작업할 docker-구성 파일을 나중에 설명 하겠지만 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-117">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

<span data-ttu-id="635ac-118">이 파일에 있는 루트 키에는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-118">The root key in this file is services.</span></span> <span data-ttu-id="635ac-119">해당 키 하에서 배포 하 고 실행할 때 실행 하려는 서비스를 정의 명령 또는이 docker compose.yml 파일을 사용 하 여 Visual Studio에서 배포할 경우 docker 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-119">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="635ac-120">이 경우 docker compose.yml 파일에는 다음 목록에 설명 된 대로 여러 서비스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-120">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="635ac-121">서버 쪽 C에서 microservices를 사용해 ASP.NET Core MVC 응용 프로그램을 포함 하 여 컨테이너 webmvc\#</span><span class="sxs-lookup"><span data-stu-id="635ac-121">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="635ac-122">catalog.api 카탈로그 ASP.NET Core 웹 API 마이크로 서비스를 포함 하 여 컨테이너</span><span class="sxs-lookup"><span data-stu-id="635ac-122">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="635ac-123">ASP.NET Core 웹 API 순서 마이크로 서비스를 포함 하 여 컨테이너 ordering.api</span><span class="sxs-lookup"><span data-stu-id="635ac-123">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="635ac-124">sql.data microservices 데이터베이스를 보유 하는 Linux 용 SQL Server를 실행 중인 컨테이너</span><span class="sxs-lookup"><span data-stu-id="635ac-124">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="635ac-125">ASP.NET Core 웹 API 바구니 마이크로 서비스와 basket.api 컨테이너</span><span class="sxs-lookup"><span data-stu-id="635ac-125">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="635ac-126">basket.data는 REDIS 캐시 바구니 데이터베이스와 함께 REDIS 캐시 서비스를 실행 중인 컨테이너</span><span class="sxs-lookup"><span data-stu-id="635ac-126">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="635ac-127">간단한 웹 서비스 API 컨테이너</span><span class="sxs-lookup"><span data-stu-id="635ac-127">A simple Web Service API container</span></span>

<span data-ttu-id="635ac-128">Catalog.api 컨테이너 마이크로 서비스 정의가 간단 하 게 하나의 컨테이너에 집중 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-128">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

<span data-ttu-id="635ac-129">이 컨테이너 화 된 서비스에는 다음과 같은 기본 구성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-129">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="635ac-130">사용자 지정 eshop/catalog.api 이미지는 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-130">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="635ac-131">단순성을에 대 한 빌드가 없는: 키 파일에서 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-131">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="635ac-132">즉, 이미지 이전에 빌드되 었어야 (docker 빌드와) 또는 모든 Docker 레지스트리에서 (명령을 사용 하 여 docker pull) 다운로드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-132">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="635ac-133">카탈로그 데이터 모델이 포함 된 SQL Server 인스턴스에 액세스 하기 위해 Entity Framework에서 사용할 연결 문자열로 ConnectionString 라는 환경 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-133">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="635ac-134">이 경우 동일한 SQL Server 컨테이너는 여러 데이터베이스를 보유 중인 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-134">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="635ac-135">따라서, Docker에 대 한 개발 컴퓨터에 메모리를 더 적게 필요.</span><span class="sxs-lookup"><span data-stu-id="635ac-135">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="635ac-136">그러나 각 마이크로 서비스 데이터베이스에 대 한 SQL Server 컨테이너를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-136">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="635ac-137">SQL Server 이름은 sql.data,이 Linux 용 SQL Server 인스턴스를 실행 하는 컨테이너에 사용 되는 동일한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-137">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="635ac-138">이 방법은 편리 합니다. 이 이름 확인 (내부 Docker 호스트에)를 사용할 수 있으므로 다른 컨테이너에서 액세스 하는 컨테이너에 대 한 내부 IP에 알아야 않아도 네트워크 주소를 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-138">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="635ac-139">연결 문자열은 환경 변수를 정의 하기 때문에 다른 메커니즘을 통해 및 다른 시간에 해당 변수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-139">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="635ac-140">예를 들어 최종 호스트 또는 VSTS 또는 기본 DevOps 시스템에서 CI/CD 파이프라인에서 수행 하 여 프로덕션 환경에 배포 하는 경우 다른 연결 문자열로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-140">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="635ac-141">Docker 호스트 내에서 catalog.api 서비스에 내부 액세스에 대 한 포트 80을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-141">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="635ac-142">호스트는 현재 Linux VM Linux 용 Docker 이미지에 기반 하는 있지만 Windows 이미지에서을 실행 하려면 컨테이너를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-142">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="635ac-143">노출 된 포트 80: 컨테이너 포트 5101 Docker 호스트 컴퓨터 (Linux VM)에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-143">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="635ac-144">웹 서비스 sql.data 서비스 (컨테이너에서 실행 되는 Linux 데이터베이스에 대 한 SQL Server 인스턴스)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-144">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="635ac-145">이 종속성을 지정 하면 catalog.api 컨테이너 시작 sql.data 컨테이너가 이미 시작 했습니다. 이것이 catalog.api SQL Server 데이터베이스가지고 있어야 하기 때문에 중요 하 고 실행 중인 먼저입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-145">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="635ac-146">그러나 이러한 종류의 컨테이너 종속성 충분 하지 않습니다 대부분의 경우에서 Docker 컨테이너 수준에만 확인 하기 때문에.</span><span class="sxs-lookup"><span data-stu-id="635ac-146">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="635ac-147">경우에 따라 (이 경우 SQL Server)에서 서비스 아닐 수 있습니다 여전히 준비 되므로 클라이언트 microservices에 지 수 백오프와 재시도 논리를 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-147">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="635ac-148">이런 방식으로 종속성 컨테이너 짧은 시간에 대 한 준비 되지 않은 경우 응용 프로그램 계속 됩니다 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-148">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="635ac-149">외부 서버에 대 한 액세스를 허용 하도록 구성 된: 추가\_설정 하는 호스트를 사용 하면 외부 서버 또는 Docker 호스트 외부의 컴퓨터에 액세스할 수 있습니다 (즉, 호스트 되는 개발 Docker는 Linux VM의 기본 외부) 로컬 SQL 등 개발 PC에 대 한 서버 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-149">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="635ac-150">다음과 같은 작용이 다음 섹션에 있는 다른, 더 많은 고급 docker compose.yml 설정도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-150">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="635ac-151">사용 하 여 docker-구성 파일을 여러 환경</span><span class="sxs-lookup"><span data-stu-id="635ac-151">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="635ac-152">Docker compose.yml 파일 정의 파일 및 해당 형식을 이해 하는 여러 인프라에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-152">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="635ac-153">가장 간단한 도구는 docker-명령을 작성 하지만 (예를 들어 docker는 Docker Swarm) orchestrators 또한 이해 하 고 해당 파일 같은 다른 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-153">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="635ac-154">따라서 사용 하 여는 docker-명령을 작성 하는 다음과 같은 주요 시나리오를 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-154">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="635ac-155">개발 환경</span><span class="sxs-lookup"><span data-stu-id="635ac-155">Development environments</span></span>

<span data-ttu-id="635ac-156">응용 프로그램을 개발 하는 경우에 격리 된 개발 환경에서 응용 프로그램을 실행할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-156">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="635ac-157">사용할 수는 CLI 명령을 사용 하 여 docker-작성 내부적는 Visual Studio를 사용 하거나 해당 환경을 만들 docker-작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-157">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="635ac-158">Docker compose.yml 파일을 사용 하면 구성 하 고 모든 응용 프로그램의 서비스 종속성 (다른 서비스, 캐시, 데이터베이스, 큐 등)를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-158">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="635ac-159">사용 하는 CLI 명령으로 docker 구성, 만들기 및 단일 명령으로 각 종속성에 대 한 하나 이상의 컨테이너를 시작할 수 있습니다 (docker-작성 위로).</span><span class="sxs-lookup"><span data-stu-id="635ac-159">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="635ac-160">Docker compose.yml 파일 Docker 엔진에서 해석 하는 구성 파일에는 있지만 다중 컨테이너 응용 프로그램의 구성에 대 한 편리한 문서 파일 역할도 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-160">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="635ac-161">테스트 환경</span><span class="sxs-lookup"><span data-stu-id="635ac-161">Testing environments</span></span>

<span data-ttu-id="635ac-162">연속 배포 (CD) 또는 CI (연속 통합) 프로세스의 중요 한 부분이 단위 테스트 및 통합 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-162">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="635ac-163">이러한 자동화 된 테스트 사용자나 응용 프로그램의 데이터 변경에 영향을 받지 않습니다 되므로 격리 된 환경을 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-163">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="635ac-164">Docker Compose를 통한 만들어 하는 명령 프롬프트 또는 다음 명령과 같은 스크립트에서 몇 가지 명령에서 매우 쉽게 해당 격리 된 환경을 삭제:</span><span class="sxs-lookup"><span data-stu-id="635ac-164">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="635ac-165">프로덕션 배포</span><span class="sxs-lookup"><span data-stu-id="635ac-165">Production deployments</span></span>

<span data-ttu-id="635ac-166">원격 Docker 엔진에 배포할 Compose를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-166">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="635ac-167">단일 Docker 호스트 인스턴스를 배포 하는 일반적인 경우 (프로덕션 VM 또는로 프로 비전 하는 서버와 같은 [Docker 컴퓨터](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="635ac-167">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="635ac-168">전체 일 수도 있지만 [docker는 Docker Swarm](https://docs.docker.com/swarm/overview/) 클러스터 docker compose.yml 파일과 호환도 포함 되므로 클러스터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-168">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="635ac-169">(Azure 서비스 패브릭, Mesos DC/OS, Kubernetes, 등) 다른 orchestrator를 사용 하는 경우에 docker-compose.yml 있지만 다른 orchestrator 데이터 원본에는 것과 같은 설정 및 메타 데이터 구성 설정을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-169">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="635ac-170">어떤 경우 든, docker 작성은 개발, 테스트 및 프로덕션 워크플로에 대 한 편리한 도구 및 메타 데이터 형식 이지만 프로덕션 워크플로 사용 하는 orchestrator에서 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-170">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="635ac-171">여러 사용 하 여 docker-구성에 여러 환경을 처리 하는 파일</span><span class="sxs-lookup"><span data-stu-id="635ac-171">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="635ac-172">다양 한 환경을 대상으로 지정 하는 경우에 여러 사용 해야 파일을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-172">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="635ac-173">이 환경에 따라 여러 구성 variant를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-173">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="635ac-174">기본 docker-compose 파일 재정의</span><span class="sxs-lookup"><span data-stu-id="635ac-174">Overriding the base docker-compose file</span></span>

<span data-ttu-id="635ac-175">이전 섹션에 표시 된 간소화 된 예제와 같이 단일 docker compose.yml 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-175">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="635ac-176">대부분의 응용 프로그램에 대 한 좋지은입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-176">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="635ac-177">기본적으로 선택적 docker compose.override.yml 파일, 두 개의 파일 및 docker-compose.yml Compose를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-177">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="635ac-178">표시 된 대로 그림 8-11의 Visual Studio를 사용 하는 고 Docker 지원을 사용 하도록 설정, Visual Studio도 만듭니다 해당 파일 및 디버깅을 위해 사용 되는 몇 가지 추가 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-178">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates those files plus some additional files used for debugging.</span></span>

![](./media/image12.png)

<span data-ttu-id="635ac-179">**그림 8-11**합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-179">**Figure 8-11**.</span></span> <span data-ttu-id="635ac-180">docker 구성 파일에서 Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="635ac-180">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="635ac-181">Visual Studio Code 또는 Sublime와 같은 편집기 docker-compose 파일을 편집 하 고 응용 프로그램을 실행할 수 있습니다는 docker 구성 최대 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-181">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="635ac-182">규칙에 따라 docker compose.yml 파일 하면 기본 구성 및 기타 정적 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-182">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="635ac-183">즉, 대상으로 하는 배포 환경에 따라 서비스 구성을 변경 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-183">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="635ac-184">Docker compose.override.yml 파일 이름에서 알 수 있듯이 배포 환경에 따라 달라 지는 구성과 같은 기본 구성을 재정의 하는 구성 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-184">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="635ac-185">또한 서로 다른 이름 가진 여러 재정의 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-185">You can have multiple override files with different names also.</span></span> <span data-ttu-id="635ac-186">재정의 파일에는 일반적으로 응용 프로그램 이지만 특정 환경에 또는 배포에 필요한 추가 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-186">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="635ac-187">여러 환경 대상 지정</span><span class="sxs-lookup"><span data-stu-id="635ac-187">Targeting multiple environments</span></span>

<span data-ttu-id="635ac-188">일반적인 사용 사례는 여러 정의 하는 경우 구성 파일 준비 CI 또는 개발 프로덕션 환경 같은 여러 환경을 대상 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-188">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="635ac-189">그림 8-12에 나와 있는 것 처럼 이러한 차이 지원 하려면 여러 파일로 작성할 구성을 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-189">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="635ac-190">**그림 8-12**합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-190">**Figure 8-12**.</span></span> <span data-ttu-id="635ac-191">기본 docker compose.yml 파일의 값을 재정의 하는 파일 다중 docker-구성</span><span class="sxs-lookup"><span data-stu-id="635ac-191">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="635ac-192">기본 docker compose.yml 파일과 함께 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-192">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="635ac-193">이 기본 파일 환경에 따라 변경 되지 않는 기본 또는 정적 구성 설정을 포함 하는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-193">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="635ac-194">예를 들어는 eShopOnContainers 기본 파일 자기 다음 docker compose.yml 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-194">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

<span data-ttu-id="635ac-195">다른 대상 배포 환경으로 인해 기본 docker compose.yml 파일의 값을 변경 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="635ac-195">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="635ac-196">Webmvc 서비스 정의에 집중 하는 경우 예를 들어, 볼 수 있습니다 어떻게 해당 정보는 훨씬는 없이 동일한 환경을 대상으로 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-196">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="635ac-197">다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-197">You have the following information:</span></span>

-   <span data-ttu-id="635ac-198">서비스 이름: webmvc 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-198">The service name: webmvc.</span></span>

-   <span data-ttu-id="635ac-199">컨테이너의 사용자 지정 이미지: eshop/webmvc 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-199">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="635ac-200">사용 하는 Dockerfile을 나타내는 사용자 지정 Docker 이미지를 빌드하려면 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-200">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="635ac-201">이 컨테이너에는 다른 종속성 컨테이너 시작 될 때까지 시작 되지 않으면 하므로 다른 서비스에 대 한 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-201">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="635ac-202">추가 구성 않았지만 중요 한 점은 기본 docker compose.yml 파일에만 되도록 환경에 공통 되는 정보를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-202">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="635ac-203">그런 다음 docker compose.override.yml 또는 프로덕션 또는 스테이징 환경에 대 한 유사한 파일에서 각 환경에 대해 관련 된 구성을 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-203">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="635ac-204">일반적으로 docker compose.override.yml eShopOnContainers에서 다음 예제와 같이 개발 환경에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-204">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="635ac-205">이 예제에서는 개발 구성을 재정의 일부 포트를 호스트, 노출 된 환경 변수를 정의 Url 리디렉션 및 개발 환경에 대 한 연결 문자열을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-205">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="635ac-206">이러한 설정은 모두에 대 한 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-206">These settings are all just for the development environment.</span></span>

<span data-ttu-id="635ac-207">실행 하는 경우를 docker 구성 (또는 Visual Studio에서 시작) 명령은 재정의 자동으로 두 파일을 병합 했습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-207">When you run docker-compose up (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="635ac-208">다른 구성 값으로 프로덕션 환경에 대 한 다른 작성 파일 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-208">Suppose that you want another Compose file for the production environment, with different configuration values.</span></span> <span data-ttu-id="635ac-209">다음과 같은 다른 재정의 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-209">You can create another override file, like the following.</span></span> <span data-ttu-id="635ac-210">(이 파일 수 수 다른 Git 리포지토리에 저장 또는 관리 되는 및 다른 팀으로 보호 합니다.)</span><span class="sxs-lookup"><span data-stu-id="635ac-210">(This file might be stored in a different Git repo or managed and secured by a different team.)</span></span>

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="635ac-211">특정 재정의 파일과 함께 배포 하는 방법</span><span class="sxs-lookup"><span data-stu-id="635ac-211">How to deploy with a specific override file</span></span>

<span data-ttu-id="635ac-212">여러 재정의 파일 또는 재정의 파일을 다른 이름으로을 사용 하려면 사용 하 여-f 옵션을 사용할 수 있습니다는 docker 명령을 작성 하 고 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-212">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="635ac-213">명령줄에 지정 된 순서로 병합 파일을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-213">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="635ac-214">다음 예제에서는 재정의 파일과 함께 배포 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-214">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="635ac-215">환경 변수를 사용 하 여 docker-작성의 파일</span><span class="sxs-lookup"><span data-stu-id="635ac-215">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="635ac-216">것이 특히 이전 예제에 나와 있는 처럼 환경 변수에서 구성 정보를 얻을 수 있게 되기를 프로덕션 환경에서에서 편리 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-216">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="635ac-217">구문을 사용 하 여 docker-compose 파일에서 환경 변수를 참조할 \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="635ac-217">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="635ac-218">Docker compose.prod.yml 파일에서 다음 줄에서는 환경 변수의 값을 참조 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-218">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="635ac-219">환경 변수에서 생성 되 고 호스트 환경에 따라 다양 한 방법으로 초기화 (Linux, Windows, 클라우드 클러스터 등.).</span><span class="sxs-lookup"><span data-stu-id="635ac-219">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="635ac-220">그러나.env 파일을 사용 하는 편리한 방법이입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-220">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="635ac-221">Docker-compose 파일의.env 파일에 있는 기본 환경 변수 선언을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-221">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="635ac-222">환경 변수에 대 한 이러한 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-222">These values for the environment variables are the default values.</span></span> <span data-ttu-id="635ac-223">하지만 각 사용자의 환경 (호스트 OS 또는 클러스터에서 환경 변수)에 정의할 수 값으로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-223">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="635ac-224">폴더에이.env 파일을 배치할 위치는 docker 구성에서 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-224">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="635ac-225">다음 예제에서는 마찬가지로.env 파일은 [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) eShopOnContainers 응용 프로그램에 대 한 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-225">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="635ac-226">형식에 포함 되도록.env 파일에서 각 줄에서는 docker 작성 &lt;변수&gt;=&lt;값&gt;합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-226">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="635ac-227">참고 항상 런타임 환경에 설정 된 값.env 파일 내에 정의 된 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-227">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="635ac-228">비슷한 방식으로 명령줄 명령 인수를 통해 전달 된 값도.env 파일에 설정 된 기본값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-228">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="635ac-229">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="635ac-229">Additional resources</span></span>

-   <span data-ttu-id="635ac-230">**Docker 간략하게 작성**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="635ac-230">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="635ac-231">**여러 Compose 파일**
    [*https://docs.docker.com/compose/extends/\#여러 구성 파일*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="635ac-231">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="635ac-232">최적화 된 ASP.NET Core Docker 이미지 작성</span><span class="sxs-lookup"><span data-stu-id="635ac-232">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="635ac-233">Docker 및.NET Core 탐색 하 인터넷에서 원본에는, 소스 컨테이너에 복사 하 여 Docker 이미지를 작성 하는 것이 간단한 방법을 보여 주는 Dockerfile를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-233">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="635ac-234">이러한 예제는 간단한 구성을 사용 하 여 있습니다는 Docker 이미지를 응용 프로그램과 함께 패키지 환경과 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-234">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="635ac-235">다음 예제에서는이 상황에서 간단한 Dockerfile을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-235">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="635ac-236">Dockerfile 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-236">A Dockerfile like this will work.</span></span> <span data-ttu-id="635ac-237">그러나 이미지, 특히 프로덕션 이미지 실질적으로 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-237">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="635ac-238">컨테이너 및 microservices 모델에서 컨테이너는 지속적으로 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-238">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="635ac-239">컨테이너를 사용 하는 일반적인 방법은 컨테이너를 삭제 하기 때문에 절전 모드는 컨테이너를 다시 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-239">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="635ac-240">Orchestrators (예: docker는 Docker Swarm, Kubernetes, DCOS 또는 Azure 서비스 패브릭)는 단순히 이미지의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-240">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="635ac-241">따라서 인스턴스화 프로세스는 속도가 더 빠를 수 있도록 작성 되는 응용 프로그램을 컴파일하여 최적화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-241">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="635ac-242">컨테이너 시작 될 때 실행할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-242">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="635ac-243">복원 및 런타임에 컴파일할 해야, dotnet를 사용 하 여 복원 및 dotnet 빌드 dotnet CLI 명령을.NET Core 및 Docker에 대 한 다양 한 블로그 게시물에 나와 있는 것 처럼입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-243">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="635ac-244">.NET 팀.NET Core 및 ASP.NET Core 컨테이너 액세스에 최적화 된 프레임 워크 있도록 중요 한 작업을 수행 하 되었습니다 했습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-244">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="635ac-245">뿐만 아니라.NET Core는 작은 메모리 사용 공간; 간단한 프레임 워크 인가요 팀에 시작 성능에 집중 하 고 같은 일부 최적화 된 Docker 이미지를 생성는 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 이미지에서 사용 가능한 [Docker 허브](https://hub.docker.com/r/microsoft/aspnetcore/), 일반적인에 비하면 [ microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) 또는 [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-245">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="635ac-246">[microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 이미지 aspnetcore의 자동 설정이 제공\_url 포트 80 및 어셈블리; pre ngend 캐시에 빠른 시작에서 이러한 설정은 둘 다가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-246">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="635ac-247">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="635ac-247">Additional resources</span></span>

-   <span data-ttu-id="635ac-248">**ASP.NET Core를 사용 하 여 Docker 이미지 구성에 최적화 된**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="635ac-248">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="635ac-249">빌드 (CI) 컨테이너에서 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="635ac-249">Building the application from a build (CI) container</span></span>

<span data-ttu-id="635ac-250">Docker의 다른 이점은 되므로 빌드 컴퓨터 또는 응용 프로그램을 빌드하는 VM을 만들 필요가 그림 8-13에 표시 된 것 처럼 미리 구성 된 컨테이너에서 응용 프로그램을 만들 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-250">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="635ac-251">사용 하거나 개발 컴퓨터에서 실행 하 여 해당 빌드 컨테이너를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-251">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="635ac-252">하지만 훨씬 더 흥미로운 것 CI (연속 통합) 파이프라인에서 동일한 빌드 컨테이너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-252">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="635ac-253">**그림 8-13**합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-253">**Figure 8-13**.</span></span> <span data-ttu-id="635ac-254">컨테이너에서.NET 비트를 구축 하는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="635ac-254">Components building .NET bits from a container</span></span>

<span data-ttu-id="635ac-255">이 시나리오에 대 한 제공는 [microsoft/aspnetcore 빌드](https://hub.docker.com/r/microsoft/aspnetcore-build/) 컴파일 및 ASP.NET Core 응용 프로그램을 작성 하는 데 사용할 수 있는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-255">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="635ac-256">출력에 따라 이미지에 배치 됩니다는 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 이미지 설명한 것 처럼 런타임 최적화 된 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-256">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="635ac-257">.NET Core, ASP.NET SDK, npm ASP.NET Core 응용 프로그램을 컴파일하는 데 필요한 모든 aspnetcore 빌드 이미지 포함 Gulp, Bower, 등입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-257">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="635ac-258">이러한 종속성 빌드 시에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-258">We need these dependencies at build time.</span></span> <span data-ttu-id="635ac-259">하지만 म 원하지 않는 응용 프로그램과 함께 이러한 런타임 시 수행할 수 없게 되므로 이미지 불필요 하 게 큰 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-259">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="635ac-260">응용 프로그램을 빌드할 수 eShopOnContainers 응용 프로그램에서 바로 실행 하 여 컨테이너에서 다음 docker-명령을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-260">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="635ac-261">그림 8-14이이 명령은 명령줄에서 실행을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-261">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="635ac-262">**그림 8-14입니다.**</span><span class="sxs-lookup"><span data-stu-id="635ac-262">**Figure 8-14.**</span></span> <span data-ttu-id="635ac-263">컨테이너에서.NET 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="635ac-263">Building your .NET application from a container</span></span>

<span data-ttu-id="635ac-264">실행 중인 컨테이너 ci 빌드를 볼 수 있듯이\_1 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-264">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="635ac-265">이 기반 aspnetcore 빌드 이미지 컴파일하고 PC에서 대신 해당 컨테이너 내에서 전체 응용 프로그램을 빌드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-265">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="635ac-266">즉 이유 현실에서 구축 되며 Linux에서.NET Core 프로젝트 컴파일-기본 Docker Linux 호스트에서 실행 되 고 해당 컨테이너 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-266">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="635ac-267">[docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) 다음 코드를 포함 하는 해당 이미지 (eShopOnContainers의 일부)에 대 한 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-267">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="635ac-268">빌드 컨테이너 사용 시작 됨을 확인할 수 있습니다는 [microsoft/aspnetcore 빌드](https://hub.docker.com/r/microsoft/aspnetcore-build/) 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-268">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* <span data-ttu-id="635ac-269">부터는 **.NET Core 2.0**, `dotnet restore` 명령이 자동으로 실행 때는 `dotnet publish` 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-269">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="635ac-270">빌드 컨테이너에 실행 되 면.NET SDK dotnet 복원 실행 되 고 dotnet.NET 비트 컴파일하려면 솔루션의 모든 프로젝트에 대해 명령을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-270">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="635ac-271">이 경우 eShopOnContainers 클라이언트 코드에 대 한 TypeScript 및 각에 따라는 SPA도 있어서 것도 확인 해야 npm와의 종속성을 JavaScript.NET 비트와 관련이 없는 작업 이지만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-271">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="635ac-272">dotnet 명령 빌드를 게시 하 고 각 프로젝트의 폴더 내에서 컴파일된 출력 게시 된... 그림 8-15에 나와 있는 것 처럼 /obj/Docker/publish 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-272">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="635ac-273">**그림 8-15입니다.**</span><span class="sxs-lookup"><span data-stu-id="635ac-273">**Figure 8-15.**</span></span> <span data-ttu-id="635ac-274">dotnet에서 생성 한 이진 파일 명령 게시</span><span class="sxs-lookup"><span data-stu-id="635ac-274">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="635ac-275">CLI에서 Docker 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="635ac-275">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="635ac-276">응용 프로그램 출력 (각 프로젝트) 내에서 관련된 폴더에 게시 되 면 다음 단계에서는 실제로 Docker 이미지를 작성 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-276">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="635ac-277">이 위해 docker-compose 빌드 사용 및 docker-작성 명령을 그림 8-16에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-277">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="635ac-278">**그림 8-16입니다.**</span><span class="sxs-lookup"><span data-stu-id="635ac-278">**Figure 8-16.**</span></span> <span data-ttu-id="635ac-279">Docker 이미지를 작성 하 고 사용 하는 컨테이너를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-279">Building Docker images and running the containers</span></span>

<span data-ttu-id="635ac-280">그림 8-17에서는 docker-compose 명령 실행을 구축 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-280">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="635ac-281">**그림 8-17**합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-281">**Figure 8-17**.</span></span> <span data-ttu-id="635ac-282">Docker 이미지는 docker가 있는 빌드-빌드 명령을 작성</span><span class="sxs-lookup"><span data-stu-id="635ac-282">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="635ac-283">차이 docker-compose 빌드하고를 docker 구성 명령을 모두 빌드 및 시작 되는 이미지를 docker 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-283">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="635ac-284">Visual Studio를 사용 하 여 이러한 모든 단계 내부적 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-284">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="635ac-285">Visual Studio.NET 응용 프로그램을 컴파일하는 Docker 이미지를 만들고 컨테이너 Docker 호스트에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-285">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="635ac-286">Visual Studio는 Visual Studio에서 직접 docker에서 실행 하 여 컨테이너를 디버그 하는 기능과 같은 추가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-286">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="635ac-287">여기서는 전반적인 takeway CI/CD 파이프라인 구축 해야 방식으로 동일한 응용 프로그램을 만들 수 있다는 것-로컬 컴퓨터에서 아닌 컨테이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-287">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="635ac-288">만든 이미지, 되 고 나면 다음 하기만 하면 docker를 사용 하 여 Docker 이미지를 실행 하려면-명령을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="635ac-288">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="635ac-289">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="635ac-289">Additional resources</span></span>

-   <span data-ttu-id="635ac-290">**컨테이너의 비트를 구축: Windows CLI 환경 (dotnet CLI Docker CLI 및 VS Code)에서 eShopOnContainers 솔루션 설정**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="635ac-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="635ac-291">[이전] (데이터-구동-crud-microservice.md) [다음] (데이터베이스 서버 container.md)</span><span class="sxs-lookup"><span data-stu-id="635ac-291">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
