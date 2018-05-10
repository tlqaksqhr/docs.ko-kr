---
title: .NET Core Docker 이미지 작성
description: Docker 이미지 및 .NET Core 이해
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: dotnet-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.custom: mvc
manager: wpickett
ms.workload:
- dotnetcore
ms.openlocfilehash: c1983be59b4a961cabd94915852e0cab7811682c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="building-docker-images-for-net-core-applications"></a>.NET Core 응용 프로그램에 대한 Docker 이미지 작성

 이 자습서에서는 Docker에서 .NET Core를 사용하는 방법에 초점을 둡니다. 먼저 Microsoft에서 제공되고 관리되는 서로 다른 Docker 이미지를 살펴보고 사례를 사용합니다. 그런 다음 ASP.NET Core 앱을 빌드하고 Docker화하는 방법을 배웁니다.

이 자습서를 진행하면서 다음을 익히게 됩니다.
> [!div class="checklist"]
> * Microsoft .NET Core Docker 이미지에 대해 알아보기 
> * Docker화할 ASP.NET Core 샘플 앱 가져오기
> * ASP.NET 샘플 앱을 로컬로 실행
> * Linux 컨테이너용 Docker로 샘플 빌드 및 실행
> * Windows 컨테이너용 Docker로 샘플 빌드 및 실행

## <a name="docker-image-optimizations"></a>Docker 이미지 최적화

개발자를 위한 Docker 이미지를 작성할 때 다음 세 가지 주요 시나리오를 중점적으로 고려했습니다.

* .NET Core 앱을 개발하는 데 사용되는 이미지
* .NET Core 앱을 빌드하는 데 사용되는 이미지
* .NET Core 앱을 실행하는 데 사용되는 이미지

왜 이 세 가지 이미지가 중요할까요?
컨테이너화된 응용 프로그램을 개발, 빌드 및 실행할 때 서로 다른 우선 순위가 있습니다.

* **개발:** 우선 순위는 신속하게 변경 내용을 반복하고 변경 내용을 디버그하는 기능에 초점을 둡니다. 이미지의 크기는 중요하지 않으며 코드를 변경하고 변경 내용을 신속하게 확인할 수 있나요?

* **빌드:** 이 이미지는 컴파일러 및 이진 파일을 최적화하는 다른 종속성을 포함하는 앱을 컴파일하는 데 필요한 모든 항목을 포함합니다.  빌드 이미지를 사용하여 프로덕션 이미지로 배치하는 자산을 만듭니다. 빌드 이미지는 연속 통합 또는 빌드 환경에서 사용됩니다. 이 방법은 빌드 에이전트가 빌드 이미지 인스턴스에서 응용 프로그램(필요한 모든 종속성과 함께)을 컴파일하고 빌드할 수 있도록 합니다. 빌드 에이전트는 이 Docker 이미지를 실행하는 방법만 알고 있으면 됩니다.

* **프로덕션:** 이미지를 얼마나 빠르게 배포하고 시작할 수 있나요? 이 이미지는 작기 때문에 Docker 레지스트리에서 Docker 호스트로 네트워크 성능이 최적화됩니다. 콘텐츠를 실행할 준비가 되면 Docker 실행부터 결과 처리까지 가장 빠른 시간에 수행할 수 있습니다. 동적 코드 컴파일은 Docker 모델에 필요하지 않습니다. 이 이미지에 배치되는 콘텐츠는 이진 파일과 응용 프로그램을 실행하는 데 필요한 콘텐츠로 제한됩니다.

    예를 들어 `dotnet publish` 출력은 다음을 포함합니다.

    * 컴파일된 이진 파일
    * .js 및 .css 파일


프로덕션 이미지에 `dotnet publish` 명령 출력을 포함하는 이유는 해당 크기를 최소로 유지하기 위해서입니다.

일부 .NET Core 이미지는 다른 태그 간의 계층을 공유하므로 최신 태그를 다운로드하는 것은 비교적 간단한 프로세스입니다. 컴퓨터에 이전 버전이 이미 있는 경우 이 아키텍처는 필요한 디스크 공간을 줄입니다.

동일한 컴퓨터에서 여러 응용 프로그램이 공용 이미지를 사용하는 경우 메모리는 공용 이미지 간에 공유됩니다. 이미지는 공유되도록 동일해야 합니다.

## <a name="docker-image-variations"></a>Docker 이미지 변형

위의 목표를 달성하기 위해 [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/)에서 이미지 변형을 제공합니다.

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) 이 이미지는 .NET Core 및 CLI(명령줄 도구)가 포함된 .NET Core SDK를 포함합니다. 이 이미지는 **개발 시나리오**에 매핑됩니다. 로컬 개발, 디버깅 및 단위 테스트에 이 이미지를 사용합니다. 이 이미지는 **빌드** 시나리오에도 사용할 수 있습니다. `microsoft/dotnet:sdk`를 사용하면 항상 최신 버전을 제공합니다.

