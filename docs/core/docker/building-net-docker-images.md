---
title: ".NET Core Docker 이미지 작성"
description: "Docker 이미지 및 .NET Core 이해"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a>.NET Core 응용 프로그램에 대한 Docker 이미지 작성

 이 자습서에서는 Docker에서.NET Core를 사용 하는 방법에 집중 합니다. 첫째, 살펴볼 제공 되며 Microsoft 및 사용 사례에서 유지 관리 하는 서로 다른 Docker 이미지입니다. 에서는 빌드 및 ASP.NET Core 응용 프로그램 dockerize 하는 방법을 알아봅니다.

이 자습서는 과정을 자세히 배울 있습니다.
> [!div class="checklist"]
> * Microsoft.NET Core Docker 이미지에 대 한 자세한 내용은 
> * ASP.NET Core Dockerize에 샘플 응용 프로그램 가져오기
> * ASP.NET 샘플 앱을 로컬로 실행
> * 빌드 및 Linux 컨테이너에 대 한 Docker가 있는 샘플 실행
> * 빌드 및 Windows 용 Docker 컨테이너와 샘플을 실행 합니다.

## <a name="docker-image-optimizations"></a>Docker 이미지 최적화

개발자를 위한 Docker 이미지를 작성할 때 다음 세 가지 주요 시나리오를 중점적으로 고려했습니다.

* .NET Core 앱을 개발하는 데 사용되는 이미지
* .NET Core 앱을 빌드하는 데 사용되는 이미지
* .NET Core 앱을 실행하는 데 사용되는 이미지

왜 이 세 가지 이미지가 중요할까요?
개발, 빌드 및 실행 중인 컨테이너 화 된 응용 프로그램 때 서로 다른 우선 해야 합니다.

* **개발:** 변경 내용 및 변경 내용을 디버깅 하는 기능에 신속 하 게 우선 순위 중점적 반복 합니다. 이미지의 크기를으로 중요 하지 않습니다, 그리고 대신 수 변경 코드를 신속 하 게 참조 하세요?

* **빌드:** 이 이미지는 컴파일러 및 이진 파일을 최적화 하기 위해 다른 종속성을 포함 하 여 응용 프로그램을 컴파일하는 데 필요한 모든 항목을 포함 합니다.  이미지를 프로덕션에 배치 하는 자산을 만드는 빌드 이미지를 사용 합니다. 연속 통합 또는 빌드 환경에서 빌드 이미지를 사용할 것입니다. 이 방법은 빌드 에이전트를 컴파일하고 빌드 이미지 인스턴스에서 (모든 필수 종속성)이 있는 응용 프로그램을 빌드할 수 있도록 합니다. 빌드 에이전트는 이 Docker 이미지를 실행하는 방법만 알고 있으면 됩니다.

* **프로덕션:** 배포 하 고 이미지를 시작할 수 속도? 이 이미지 Docker 호스트에 Docker 레지스트리에서 네트워크 성능을 최적화 하도록 작습니다. 콘텐츠를 실행할 준비가 되면 Docker 실행부터 결과 처리까지 가장 빠른 시간에 수행할 수 있습니다. 동적 코드 컴파일에 Docker 모델에 필요 하지 않습니다. 이 이미지에 배치되는 콘텐츠는 이진 파일과 응용 프로그램을 실행하는 데 필요한 콘텐츠로 제한됩니다.

    예를 들어는 `dotnet publish` 출력에 포함 되어 있습니다.

    * 컴파일된 이진 파일
    * .css 및.js 파일


포함 하는 이유는 `dotnet publish` 프로덕션 이미지에서 명령 출력은 변경 하지 않으려면 해당 '는 최소 크기입니다.

일부.NET Core 이미지 최신 태그를 다운로드 하는 것은 비교적 단순해 프로세스 않도록 다른 태그 간의 계층을 공유 합니다. 컴퓨터에 이전 버전이 이미 있는 경우이 아키텍처는 필요한 디스크 공간을 줄입니다.

동일한 컴퓨터에 공용 이미지를 사용 하는 여러 응용 프로그램, 메모리 공용 이미지 간에 공유 됩니다. 이미지를 공유할 수 동일 해야 합니다.

## <a name="docker-image-variations"></a>Docker 이미지 변형

