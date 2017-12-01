---
title: "Docker 앱에 대 한 개발 워크플로"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker 앱에 대 한 개발 워크플로"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a>Docker 앱에 대 한 개발 워크플로

응용 프로그램 개발 수명 주기는 개발자가 기본 설정된 언어를 사용 하 여 응용 프로그램 코드와 로컬로 테스트 여기서 각 개발자의 컴퓨터에서 시작 됩니다. 어떤 언어, 프레임 워크 및이 워크플로에 개발자가 선택 되는 플랫폼에 관계 없이 개발자가 항상 개발 및 테스트, Docker 컨테이너 하지만 로컬입니다.

각 컨테이너 (Docker 이미지의 인스턴스)는 다음 구성 요소가 포함 되어 있습니다.

-   (예를 들어 Linux 배포판, Windows Nano Server 또는 Windows Server Core)는 운영 체제 선택 합니다.

-   (응용 프로그램 이진 파일 등)은 개발자가 추가 되는 파일입니다.

-   구성 정보 (환경 설정 및 종속성)입니다.

## <a name="workflow-for-developing-docker-container-based-applications"></a>Docker 컨테이너 기반 응용 프로그램을 개발 하기 위한 워크플로

이 섹션에 설명 된 *내부 루프* Docker 컨테이너 기반 응용 프로그램에 대 한 개발 워크플로에 합니다. 내부 루프 워크플로 사용 하지 계정으로 보다 광범위 한 DevOps 워크플로 및 개발자의 컴퓨터에서 수행 되는 개발 작업에만 중점을 두고 것을 의미 합니다. 한 번만 완료 된 후에 환경을 설정 하는 초기 단계, 포함 되지 않습니다.

응용 프로그램 서비스과 추가 라이브러리 (종속성)으로 구성 됩니다. 일반적으로 수행 하는 Docker 응용 프로그램을 빌드하는 경우 그림 5-1을 보여 주는 것 처럼 기본 단계는 다음과 같습니다.

![](./media/image1.png)

**그림 5-1입니다.** Docker 컨테이너 화 가능한 응용 프로그램을 개발 하기 위한 단계별 워크플로

이 가이드에서이 전체 프로세스를 자세히 설명 하 고 모든 주요 단계는 Visual Studio 환경 중점적으로 설명 합니다.