> [!TIP]
> 필요한 것이 확실하지 않은 경우 `microsoft/dotnet:<version>-sdk` 이미지를 사용하려고 합니다. "de facto" 이미지로 삭제 컨테이너로 사용되도록 디자인되었으며(소스 코드 탑재 및 앱을 시작하도록 컨테이너 시작) 기본 이미지로 다른 이미지를 빌드하도록 디자인되었습니다.

* `microsoft/dotnet:<version>-runtime`: 이 이미지는 .NET Core(런타임 및 라이브러리)를 포함하며 **프로덕션**에서 실행 중인 .NET Core 앱에 최적화되어 있습니다.

## <a name="alternative-images"></a>대체 이미지

개발, 빌드 및 프로덕션에 최적화된 시나리오 외에도 추가 이미지를 제공합니다.

* `microsoft/dotnet:<version>-runtime-deps`: **runtime-deps** 이미지는 .NET Core에 필요한 모든 기본 종속성과 함께 운영 체제를 포함합니다. 이 이미지는 [자체 포함된 응용 프로그램](../deploying/index.md)을 위한 것입니다.

각 변형의 최신 버전:

* `microsoft/dotnet` 또는 `microsoft/dotnet:latest`(SDK 이미지에 대한 별칭)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>탐색할 샘플

* [이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp)은 프로덕션용 ASP.NET Core 앱에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다. 샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.

* 이 .NET Core Docker 샘플은 [프로덕션용 .NET Core 앱에 대한 Docker 이미지를 빌드](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)하는 것과 관련한 모범 사례 패턴을 보여 줍니다.

## <a name="your-first-aspnet-core-docker-app"></a>첫 번째 ASP.NET Core Docker 앱

이 자습서의 경우 docker화하려는 앱에 대한 ASP.NET Core Docker 샘플 응용 프로그램을 사용하도록 합니다. 이 ASP.NET Core Docker 샘플 응용 프로그램은 프로덕션용 ASP.NET Core 앱에 대한 Docker 이미지를 빌드하는 것과 관련한 모범 사례 패턴을 보여 줍니다. 샘플은 Linux 컨테이너와 Windows 컨테이너 둘 다에서 작동합니다.

샘플 Dockerfile은 ASP.NET Core 런타임 Docker 기본 이미지 기반의 ASP.NET Core 응용 프로그램 Docker 이미지를 만듭니다.

