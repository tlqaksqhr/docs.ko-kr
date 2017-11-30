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
# <a name="introduction-to-net-and-docker"></a>.NET 및 Docker 소개

 이 문서를 소개 하 고 Docker에는.NET 작업의 배경 개념을 제공 합니다. 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: 배포 하 고 원하는 위치에 실행 하 여 앱 패키징

[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) 개발자와 관리자가 빌드할 수 있도록 하는 개방형 플랫폼은 [이미지](https://docs.docker.com/glossary/?term=image), 배송, 및 라는 느슨하게 격리 된 환경에서 배포 응용 프로그램을 실행 한 [컨테이너](https://www.docker.com/what-container). 이 방법을 개발, QA, 및 프로덕션 환경 간의 효율적인 응용 프로그램 수명 주기 관리를 사용 하면 됩니다.
 
[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform) 사용 하 여는 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine) 을 신속 하 게 빌드하고로 앱을 패키지할 [Docker images](https://docs.docker.com/glossary/?term=image) 로 작성 된 파일을 사용 하 여 만든는 [Dockerfile ](https://docs.docker.com/glossary/?term=Dockerfile) 형식이 다음 되어 배포에서 실행 한 [컨테이너 계층화](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)합니다.

만들거나 사용자 고유의 [이미지 계층화](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) dockerfile 또는 기존 업체에서 사용 하 여 한 [레지스트리](https://docs.docker.com/glossary/?term=registry)처럼 [Docker 허브](https://docs.docker.com/glossary/?term=Docker%20Hub)합니다.

[Docker 컨테이너, 이미지 및 레지스트리 간의 관계](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) 은 중요 한 개념 때 [설계 하 고 구축 응용 프로그램 또는 microservices 컨테이너 화 된](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/)합니다. 이 방법은 개발 및 배포 사이의 시간을 크게 줄입니다.

### <a name="further-reading-and-watching"></a>추가 정보 (및 보고)

* [Windows 기반 컨테이너: 엔터프라이즈급 컨트롤이 있는 최신 웹 개발 합니다.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Docker 개요](https://docs.docker.com/engine/docker-overview/)
* [Windows 컨테이너의 Dockerfile](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Dockerfile을 작성 하기 위한 모범 사례](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [.NET Core 응용 프로그램에 대 한 빌딩 Docker 이미지](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>.NET Docker 이미지 가져오기

공식.NET Docker 이미지 생성 및 Microsoft에 의해 최적화 됩니다. 서로 공개적으로 사용할 수 있는 것은 Docker 허브에서 Microsoft 저장소에서입니다. 각 저장소는 OS 버전 및.NET 버전에 따라 여러 이미지를 포함할 수 있습니다. 대부분 이미지 리포지토리 특정 프레임 워크 버전 및 OS (Linux 배포판 또는 Windows 버전)를 모두 선택할 수 있도록 광범위 한 태그를 제공 합니다.

## <a name="scenario-based-guidance"></a>시나리오 기반 지침

.NET 저장소에 대 한 Microsoft의 용도 세부적인 이어서 초점을 맞추고 리포지토리 있으며 특정 시나리오 나 작업을 나타냅니다.

`microsoft/aspnetcore` 컨테이너 더 빠르게 시작할 수 있습니다, Docker에 대 한 ASP.NET Core 응용 프로그램에 대해 이미지 최적화 됩니다.

.NET Core 이미지 (`microsoft/dotnet`)은.NET Core를 기반으로 하는 콘솔 앱을 위한 것입니다. 예를 들어 일괄 처리, Azure WebJobs 및 기타 콘솔 시나리오는 최적화 된.NET Core 이미지를 사용 해야 합니다.

Docker 및.NET 응용 프로그램을 사용 하는 가장 확실 한 가로 시나리오는 프로덕션 배포 및 호스팅에 사용 합니다. 사실은 프로덕션 시나리오 하나는 및의 다른 요소는 동일 하 게 유용 합니다. 이러한 시나리오는.NET에 한정 되지 않는 있지만 대부분의 개발자 플랫폼에 적용 해야 합니다.

* **낮은 마찰 설치** -로컬 설치 없이.NET 시도할 수 있습니다. 방금에.net Docker 이미지를 다운로드 합니다.

* **컨테이너에서 개발한** -개발 및 프로덕션 환경을 (개발자 컴퓨터에서 전역 상태와 같은 문제를 방지) 유사 하 게 만드는 일관 된 환경에서 개발할 수 있습니다. 도 Docker 용 visual Studio Tools를 사용 하는 컨테이너 Visual Studio에서 직접 시작 수 있습니다.

* **컨테이너에서 테스트** -마지막 테스트에서 남아 있는 기타 변경 내용 또는 잘못 구성 된 환경으로 인 한 실패를 줄이는 한 컨테이너에서 테스트할 수 있습니다.

* **컨테이너에 빌드** -올바르게 여러 환경에 대 한 공유 빌드 컴퓨터를 구성 하지만 대신 "BYOC" 이동 필요가 없도록는 컨테이너의 코드를 작성할 수 있습니다 (사용자 고유의 컨테이너 bring) 접근 방식입니다.

* **모든 환경에서 배포** -사용자 환경의 모든 이미지를 배포할 수 있습니다. 이 방법은 일반적으로 외부 구성 (예를 들어 삽입 된 환경 변수)를 통해 이미지 동작을 변경 하는 구성 차이로 인 한 오류를 줄일 수 있습니다.

[일반적인 지침](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) Docker 컨테이너 개발을 위한.NET Core와.NET Framework 중에서 결정 하는 것에 대 한 합니다.

### <a name="common-docker-development-scenarios"></a>일반적인 Docker 개발 시나리오

#### <a name="net-core"></a>.NET Core

**.NET core 리소스**

 관심 있는 시나리오에 맞는.NET Core 샘플을 선택 합니다. 모든 샘플 지침 Windows, Linux 또는 macOS 호스트에서 Windows 또는 Linux Docker 이미지를 대상으로 하는 방법에 설명 합니다.

샘플은.NET Core 2.0을 사용 합니다. Docker를 사용 [여러 단계로 이루어진 빌드](https://github.com/dotnet/announcements/issues/18) 및 [다중 아치 태그](https://github.com/dotnet/announcements/issues/14) 해당 하는 경우.

* [DockerHub에서.NET core 이미지](https://hub.docker.com/r/microsoft/dotnet/)

* [.NET Core 응용 프로그램 dockerize](https://docs.docker.com/engine/examples/dotnetcore/)

* 이.NET Core Docker 샘플에서는 설명 하는 방법을 [.NET Core 개발 프로세스에서 Docker를 사용 하 여](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev)합니다. 샘플은 Windows와 Linux 컨테이너에서 작동합니다.

* 이.NET Core Docker 샘플에 대 한 모범 사례 패턴 [프로덕션에 대 한.NET Core 응용 프로그램에 대 한 Docker 이미지를 작성 합니다.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) 샘플은 Windows와 Linux 컨테이너에서 작동합니다.

* 이 [.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) Docker 이미지를 구축 하기 위한 모범 사례 패턴을 보여 줍니다 [자체 포함 된.NET Core 응용 프로그램](https://docs.microsoft.com/dotnet/core/deploying/)합니다. 이점을 활용 하지 않고 작은 프로덕션 컨테이너에 사용 되는 [컨테이너 간의 기본 이미지를 공유](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/)합니다. 그러나 하위 Docker 계층을 공유할 수 없습니다.

#### <a name="arm32--raspberry-pi"></a>ARM32 라스베리 Pi /

* [.NET core 런타임 ARM32 빌드 알림](https://github.com/dotnet/announcements/issues/29)

* [ARM32 DockerHub에 라스베리 Pi.NET Core 이미지 /](https://hub.docker.com/r/microsoft/dotnet/)

* [ARM32 GitHub에서 샘플을.NET Core Docker 라즈베리 Pi /](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [DockerHub에서.NET framework 이미지](https://hub.docker.com/r/microsoft/dotnet-framework/) 이 리포지토리에 다양 한.NET Framework Docker 구성을 보여 주는 샘플이 포함 되어 있습니다. 사용자 고유의 Docker 이미지의 기반으로 이러한 이미지를 사용할 수 있습니다.

**.NET framework 4.7**

[는 [dotnet-프레임 워크: 4.7 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) 의 기본 "hello world" 사용법을 보여 줍니다는 [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47)합니다. 빌드에 의존 하는 앱을 배포 하는 방법을 표시 하는 [.NET Framework 4.7 docker 이미지](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile)합니다.

**.NET framework 4.6.2**

[dotnet-프레임 워크: 4.6.2 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) 의 기본 "hello world" 사용법을 보여 줍니다는 [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462)합니다. 빌드에 의존 하는 앱을 배포 하는 방법을 표시 하는 [.NET Framework 4.6.2 docker 이미지](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2)합니다.

**.NET framework 3.5**

 [dotnet-프레임 워크: 3.5 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) 의 기본 "hello world" 사용법을 보여 줍니다 [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5)합니다. 표시 빌드 Docker에서.NET Framework 3.5에 의존 하는 프로젝트를 배포 하는 방법.

#### <a name="aspnet-core"></a>ASP.NET Core

* [이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) 프로덕션에 대 한 앱 ASP.NET Core 용 Docker 이미지를 구성 하기 위한 모범 사례 패턴을 보여 줍니다. 샘플은 Windows와 Linux 컨테이너에서 작동합니다.

* [DockerHub에서 ASP.NET Core 이미지](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [GitHub에서 ASP.NET Core 이미지](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>ASP.NET 프레임 워크 

* [DockerHub에서 ASP.NET 프레임 워크 이미지](https://hub.docker.com/r/microsoft/aspnet/)

* [ASP.NET Web Forms 응용 프로그램에서.NET Framework 4.6.2 샘플에 액세스](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [DockerHub에서 프레임 워크 WCF (Windows Communication) 이미지](https://hub.docker.com/r/microsoft/wcf/)

* [GitHub의 Windows Communication Framework (WCF) 이미지](https://github.com/microsoft/iis-docker)

* [.NET Full Framework 4.6.2를 사용 하 여 Windows Communication Framework (WCF) Docker 예제](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [DockerHub에서 인터넷 정보 서버 (IIS) 이미지](https://hub.docker.com/r/microsoft/iis/)

* [GitHub의 인터넷 정보 서버 (IIS) 이미지](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>다른 Microsoft 스택 컨테이너 이미지와 상호 작용

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Docker 빠른 시작으로 2017 Linux 컨테이너 이미지를 위한 Microsoft SQL Server 실행](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [DockerHub에 Linux 이미지에 대 한 Microsoft SQL Server](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [DockerHub에서 Windows 컨테이너에 대 한 Microsoft SQL Server 이미지](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [DockerHub에 Windows 컨테이너에 대 한 Microsoft SQL Server Express Edition 이미지](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [DockerHub에 Windows 컨테이너에 대 한 Microsoft SQL Server Developer Edition 이미지](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Visual Studio Team Services (VSTS) 에이전트

* [DockerHub에서 visual Studio Team Services (VSTS) 에이전트 이미지](https://hub.docker.com/r/microsoft/vsts-agent/)

* [GitHub에서 visual Studio Team Services (VSTS) 에이전트 이미지](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Operations Management Suite (OMS) Linux 에이전트

* [Operations Management Suite (OMS) Linux 에이전트 개요](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [DockerHub에 operations Management Suite (OMS) 이미지](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [GitHub에 operations Management Suite (OMS) 이미지](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Microsoft Azure 명령줄 인터페이스 (CLI)

* [DockerHub에서 Microsoft Azure 명령줄 인터페이스 (CLI) 이미지](Docker image for Microsoft Azure Command Line Interface) 

* [GitHub의 Microsoft Azure 명령줄 인터페이스 (CLI) 이미지](https://github.com/Microsoft/OMS-docker)

> [!Note]
> Azure 구독이 없는 경우 [바로 등록할](https://azure.microsoft.com/free/?b=16.48) 무료 30 일 계정 및 Azure 서비스의 조합을 사용해 Azure 크레딧에서 get $200에 대 한 합니다.
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Microsoft Azure DB Cosmos 에뮬레이터 (Windows 컨테이너에만 해당)

* [DockerHub에서 Microsoft Azure Cosmos DB 에뮬레이터 이미지](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [로컬 개발 및 테스트에 대 한 Azure Cosmos DB 에뮬레이터를 사용 하 여](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>풍부한 Docker 개발 생태계를 탐색합니다.

Docker 플랫폼 및 다른 Docker 이미지에 대해 배웠습니다, 했으므로 풍부한 Docker 생태계를 탐색 하는 다음 단계가입니다. 다음 링크는 Microsoft 도구 컨테이너 개발을 보완 하는 방법을 보여 줍니다.

* [.NET 및 Docker를 함께 사용 하 여](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [디자인 하 고 여러 컨테이너 및 마이크로 서비스 기반.NET 응용 프로그램 개발](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [Visual Studio 코드 Docker 확장](https://code.visualstudio.com/docs/languages/dockerfile) 
* [Azure Service Fabric을 사용 하는 방법에 알아봅니다](https://docs.microsoft.com/azure/service-fabric/) 
* [서비스 패브릭 Getting Started 샘플](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [Windows 컨테이너의 이점](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [Visual Studio Docker 도구 사용](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Azure 컨테이너 인스턴스를 Azure 컨테이너 레지스트리에서 Docker 이미지 배포](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Visual Studio 코드를 사용 하 여 디버깅](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [가져오기 손에 Visual Studio와 함께 Mac, 컨테이너 및 서버 없이 코드에 대 한 클라우드](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Mac 랩 용 Docker 및 Visual Studio 시작](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a>다음 단계

* [.NET core Docker 기본 사항 알아보기](../docker/docker-basics-dotnet-core.md)
* [.NET Core Docker 이미지 작성](../docker/building-net-docker-images)