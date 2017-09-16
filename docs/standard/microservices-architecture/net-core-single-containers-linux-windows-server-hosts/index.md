---
title: "Linux 또는 Windows Nano 서버 호스트에 단일 컨테이너 기반 .NET Core 웹 응용 프로그램 배포"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Linux 또는 Windows Nano 서버 호스트에 단일 컨테이너 기반 .NET Core 웹 응용 프로그램 배포"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: a50c2ad3183c80fd76e6db042674e49367d7ffc9
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a>Linux 또는 Windows Nano 서버 호스트에 단일 컨테이너 기반 .NET Core 웹 응용 프로그램 배포

*간단한 웹 응용 프로그램의 모놀리식 배포에 대해 Docker 컨테이너를 사용할 수 있습니다. 이를 통해 지속적인 통합 및 지속적인 배포 파이프라인이 개선되며 프로덕션에 배포할 수 있습니다. 더 이상 “내 컴퓨터에서는 되는데 프로덕션에서는 되지 않는” 문제가 발생하지 않습니다.*

마이크로 서비스 기반 아키텍처에는 다양한 이점이 있지만 그에 따른 복잡성도 고려해야 합니다. 이점보다 비용이 더 많이 들어서, 단일 컨테이너 또는 소수의 컨테이너에서 실행되는 모놀리식 배포 응용 프로그램을 사용하는 것이 더 나은 경우도 있습니다. 

모놀리식 응용 프로그램은 잘 분리된 마이크로 서비스로 쉽게 분할되지 않을 수 있습니다. 앞서 언급한 대로, 마이크로 서비스는 기능별로 분할되어야 합니다. 마이크로 서비스는 독립적으로 작업을 수행하며 복원력이 우수한 응용 프로그램을 제공합니다. 응용 프로그램의 기능 조각을 제공할 수 없는 경우 응용 프로그램을 분리하면 복잡성만 더할 뿐입니다.

응용 프로그램의 기능을 독립적으로 확장할 필요가 없을 수 있습니다. eShopOnContainers 참조 응용 프로그램의 수명 초기에, 트래픽 때문에 기능을 여러 마이크로 서비스로 분리할 필요가 없는 상황을 가정해 봅시다. 트래픽은 매우 작기 때문에 대개 하나의 서비스에 리소스를 추가하면 모든 서비스에 리소스가 추가됩니다. 추가로 응용 프로그램을 불연속 서비스로 분리해서 얻는 이점은 매우 적습니다.

또한 응용 프로그램의 개발 초기에는 자연적인 기능 경계를 명확하게 알지 못할 수 있습니다. 최소 기능 제품을 개발할 때는 자연적인 분리가 아직 발생하지 않을 수 있습니다.

이러한 조건 중 일부는 일시적일 수 있습니다. 모놀리식 응용 프로그램을 만들어 시작하고 나중에 일부 기능을 분리하여 마이크로 서비스로 개발하고 배포할 수 있습니다. 응용 프로그램의 문제 영역에는 다른 조건이 필요할 수 있습니다. 즉, 응용 프로그램은 여러 마이크로 서비스로 분리되지 않을 수 있습니다.

응용 프로그램을 다수의 불연속 프로세스로 분리하면 오버헤드도 발생합니다. 기능을 다른 프로세스로 분리하는 작업이 더 어려워지며 통신 프로토콜이 더 복잡해집니다. 서비스 간에 메서드 호출 대신 비동기적인 통신을 사용해야 합니다. 마이크로 서비스 아키텍처로 이동하면 이벤트 버스 처리, 메시지 복원력 및 다시 시도, 최종 일관성 등 eShopOnContainers 응용 프로그램의 마이크로 서비스 버전에서 구현된 빌드 블록을 많이 추가해야 합니다.

한층 간소화된 버전의 eShopOnContainers([eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic)이라고 하며 동일한 GitHub 리포지토리에 포함됨)는 모놀리식 MVC 응용 프로그램으로 실행되며 설명한 바와 같이 이러한 디자인 선택에는 이점이 있습니다. GitHub에서 이 응용 프로그램에 대한 소스를 다운로드하고 로컬에서 실행할 수 있습니다. 이 모놀리식 응용 프로그램도 컨테이너 환경에서의 배포를 통해 이점을 얻습니다.

첫째, 컨테이너화된 배포는 응용 프로그램의 모든 인스턴스가 동일한 환경에서 실행되는 것을 의미합니다. 여기에는 초기 테스트 및 개발이 이루어지는 개발자 환경이 포함됩니다. 개발 팀은 프로덕션 환경과 일치하는 컨테이너화된 환경에서 응용 프로그램을 실행할 수 있습니다.

둘째, 저렴한 비용으로 컨테이너화된 응용 프로그램을 확장할 수 있습니다. 앞서 살펴본 것처럼 컨테이너 환경에서는 기존의 VM 환경에서보다 더 많은 리소스를 공유할 수 있습니다.