다음 작업을 수행하는 데 [Docker 다단계 빌드 기능](https://docs.docker.com/engine/userguide/eng-image/multistage-build/)을 사용합니다.

* **더 큰** ASP.NET Core 빌드 Docker 기본 이미지에 따라 컨테이너에서 샘플 빌드 
* **더 작은** ASP.NET Core Docker 런타임 기본 이미지에 따라 최종 빌드 결과를 Docker 이미지로 복사

> [!NOTE]
> 빌드 이미지는 응용 프로그램을 빌드하는 데 필요한 도구를 포함하는 반면 런타임 이미지는 그렇지 않습니다.

### <a name="prerequisites"></a>전제 조건

빌드하고 실행하려면 다음 항목을 설치합니다.

#### <a name="net-core-20-sdk"></a>.NET Core 2.0 SDK

* [.NET Core SDK 2.0](https://www.microsoft.com/net/core)을 설치합니다.

* 아직 없는 경우 즐겨 찾는 코드 편집기를 설치합니다.

> [!TIP]
> 코드 편집기를 설치해야 하나요? [Visual Studio](https://visualstudio.com/downloads)를 체험해 보세요.

#### <a name="installing-docker-client"></a>Docker 클라이언트 설치

[Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) 이상의 Docker 클라이언트를 설치합니다.

Docker 클라이언트를 다음에 설치할 수 있습니다.

* Linux 배포

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/)

#### <a name="installing-git-for-sample-repository"></a>샘플 리포지토리용 Git 설치

* 리포지토리를 복제하려는 경우 [git](https://git-scm.com/download)를 설치합니다.

### <a name="getting-the-sample-application"></a>샘플 응용 프로그램 가져오기

샘플을 가져오는 가장 쉬운 방법은 다음 지침을 사용하여 git로 [샘플 리포지토리](https://github.com/dotnet/dotnet-docker-samples)를 복제하는 것입니다. 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

.NET Core Docker 샘플 리포지토리에서 zip으로 리포지토리(작음)를 다운로드할 수도 있습니다.

### <a name="run-the-aspnet-app-locally"></a>ASP.NET 앱을 로컬로 실행

참조 지점으로 응용 프로그램을 컨테이너화하기 전에 먼저 로컬로 응용 프로그램을 실행합니다.

다음 명령을 사용하여 .NET Core 2.0 SDK와 함께 응용 프로그램을 로컬로 빌드하고 실행할 수 있습니다(지침에서는 리포지토리의 루트를 가정).

```console
cd aspnetapp
dotnet run
```

응용 프로그램이 시작된 후 웹 브라우저에서 **http://localhost:5000**을 방문합니다.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Linux 컨테이너용 Docker로 샘플 빌드 및 실행

다음 명령을 사용하여 Linux 컨테이너를 사용하는 Docker에서 샘플을 빌드하고 실행할 수 있습니다(지침에서는 리포지토리의 루트를 가정).

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> `docker run` '-p' 인수는 로컬 컴퓨터의 포트 5000을 컨테이너의 포트 80으로 매핑합니다(포트 매핑 형식은 `host:container`). 자세한 내용은 명령줄 매개 변수의 [docker run](https://docs.docker.com/engine/reference/commandline/exec/) 참조를 참조하세요.

응용 프로그램이 시작된 후 웹 브라우저에서 **http://localhost:5000**을 방문합니다.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Windows 컨테이너용 Docker로 샘플 빌드 및 실행

다음 명령을 사용하여 Windows 컨테이너를 사용하는 Docker에서 샘플을 빌드하고 실행할 수 있습니다(지침에서는 리포지토리의 루트를 가정).

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> Windows 컨테이너를 사용하는 경우 브라우저에서 **컨테이너 IP 주소**(http://localhost)와 반대로)로 이동해야 합니다. 다음 단계를 사용하여 컨테이너의 IP 주소를 가져올 수 있습니다.

* 다른 명령 프롬프트를 엽니다.
* `docker ps`를 실행하여 실행 중인 컨테이너를 봅니다. "aspnetcore_sample" 컨테이너가 있어야 합니다.
* `docker exec aspnetcore_sample ipconfig`를 실행합니다.
* 컨테이너 IP 주소를 복사하고 브라우저로 붙여 넣습니다(예: 172.29.245.43).

> [!NOTE]
> Docker exec는 이름 또는 해시로 컨테이너 식별을 지원합니다. 예제에서는 이름(aspnetcore_sample)이 사용됩니다.

실행 중인 Windows 컨테이너의 IP 주소를 가져오는 방법의 다음 예제를 참조하세요.

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!NOTE]
> Docker exec는 실행 중인 컨테이너에서 새 명령을 실행합니다. 자세한 내용은 명령줄 매개 변수의 [docker exec 참조](https://docs.docker.com/engine/reference/commandline/exec/)를 참조하세요.

[dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 프로덕션에 로컬로 배포할 준비가 된 응용 프로그램을 만들 수 있습니다.

```console
dotnet publish -c release -o published
```

> [!NOTE]
> -c 릴리스 인수는 릴리스 모드에서 응용 프로그램을 빌드합니다(기본값은 디버그 모드). 자세한 내용은 명령줄 매개 변수의 [docker run 참조](../tools/dotnet-run.md)를 참조하세요.

다음 명령을 사용하여 **Windows**에서 응용 프로그램을 실행할 수 있습니다.

```console
dotnet published\aspnetapp.dll
```

다음 명령을 사용하여 **Linux** 또는 **macOS**에서 응용 프로그램을 실행할 수 있습니다.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>이 샘플에 사용된 Docker 이미지

이 샘플에서는 다음 Docker 이미지가 사용됨

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

지금까지 다음 작업을 수행했습니다.
> [!div class="checklist"]
> * Microsoft .NET Core Docker 이미지에 대해 알아보기
> * Docker화할 ASP.NET Core 샘플 앱 가져오기
> * ASP.NET 샘플 앱을 로컬로 실행
> * Linux 컨테이너용 Docker로 샘플 빌드 및 실행
> * Windows 컨테이너용 Docker로 샘플 빌드 및 실행


**다음 단계**

수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.

* [Visual Studio Docker 도구로 작업](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Azure Container Registry의 Docker 이미지를 Azure Container Instances에 배포](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)(Visual Studio Code를 사용한 디버깅) 
* [클라우드에서 Mac용 Visual Studio, 컨테이너 및 서버리스 코드에 익숙해지기](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)(Docker 및 Mac용 Visual Studio 랩 시작)

> [!NOTE]
> Azure 구독이 없는 경우 무료 30일 계정에 [오늘 등록](https://azure.microsoft.com/free/?b=16.48)하고 Azure 크레딧 $200를 받아 원하는 조합의 Azure 서비스를 사용해 보세요.