목표를 달성 하기 위, 아래 이미지 변형 제공 [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/)합니다.

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`)이이 이미지는.NET Core 및 명령줄 도구 (CLI)을 포함 하는.NET Core SDK를 포함 합니다. 이 이미지는 **개발 시나리오**에 매핑됩니다. 이 이미지를 사용 하 여 로컬 개발, 디버깅 및 단위 테스트에 대 한 합니다. 이 이미지는 **빌드** 시나리오에도 사용할 수 있습니다. 사용 하 여 `microsoft/dotnet:sdk` 항상 최신 버전을 제공 합니다.

> [!TIP]
> 사용 하려는 경우 확실 하지 않은 사용자의 요구에 대 한,는 `microsoft/dotnet:<version>-sdk` 이미지입니다. Throw가으로 사용할 수 있도록 설계 했습니다 "사실상" 이미지로 트래버스하여 컨테이너 (소스 코드를 탑재 및 응용 프로그램을 시작 컨테이너 시작) 및 다른 이미지를 작성 하는 기본 이미지입니다.

* `microsoft/dotnet:<version>-runtime`:이 이미지.NET Core (런타임 및 라이브러리)을 포함 하 고 실행 중인.NET Core 응용 프로그램에 최적화 되어 **프로덕션**합니다.

## <a name="alternative-images"></a>대체 이미지

개발, 빌드 및 프로덕션에 최적화된 시나리오 외에도 추가 이미지를 제공합니다.

* `microsoft/dotnet:<version>-runtime-deps`: **런타임 deps** 이미지.NET Core에서 필요한 네이티브 종속성의 모든 운영 체제를 포함 합니다. 이 이미지에 대 한는 [자체 포함 된 응용 프로그램](https://docs.microsoft.com/dotnet/core/deploying/index)합니다.

각 변형의 최신 버전:

* `microsoft/dotnet`또는 `microsoft/dotnet:latest` (SDK 이미지에 대 한 별칭)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>탐색 하는 샘플

* [이 ASP.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) 프로덕션에 대 한 앱 ASP.NET Core 용 Docker 이미지를 구성 하기 위한 모범 사례 패턴을 보여 줍니다. 샘플은 Windows와 Linux 컨테이너에서 작동합니다.

* 이.NET Core Docker 샘플에 대 한 모범 사례 패턴 [프로덕션에 대 한.NET Core 응용 프로그램에 대 한 Docker 이미지를 작성 합니다.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)

## <a name="your-first-aspnet-core-docker-app"></a>첫 번째 ASP.NET Core Docker 앱

이 자습서에서는 dockerize 하고자 하는 앱에 대 한 ASP.NET Core Docker 샘플 응용 프로그램을 사용 하 여 수 있습니다. ASP.NET Core Docker 샘플 응용 프로그램에이 프로덕션에 대 한 앱 ASP.NET Core 용 Docker 이미지를 구성 하기 위한 모범 사례 패턴을 보여 줍니다. 샘플은 Windows와 Linux 컨테이너에서 작동합니다.

Dockerfile 샘플 ASP.NET Core 런타임 Docker 기본 이미지 기반으로 ASP.NET Core 응용 프로그램 Docker 이미지를 만듭니다.

사용 하 여는 [여러 단계로 이루어진 Docker 빌드 기능](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) 에:

* 에 따라 컨테이너에서 샘플을 빌드하는 **큰** ASP.NET Core 빌드 Docker 기본 이미지 
* 최종 빌드 결과에 따라 Docker 이미지를에 복사는 **더 작은** ASP.NET Core Docker 런타임 기본 이미지

> [!Note]
> 빌드 이미지 런타임 이미지는 손실 응용 프로그램을 빌드하는 필요한 도구를 포함 합니다.

### <a name="prerequisites"></a>필수 구성 요소

빌드하고 실행 하려면 다음 항목을 설치 합니다.

#### <a name="net-core-20-sdk"></a>.NET core 2.0 SDK

* 설치 [.NET Core SDK 2.0](https://www.microsoft.com/net/core)합니다.

* 아직 없는 경우, 즐겨 찾는 코드 편집기를 설치 합니다.

> [!TIP]
> 코드 편집기를 설치 해야? 시도 [Visual Studio](https://visualstudio.com/downloads)!

#### <a name="installing-docker-client"></a>Docker 클라이언트를 설치합니다.

설치 [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) Docker 클라이언트의 이상.

에 Docker 클라이언트를 설치할 수 있습니다.

* Linux 배포

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/)합니다.

#### <a name="installing-git-for-sample-repository"></a>샘플 저장소에 대 한 Git 설치

* 설치 [git](https://git-scm.com/download) 리포지토리 복제 하려는 경우.

### <a name="getting-the-sample-application"></a>샘플 응용 프로그램 가져오기

복제 하 여이 샘플을 가져오는 가장 쉬운 방법은 [샘플 리포지토리](https://github.com/dotnet/dotnet-docker-samples) git에서 다음 지침을 사용 하 여: 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

또한.NET Core Docker 샘플 리포지토리에서 zip으로 (에 작은) 저장소를 다운로드할 수 있습니다.

### <a name="run-the-aspnet-app-locally"></a>ASP.NET 응용 프로그램을 로컬로 실행

참조 지점으로 응용 프로그램을 컨테이너화하기 전에 먼저 로컬로 응용 프로그램을 실행합니다.

작성 하 고 (지침에서는 저장소의 루트를 가정 하는 데 사용) 다음 명령을 사용 하 여.NET Core 2.0 SDK와 함께 응용 프로그램을 로컬로 실행할 수 있습니다.

```console
cd aspnetapp
dotnet run
```

응용 프로그램이 시작 된 후 방문 **http://localhost:5000** 웹 브라우저에서 합니다.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>빌드 및 Linux 컨테이너에 대 한 Docker가 있는 샘플 실행

빌드하고 수 있습니다 (지침에서는 저장소의 루트를 가정 하는 데 사용) 다음 명령을 사용 하 여 Linux 컨테이너를 사용 하 여 Docker에서 샘플을 실행 합니다.

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] `docker run` '-p' 인수 지도 포트 컨테이너에는 80으로 로컬 컴퓨터에서 5000 포트 (포트 매핑 폼이 `host:container`). 자세한 내용은 참조는 [docker 실행](https://docs.docker.com/engine/reference/commandline/exec/) 명령줄 매개 변수에 대 한 참조입니다.

응용 프로그램이 시작 된 후 방문 **http://localhost:5000** 웹 브라우저에서 합니다.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>빌드 및 Windows 용 Docker 컨테이너와 샘플을 실행 합니다.

빌드하고 수 있습니다 (지침에서는 저장소의 루트를 가정 하는 데 사용) 다음 명령을 사용 하 여 Windows 컨테이너를 사용 하 여 Docker에서 샘플을 실행 합니다.

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> 이동 해야 합니다는 **컨테이너 IP 주소** (http://localhost) 대비 직접 브라우저에서 Windows 컨테이너를 사용 하는 경우. 다음 단계를 컨테이너의 IP 주소를 가져올 수 있습니다.

* 다른 명령 프롬프트를 엽니다.
* 실행 `docker ps` 프로그램 실행 중인 컨테이너를 볼 수 있습니다. "Aspnetcore_sample" 컨테이너가 있어야 합니다.
* `docker exec aspnetcore_sample ipconfig`를 실행합니다.
* 컨테이너 IP 주소를 복사 하 고 (예를 들어 172.29.245.43) 브라우저에 붙여 넣습니다.

> [!Note]
> Docker exec 식별 컨테이너의 이름이 나 해시를 지원합니다. 이름 (aspnetcore_sample) 예에서 사용 됩니다.

다음 예제에서는 실행 중인 Windows 컨테이너의 IP 주소를 얻어야 하는 방법의를 참조 하십시오.

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

> [!Note]
> Docker exec 실행 중인 컨테이너에 새 명령을 실행합니다. 자세한 내용은 참조는 [docker exec 참조](https://docs.docker.com/engine/reference/commandline/exec/) 에 명령줄 매개 변수입니다.

사용 하 여 로컬로 프로덕션 배포를 준비 하는 응용 프로그램을 만들 수 있습니다는 [dotnet 게시](../tools/dotnet-publish.md) 명령입니다.

```console
dotnet publish -c release -o published
```

> [!Note]
> -C 릴리스 인수 (기본값은 디버그 모드) 릴리스 모드에서 응용 프로그램을 작성 합니다. 자세한 내용은 참조는 [dotnet run 참조](../tools/dotnet-run.md) 명령줄 매개 변수에 대.

응용 프로그램을 실행할 수 있습니다 **Windows** 다음 명령을 사용 합니다.

```console
dotnet published\aspnetapp.dll
```

응용 프로그램을 실행할 수 있습니다 **Linux** 또는 **macOS** 다음 명령을 사용 합니다.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>이 샘플에 사용 되는 docker 이미지

이 예제에 사용 된 다음 Docker 이미지

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

지금까지 바로 사용할 수 있습니다.
> [!div class="checklist"]
> * Microsoft.NET Core Docker 이미지에 대 한 학습
> * ASP.NET Core Dockerize에 샘플 응용 프로그램을 가져왔습니다.
> * ASP.NET 샘플 앱을 로컬로 실행
> * 빌드 및 Linux 컨테이너에 대 한 Docker가 있는 샘플 실행
> * 빌드 및 Windows 용 Docker 컨테이너와 샘플을 실행 했습니다.


**다음 단계**

수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.

* [Visual Studio Docker 도구 사용](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Azure 컨테이너 인스턴스를 Azure 컨테이너 레지스트리에서 Docker 이미지 배포](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Visual Studio 코드를 사용 하 여 디버깅](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [가져오기 손에 Visual Studio와 함께 Mac, 컨테이너 및 서버 없이 코드에 대 한 클라우드](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Mac 랩 용 Docker 및 Visual Studio 시작](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> Azure 구독이 없는 경우 [바로 등록할](https://azure.microsoft.com/free/?b=16.48) 무료 30 일 계정 및 Azure 서비스의 조합을 사용해 Azure 크레딧에서 get $200에 대 한 합니다.
