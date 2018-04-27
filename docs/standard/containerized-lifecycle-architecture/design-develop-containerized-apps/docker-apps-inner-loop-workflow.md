---
title: Docker 앱에 대 한 내부 루프 개발 워크플로
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8ee1918091fe72e8606be6e7503ecd850084a4ba
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Docker 앱에 대 한 내부 루프 개발 워크플로

전체 DevOps 스패닝 외부 반복 워크플로 트리거하기 전에 순환, 모든 정보가 각 개발자의 컴퓨터에서 응용 프로그램 자체가 해당 기본 설정된 언어 또는 플랫폼을 사용 하 여 코딩과 로컬로 테스트 (그림 4-14). 하겠지만 모든 경우에 매우 중요 한 점은 공통적으로 선택 하는 언어, 프레임 워크 또는 플랫폼에 관계 없이 합니다. 이 특정 워크플로의 항상 개발 및 Docker 컨테이너를 로컬로 테스트 합니다.

![](./media/image18.png)

그림 4-14: 내부 루프 개발 컨텍스트

컨테이너 또는 Docker 이미지의 인스턴스는 이러한 구성 요소를 포함 됩니다.

-   운영 체제 선택 (예를 들어 Linux 배포 또는 Windows)

-   개발자 (예를 들어 응용 프로그램 이진 파일)가 추가 된 파일

-   구성 (예를 들어, 환경 설정 및 종속성)

-   Docker 실행을 처리 하는 것에 대 한 지침

(다음 섹션에서 설명) 프로세스로 Docker를 활용 하는 내부 루프 개발 워크플로를 설정할 수 있습니다. 한 번만 그렇게 해야 하기 때문에 환경을 설정 하는 초기 단계 포함 되어 있지 고려해 서 수행 합니다.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Visual Studio Code 및 Docker CLI를 사용 하 여 Docker 컨테이너 내에서 단일 응용 프로그램 작성

앱에서 사용자 고유의 서비스 추가 라이브러리 (종속성)로 구성 됩니다.

그림 4-15에서는 일반적으로 각 단계에 자세히 설명 뒤 Docker 앱을 개발할 때 수행 해야 하는 기본 단계를 보여 줍니다.

![](./media/image19.png)

그림 4-15: Docker CLI를 사용 하 여 Docker 컨테이너 화 가능한 응용 프로그램에 대 한 기간에 대 한 높은 수준의 워크플로

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>1 단계: Visual Studio Code에서 코딩을 시작 하 고 초기 응용 프로그램/서비스 기준 만들기

응용 프로그램을 개발 하는 방법은 Docker 없이 수행 하는 방법은 매우 비슷합니다. 에 차이가 있는지를 개발 하는 동안 배포 및 테스트 중인 응용 프로그램 또는 로컬 환경 (예: Linux VM 또는 Windows)에 배치 하는 Docker 컨테이너 내에서 실행 되는 서비스.

**로컬 환경 설정**

Mac 및 Windows 용 Docker의 최신 버전으로 이전에 Docker 응용 프로그램을 개발 하는 보다 훨씬 더 쉽게 및 설치가 간단 합니다.

**자세한 내용은** 이동에 대 한 지침은 Windows 용 Docker 설정, [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/)합니다.

에 대 한 지침은 Mac 용 Docker 설정로 이동 <https://docs.docker.com/docker-for-mac/>합니다.

또한 Docker CLI를 사용 하는 동안 응용 프로그램을 실제로 개발할 수 있도록 코드 편집기를 필요 합니다.