마지막으로, 응용 프로그램을 컨테이너화하면 비즈니스 논리와 저장소 서버 사이에서 강제 분할이 발생합니다. 응용 프로그램이 확장되면 여러 컨테이너는 모두 단일 실제 저장소 매체를 사용하게 됩니다. 일반적으로 SQL Server 데이터베이스를 실행하는 고가용성의 서버가 됩니다.

## <a name="application-tour"></a>응용 프로그램 둘러보기

[eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) 응용 프로그램은 모놀리식 응용 프로그램으로 실행되는 eShopOnContainers 응용 프로그램인 .NET Core에서 실행되는 ASP.NET Core MVC 기반 응용 프로그램의 일부를 나타냅니다. 이 응용 프로그램은 이전 섹션에서 설명했던 카탈로그 검색 기능을 주로 제공합니다.

이 응용 프로그램은 카탈로그 저장소에 대해 SQL Server 데이터베이스를 사용합니다. 컨테이너 기반 배포에서 이 모놀리식 응용 프로그램은 마이크로 서비스 기반 응용 프로그램과 동일한 데이터 저장소에 액세스할 수 있습니다. 이 응용 프로그램은 모놀리식 응용 프로그램과 함께 컨테이너에서 SQL Server를 실행할 수 있도록 구성됩니다. 프로덕션 환경에서 SQL Server는 Docker 호스트 외부의 고가용성 컴퓨터에서 실행됩니다. 편의를 위해 개발 또는 테스트 환경에서는 자체 컨테이너에서 SQL Server를 실행하는 것이 좋습니다.

