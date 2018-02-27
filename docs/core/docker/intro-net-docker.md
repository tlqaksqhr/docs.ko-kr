---
title: ".NET 및 Docker 소개"
description: "Docker 및 .NET Core 이해"
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
ms.workload:
- dotnetcore
ms.openlocfilehash: dabc7c0c4a0afab8edf7d2bab410bb9635821936
ms.sourcegitcommit: 75a180acb5d8a2dbd4a52915ce8e980749fb1d05
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2018
---
# <a name="introduction-to-net-and-docker"></a>.NET 및 Docker 소개

이 문서에서는 Docker에서의 .NET 작업을 소개하고 관련 개념적 배경을 제공합니다.

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: 앱을 패키지하여 어디서나 배포 및 실행

[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md)는 개발자 및 관리자가 [컨테이너](https://www.docker.com/what-container)라는 느슨하게 격리된 환경에서 [이미지](https://docs.docker.com/glossary/?term=image)를 빌드하고, 분산 응용 프로그램을 제공 및 실행할 수 있게 해주는 개방형 플랫폼입니다. 이 접근 방식을 통해 개발, QA 및 프로덕션 환경 간에 효율적으로 응용 프로그램 수명 주기를 관리할 수 있습니다.
 
[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform)에서는 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine)을 사용하여 신속하게 앱을 만들고 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 형식으로 작성된 다음 [계층화된 컨테이너](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)에서 배포 및 실행되는 파일을 사용하여 만들어진 [Docker 이미지](https://docs.docker.com/glossary/?term=image)로 패키지합니다.

고유한 [계층화된 이미지](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)를 dockerfile로 만들거나 [레지스트리](https://docs.docker.com/glossary/?term=registry)의 기존 dockerfile(예: [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub))을 사용할 수 있습니다.

[Docker 컨테이너, 이미지 및 레지스트리 간의 관계](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md)는 [컨테이너화된 응용 프로그램이나 마이크로 서비스를 설계 및 빌드](../../standard/microservices-architecture/architect-microservice-container-applications/index.md)할 때 중요한 개념입니다. 이 접근 방식은 개발과 배포 간의 시간을 크게 줄여 줍니다.

### <a name="further-reading-and-watching"></a>추가 읽기(및 보기) 정보

* [Windows-based containers: Modern app development with enterprise-grade control](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)(Windows 기반 컨테이너: 엔터프라이즈급 제어 기능을 통한 최신 앱 개발)
* [Docker overview](https://docs.docker.com/engine/docker-overview/)(Docker 개요)
* [Windows 컨테이너의 Dockerfile](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)(Dockerfile 작성에 대한 모범 사례)
* [.NET Core 응용 프로그램에 대한 Docker 이미지 작성](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>.NET Docker 이미지 가져오기

공식 .NET Docker 이미지는 Microsoft에서 만들고 최적화합니다. 이러한 이미지는 Docker Hub의 Microsoft 리포지토리에서 공개적으로 사용할 수 있습니다. 각 리포지토리에는 .NET 버전 및 OS 버전에 따라 여러 이미지가 포함될 수 있습니다. 이미지 리포지토리 대부분은 특정 프레임워크 버전과 OS(Linux 배포 또는 Windows 버전)를 모두 선택하는 데 도움이 되는 광범위한 태그 지정을 제공합니다.

## <a name="scenario-based-guidance"></a>시나리오 기반 지침

.NET 리포지토리에 대한 Microsoft의 의도는 특정 시나리오나 워크로드를 나타내는 세분화되고 집중된 리포지토리를 제공하는 것입니다.

`microsoft/aspnetcore` 이미지는 Docker의 ASP.NET Core 앱에 최적화되어 있으므로 컨테이너를 빠르게 시작할 수 있습니다.

.NET Core 이미지(`microsoft/dotnet`)는 .NET Core를 기반으로 하는 콘솔 앱을 위한 것입니다. 예를 들어 일괄 처리 프로세스, Azure WebJobs 및 기타 콘솔 시나리오는 최적화된 .NET Core 이미지를 사용해야 합니다.

Docker 및 .NET 응용 프로그램 사용에 대한 가장 명확한 수평적 시나리오는 프로덕션 배포 및 호스팅에 대한 것입니다. 프로덕션은 한 가지 시나리오일 뿐이며, 다른 시나리오도 동일하게 유용한 것으로 판명되었습니다. 이러한 시나리오는 .NET에만 국한된 것이 아니라, 대부분의 개발자 플랫폼에 적용됩니다.

* **저마찰 설치** - 로컬 설치 없이 .NET을 사용해 볼 수 있습니다. .NET이 포함된 Docker 이미지를 다운로드하기만 하면 됩니다.

* **컨테이너에서 개발** - 일관된 환경에서 개발하여 개발 환경과 프로덕션 환경을 유사하게 만들 수 있습니다(개발자 컴퓨터의 전역 상태와 같은 문제 방지). Visual Studio Tools for Docker를 통해 Visual Studio에서 직접 컨테이너를 시작할 수도 있습니다.

* **컨테이너에서 테스트** - 컨테이너에서 테스트하여 잘못 구성된 환경이나 마지막 테스트에서 남겨진 기타 변경 내용으로 인한 실패를 줄일 수 있습니다.

* **컨테이너에서 빌드** - 컨테이너에서 코드를 빌드하여 여러 환경에 대해 공유 빌드 컴퓨터를 올바르게 구성할 필요 없이, 대신 “BYOC”(Bring Your Own Container) 접근 방식으로 넘어갈 수 있습니다.

* **모든 환경에서 배포** - 모든 환경을 통해 이미지를 배포할 수 있습니다. 이 접근 방식을 사용하면 구성 차이로 인한 실패가 줄어듭니다(일반적으로 외부 구성을 통해 이미지 동작 변경(예: 삽입된 환경 변수)).

Docker 컨테이너 개발을 위해 .NET Core와 .NET Framework 중에서 결정하는 데 대한 [일반적인 지침](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md)입니다.

### <a name="common-docker-development-scenarios"></a>일반적인 Docker 개발 시나리오

#### <a name="net-core"></a>.NET Core

**.NET Core 리소스**

 관심 있는 시나리오에 맞는 .NET Core 샘플을 선택하세요. 모든 샘플 지침은 Windows, Linux 또는 macOS 호스트에서 Windows 또는 Linux Docker 이미지를 대상으로 하는 방법을 설명합니다.

샘플에서는 .NET Core 2.0을 사용합니다. 이러한 샘플에서는 해당하는 경우 Docker [다단계 빌드](https://github.com/dotnet/announcements/issues/18) 및 [다중 아키텍처 태그](https://github.com/dotnet/announcements/issues/14)를 사용합니다.

* [DockerHub의 .NET Core 이미지](https://hub.docker.com/r/microsoft/dotnet/)

* [Dockerize a .NET Core application](https://docs.docker.com/engine/examples/dotnetcore/)(.NET Core 응용 프로그램 Docker화)

* 이 .NET Core Docker 샘플은 [.NET Core 개발 프로세스에서 Docker를 사용](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)하는 방법을 보여 줍니다. 샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.

* 이 .NET Core Docker 샘플은 [프로덕션용 .NET Core 앱에 대한 Docker 이미지를 빌드](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)하는 것과 관련한 모범 사례 패턴을 보여 줍니다. 샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.

* 이 [.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained)은 [자체 포함된 .NET Core 응용 프로그램](../deploying/index.md)에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다. [컨테이너 간에 기본 이미지 공유](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)의 이점이 없는 가장 작은 프로덕션 컨테이너에 사용됩니다. 그러나 하위 Docker 계층은 공유할 수 있습니다.

#### <a name="arm32--raspberry-pi"></a>ARM32/Raspberry Pi

* [.NET Core 런타임 ARM32 빌드 공지 사항](https://github.com/dotnet/announcements/issues/29)

* [DockerHub의 ARM32/Raspberry Pi .NET Core 이미지](https://hub.docker.com/r/microsoft/dotnet/)

* [GitHub의 ARM32/Raspberry Pi .NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [DockerHub의 .NET Framework 이미지](https://hub.docker.com/r/microsoft/dotnet-framework/)

이 리포지토리에는 다양한 .NET Framework Docker 구성을 보여 주는 샘플이 포함되어 있습니다. 이러한 이미지를 고유한 Docker 이미지의 기반으로 사용할 수 있습니다.

**.NET Framework 4.7**

[dotnet-framework:4.7 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7)은 [.NET Framework 4.7](../../framework/whats-new/index.md#v47)의 기본 “Hello World” 사용을 보여 줍니다. 이 샘플은 [.NET Framework 4.7 Docker 이미지](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile)를 사용하여 앱을 빌드하고 배포하는 방법을 보여 줍니다.

**.NET Framework 4.6.2**

[dotnet-framework:4.6.2 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2)은 [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462)의 기본 “Hello World” 사용을 보여 줍니다. 이 샘플은 [.NET Framework 4.6.2 Docker 이미지](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2)를 사용하여 앱을 빌드하고 배포하는 방법을 보여 줍니다.

**.NET Framework 3.5**

 [dotnet-framework:3.5 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5)은 [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5)의 기본 “Hello World” 사용을 보여 줍니다. 이 샘플은 Docker에서 .NET Framework 3.5를 사용하여 프로젝트를 빌드하고 배포하는 방법을 보여 줍니다.

#### <a name="aspnet-core"></a>ASP.NET Core

* [이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)은 프로덕션용 ASP.NET Core 앱에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다. 샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.

* [DockerHub의 ASP.NET Core 이미지](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [GitHub의 ASP.NET Core 이미지](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>ASP.NET Framework

* [DockerHub의 ASP.NET Framework 이미지](https://hub.docker.com/r/microsoft/aspnet/)

* [.NET Framework 4.6.2의 ASP.NET Web Forms 앱 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>WCF(Windows Communication Framework)

* [DockerHub의 WCF(Windows Communication Framework) 이미지](https://hub.docker.com/r/microsoft/wcf/)

* [GitHub의 WCF(Windows Communication Framework) 이미지](https://github.com/microsoft/iis-docker)

* [.NET Full Framework 4.6.2를 사용하는 WCF(Windows Communication Framework) Docker 샘플](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>IIS(Internet Information Server)

* [DockerHub의 IIS(Internet Information Server) 이미지](https://hub.docker.com/r/microsoft/iis/)

* [GitHub의 IIS(Internet Information Server) 이미지](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>다른 Microsoft 스택 컨테이너 이미지와 상호 작용

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Docker 빠른 시작을 통해 Linux 2017용 Microsoft SQL Server 컨테이너 이미지 실행](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [DockerHub의 Linux용 Microsoft SQL Server 이미지](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [DockerHub의 Windows 컨테이너용 Microsoft SQL Server 이미지](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [DockerHub의 Windows 컨테이너용 Microsoft SQL Server Express Edition 이미지](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [DockerHub의 Windows 컨테이너용 Microsoft SQL Server Developer Edition 이미지](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>VSTS(Visual Studio Team Services) 에이전트

* [DockerHub의 VSTS(Visual Studio Team Services) 에이전트 이미지](https://hub.docker.com/r/microsoft/vsts-agent/)

* [GitHub의 VSTS(Visual Studio Team Services) 에이전트 이미지](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>OMS(Operations Management Suite) Linux 에이전트

* [OMS(Operations Management Suite) Linux 에이전트 개요](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [DockerHub의 OMS(Operations Management Suite) 이미지](https://hub.docker.com/r/microsoft/vsts-agent/)

* [GitHub의 OMS(Operations Management Suite) 이미지](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Microsoft Azure CLI(명령줄 인터페이스)

* [DockerHub의 Microsoft Azure CLI(명령줄 인터페이스) 이미지](https://hub.docker.com/r/microsoft/azure-cli/) 

* [GitHub의 Microsoft Azure CLI(명령줄 인터페이스) 이미지](https://github.com/Microsoft/OMS-docker)

> [!NOTE]
> Azure 구독이 없는 경우 무료 30일 계정에 [오늘 등록](https://azure.microsoft.com/free/?b=16.48)하고 Azure 크레딧 $200를 받아 원하는 조합의 Azure 서비스를 사용해 보세요.

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Microsoft Azure Cosmos DB 에뮬레이터(Windows 컨테이너만 해당)

* [DockerHub의 Microsoft Azure Cosmos DB 에뮬레이터 이미지](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [로컬 개발 및 테스트에 Azure Cosmos DB 에뮬레이터 사용](/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>풍부한 Docker 개발 에코시스템 살펴보기

Docker 플랫폼 및 다양한 Docker 이미지에 대해 알아보았으므로, 다음 단계는 풍부한 Docker 에코시스템을 살펴보는 것입니다. 다음 링크는 Microsoft 도구가 컨테이너 개발을 보완하는 방법을 보여 줍니다.

* [Using .NET and Docker together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/)(.NET 및 Docker 함께 사용)
* [다중 컨테이너 및 마이크로 서비스 기반 .NET 응용 프로그램 디자인 및 개발](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [Visual Studio Code Docker 확장](https://code.visualstudio.com/docs/languages/dockerfile)
* [Azure Service Fabric 사용 방법 알아보기](/azure/service-fabric/index)
* [Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)(Service Fabric 시작 샘플)
* [Windows 컨테이너의 혜택](/virtualization/windowscontainers/about/index#video-overview)
* [Visual Studio Docker 도구로 작업](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)(Azure Container Registry의 Docker 이미지를 Azure Container Instances에 배포)
* [Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)(Visual Studio Code를 사용한 디버깅)
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)(클라우드에서 Mac용 Visual Studio, 컨테이너 및 서버리스 코드에 익숙해지기)
* [Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)(Docker 및 Mac용 Visual Studio 랩 시작)

## <a name="next-steps"></a>다음 단계

* [.NET Core와 Docker 기본 사항 알아보기](docker-basics-dotnet-core.md)
* [.NET Core Docker 이미지 작성](building-net-docker-images.md)