Microsoft 제공 Mac, Windows 및 Linux에서 지원 되 고 있는 IntelliSense를 제공 하는 간단한 코드 편집기는 Visual Studio Code [여러 언어에 대 한 지원](https://code.visualstudio.com/docs/languages/overview) (JavaScript,.NET, 이동, Java, Ruby, Python 및 가장 최신 언어의 경우) [디버깅](https://code.visualstudio.com/Docs/editor/debugging), [Git와의 통합](https://code.visualstudio.com/Docs/editor/versioncontrol) 및 [extensions 지원](https://code.visualstudio.com/docs/extensions/overview)합니다. 이 편집기는 Mac 및 Linux 개발자를 위한 매우 적합 합니다. Windows에서 전체 Visual Studio 응용 프로그램을 사용할 수 있습니다.

**자세한 내용은** 이동에 대 한 지침은 Visual Studio for Windows, Mac 또는 Linux를 설치, [ http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/ ](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/)합니다.

Docker CLI를 사용 하 고 다른 코드 편집기를 사용 하 여 코드를 작성 하지만 Dockerfile 작성자에 게 쉽게 및 docker compose.yml 파일 작업 영역에는 Visual Studio 코드를 사용 하는 경우. 또한 아래 Docker CLI를 사용 하 여 상세 작업 실행 될 수 있는 스크립트 물어봅니다 IDE에서 Visual Studio 코드 작업을 실행할 수 있습니다.

Visual Studio 코드를 설치 해야 하는 확장에 의해 제공 됩니다. 이렇게 하려면, 키를 눌러 Ctrl + Shift + P를 입력 **ext 설치**, 다음 확장을 실행 하 고: 설치 확장 명령을 마켓플레이스 확장 목록을 표시 합니다. 그런 다음 입력 **docker** 결과 필터링 하 그림 4-16 표시 된 것 처럼 Dockerfile 및 Docker 구성 파일 (yml) 지원 확장을 선택 합니다.

![](./media/image20.png)

그림 4-16: Visual Studio 코드에서 Docker 확장 설치

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>2 단계: 기존 이미지 (일반 운영 체제 또는.NET Core, Node.js, 및 Ruby와 같은 개발 환경)와 관련 된 DockerFile 만들기

DockerFile을 빌드해야 하는 사용자 지정 이미지 및 컨테이너를 배포 해야 합니다, 그리고 따라서 응용 프로그램은 하나의 사용자 지정 서비스 이루어진 경우 단일 DockerFile 해야 합니다. 그러나 응용 프로그램은 여러 서비스 (예: microservices 아키텍처)으로 구성 된 경우에 서비스 당 하나의 Dockerfile 필요 합니다.

DockerFile은 일반적으로 응용 프로그램 또는 서비스의 루트 폴더에 배치 하 고 해당 Docker를 설정 하 고 해당 응용 프로그램 또는 서비스를 실행 하는 방법을 알 수 있도록 필요한 명령이 포함 되어 합니다. DockerFile을 만들고 코드와 함께 프로젝트에 추가할 수 있습니다 (node.js,.NET Core 등), 또는 환경을 처음 접하는 경우 다음 팁을 참조 합니다.

> [!TIP]
> 라는 명령줄 도구를 사용할 수 있습니다 [yo docker](https://github.com/Microsoft/generator-docker)는 스 캐 폴드에서 선택 하 고 필요한 Docker 구성 파일을 추가 하 여 언어의 프로젝트 파일입니다. 기본적으로, 적절 한 DockerFile 생성을 지원 하기 위해 시작 하는 개발자가 docker-compose.yml 및 기타 관련된 스크립트 작성 하 고 Docker 컨테이너를 실행 합니다. 이 yeoman 생성기 선택한 개발 언어와 대상 컨테이너 호스트를 요청 하는 몇 가지 질문을 라는 나타납니다.

![yo docker](./media/image21.png)

Windows에서 및 Mac에서, 두 경우 모두 실행 yo docker를 생성 하는 샘플 코드 프로젝트 (현재.NET Core, Golang, 및 지원 되는 언어와 Node.js)에서 작동 하도록 이미 구성 되어 그림 4-17 터미널에서 두 가지 스크린샷입니다를 표시 하는 예를 들어, Docker의 맨 위로 이동 합니다.

![](./media/image22.PNG)  ![](./media/image23.png)

그림 4-17: yo docker 명령 창 (왼쪽)에서 고 Mac의 도구

그림 4-18를 사용 하는 예제 yo docker 다음 기존.NET Core 프로젝트에 스 캐 폴드 된 수를 표시 합니다.

![](./media/image24.PNG)

그림 4-18: yo 기존.NET core는 docker 프로젝트 준비

DockerFile에에서 (예: "보낸 사람 microsoft/dotnet:1.0.0-core" 사용) 사용 하 게 어떤 기본 Docker 이미지를 지정 합니다. 일반적으로 사용자 지정 이미지에서 공식 모든 리포지토리에서 얻을 수 있는 기본 이미지를 기반으로 빌드됩니다는 [Docker 허브 레지스트리](https://hub.docker.com/) (같은 [.NET Core에 대 한 이미지](https://hub.docker.com/r/microsoft/dotnet/) 또는 한 개의 [Node.js용](https://hub.docker.com/_/node/)).

***옵션 a: 기존 공식 Docker 이미지 사용***

언어 a c k의 공식 리포지토리를 사용 하 여 버전 번호를 가진 동일한 언어 기능을 모든 컴퓨터 (개발, 테스트 및 프로덕션 포함)에서 사용할 수 있는지 확인 합니다.

다음은.NET Core 컨테이너에 대 한 샘플 DockerFile입니다.

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

이 경우 microsoft/aspnetcore:1.0.1 라는 Linux 용 공식 ASP.NET Core Docker 이미지의 버전 1.0.1 사용 중인 합니다. 자세한 내용은 참조는 [ASP.NET Core Docker 이미지 페이지](https://hub.docker.com/r/microsoft/aspnetcore/) 및 [.NET Core Docker 이미지 페이지](https://hub.docker.com/r/microsoft/dotnet/)합니다. 사용자도 사용할 수 노드: 4와 같은 다른 비교 가능한 이미지-Node.js 또는에서 제공 되는 개발 언어에 대 한 다른 많은 미리 구성 된 이미지에 대 한 onbuild [Docker 허브](https://hub.docker.com/explore/)합니다.

DockerFile의 Docker (예: 포트 80) 런타임 시 사용할 TCP 포트를 수신 하도록 지시 해야 합니다.

Docker에서 응용 프로그램을 실행 하는 방법을 알 수 있도록 언어/프레임 워크를 사용 하는 따라 DockerFile에 추가할 수 있는 구성의 다른 줄 있습니다. ENTRYPOINT 줄을 해야 하는 예를 들어, \["dotnet", "MyCustomMicroservice.dll"\] 작성 하 고 서비스를 실행 하는 방법에 따라 여러 변형을 추가할을 포함할 수는 있지만.NET Core 응용 프로그램에 실행 되도록 합니다. 사용 중인 SDK 및 CLI dotnet 작성 하 고.NET 응용 프로그램을 실행 하는 경우 약간 다른 것입니다. 결론입니다 ENTRYPOINT 줄 및 줄에서 응용 프로그램에 대해 선택한 언어/플랫폼에 따라 다른을 수 있습니다.

**자세한 내용은** .NET Core 응용 프로그램에 대 한 Docker 이미지를 작성 하는 방법에 대 한 정보로 이동 <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>합니다.

사용자 고유의 이미지를 작성 하는 방법에 대 한 자세한 내용은 이동 [ https://docs.docker.com/engine/\자습서/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/)합니다.

**다중 플랫폼 이미지 리포지토리와**

Windows 컨테이너 점점 더 많이 사용 된, 단일 리포지토리에 플랫폼 변형 Linux 및 Windows 이미지 등을 포함할 수 있습니다. 이 단일 저장소와 같은 여러 플랫폼을 사용 하는 공급 업체에 대 한 가능 하 게 하는 Docker에 방문 하 고 새로운 기능 [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) DockerHub 레지스트리에서 사용할 수 있는 저장소입니다. 기능 활성화 되 면 서비스를 Windows 호스트에서이 이미지를 끌어오려면 끌어오고 Windows variant Linux variant 끌어오고 Linux 호스트에서 동일한 이미지 이름을 끌어오기 반면 합니다.

***처음부터 기본 이미지 b: 만들기 옵션***

이 항목에 설명 된 대로 처음부터 직접 Docker 기본 이미지를 만들 수 있습니다 [문서](https://docs.docker.com/engine/userguide/eng-image/baseimages/) Docker에서 합니다. Docker로 시작 하는 경우에 가장 적합 한 되지 않았을 수 있는 시나리오 이지만 기본 이미지의 특정 비트를 설정 하려는 경우 수행할 수 있습니다.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>3 단계: 서비스를 포함 하 여 사용자 지정 Docker 이미지 만들기

응용 프로그램을 구성 하는 각 사용자 지정 서비스에 대해 관련된 이미지를 만드는 데 필요 합니다. 응용 프로그램 구성 된 단일 서비스 또는 웹 앱을 단일 이미지 방금 해야 합니다.

> [!NOTE]
> 계정 "외부 루프 DevOps"워크플로 고려 하는 경우 이미지에서 생성 됩니다는 자동화 된 빌드 프로세스에 의해 해당 글로벌 환경에서 이미지를 만들 수는 소스 코드 (연속 통합) Git 리포지토리에 푸시 될 때마다 사용자 소스 코드입니다.

하지만 해당 외부 반복 경로 생각 전에 Docker 응용 프로그램이 실제로 제대로 작동 하는지 (Git 등) 소스 제어 시스템에 제대로 작동 하지 않을 수 있는 코드를 푸시 하지 않도록 확인 해야 합니다.

따라서 각 개발자는 전체 내부 루프 프로세스 로컬 테스트 및 개발 완전 한 기능 하거나 소스 제어 시스템으로 변경 해야 할 때까지 계속 작업을 수행 해야 하는 먼저 합니다.

로컬 환경 및 DockerFile을 사용 하 여 이미지를 만들려면 사용할 수 있듯이 그림 4-19 docker 빌드 명령 (실행할 수 있습니다 docker 작성-를 몇 가지 컨테이너/서비스에 의해 구성 되는 응용 프로그램에 대 한 빌드).

![](./media/image25.png)

그림 4-19: docker 빌드를 실행합니다.

필요에 따라 직접 docker를 실행 하는 대신 프로젝트의 폴더에서 빌드를 처음 실행된 dotnet를 사용 하 여 명령을 게시 하 고 docker 빌드를 실행 한 다음 필요한.NET 라이브러리와 함께 배포 가능한 폴더를 생성할 수 있습니다.

이 예제에서는이 Docker 이미지를 사용 하 여 만듭니다는 이름 cesardl/netcore-webapi-마이크로 서비스-docker: 첫 번째 (: 먼저가 한 개의 태그, 예: 특정 버전). 각 사용자 지정 이미지를 만들어야 할 여러 컨테이너를 사용 하 여 구성 된 Docker 응용 프로그램에 대해이 단계를 수행할 수 있습니다.

명령을 찾을 수 있습니다 기존 이미지 로컬 저장소 (개발 컴퓨터)에서 docker를 사용 하 여 이미지, 그림 4-20을 보여 주는 것 처럼 합니다.

![](./media/image26.png)

그림 4-20: 보기 docker 이미지를 사용 하 여 기존 이미지

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>4 단계: (선택 사항) 정의에서 docker compose.yml 여러 서비스를 사용 하는 구성 된 Docker 응용 프로그램을 빌드할 때 서비스

Docker compose.yml 파일에서 다음 단계에에서 설명 된 배포 명령을 사용 하 여 구성 된 응용 프로그램으로 배포 될 관련된 서비스 집합을 정의할 수 있습니다.

해당 프로그램 main에서 파일 또는 루트 솔루션 폴더를 만들어야 합니다. 유사 콘텐츠는 다음 docker compose.yml 파일에 있어야 합니다.

```yml
version: '2'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

이 특별 한 경우에이 파일은 두 서비스를 정의 합니다. (사용자 지정 서비스) 웹 서비스 및 redis 서비스 (인기 있는 캐시 서비스). 각 서비스를 각각에 대 한 구체적인 Docker 이미지를 사용 해야 하므로 컨테이너 기능을 배포 됩니다. 이 특정 웹 서비스에 대 한 이미지는 다음을 수행 해야 합니다.

-   현재 디렉터리에 DockerFile에서 빌드

-   노출 된 포트 80: 컨테이너 호스트 컴퓨터의 포트 81에 전달

-   프로젝트 디렉터리를 이미지를 다시 빌드하지 않고도 코드를 수정할 수 있도록 /code 컨테이너 내에 호스트에 탑재 하십시오.

-   웹 서비스는 redis 서비스에 연결

Redis 서비스에서 사용 하는 [최신 공용 redis 이미지](https://hub.docker.com/_/redis/) Docker 허브 레지스트리에서 찾아볼 수 있습니다. [redis](https://redis.io/) 는 서버 쪽 응용 프로그램을 위한 인기 있는 캐시 시스템.

### <a name="step-5-build-and-run-your-docker-app"></a>5 단계: 빌드 및 Docker 앱 실행

응용 프로그램에 단일 컨테이너에만 있는 경우 (VM 또는 실제 서버) Docker 호스트에 배포 하 여 실행 하기만 하면 됩니다. 그러나 앱 여러 서비스 이루어진 경우 해야 *작성*도 합니다. 다양 한 옵션을 살펴보겠습니다.

***A: 실행 단일 컨테이너 또는 서비스 옵션***

다음과 같이 명령을 실행 하는 docker를 사용 하 여 Docker 이미지를 실행할 수 있습니다.

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

Note를이 특정 배포에 대 한에서는 합니다 수 리디렉션 5000 내부 포트를 포트 80에 전송 된 요청입니다. 이제 응용 프로그램은 외부 포트는 호스트 수준에서 80에서 수신 대기 합니다.

***옵션 b: 작성 및 여러 컨테이너 응용 프로그램 실행***

대부분의 엔터프라이즈 시나리오에서 여러 서비스 Docker 응용 프로그램 구성 됩니다. 이러한 경우에는 명령을 실행할 수 있습니다 docker 작성를 (그림 4-21) 있으며에 이전에 만든 docker compose.yml 파일을 사용 합니다. 이 명령을 실행의 관련된 컨테이너의 모든 구성 된 응용 프로그램을 배포 합니다.

![](./media/image27.png)

그림 4-21: "docker-작성을" 명령을 실행 결과

Docker를 실행 한 후-를 작성, 그림 4-22에서 VM 표현에 표시 된 것 처럼 응용 프로그램 및 해당 관련된 컨테이너에 Docker 호스트에 배포 합니다.

![](./media/image28.png)

배포 된 Docker 컨테이너를 사용 하 여 그림 4-22: VM

참고 docker-작성을 및 docker 실행 하면 컨테이너 개발 환경에서 테스트를 위해 충분 수도 있지만 있습니다 수 전혀 사용 하지 않는 해당 Docker 클러스터 작업을 하기를 기대 하 고 docker는 Docker Swarm, Mesosphere DC/OS 또는 Kubernetes orchestrators와 같은 경우 까지 확장할 수 있습니다. 같은 클러스터를 사용 하 여 [docker는 Docker Swarm 모드](https://docs.docker.com/engine/swarm/) 배포 하 고 있는 경우 또는 단일 서비스에 대 한 docker 서비스 만들기와 같은 추가 명령을 사용 하 여 테스트 해야 (사용 가능 Docker에 대 한 Windows 및 Mac에서 1.12 버전 이후) 여러 컨테이너를 구성 하는 응용 프로그램을 배포, 번들 작성 docker를 사용 하 여 한 docker는 myBundleFile, 문서에 설명 된 대로 스택으로 구성 된 앱을 배포 하 여 배포 [분산 응용 프로그램 번들](https://blog.docker.com/2016/06/docker-app-bundle/) Docker에서 합니다.

에 대 한 [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) 및 [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) 다양 한 배포 명령 및 스크립트를 사용 합니다.

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>6 단계: (로컬로 로컬 CD VM)에서 Docker 응용 프로그램 테스트

이 단계는 앱이 수행 하는 따라 달라 집니다.

매우 간단한.NET Core Web API에서 "Hello World"로 단일 컨테이너 또는 서비스 배포를 DockerFile에 지정 된 TCP 포트를 제공 하 여 서비스에 액세스 해야만 합니다.

사용자가 서비스를 이동 하려면 localhost, 설정 되지 않은 경우는이 명령을 사용 하 여 컴퓨터에 대 한 IP 주소를 찾을:

docker 컴퓨터 ip *사용자 컨테이너 이름*

Docker 호스트에 브라우저를 열고 해당 사이트;로 이동 를 실행 하 여 응용 프로그램/서비스 그림 4-23에서와 같이 표시 됩니다.

![](./media/image29.png)

그림 4-23: localhost를 사용 하 여 로컬로 Docker 응용 프로그램 테스트

어떻게에 배포 된 docker run. 앞에서 설명한 대로 있기 때문에 포트 80을 사용 하지만 내부적으로 5000, 포트에 리디렉션되지가 note 합니다.

이 터미널에서 CURL을 사용 하 여 테스트할 수 있습니다. Windows에서 Docker 설치에서 기본 IP 그림 4-24 표시 된 것 처럼 10.0.75.1, 됩니다.

![](./media/image30.png)

그림 4-24: CURL을 사용 하 여 로컬로 Docker 응용 프로그램 테스트

**Docker에서 실행 중인 컨테이너 디버깅**

Node.js 및.NET Core 컨테이너 등의 다른 플랫폼을 사용 하는 경우 visual Studio 코드 디버깅 Docker를 지원 합니다.

또한 디버그할 수.NET Core 컨테이너 Docker에서 Visual Studio를 사용 하는 경우 다음 섹션에 설명 된 대로 합니다.

**추가 정보:** 이동 Node.js Docker 컨테이너를 디버깅 하는 방법에 대 한 자세한 내용은 <https://blog.docker.com/2016/07/live-debugging-docker/> 및 [ https://blogs.msdn.microsoft.com/\ \ 사용자\_ed/2016/02/27 / visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/)합니다.


>[!div class="step-by-step"]
[이전] (docker-앱-개발-environment.md) [다음] (visual-studio-도구-에-docker.md)