초기 기능 집합에서는 카탈로그 검색 기능만 사용할 수 있습니다. 업데이트하면 컨테이너화된 응용 프로그램의 전체 기능 집합을 사용할 수 있습니다. 고급 모놀리식 웹 응용 프로그램 아키텍처는 [ASP.NET 웹 응용 프로그램 아키텍처 사례](https://aka.ms/webappebook) 전자책과 관련 [eShopOnWeb 응용 프로그램 예제](http://aka.ms/WebAppArchitecture)에 설명되어 있습니다. 단, 이 경우에는 해당 시나리오가 ASP.NET Core를 사용한 일반 웹 개발에 집중하므로 Docker 컨테이너에서 실행되지 않습니다.

그러나 eShopOnContainers(eShopWeb)에서 사용할 수 있는 단순화된 버전은 Docker 컨테이너에서 실행됩니다.

## <a name="docker-support"></a>Docker 지원

eShopOnWeb 프로젝트는.NET Core에서 실행됩니다. 따라서 Linux 기반 또는 Windows 기반 컨테이너에서 실행할 수 있습니다. Docker 배포에서는 SQL Server에 대해서 동일한 호스트 유형을 사용할 수 있습니다. 사람들은 Linux 기반 컨테이너를 선호하며 여기에서는 더 작은 공간을 사용할 수 있습니다.

Visual Studio는 Docker에 대한 지원을 솔루션에 추가하는 프로젝트 템플릿을 제공합니다. 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭하면 **Docker 지원**이 표시됩니다. 템플릿은 Dockerfile을 기존 프로젝트와 시작 docker-compose.yml 파일을 제공하는 새 **docker-compose** 프로젝트에 추가합니다. 이 단계는 GitHub에서 다운로드한 eShopOnWeb 프로젝트에서 이미 완료되었습니다. 그림 6-1에 표시된 것처럼 솔루션에 **eShopOnWeb** 프로젝트와 **docker-compose** 프로젝트가 포함되었음을 확인할 수 있습니다.

![](./media/image1.png)

**그림 6-1**. 단일 컨테이너 웹 응용 프로그램의 **docker-compose** 프로젝트

이러한 파일은 모든 Docker 프로젝트와 일치하는 표준 docker-compose 파일입니다. Visual Studio 또는 명령줄에서 해당 파일을 사용할 수 있습니다. 이 응용 프로그램은 .NET Core에서 실행되며 Linux 컨테이너를 사용하므로 Mac 또는 Linux 컴퓨터에서 응용 프로그램을 코딩, 빌드 및 실행할 수도 있습니다.

Docker compose.yml 파일에는 빌드할 이미지 및 시작할 컨테이너에 대한 정보가 포함됩니다. 템플릿은 eshopweb 이미지를 빌드하고 응용 프로그램의 컨테이너를 시작하는 방법을 지정합니다. 컨테이너를 빌드하고 시작하려면 이미지(예: mssql-server-linux)를 포함하여 SQL Server에서 종속성을 추가하고 Docker의 sql.data 이미지에 대한 서비스를 추가해야 합니다. 이러한 설정이 다음 예제에 나와 있습니다.

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

depends\_on 지시문은 eShopWeb 이미지가 sql.data 이미지에 종속된다는 사실을 Docker에게 알려 줍니다. 해당 지시문 아래 줄은 microsoft/mssql-server-linux 이미지를 사용하여 이미지가 태그된 sql.data를 빌드하기 위한 지침입니다.

**docker-compose** 프로젝트는 기본 docker-compose.yml 노드에서 다른 docker-compose 파일을 표시하여 해당 파일과 관련된 시각적 표시를 제공합니다. docker-compose-override.yml 파일에는 연결 문자열 및 다른 응용 프로그램 설정과 같은 두 서비스 모두에 대한 설정이 포함됩니다.

다음 예제에서는 Visual Studio의 디버깅에 사용되는 설정이 포함된 docker-compose.vs.debug.yml 파일을 보여 줍니다. 해당 파일에서는 eshopweb 이미지에 개발 태그가 추가되어 있습니다. 개발 태그가 릴리스 이미지에서 디버그를 분리하는 작업을 도와주어 실수로 디버그 정보를 프로덕션 환경에 배포하는 문제가 발생하지 않습니다.

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

추가된 마지막 파일은 docker-compose.ci.build.yml입니다. 이 파일은 CI 서버에서 프로젝트를 빌드하기 위해 명령줄에서 사용됩니다. 이 compose 파일은 응용 프로그램에 필요한 이미지를 빌드하는 Docker 컨테이너를 시작합니다. 다음 예제에서는 docker-compose.ci.build.yml 파일의 내용을 보여 줍니다.

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

이 이미지는 ASP.NET Core 빌드 이미지입니다. 해당 이미지에는 응용 프로그램을 빌드하고 필수 이미지를 만들기 위한 SDK와 빌드 도구가 포함됩니다. 이 파일을 사용하여 **docker-compose** 프로젝트를 실행하면 이미지에서 컨테이너가 빌드된 후 해당 컨테이너에서 응용 프로그램의 이미지가 빌드됩니다. docker-compose 파일을 명령줄의 일부로 지정하여 Docker 컨테이너에서 응용 프로그램을 빌드한 다음 시작하면 됩니다.

다른 응용 프로그램을 실행할 때와 같이 Visual Studio에서 **docker-compose** 프로젝트를 시작 프로젝트로 선택한 다음 Ctrl+F5(디버그하려면 F5 키)를 눌러 Docker 컨테이너에서 응용 프로그램을 실행할 수 있습니다. **docker-compose** 프로젝트를 시작하면 Visual Studio는 docker-compose.yml 파일, docker-compose.override.yml 파일 및 docker-compose.vs.\* 파일 중 하나를 사용하여 **docker-compose**를 실행합니다. 응용 프로그램이 시작되면 Visual Studio에서는 브라우저가 시작됩니다.

디버거에서 응용 프로그램을 시작한 경우 Visual Studio는 Docker에서 실행 중인 응용 프로그램을 첨부합니다.

## <a name="troubleshooting"></a>문제 해결

이 섹션에서는 로컬에서 컨테이너를 실행할 때 발생할 수 있는 몇 가지 문제를 설명하고 일부 해결 방법을 제안합니다.

### <a name="stopping-docker-containers"></a>Docker 컨테이너 중지 

컨테이너화된 응용 프로그램을 시작한 후 디버깅을 중지했음에도 컨테이너가 계속 실행됩니다. 명령줄에서 docker ps 명령을 실행하여 실행 중인 컨테이너를 확인할 수 있습니다. 그림 6-2에 표시된 것처럼 docker stop 명령은 실행 중인 컨테이너를 중지합니다.

![](./media/image2.png)

**그림 6-2**. docker ps 및 docker stop CLI 명령을 사용하여 컨테이너 목록 표시 및 중지

서로 다른 구성 간에 전환할 때는 실행 중인 프로세스를 중지해야 합니다. 그러지 않으면 웹 응용 프로그램을 실행 중인 컨테이너에서 응용 프로그램에 대한 포트(이 예에서는 5106)를 계속 사용합니다.

### <a name="adding-docker-to-your-projects"></a>프로젝트에 Docker 추가

Docker 지원을 추가하는 마법사는 실행 중인 Docker 프로세스와 통신합니다. 마법사를 시작할 때 Docker가 실행되고 있지 않은 경우 마법사가 올바르게 실행되지 않습니다. 또한 마법사는 올바른 Docker 지원을 추가하기 위해 현재 선택한 컨테이너를 검사합니다. Windows 컨테이너에 대한 지원을 추가하려는 경우 구성된 Windows 컨테이너를 통해 Docker가 실행되는 동안 마법사를 실행해야 합니다. Linux 컨테이너에 대한 지원을 추가하려는 경우 구성된 Linux 컨테이너를 통해 Docker가 실행되는 동안 마법사를 실행해야 합니다.

>[!div class="step-by-step"]
[이전] (../docker-application-development-process/docker-app-development-workflow.md) [다음] (../containerize-net-framework-applications/index.md)