편집기/CLI 개발 방법 (예를 들어 Visual Studio 코드와 macOS에서 Docker CLI 또는 Windows)를 사용 하는 경우 모든 단계를 일반적으로 Visual Studio를 사용 하는 경우 보다 더 자세히 파악 해야 합니다. CLI 환경에서 작업 하는 방법에 대 한 자세한 내용은 전자책 참조 [Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 가능한 응용 프로그램 수명 주기](http://aka.ms/dockerlifecycleebook/)합니다.

Visual Studio 2015 또는 Visual Studio 2017을 사용 하는 경우 이러한 단계 대부분의 생산성을 크게 향상 되는 자동으로 처리 됩니다. Visual Studio 2017 사용 하면서 다중 컨테이너 응용 프로그램을 대상으로 할 때 특히 유용 합니다. 예를 들어, 하나만 마우스 클릭으로 Visual Studio는 Dockerfile 및 docker compose.yml 파일 프로젝트를 추가 응용 프로그램에 대 한 구성 사용 합니다. Docker 이미지를 작성 및 Docker에서 직접 여러 컨테이너 응용 프로그램을 실행 합니다. Visual Studio에서 응용 프로그램을 실행 하는 경우 도 한 번에 여러 컨테이너를 디버깅할 수 있습니다. 이러한 기능에는 개발 속도 향상 됩니다.

그러나 Visual Studio에서는 이러한 단계가 자동 해 서 의미가 어떻게 진행 되 고 알 필요가 없습니다 Docker가 있는 on 아래 합니다. 따라서 아래 지침에 모든 단계를 자세히 했습니다.

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>1단계: 코딩을 시작 하 고 초기 응용 프로그램 또는 서비스 기준을 만들려면

Docker 응용 프로그램을 개발 하는 것은 Docker 없는 응용 프로그램을 개발 하는 방법은 비슷합니다. 다른 점은 Docker를 개발 하는 동안 배포 및 테스트 중인 응용 프로그램 또는 로컬 환경에서 Docker 컨테이너 내에서 실행 되는 서비스입니다. Linux 컨테이너 또는 Windows 컨테이너는 컨테이너 수 있습니다.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Visual Studio와 함께 로컬 환경 설정

를 시작 하려면 했는지 확인 [Docker Community Edition (CE)](https://www.docker.com/community-edition) 경우 다음 지침에에서 설명 된 대로 설치 하는 Windows 용:

[Windows 용 Docker CE 시작](https://docs.docker.com/docker-for-windows/)

또한 Visual Studio 2017 설치 해야 합니다. 이것은 것이 좋습니다 Visual Studio 2015는 Visual Studio tools for Docker 추가 기능을 통해 Visual Studio 2017 컨테이너 디버깅에 대 한 지원 같은 Docker에 대 한 지원을 고급 있습니다. Visual Studio 2017을 선택한 경우 Docker에 대 한 도구에 포함 되어는 **.NET Core 및 Docker** 그림 5-2와 같이 설치 하는 동안 작업 합니다.

![](./media/image3.png)

**그림 5-2**합니다. 선택 하 고 **.NET Core 및 Docker** Visual Studio 2017 설치 하는 동안 작업

응용 프로그램에서 Docker를 사용 하도록 설정 하 고 배포 및 Docker에서 테스트 하기 전에 응용 프로그램 (일반적으로.NET Core 컨테이너를 사용 하려는 경우)에 일반.net 코딩을 시작할 수 있습니다. 그러나 Docker에서 가능한 한 빨리 실제 환경 수 있는 모든 문제를 가능한 한 빨리 검색 하기 때문에 작업을 시작 하는 것이 좋습니다. Visual Studio를 사용 하면 Docker는 거의 마치 투명 하 게 사용 하는 것이 쉽지 때문에이 방법은 권장-Visual Studio에서 여러 컨테이너 응용 프로그램을 디버깅 하는 경우 가장 좋은 예입니다.

### <a name="additional-resources"></a>추가 리소스

-   **Windows 용 Docker CE 시작**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio 2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>2단계. 기존.NET 기본 이미지와 관련 된 Dockerfile 만들기

Dockerfile; 빌드 하려는 각 사용자 지정 이미지 필요 Visual Studio 또는 Docker CLI를 사용 하 여 수동으로에서 자동으로 배포 여부를 각 컨테이너에 대 한 배포를 Dockerfile을 또한 해야 (실행 docker 및 docker-명령을 작성). 응용 프로그램은 하나의 사용자 지정 서비스를 포함 하는 경우 단일 Dockerfile 해야 합니다. 응용 프로그램 (예: microservices 아키텍처)는 여러 서비스를 포함 하는 경우 각 서비스에 대 한 Dockerfile 필요 합니다.

Dockerfile은 응용 프로그램 또는 서비스의 루트 폴더에 배치 됩니다. Docker를 설정 하 고 컨테이너에 응용 프로그램 또는 서비스를 실행 하는 방법을 지시 하는 명령이 포함 됩니다. 수동으로 코드에서 Dockerfile을 만들 하 고.NET 종속성과 함께 프로젝트에 추가할 수 있습니다.

Visual Studio 및 Docke에 대 한 도구와이 작업에는 몇 가지 마우스 클릭 해야합니다. 명명 된 하는 옵션은 Visual Studio 2017에 새 프로젝트를 만들 때 **컨테이너를 사용 하도록 설정 (Docker) 지원**그림 5-3에 표시 된 것 처럼 합니다.

![](./media/image5.png)

**그림 5-3**합니다. Visual Studio 2017에서 새 프로젝트를 만들 때 Docker 지원을 사용 하도록 설정

Visual Studio에서 프로젝트 파일을 마우스 오른쪽 단추로 클릭 하 고 옵션을 선택 하 여 새 프로젝트나 기존 프로젝트에서 Docker 지원을 설정할 수도 있습니다 **추가 Docker 프로젝트 지원**그림 5-4에 표시 된 것 처럼 합니다.

![](./media/image6.png)

**그림 5-4**합니다. 기존 Visual Studio 2017 프로젝트에서 Docker 지원을 사용 하도록 설정

이 작업 (예: ASP.NET 웹 응용 프로그램 또는 웹 API 서비스) 프로젝트에 필요한 구성으로 프로젝트를 Dockerfile을 추가합니다. 또한 전체 솔루션에 대 한 docker compose.yml 파일을 추가합니다. 다음 섹션에서는 이러한 각 파일에 입력 되는 정보가 설명 합니다. Visual Studio,이 작업을 수행할 수 있지만 Dockerfile에 포함할 항목을 이해 하는 것이 유용 합니다.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>옵션 a: 기존 공식.NET Docker 이미지를 사용 하 여 프로젝트 만들기

일반적으로 기본 이미지에는 공식 저장소에서 가져올 수를 기반으로 컨테이너에 대해 사용자 지정 이미지를 만들기는 [Docker 허브](https://hub.docker.com/) 레지스트리 합니다. 하는 방법을 보여 줍니다 정확 하 게 내부적 Visual Studio에서 Docker 지원 기능을 설정 합니다. Dockerfile 기존 aspnetcore 이미지를 사용 합니다.

이전에서는 설명는 Docker 이미지 리포지토리 프레임 워크와 선택한 운영 체제에 따라 사용할 수 있습니다. 예를 들어, ASP.NET Core (Linux 또는 Windows)를 사용 하려는 경우 사용할 이미지는 microsoft / aspnetcore:2.0 합니다. 따라서 컨테이너에 대해 사용할 어떤 기본 Docker 이미지를 지정 하기만 하면 됩니다. Microsoft에서 추가 하 여 그렇게 / aspnetcore:2.0 Dockerfile에 있습니다. 이 자동으로 수행 됩니다 Visual Studio가 있지만이 값을 업데이트, 버전을 업데이트 하는 경우.

Docker 허브에서 공식.NET 이미지 리포지토리를 사용 하 여 버전 번호는 동일한 언어 기능은 모든 컴퓨터 (개발, 테스트 및 프로덕션 포함)에서 사용할 수 있는지 확인 합니다.

다음 예제에서는 ASP.NET Core 컨테이너에 대 한 Dockerfile 예제를 보여 줍니다.

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

이 경우 컨테이너 공식 ASP.NET Core Docker 이미지 (Linux 및 Windows 용 다중 arch)의 버전 2.0은 기반으로 합니다. 이 값은 설정 `FROM microsoft/aspnetcore:2.0`합니다. (이 기본 이미지에 대 한 자세한 내용은 참조는 [ASP.NET Core Docker 이미지](https://hub.docker.com/r/microsoft/aspnetcore/) 페이지 및 [.NET Core Docker 이미지](https://hub.docker.com/r/microsoft/dotnet/) 페이지입니다.) Dockerfile의 Docker (이 경우 포트 80 노출 설정으로 구성 된 대로)에서 런타임에 사용할 TCP 포트에서 수신 대기 하도록 지시 해야 합니다.

언어 및 사용 하는 프레임 워크에 따라 Dockerfile의 추가 구성 설정을 지정할 수 있습니다. 예를 들어, ENTRYPOINT 줄을 \["dotnet", "MySingleContainerWebApp.dll"\] .NET Core 응용 프로그램을 실행 하는 Docker를 알려 줍니다. 을 사용 중인 SDK 및.NET Core CLI (dotnet CLI) 작성 하 고.NET 응용 프로그램을 실행 하는 경우이 설정은 다른 것입니다. 결론입니다 ENTRYPOINT 줄 및 기타 설정에서 응용 프로그램에 대해 선택한 언어 및 플랫폼에 따라 달라을 수 있습니다.

### <a name="additional-resources"></a>추가 리소스

-   **.NET Core 응용 프로그램에 대 한 Docker 이미지를 작성**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)

-   **사용자 고유의 이미지를 작성할**합니다. 공식 Docker 설명서입니다.
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>다중 아치 이미지 저장소를 사용 하 여

단일 리포지토리 플랫폼 변형 Linux 이미지 등 Windows 이미지를 포함할 수 있습니다. 이 기능에는 Microsoft (기본 이미지 작성자)와 같은 공급 업체를 (즉, Linux 및 Windows)는 여러 플랫폼을 처리 하려면 단일 리포지토리를 만들 수 있습니다. 예를 들어는 [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) Docker 허브 레지스트리에서 사용할 수 있는 저장소 같은 리포지토리 이름을 사용 하 여 Linux 및 Windows Nano Server에 대 한 지원을 제공 합니다.

다음과 같은 경우에는 다음과 같은 명시적 되는 플랫폼을 대상으로 하는 태그를 지정 하는 경우:

-   **microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

그러나 이것이 2017 중순 이후 새로운 지정 하는 경우 같은 태그 된 경우에 동일한 이미지 이름, (예: 여러 아키텍처를 지 원하는 aspnetcore 이미지) 새 다중 아치 이미지에서 배포 하는 Docker 호스트 운영 체제에 따라 Linux 또는 Windows 버전을 사용 하 고 를 다음 예제와 같이:

-   **microsoft / aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

이러한 방식으로 Windows 호스트에서 이미지를 가져올 때, Windows variant 끌어오고 것 및 Linux 호스트에서 동일한 이미지 이름을 끌어오기은 Linux 변형을 가져옵니다.

### <a name="option-b-creating-your-base-image-from-scratch"></a>옵션 b: 처음부터 기본 이미지 만들기

처음부터 직접 Docker 기본 이미지를 만들 수 있습니다. 이 시나리오는 적합 하지 않습니다 Docker로 시작 하는 사람 있지만 사용자 고유의 기본 이미지의 특정 비트를 설정 하려는 경우 그렇게 할 수 있습니다.

### <a name="additional-resources"></a>추가 리소스

-   **다중 아치.NET Core 이미지**합니다.
https://github.com/dotnet/announcements/issues/14 
-   **기본 이미지를 만들**합니다. 공식 Docker 설명서입니다.
    [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>3단계. 사용자 지정 Docker 이미지를 만들고 여기에 응용 프로그램 또는 서비스 포함

응용 프로그램에서 각 서비스에 대해 관련된 이미지를 만드는 데 필요 합니다. 응용 프로그램은 하나의 서비스 또는 웹 응용 프로그램의 구성 된, 경우 하기만 하면 단일 이미지 됩니다.

Docker 이미지는 자동으로 사용자에 대 한 Visual Studio에서 작성 하는 참고 사항 다음 단계는만 편집기/CLI 워크플로에 필요 하 고 쉽게 구별할 수 있도록 아래 수행 되는 작업에 대 한 설명입니다.

개발자 해야 개발 하 고 로컬로 푸시할은 완료 될 때까지 테스트 기능 또는 소스 제어 시스템 (예를 들어 GitHub에서)로 변경 합니다. 이 Docker 이미지를 만들려면 및 (Windows 또는 Linux VM) 로컬 Docker 호스트에 컨테이너를 배포 및 실행, 테스트 및 로컬 해당 컨테이너에 대 한 디버그 해야 할 것을 의미 합니다.

Docker CLI 및 Dockerfile을 사용 하 여 로컬 환경에서 사용자 지정 이미지를 만들려면, docker 빌드 명령을 그림 5-5와 같이 사용할 수 있습니다.

![](./media/image8.png)

**그림 5-5**합니다. 사용자 지정 Docker 이미지 만들기

필요에 따라 docker 빌드 프로젝트 폴더에서를 직접 실행 하는 대신 먼저 필요한.NET 라이브러리와 함께 배포 가능한 폴더를 생성할 수 있습니다 게시 하 고 dotnet를 실행 하 여 이진 파일을 다음 docker 빌드 명령을 사용 합니다.

이렇게 하면 만들어지고 Docker 이미지의 이름 cesardl/netcore-webapi-마이크로 서비스-docker: 첫 번째입니다. 이 경우: 먼저는 특정 버전을 나타내는 태그입니다. 구성 된 Docker 응용 프로그램에 대해 만들어야 할 각 사용자 지정 이미지에 대해이 단계를 반복할 수 있습니다.

응용 프로그램의 여러 컨테이너 만들어질 때 (즉,이 다중 컨테이너 응용 프로그램)를 사용할 수도 있습니다는-관련의 노출 된 메타 데이터를 사용 하 여 하나의 명령으로 모든 관련된 이미지를 만들려면 빌드 명령을를 docker 구성 docker compose.yml 파일입니다.

명령을 찾을 수 있습니다 기존 이미지 로컬 저장소에서 docker를 사용 하 여 이미지, 그림 5-6에 나와 있는 것 처럼 합니다.

![](./media/image9.png)

**그림 5-6입니다.** Docker 이미지 명령을 사용 하 여 보기 기존 이미지

### <a name="creating-docker-images-with-visual-studio"></a>Visual Studio를 사용 하 여 Docker 이미지 만들기

프로젝트를 만들려면 Docker 지 원하는 Visual Studio를 사용 하면 명시적으로 만들지 마십시오 이미지. 대신, 이미지가 만들어집니다 dockerized 응용 프로그램이 나 서비스를 실행 하 고 F5 키를 누릅니다. 이 단계는 Visual Studio에서 자동 및 발생 표시 되지 것입니다 이지만 진행 상황을 파악 하는 것에 아래 합니다.

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>4단계. 다중 컨테이너 Docker 응용 프로그램을 빌드할 때 docker compose.yml 서비스 정의

[docker compose.yml](https://docs.docker.com/compose/compose-file/) 파일로 배포 명령 사용 하 여 구성 된 응용 프로그램으로 배포 될 관련된 서비스의 집합을 정의할 수 있습니다.

Docker compose.yml 파일을 사용 하려면 다음 예제에서와 비슷한 콘텐츠로 프로그램 main에서 파일 또는 루트 솔루션 폴더를 만드는 데 필요 합니다.

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

Docker compose.yml 파일 단순화 되 고 병합 된 버전을 참고 합니다. (예: 이름 사용자 지정 이미지의)을 배포 환경 연결 문자열과 같은 종속 된 구성 정보 및 항상 적용 하는 각 컨테이너에 대 한 정적 구성 데이터를 포함 합니다. 이후 섹션에서 배웁니다 어떻게 docker compose.yml 구성을 여러도 분할할 수 있습니다 docker 구성 파일 및 환경 및 실행 유형 (디버그 또는 릴리스)에 따라 값을 재정의 합니다.

Docker compose.yml 파일 예제에서는 5 개의 서비스 정의: webmvc 서비스 (웹 응용 프로그램), 두 microservices (catalog.api 및 ordering.api) 및 하나 이상의 데이터 원본 컨테이너를 sql.data, 컨테이너를 실행 하는 Linux 용 SQL Server에 기반 합니다. 각 서비스는 Docker 이미지를 각각에 대 한 필요 않도록 컨테이너 기능을 배포 됩니다.

Docker compose.yml 파일에는 어떤 컨테이너가 사용 하 여을 뿐 아니라 개별적으로 구성 방법을 지정 합니다. 예를 들어, webmvc 컨테이너에에서 있는 정의.yml 파일:

-   미리 작성 된 eshop를 사용 하 여 / 웹: 최신 이미지입니다. 그러나 이미지의 일부로 작성도 구성할 수는 docker 구성 빌드를 기반으로 하는 추가 구성을 실행: docker-compose 파일의 섹션입니다.

-   두 개의 환경 변수를 (CatalogUrl 및 OrderingUrl)를 초기화합니다.

-   호스트 컴퓨터의 외부 포트 80 컨테이너에는 80 노출 된 포트를 전달합니다.

-   웹 응용 프로그램 카탈로그 및 서비스를 순서에 연결 된 종속\_설정에 합니다. 이렇게 하면 해당 서비스가 시작 될 때까지 대기 하는 서비스입니다.

이후 섹션에서 docker compose.yml 파일 microservices 및 다중 컨테이너 응용 프로그램을 구현 하는 방법을 다룰 때 다시 표시 합니다.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Visual Studio 2017에 docker compose.yml 작업

그림 5-7에 표시 된 것 처럼 서비스 프로젝트는 Visual Studio 솔루션에 Docker 솔루션 지원을 추가 하면 Visual Studio 프로젝트에 Dockerfile을 추가 하 고 docker compose.yml 파일과 함께 서비스 섹션 (프로젝트) 솔루션에 추가 합니다. 여러 컨테이너 솔루션 작성을 시작 하는 쉬운 방법입니다. 그런 다음 docker compose.yml 파일 열고 추가 기능으로 업데이트할 수 있습니다.

![](./media/image6.png)

**그림 5-7**합니다. ASP.NET Core 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 Visual Studio 2017에 Docker 지원 추가

Visual Studio에서 Docker 지원을 추가 Dockerfile을 프로젝트에 추가 하는 뿐 아니라 솔루션 수준에서 설정 된 여러 개의 전역 docker compose.yml 파일에 구성 정보를 추가 합니다.

Visual Studio에서 솔루션에 Docker 지원을 추가 하면 그림 5-8에 나와 있는 것 처럼 추가 docker compose.yml 파일을 포함 하는 솔루션 탐색기에서 새 노드는 docker compose.dcproj 프로젝트 파일에 나타납니다.

![](./media/image11.PNG)

**그림 5-8**합니다. **docker 작성** 추가 Visual Studio 2017 솔루션 탐색기에서 트리 노드

사용 하 여 단일 docker compose.yml 파일 다중 컨테이너 응용 프로그램을 배포할 수 있습니다는 docker 명령을 작성 합니다. 환경 (프로덕션 및 개발) 및 실행에 따라 값을 재정의할 수 있도록 Visual Studio 그중에서 그룹을 추가 하는 반면 유형 (디버그와 릴리스). 이 기능은 이후 섹션에서 설명 되어 있습니다.

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>5단계. Docker 응용 프로그램 빌드 및 실행

응용 프로그램에 단일 컨테이너에 있는 경우 (VM 또는 실제 서버) Docker 호스트에 배포 하 여 실행할 수 있습니다. 그러나 응용 프로그램에 여러 서비스 있으면 배포할 수 있습니다는 구성 된 응용 프로그램으로 단일 CLI 명령을 사용 하 여 (docker-작성 위로), 또는 Visual Studio와 함께 있으며 내부적 해당 명령을 사용 합니다. 다양 한 옵션에 살펴보겠습니다.

### <a name="option-a-running-a-single-container-with-docker-cli"></a>Docker CLI를 단일 컨테이너를 실행 하는 옵션 a:

Docker run 명령, 그림 5-9와 같이 사용 하 여 Docker 컨테이너를 실행할 수 있습니다.

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**그림 5-9**합니다. Docker run 명령을 사용 하 여 Docker 컨테이너를 실행 합니다.

이 경우 명령은 호스트 컴퓨터의 포트 80 컨테이너의 내부 포트 5000에 바인딩합니다. 즉, 호스트 포트 80에서 수신 대기 하 고 포트 5000 컨테이너에 전달 합니다.

### <a name="option-b-running-a-multi-container-application"></a>다중 컨테이너 응용 프로그램을 실행 하는 옵션 b:

대부분의 엔터프라이즈 시나리오에서 Docker 응용 프로그램 구성 됩니다 여러 서비스 그림 5-10에서와 같이 여러 컨테이너 응용 프로그램을 실행 해야 합니다.

![](./media/image14.png)

**그림 5-10**합니다. 배포 된 Docker 컨테이너를 사용 하 여 VM

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>Docker CLI와 다중 컨테이너 응용 프로그램을 실행합니다.

Docker를 실행할 수를 Docker CLI 사용 다중 컨테이너 응용 프로그램을 실행 하려면-명령을 작성 합니다. 포함 되는 다중 컨테이너 응용 프로그램을 배포 하려면 솔루션 수준에서이 명령 사용 하 여 docker compose.yml 파일입니다. 그림 5-11 docker compose.yml 파일이 포함 된 기본 프로젝트 디렉터리에서 명령을 실행할 때 결과 보여줍니다.

![](./media/image15.png)

**그림 5-11**합니다. 실행 하는 경우 결과 예는 명령을 docker 구성

Docker 후-명령 실행을 작성, VM 표시 그림 5-10에서에서 보여 주는 것 처럼 응용 프로그램 및 해당 관련된 컨테이너 Docker 호스트에 배포 됩니다.

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>실행 하 고 Visual Studio와 함께 여러 컨테이너 응용 프로그램 디버깅 

Visual Studio 2017을 사용 하 여 다중 컨테이너 응용 프로그램을 실행 하는 것은 간단 가져올 수 없습니다. 수만 실행 하면 여러 컨테이너 응용 프로그램 있지만 일반적인 중단점을 설정 하 여 Visual Studio에서 직접 모든 해당 컨테이너 디버깅 수 있습니다.

솔루션 내의 프로젝트를 솔루션 지원 Docker를 추가할 때마다 전에 언급 했 듯이 실행 하거나 전체 솔루션을 한 번에 디버그할 수 있는 글로벌 (솔루션 수준의) docker compose.yml 파일에서 해당 프로젝트 구성 됩니다. Visual Studio Docker 솔루션 지원이 활성화 되는 각 프로젝트에 대 한 컨테이너를 시작 되며 모든 내부 단계를 수행 하면 (dotnet 게시, docker 빌드 등.).

여기서 중요 한 점은, 그림 5-12, 표시 된 것 처럼 Visual Studio 2017에 있다는 점입니다 추가 **Docker** F5 키 작업에 대 한 명령입니다. 이 옵션을 사용 하 여 실행 하거나 솔루션 수준에서 docker compose.yml 파일에 정의 된 모든 컨테이너를 실행 하 여 다중 컨테이너 응용 프로그램을 디버깅할 수 있습니다. 여러 컨테이너 솔루션을 디버깅 하는 기능 (컨테이너)를 다른 프로젝트에 중단점을 여러 개, 각 중단점을 설정할 수 있습니다 및에서 실행 하 고 다른 프로젝트에 정의 된 중단점에서 중지 됩니다 Visual Studio에서 디버깅 하는 동안 의미 다른 컨테이너입니다.

![](./media/image16.png)

**그림 5-12**합니다. Visual Studio 2017에 실행 중인 다중 컨테이너 응용 프로그램

### <a name="additional-resources"></a>추가 리소스

-   **원격 Docker 호스트에는 ASP.NET 컨테이너를 배포**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>테스트 및 orchestrators 사용 하 여 배포에 대 한 메모

docker 작성 하 고 docker 실행 명령을 (또는 실행 및 디버깅을 Visual Studio에서 컨테이너)는 개발 환경에서 컨테이너를 테스트 하기에 충분 합니다. 하지만 Docker 클러스터를 대상으로 하 고 docker는 Docker Swarm, Mesosphere DC/OS 또는 Kubernetes orchestrators 형식 하는 경우이 방법을 사용 하지 않아야 합니다. 같은 클러스터를 사용 하는 경우 [docker는 Docker Swarm 모드](https://docs.docker.com/engine/swarm/) 배포 및와 같은 추가 명령을 사용 하 여 테스트 해야 할 (사용 가능 Windows 용 Docker CE 및 Mac 1.12 버전부터), [docker 서비스를 만들](https://docs.docker.com/engine/reference/commandline/service_create/) 에 대 한 단일 서비스입니다. 사용 하면 여러 컨테이너를 구성 하는 응용 프로그램을 배포 하는 경우 [docker 번들 작성](https://docs.docker.com/compose/reference/bundle/) 및 [docker 배포 myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) 으로 구성 된 응용 프로그램을 배포 하는 *스택*. 자세한 내용은 블로그 게시물을 참조 하십시오. [실험적 분산 응용 프로그램 번들 소개](https://blog.docker.com/2016/06/docker-app-bundle/) Docker 설명서에 있습니다. Docker 사이트입니다.

에 대 한 [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) 및 [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) 다양 한 배포 명령 및 스크립트에도 사용 합니다.

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>6단계. 로컬 Docker 호스트를 사용 하 여 Docker 응용 프로그램 테스트

이 단계는 응용 프로그램이 수행 하는 작업에 따라 달라 집니다. 간단한.NET Core 웹 응용 프로그램에서 단일 컨테이너 또는 서비스로 배포 된 Docker 호스트에서 브라우저를 열고 그림 5-13에 표시 된 것 처럼 해당 사이트로 이동 하는 서비스를 액세스할 수 있습니다. (Dockerfile의 구성 컨테이너의 포트 80 이외의 값이 설정 되어 있는 호스트에 매핑되면, 후 호스트를 URL에 포함 합니다.)

![](./media/image18.png)

**그림 5-13**합니다. Localhost를 사용 하 여 로컬로 Docker 응용 프로그램 테스트의 예

Localhost Docker를 가리키지 않습니다 경우 호스트 IP (기본적으로 Docker CE를 사용 하는 경우, 것)으로 서비스를 탐색 하려면 해당 컴퓨터의 네트워크 카드의 IP 주소를 사용 합니다.

참고가이 URL은 브라우저에서 설명 하는 특정 컨테이너 예제에 대 한 포트 80을 사용 합니다. 그러나 내부적으로 요청으로 리디렉션됩니다 port 5000, 기 때문에 해당 방법을 배포 된 docker run 명령, 이전 단계에서 설명한 것 처럼 합니다.

그림 5-14에 나와 있는 것 처럼는 터미널에서 curl을 사용 하 여 응용 프로그램을 테스트할 수도 있습니다. Windows에서 Docker 설치에서 기본 Docker 호스트 IP는 항상 컴퓨터의 실제 IP 주소와 함께 10.0.75.1 합니다.

![](./media/image19.png)

**그림 5-14**합니다. Curl을 사용 하 여 로컬로 Docker 응용 프로그램 테스트의 예

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>테스트 및 Visual Studio 2017을 사용 하 여 컨테이너 디버깅

실행 되 고 Visual Studio 2017을 사용 하 여 컨테이너 디버깅, 컨테이너 없이 실행 되는 때와 거의 동일한 방법으로.NET 응용 프로그램을 디버깅할 수 있습니다.

### <a name="testing-and-debugging-without-visual-studio"></a>테스트 및 Visual Studio가 없는 디버깅

편집기/CLI 방식을 사용 하 여를 개발 하는 경우 컨테이너를 디버깅 하는 것이 더 어렵기 및 추적을 생성 하 여 디버그 하려는 합니다.

### <a name="additional-resources"></a>추가 리소스

-   **로컬 Docker 컨테이너에서 앱 디버깅**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker 합니다. 빌드, 디버그, Docker 사용 하 여 ASP.NET Core 앱을 배포 합니다.** 비디오입니다.
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Visual Studio를 사용 하 여 컨테이너를 개발할 때 간소화 된 워크플로

효과적으로, Visual Studio를 사용 하는 경우 워크플로 편집기/CLI 방식을 사용 하는 경우 보다 훨씬 쉽습니다. 대부분의 Docker에 필요한 단계는 Dockerfile과 관련 docker compose.yml 파일 숨겨져 있거나 그림 5-15에 나와 있는 것 처럼 Visual Studio를 통해 보다 간단해 집니다.

![](./media/image20.png)

**그림 5-15**합니다. Visual Studio와 함께 개발 하는 경우 간소화 된 워크플로

또한 (프로젝트에 추가 Docker 지원) 2 단계를 한 번만 수행 해야 합니다. 따라서.NET 다른 개발 작업을 사용 하는 경우 워크플로 일반적인 개발 작업 비슷합니다. 실행 중인 내부적 (이미지 빌드 프로세스, 어떤 사용 하는 기본 이미지, 컨테이너 등의 배포) 하 고 경우에 따라 동작을 사용자 지정 하려면 Dockerfile 또는 docker compose.yml 파일을 편집 해야 알아야 합니다. 하지만 대부분의 작업은 훨씬 더 생산적 있게 되므로 Visual Studio를 사용 하 여 크게 단순화 합니다.

### <a name="additional-resources"></a>추가 리소스

-   **Steve Lasker 합니다. Visual Studio 2017 함께.NET docker 개발**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey 화 Fritz 합니다. Visual Studio에 대 한 새로운 Docker 도구를 사용 하 여 컨테이너에서.NET Core 앱 배치**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Dockerfile의 PowerShell 명령을 사용 하 여 Windows 컨테이너를 설정 

[Windows 컨테이너](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) Docker 이미지를 기존 Windows 응용 프로그램을 변환 하 고 Docker 생태계의 나머지 부분과 동일한 도구와 함께 배포할 수 있습니다. Windows 컨테이너를 사용 하려면 다음 예에서 같이 Dockerfile의 PowerShell 명령을 실행 합니다.

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

이 경우 Windows Server Core 기본 이미지 (FROM 설정) 하 고 PowerShell 명령 (실행 설정)를 사용 하 여 IIS를 설치 합니다. 유사한 방식 ASP.NET 4.x,.NET 4.6 또는 다른 Windows 소프트웨어와 같은 추가 구성 요소를 설정 하려면 PowerShell 명령을 사용할 수도 있습니다. 예를 들어 ASP.NET 4.5를 Dockerfile에 다음 명령을 설정합니다.

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>추가 리소스

-   **Dockerfile aspnet docker/입니다.** Windows 기능을 포함 하도록 dockerfile에서 실행 되도록 예제 Powershell 명령입니다.
    [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[이전] [다음]을 (index.md) (... / net-core-single-containers-linux-windows-server-hosts/index.md)
