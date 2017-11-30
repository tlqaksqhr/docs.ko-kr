---
title: ".NET core Docker 기본 사항 알아보기"
description: "Docker 및.NET Core 기본 자습서"
keywords: ".NET,.NET core, Docker, 자습서"
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
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a>.NET core Docker 기본 사항 알아보기

이 자습서에서는 Docker 컨테이너를 빌드 및.NET Core 응용 프로그램에 대 한 작업을 배포 합니다. 이 자습서는 과정을 자세히 배울 있습니다.

> [!div class="checklist"]
> * Dockerfile 파일을 만드는 방법
> * .NET Core 응용 프로그램을 만드는 방법.
> * Docker 컨테이너에 앱을 배포 하는 방법입니다.

[Docker 플랫폼](https://docs.docker.com/engine/docker-overview/#the-docker-platform) 사용 하 여는 [Docker 엔진](https://docs.docker.com/engine/docker-overview/#docker-engine) 을 신속 하 게 빌드하고로 앱을 패키지할 [Docker images](https://docs.docker.com/glossary/?term=image)합니다. 이러한 이미지 작성는 [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) 형식 수 배포에서 실행 하는 [컨테이너 계층에](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers)합니다.

## <a name="net-core-easiest-way-to-get-started"></a>.NET core: 가장 쉬운 방법은 시작 하려면

Docker 이미지를 만들기 전에 응용 프로그램을 컨테이너 화할 해야 합니다. Windows, Linux 또는 MacOS 등에서 만들 수 있습니다. 작업을 수행 하는 빠르고 쉬운 방법을.NET Core를 사용 하는 것입니다.

.NET Core CLI 도구 집합에 익숙하지 않은 경우 [.NET Core SDK 개요](../tools/index.md)를 읽어 보세요.

사용 하 여 Windows와 Linux 컨테이너를 빌드할 수 [다중 arch 기반 태그](https://github.com/dotnet/announcements/issues/14)합니다.

## <a name="your-first-net-core-docker-app"></a>첫 번째.NET Core Docker 앱

### <a name="prerequisites"></a>필수 구성 요소

이 자습서를 완료 합니다.

#### <a name="net-core-20-sdk"></a>.NET core 2.0 SDK

* 설치 [.NET Core SDK 2.0](https://www.microsoft.com/net/core)합니다.

지원 OS 버전 중 .NET Core 2.x를 지원하는 운영 체제 및 수명 주기 정책 링크는 [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)(.NET Core 2.x가 지원되는 OS 버전)를 참조하세요.

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

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>Dockerization에 대 한.NET Core 2.0 콘솔 응용 프로그램 만들기

명령 프롬프트를 열고 *Hello*라는 폴더를 만듭니다. 사용자가 만든 폴더를 찾아 다음 명령을 입력 합니다.

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
   * `TargetFramework` 태그에서는 대상으로 하는 .NET 구현을 지정합니다. 고급 시나리오에서는 여러 대상 프레임 워크를 지정 하 고 단일 작업에서 지정 된 프레임 워크를 구축할 수 있습니다. 이 자습서에서는.NET Core 2.0에 대 한 빌드합니다.

   `Program.cs`:

   프로그램을 시작 하 여 `using System`합니다. 이 문구는 의미 "의 모든 항목으로 전환한는 `System` 이 파일에 대 한 범위로 네임 스페이스입니다." `System` 네임스페이스에는 `string` 또는 숫자 형식과 같은 기본 구문이 포함되어 있습니다.

   그런 다음 `Hello`라는 네임스페이스를 정의합니다. 네임 스페이스를 원하는 대로 변경할 수 있습니다. `Program`이라는 클래스는 해당 네임스페이스 내에서 인수로 문자열 배열을 사용하는 `Main` 메서드로 정의됩니다. 이 배열에는 컴파일된 프로그램을 호출할 때 전달된 인수 목록이 포함되어 있습니다. 예제에서는 프로그램만 쓴 "Hello World!" 표시합니다.

2. `$ dotnet restore`

   .NET Core에서는 2.x **dotnet 새** 실행 되는 [ `dotnet restore` ](../tools/dotnet-restore.md) 명령입니다. **Dotnet 복원** 복원와 종속성 트리는 [NuGet](https://www.nuget.org/)(.NET 패키지 관리자) 호출 합니다.
   NuGet에서는 다음 작업을 수행합니다.
   * 분석 하는 *Hello.csproj* 파일 
   * 파일 다운로드 종속성 (또는 컴퓨터 캐시에서 가져와)
   * 기록 된 *obj/project.assets.json* 파일

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   *project.assets.json* 파일은 NuGet 종속성 그래프, 바인딩 해상도 및 다른 응용 프로그램 메타 데이터의 전체 집합입니다. 이 필수와 같은 다른 도구에서 사용은 파일 [ `dotnet build` ](../tools/dotnet-build.md) 및 [ `dotnet run` ](../tools/dotnet-run.md), 소스 코드를 올바르게 처리 하려면.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)호출 [ `dotnet build` ](../tools/dotnet-build.md) 성공적인 빌드를 차례로 호출을 확인 하려면 `dotnet <assembly.dll>` 응용 프로그램을 실행 합니다.
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    고급 시나리오에 대 한 참조 [.NET Core 응용 프로그램 배포](../deploying/index.md) 대 한 자세한 내용은 합니다.

## <a name="dockerize-the-net-core-application"></a>.NET Core 응용 프로그램 dockerize

Hello.NET Core 콘솔 앱 성공적으로 로컬로 실행합니다. 이제 보겠습니다 더 나아가 단계를 빌드 및 Docker에서 앱을 실행 합니다.

### <a name="your-first-dockerfile"></a>첫 번째 Dockerfile

텍스트 편집기를 열고 시작 해 보겠습니다! 응용 프로그램에 구축 Hello 디렉터리에서 계속 작업 중입니다.

어느 Linux에 대 한 다음 Docker 명령을 추가 또는 [Windows 컨테이너](https://docs.microsoft.com/virtualization/windowscontainers/about/) 새 파일에 있습니다. 완료 되 면으로 Hello 디렉터리의 루트에 저장 **Dockerfile**을 확장명이 없는 (파일 형식으로 설정 해야 `All types (*.*)` 또는 이와 유사한).

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

Dockerfile에 순서 대로 실행 되는 Docker 빌드 명령이 포함 되어 있습니다.

첫 번째 명령 이어야 [ **FROM**](https://docs.docker.com/engine/reference/builder/#from)합니다. 이 명령은 새 빌드 단계를 초기화 하 고 나머지 지시에 대 한 기본 이미지를 설정 합니다. 다중 아치 태그 Windows 용 Docker에 따라 Windows 또는 Linux 컨테이너를 끌어오도록 [컨테이너 모드](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers)합니다. 이 샘플에 대 한 기본 이미지는 microsoft/dotnet 리포지토리에서 2.0 sdk 이미지

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

[ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) 명령 작업 디렉터리 설정 모든 나머지 실행, CMD, ENTRYPOINT, 복사 및 추가 Dockerfile에 대 한 지침입니다. 디렉터리가 존재 하지 않는 경우 자동으로 만들어집니다. 이 경우 WORKDIR 앱 디렉터리로 설정 됩니다.

```Dockerfile
WORKDIR /app
```

[ **복사** ](https://docs.docker.com/engine/reference/builder/#copy) 명령 원본 경로에서 새 파일 또는 디렉터리를 복사 하 고 대상 컨테이너 파일 시스템에 추가 합니다. 이 명령으로 C# 프로젝트 파일 컨테이너에 복사 합니다.

```Dockerfile
COPY *.csproj ./
```

[ **실행** ](https://docs.docker.com/engine/reference/builder/#run) 명령 현재 이미지를 기반으로 새 계층의 모든 명령을 실행 하 고 결과 커밋합니다. 결과 커밋된 이미지는 Dockerfile의 다음 단계에 사용 됩니다. 실행 중인 **dotnet 복원** C# 프로젝트 파일의 필요한 종속성을 가져오려면 합니다. 

```Dockerfile
RUN dotnet restore
```

이 **복사** 복사 하는 명령 파일의 나머지 부분에이 컨테이너에 새 [레이어](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers)합니다.

```Dockerfile
COPY . ./
```

이 응용 프로그램 게시 **실행** 명령입니다. [ **dotnet 게시** ](../tools/dotnet-publish.md) 명령은 응용 프로그램을 컴파일하고, 프로젝트 파일에 지정 된 종속성을 읽는다는 및 디렉터리에 파일의 결과 집합을 게시 합니다. 앱과 함께 게시 되는 **릴리스** 구성 및 기본 디렉터리에 출력 합니다.

```Dockerfile
RUN dotnet publish -c Release -o out
```

[ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) 명령 실행 파일로 실행할 컨테이너 수 있습니다.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Dockerfile 이제입니다.

* 앱 이미지 복사
* 이미지에 대 한 응용 프로그램의 종속성
* 앱이 실행 파일로 실행 되도록 작성

### <a name="build-and-run-the-hello-net-core-20-app"></a>Hello.NET Core 2.0 앱 빌드 및 실행

#### <a name="essential-docker-commands"></a>필수 Docker 명령

필수 이러한 Docker 명령은 다음과 같습니다.

* [docker 빌드](https://docs.docker.com/engine/reference/commandline/build/)
* [docker 실행](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker 이미지](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>빌드 및 실행

Dockerfile; 작성 했습니다. 이제 Docker는 응용 프로그램을 작성 하 고 컨테이너를 실행 합니다.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

출력을는 `docker build` 명령 콘솔 출력은 다음과 같은 형태가 됩니다.

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

출력에서 보시 Docker 엔진 사용 Dockerfile이 컨테이너를 빌드합니다.

출력을는 `docker run` 명령 콘솔 출력은 다음과 같은 형태가 됩니다.

```console
Hello World!
```

지금까지 바로 사용할 수 있습니다.
> [!div class="checklist"]
> * 로컬.NET Core 응용 프로그램 작성
> * 만든 첫 번째 컨테이너를 만들려는 Dockerfile
> * 빌드되고 Dockerized 앱 실행



## <a name="next-steps"></a>다음 단계

수행할 수 있는 몇 가지 다음 단계는 다음과 같습니다.

* [.NET Docker 이미지 비디오 소개](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker 및 Azure 컨테이너 인스턴스 시너지 효과!](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Azure Quickstarts 용 docker](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Azure에 대 한 Docker에서 앱 배포](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Azure 구독이 없는 경우 [바로 등록할](https://azure.microsoft.com/free/?b=16.48) 무료 30 일 계정 및 Azure 서비스의 조합을 사용해 Azure 크레딧에서 get $200에 대 한 합니다.

## <a name="docker-images-used-in-this-sample"></a>이 샘플에 사용 되는 docker 이미지

이 예제에 사용 된 다음 Docker 이미지

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>관련 참고 자료

* [.NET core Docker 샘플](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Windows 컨테이너의 Dockerfile](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [.NET framework Docker 샘플](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [DockerHub에서 ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/)
* [.NET Core 응용 프로그램-Docker 자습서 dockerize](https://docs.docker.com/engine/examples/dotnetcore/)
* [Visual Studio Docker 도구 사용](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Azure 컨테이너 인스턴스를 Azure 컨테이너 레지스트리에서 Docker 이미지 배포](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)