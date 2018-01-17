---
title: ".NET Core와 Docker 기본 사항 알아보기"
description: "Docker 및 .NET Core 기본 자습서"
keywords: ".NET, .NET Core, Docker, 자습서"
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
ms.workload: dotnetcore
ms.openlocfilehash: 79ded2ce5de5100c18301127a2654f8791b8ed76
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="learn-docker-basics-with-net-core"></a>.NET Core와 Docker 기본 사항 알아보기

이 자습서에서는 Docker 컨테이너 빌드 및 .NET Core 응용 프로그램에 대한 배포 작업을 설명합니다. 이 자습서를 진행하면서 다음을 익히게 됩니다.

> [!div class="checklist"]
> * Dockerfile 파일을 만드는 방법
> * .NET Core 앱을 만드는 방법
> * 앱을 Docker 컨테이너에 배포하는 방법

[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform)은 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine)을 사용하여 [Docker 이미지](https://docs.docker.com/glossary/?term=image)로 앱을 신속하게 빌드하고 패키지합니다. 이러한 이미지는 [계층화된 컨테이너](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)에서 배포되고 실행되도록 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 형식으로 작성됩니다.

## <a name="net-core-easiest-way-to-get-started"></a>.NET Core: 시작하는 가장 쉬운 방법

Docker 이미지를 만들기 전에 컨테이너화할 응용 프로그램이 필요합니다. Linux, MacOS 또는 Windows에서 만들 수 있습니다. 작업을 수행하는 가장 빠르고 쉬운 방법은 .NET Core를 사용하는 것입니다.

.NET Core CLI 도구 집합에 익숙하지 않은 경우 [.NET Core SDK 개요](../tools/index.md)를 읽어 보세요.

[다중 아키텍처 기반 태그](https://github.com/dotnet/announcements/issues/14)를 사용하여 Windows와 Linux 컨테이너 모두를 빌드할 수 있습니다.

## <a name="your-first-net-core-docker-app"></a>첫 번째 .NET Core Docker 앱

### <a name="prerequisites"></a>필수 구성 요소

이 자습서를 완료하려면 다음이 필요합니다.

#### <a name="net-core-20-sdk"></a>.NET Core 2.0 SDK

* [.NET Core SDK 2.0](https://www.microsoft.com/net/core)을 설치합니다.

지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.

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

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>Dockerization에 대한 .NET Core 2.0 콘솔 앱 만들기

명령 프롬프트를 열고 *Hello*라는 폴더를 만듭니다. 만든 폴더로 이동하고 다음 명령을 입력합니다.

```console
dotnet new console
dotnet run
```

이제 간단한 연습을 해보겠습니다.

1. `$ dotnet new console`

   [`dotnet new`](../tools/dotnet-new.md)는 콘솔 앱을 빌드하는 데 필요한 종속성이 있는 최신 `Hello.csproj` 프로젝트 파일입니다.  응용 프로그램에 대한 진입점을 포함하는 기본 파일인 `Program.cs`도 만듭니다.
   
   `Hello.csproj`:

   프로젝트 파일은 종속성을 복원하고 프로그램을 빌드하는 데 필요한 모든 항목을 지정합니다.

   * `OutputType` 태그에서는 실행 파일, 즉 콘솔 응용 프로그램을 빌드하고 있음을 지정합니다.
   * `TargetFramework` 태그에서는 대상으로 하는 .NET 구현을 지정합니다. 고급 시나리오에서는 여러 대상 프레임워크를 지정하고 단일 작업에서 지정된 프레임워크로 빌드할 수 있습니다. 이 자습서에서는 .NET Core 2.0에 대해 빌드합니다.

   `Program.cs`:

   프로그램은 `using System`으로 시작됩니다. 즉, "`System` 네임스페이스의 모든 항목을 이 파일 범위로 가져옵니다". `System` 네임스페이스에는 `string` 또는 숫자 형식과 같은 기본 구문이 포함되어 있습니다.

   그런 다음 `Hello`라는 네임스페이스를 정의합니다. 네임스페이스를 원하는 값으로 변경할 수 있습니다. `Program`이라는 클래스는 해당 네임스페이스 내에서 인수로 문자열 배열을 사용하는 `Main` 메서드로 정의됩니다. 이 배열에는 컴파일된 프로그램을 호출할 때 전달된 인수 목록이 포함되어 있습니다. 예제에서 프로그램은 콘솔에 "Hello World!"만 표시합니다.

2. `$ dotnet restore`

   .NET Core 2.x에서 **dotnet new**는 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 실행합니다. **Dotnet restore**는 [NuGet](https://www.nuget.org/)(.NET 패키지 관리자) 호출로 종속성 트리를 복원합니다.
   NuGet은 다음 작업을 수행합니다.
   * *Hello.csproj* 파일 분석 
   * 파일 종속성 다운로드(또는 컴퓨터 캐시에서 가져오기)
   * *obj/project.assets.json* 파일 작성

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   *project.assets.json* 파일은 NuGet 종속성 그래프, 바인딩 해상도 및 다른 앱 메타데이터의 전체 집합입니다. 이 필수 파일은 소스 코드를 올바르게 처리하도록 [`dotnet build`](../tools/dotnet-build.md) 및 [`dotnet run`](../tools/dotnet-run.md) 등의 다른 도구에서 사용됩니다.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)는 성공적인 필드를 확인하기 위해 [`dotnet build`](../tools/dotnet-build.md)를 호출한 다음 응용 프로그램을 실행하기 위해 `dotnet <assembly.dll>`을 호출합니다.
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    고급 시나리오의 경우 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.

## <a name="dockerize-the-net-core-application"></a>.NET Core 응용 프로그램 Docker화

Hello .NET Core 콘솔 앱은 성공적으로 로컬로 실행됩니다. 이제 한 단계 나아가서 Docker에서 앱을 빌드하고 실행해 보겠습니다.

### <a name="your-first-dockerfile"></a>첫 번째 Dockerfile

텍스트 편집기를 열고 시작해 보겠습니다! 앱을 빌드한 Hello 디렉터리에서 계속 작업 중입니다.

Linux 또는 [Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/)용 다음 Docker 명령을 새 파일에 추가합니다. 완료되면 확장명 없이 Hello 디렉터리의 루트에 **Dockerfile**로 저장합니다(파일 형식을 `All types (*.*)` 또는 유사한 것으로 설정해야 할 수 있음).

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Dockerfile은 순서대로 실행되는 Docker 빌드 명령을 포함합니다.

첫 번째 명령은 [**FROM**](https://docs.docker.com/engine/reference/builder/#from)이어야 합니다. 이 명령은 새 빌드 단계를 초기화하고 나머지 명령에 대한 기본 이미지를 설정합니다. 다중 아키텍처 태그는 Windows [컨테이너 모드](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers)용 Docker에 따라 Windows 또는 Linux 컨테이너를 끌어옵니다. 샘플에 대한 기본 이미지는 microsoft/dotnet 리포지토리에서 2.0-sdk 이미지입니다.

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

[**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) 명령은 나머지 RUN, CMD, ENTRYPOINT, COPY 및 ADD Dockerfile 명령에 대해 작업 디렉터리를 설정합니다. 디렉터리가 없을 경우 만들어집니다. 이 경우 WORKDIR은 앱 디렉터리로 설정됩니다.

```Dockerfile
WORKDIR /app
```

[**COPY**](https://docs.docker.com/engine/reference/builder/#copy) 명령은 원본 경로에서 새 파일 또는 디렉터리를 복사하고 대상 컨테이너 파일 시스템에 추가합니다. 이 명령으로 C# 프로젝트 파일을 컨테이너에 복사합니다.

```Dockerfile
COPY *.csproj ./
```

[**RUN**](https://docs.docker.com/engine/reference/builder/#run) 명령은 현재 이미지를 기반으로 새 계층의 모든 명령을 실행하고 결과를 커밋합니다. 커밋된 결과 이미지는 Dockerfile의 다음 단계에 사용됩니다. C# 프로젝트 파일의 필요한 종속성을 가져오기 위해 **dotnet restore**를 실행하는 중입니다. 

```Dockerfile
RUN dotnet restore
```

이 **COPY** 명령은 파일의 나머지 부분을 새 [계층](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)의 컨테이너로 복사합니다.

```Dockerfile
COPY . ./
```

이 **RUN** 명령으로 앱을 게시하는 중입니다. [**dotnet publish**](../tools/dotnet-publish.md) 명령은 응용 프로그램을 컴파일하고, 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다. 앱은 **릴리스** 구성과 함께 게시되며 기본 디렉터리에 출력됩니다.

```Dockerfile
RUN dotnet publish -c Release -o out
```

[**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) 명령을 통해 컨테이너는 실행 파일로 실행할 수 있습니다.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

이제 다음을 수행하는 Dockerfile이 있습니다.

* 앱을 이미지에 복사
* 이미지에 대한 앱의 종속성
* 앱이 실행 파일로 실행되도록 빌드

### <a name="build-and-run-the-hello-net-core-20-app"></a>Hello .NET Core 2.0 앱 빌드 및 실행

#### <a name="essential-docker-commands"></a>필수 Docker 명령

필수 Docker 명령은 다음과 같습니다.

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>빌드 및 실행

dockerfile을 작성했습니다. 이제 Docker는 앱을 빌드한 다음 컨테이너를 실행합니다.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

`docker build` 명령의 출력은 다음 콘솔 출력과 유사해야 합니다.

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

출력에서 볼 수 있듯이 Docker 엔진은 컨테이너를 빌드하는 데 Dockerfile을 사용했습니다.

`docker run` 명령의 출력은 다음 콘솔 출력과 유사해야 합니다.

```console
Hello World!
```

지금까지 다음 작업을 수행했습니다.
> [!div class="checklist"]
> * 로컬 .NET Core 앱 생성
> * 첫 번째 컨테이너를 빌드하도록 Dockerfile 생성
> * Docker화된 앱 빌드 및 실행



## <a name="next-steps"></a>다음 단계

수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.

* [.NET Docker 이미지 비디오 소개](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker 및 Azure Container Instances의 시너지 효과!](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Azure 빠른 시작용 Docker](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Azure용 Docker에서 앱 배포](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Azure 구독이 없는 경우 무료 30일 계정에 [오늘 등록](https://azure.microsoft.com/free/?b=16.48)하고 Azure 크레딧 $200를 받아 원하는 조합의 Azure 서비스를 사용해 보세요.

## <a name="docker-images-used-in-this-sample"></a>이 샘플에 사용된 Docker 이미지

이 샘플에서는 다음 Docker 이미지가 사용됨

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>관련 참고 자료

* [.NET Core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Windows 컨테이너의 Dockerfile](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [.NET Framework Docker 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [DockerHub의 ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/)
* [.NET Core 응용 프로그램 Docker화 - Docker 자습서](https://docs.docker.com/engine/examples/dotnetcore/)
* [Visual Studio Docker 도구로 작업](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)(Azure Container Registry의 Docker 이미지를 Azure Container Instances에 배포)