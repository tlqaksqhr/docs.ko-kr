---
title: Docker에서 호스트되는 마이크로 서비스 - C#
description: Docker 컨테이너에서 실행되는 ASP.NET Core 서비스를 만드는 방법 알아보기
ms.date: 02/03/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 7428051c1d9a29ba98ca1f28288b3c50ea36ae1a
ms.sourcegitcommit: 54231aa56fca059e9297888a96fbca1d4cf3746c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
---
# <a name="microservices-hosted-in-docker"></a>Docker에서 호스트되는 마이크로 서비스

이 자습서에서는 Docker 컨테이너에서 ASP.NET Core 마이크로 서비스를 빌드 및 배포하는 데 필요한 작업에 대해 설명합니다. 이 자습서를 진행하면서 다음을 익히게 됩니다.

* Yeoman를 사용하여 ASP.NET Core 응용 프로그램을 생성하는 방법
* 개발 Docker 환경을 만드는 방법
* 기존 이미지에 따라 Docker 이미지를 빌드하는 하는 방법
* 서비스를 Docker 컨테이너에 배포하는 방법

이러한 방법을 진행하면서 다음과 같은 일부 C# 언어 기능도 확인합니다.

* C# 개체를 JSON 페이로드로 변환하는 방법
* 변경할 수 없는 데이터 전송 개체를 빌드하는 방법
* 들어오는 HTTP 요청을 처리하고 HTTP 응답을 생성하는 방법
* null 허용 값 형식을 사용하는 방법

이 항목에 대한 [샘플 앱을 보거나 다운로드](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice)할 수 있습니다. 다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.

### <a name="why-docker"></a>Docker를 사용해야 하는 이유

Docker를 사용하면 데이터 센터 또는 공용 클라우드에서 서비스를 호스트하는 표준 컴퓨터 이미지를 쉽게 만들 수 있습니다. Docker는 이미지를 구성하고, 필요할 때 이미지를 복제하여 응용 프로그램의 설치 크기를 조정할 수 있도록 합니다.

이 자습서의 모든 코드는 모든 .NET Core 환경에서 작동합니다.
Docker 설치를 위한 추가 작업은 ASP.NET Core 응용 프로그램에 해당합니다. 

## <a name="prerequisites"></a>전제 조건
.NET Core를 실행하도록 컴퓨터에 설정해야 합니다. [.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.
Windows, Ubuntu Linux, macOS 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다. 선호하는 코드 편집기를 설치해야 합니다. 아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다. 그러나 익숙한 어떤 도구도 사용 가능합니다.

또한 Docker 엔진을 설치해야 합니다. 사용하는 플랫폼에 대한 지침을 보려면 [Docker 설치 페이지](http://www.docker.com/products/docker)를 참조하세요.
Docker는 여러 Linux 배포판, macOS 또는 Windows에 설치할 수 있습니다. 위에 참조된 페이지에는 사용 가능한 각 설치에 대한 섹션이 포함되어 있습니다.

설치할 대부분의 구성 요소는 패키지 관리자에서 수행됩니다. node.js의 패키지 관리자 `npm`이 설치된 경우 이 단계를 건너뛰어도 됩니다. 그렇지 않은 경우 [nodejs.org](https://nodejs.org)에서 최신 NodeJs를 설치합니다. 그러면 npm 패키지 관리자가 설치됩니다. 

이제 ASP.NET Core 개발을 지원하는 다양한 명령줄 도구를 설치해야 합니다. 명령줄 템플릿은 Yeoman, Bower, Grunt 및 Gulp를 사용합니다. 적절한 템플릿이 설치되어 있으면 즐겨 사용하는 셸에 다음을 입력합니다.

`npm install -g yo bower grunt-cli gulp`

`-g` 옵션은 전역 설치임을 나타내므로 해당 도구를 시스템 전체에서 사용할 수 있습니다. (로컬 설치의 경우 패키지가 단일 프로젝트에 적용됨). 이러한 핵심 도구를 설치한 후 yeoman ASP.NET 템플릿 생성기를 설치해야 합니다.

`npm install -g generator-aspnet`

## <a name="create-the-application"></a>응용 프로그램 만들기

이제 모든 도구를 설치했으므로 새로운 ASP.NET Core 응용 프로그램을 만들어 보겠습니다. 명령줄 생성기를 사용하려면 즐겨 사용하는 셸에서 다음 yeoman 명령을 실행합니다.

`yo aspnet`

이 명령은 만들려는 응용 프로그램의 종류를 선택하라는 메시지를 표시합니다. 이 마이크로 서비스에 대해 가능한 가장 간단하고 가장 경량의 웹 응용 프로그램에서 만들려고 하므로 '빈 웹 응용 프로그램'을 선택합니다. 템플릿은 이름을 묻는 메시지를 표시합니다. 'WeatherMicroservice'를 선택합니다. 

템플릿은 다음 8개의 파일을 만듭니다.

* ASP.NET Core 응용 프로그램에 대해 사용자 지정된 .gitignore
* Startup.cs 파일. 여기에는 응용 프로그램의 기본 사항이 포함됩니다.
* Program.cs 파일. 여기에는 응용 프로그램의 진입점이 포함됩니다.
* WeatherMicroservice.csproj 파일. 응용 프로그램에 대한 빌드 파일입니다.
* Dockerfile. 이 스크립트는 응용 프로그램에 대한 Docker 이미지를 만듭니다.
* README.md. 다른 ASP.NET Core 리소스에 대한 링크를 포함합니다.
* web.config 파일. 기본 구성 정보를 포함합니다.
* runtimeconfig.template.json 파일. IDE에 사용되는 디버깅 설정을 포함합니다.

이제 템플릿 생성 응용 프로그램을 실행할 수 있습니다. 이 작업은 명령줄에서 일련의 도구를 사용하여 수행합니다. `dotnet` 명령은 .NET 개발에 필요한 도구를 실행합니다. 각 동사는 다른 명령을 실행합니다.

첫 번째 단계는 모든 종속성을 복원하는 것입니다.

```console
dotnet restore
```

Dotnet은 NuGet 패키지 관리자를 사용하여 필요한 모든 패키지를 응용 프로그램 디렉터리에 설치합니다. 또한 project.json.lock 파일을 생성합니다. 이 파일에는 참조되는 각 패키지에 대한 정보가 포함됩니다. 모든 종속성을 복원한 후 응용 프로그램을 빌드합니다.

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

일단 응용 프로그램을 빌드한 후에는 명령줄에서 실행합니다.

```console
dotnet run
```

기본 구성은 `http://localhost:5000`을 수신 대기합니다. 브라우저를 열고 해당 페이지로 이동하면 "Hello World!" 반환됩니다.

### <a name="anatomy-of-an-aspnet-core-application"></a>ASP.NET Core 응용 프로그램 분석

응용 프로그램을 빌드했으므로 기능이 구현되는 방식을 살펴보겠습니다. 생성된 파일 중에서 이 시점에서 특히 흥미로운 2개의 파일은 project.json과 Startup.cs입니다. 

Project.json에는 프로젝트에 대한 정보가 포함됩니다. 자주 사용하는 두 개의 노드는 '종속성'과 '프레임워크'입니다. 종속성 노드에는 이 응용 프로그램에 필요한 모든 패키지가 나열됩니다.
현재 이 노드는 작으며 웹 서버를 실행하는 패키지만 필요합니다.

'프레임워크' 노드는 이 응용 프로그램을 실행하는 .NET Framework의 버전 및 구성을 지정합니다.

응용 프로그램은 Startup.cs에서 구현됩니다. 이 파일에는 startup 클래스가 포함되어 있습니다.

두 메서드는 ASP.NET Core 인프라에서 응용 프로그램을 구성 및 실행하기 위해 호출됩니다. `ConfigureServices` 메서드는 이 응용 프로그램에 필요한 서비스에 대해 설명합니다. Lean 마이크로 서비스를 빌드하는 경우 어떤 종속성도 구성할 필요가 없습니다. `Configure` 메서드는 들어오는 HTTP 요청에 대한 처리기를 구성합니다. 템플릿은 텍스트 'Hello World!'를 포함하는 모든 요청에 응답하는 간단한 처리기를 생성합니다.

## <a name="build-a-microservice"></a>마이크로 서비스 빌드

빌드하려는 서비스는 전 세계 어디에서든지 날씨 보고서를 전달할 것입니다. 프로덕션 응용 프로그램에서는 날씨 데이터를 검색하기 위해 몇 가지 서비스를 호출할 수 있습니다. 이 샘플에서는 임의 일기 예보를 생성합니다. 

임의 날씨 서비스를 구현하기 위해 수행해야 하는 많은 작업이 있습니다.

* 들어오는 요청을 구문 분석하여 위도와 경도를 읽습니다.
* 일부 임의 예보 데이터를 생성합니다.
* C# 개체의 임의 예보 데이터를 JSON 패킷으로 변환합니다.
* 사용자 서비스가 JSON을 다시 전송함을 나타내도록 응답 헤더를 설정합니다.
* 응답을 씁니다.

다음 섹션에서는 이러한 각 단계를 안내합니다.

### <a name="parsing-the-query-string"></a>쿼리 문자열 구문 분석.

먼저 쿼리 문자열을 구문 분석합니다. 서비스는 다음 형식으로 쿼리 문자열의 'lat' 및 'long' 인수를 수락합니다.

`http://localhost:5000/?lat=-35.55&long=-12.35`  

수행해야 하는 모든 변경 내용은 람다 식에 startup 클래스의 `app.Run`에 대한 인수로 정의되어 있습니다.

람다 식의 인수는 요청에 대한 `HttpContext`입니다. 해당 속성 중 하나는 `Request` 개체입니다. `Request` 개체는 요청에 대한 쿼리 문자열에 있는 모든 값의 사전을 포함하는 `Query` 속성을 갖습니다. 첫 번째 추가 내용은 위도 및 경도 값을 확인하는 것입니다.

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

쿼리 사전 값은 `StringValue` 형식입니다. 해당 형식에는 문자열 컬렉션이 포함될 수 있습니다. 날씨 서비스의 경우 각 값이 단일 문자열입니다. 이 때문에 위의 코드에서 `FirstOrDefault()`가 호출되는 것입니다. 

다음에는 문자열을 double 값으로 변환해야 합니다. 문자열을 double로 변환하는 데 사용하는 메서드는 `double.TryParse()`입니다.

```csharp
bool TryParse(string s, out double result);
```

이 메서드는 C# out 매개 변수를 사용하여 입력 문자열을 double로 변환할 수 있는지를 나타냅니다. 문자열이 double에 대한 유효한 표현을 나타낼 경우 이 메서드는 true를 반환하고 `result` 인수는 값을 포함합니다. 문자열이 유효한 double을 나타내지 않을 경우 이 메서드는 false를 반환합니다.

*null 허용 double*을 반환하는 *확장 메서드*를 사용하여 해당 API를 조정할 수 있습니다. *null 허용 값 형식*은 일부 값 형식을 나타내는 형식으로 누락된 값 또는 null 값을 포함할 수도 있습니다. Null 허용 형식은 형식 선언에 `?` 문자를 추가하여 나타냅니다. 

확장 메서드는 정적 메서드로 정의되지만 첫 번째 매개 변수에 `this` 한정자를 추가하여 마치 해당 클래스의 멤버인 것처럼 호출할 수 있습니다. 확장 메서드는 정적 클래스에서만 정의할 수 있습니다. 구문 분석을 위한 확장 메서드를 포함하는 클래스의 정의는 다음과 같습니다.

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

`default(double?)` 식은 `double?` 형식의 기본값을 반환합니다. 기본값은 null(또는 누락된) 값입니다.

이 확장 메서드를 사용하여 쿼리 문자열 인수를 double 형식으로 변환할 수 있습니다.

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

구문 분석 코드를 쉽게 테스트하기 위해 인수 값을 포함하도록 응답을 업데이트합니다.

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

이제 웹 응용 프로그램을 실행하고 구문 분석 코드가 작동하는지 확인할 수 있습니다. 브라우저에서 웹 요청에 값을 추가합니다. 그러면 업데이트된 결과가 표시됩니다.

### <a name="build-a-random-weather-forecast"></a>임의 일기 예보 빌드

다음 작업은 임의 일기 예보를 빌드하는 것입니다. 일기 예보에 대해 원하는 값을 포함하는 데이터 컨테이너부터 시작하겠습니다.

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

다음에는 해당 값을 임의로 설정하는 생성자를 빌드합니다. 이 생성자는 위도 및 경도 값을 사용하여 난수 생성기를 시드합니다. 즉, 같은 위치에 대한 예보는 동일합니다. 위도 및 경도 대한 인수를 변경하면 다른 예보를 얻게 됩니다(다른 시드로 시작하므로).

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

이제 응답 메서드에서 5일 예보를 생성할 수 있습니다.

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a>JSON 응답을 빌드합니다.

서버의 최종 코드 작업은 WeatherReport 배열을 JSON 패킷으로 변환하고 클라이언트에 다시 전송하는 것입니다. 먼저 JSON 패킷을 만들어 보겠습니다. 종속성 목록에 NewtonSoft JSON Serializer를 추가합니다. 이 경우 `dotnet` CLI를 사용하면 됩니다.

```
dotnet add package Newtonsoft.Json
```

그런 다음 `JsonConvert` 클래스를 사용하여 개체를 문자열에 쓸 수 있습니다.

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

위의 코드는 예보 개체(`WeatherForecast` 개체 목록)를 JSON 패킷으로 변환합니다. 응답 패킷을 생성한 다음 콘텐츠 형식을 `application/json`으로 설정하고 문자열을 씁니다.

이제 응용 프로그램이 실행되고 임의 예보를 반환합니다.

## <a name="build-a-docker-image"></a>Docker 이미지 빌드

마지막 작업은 Docker에서 응용 프로그램을 실행하는 것입니다. 응용 프로그램을 나타내는 Docker 이미지를 실행하는 Docker 컨테이너를 만들 것입니다.

***Docker 이미지***는 응용 프로그램을 실행하기 위한 환경을 정의하는 파일입니다.

***Docker 컨테이너***는 실행 중인 Docker 이미지 인스턴스를 나타냅니다.

비유하자면 *Docker 이미지*를 *클래스*로, *Docker 컨테이너*를 개체 또는 해당 클래스의 인스턴스로 생각할 수 있습니다.  

ASP.NET 템플릿에서 만들어진 Dockerfile이 현재 작업에 사용됩니다. 해당 내용을 살펴보겠습니다.

첫 번째 줄은 소스 이미지를 지정합니다.

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

Docker를 사용하여 소스 템플릿을 기준으로 컴퓨터 이미지를 구성할 수 있습니다. 시작할 때 컴퓨터의 모든 매개 변수를 제공할 필요는 없으며 변경 내용만 제공하면 됩니다. 여기서 변경은 응용 프로그램을 포함하는 것입니다.

이 첫 번째 샘플에서는 `1.1-sdk-msbuild` 버전의 dotnet 이미지를 사용합니다. 이것이 작업 Docker 환경을 만드는 가장 쉬운 방법입니다. 이 이미지는 dotnet core 런타임 및 dotnet SDK를 포함합니다. 이 이미지를 사용하면 보다 쉽게 시작하고 빌드할 수 있지만 더 큰 이미지가 만들어집니다.

다음 5개 줄은 응용 프로그램을 설정하고 빌드합니다.

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroService.csproj .
RUN dotnet restore 

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

현재 디렉터리의 프로젝트 파일에 Docker VM으로 복사되고 모든 패키지가 복원됩니다. dotnet CLI를 사용하면 Docker 이미지에 .NET Core SDK가 포함됩니다. 그런 다음 응용 프로그램의 나머지 부분이 복사되고 dotnet publish 명령이 응용 프로그램을 빌드하고 패키지합니다.

파일의 마지막 줄은 응용 프로그램을 실행합니다.

```
ENTRYPOINT ["dotnet", "out/WeatherMicroService.dll", "--server.urls", "http://0.0.0.0:5000"]
```

이 구성된 포트는 Dockerfile의 마지막 줄에 있는 `dotnet`에 대한 `--server.urls` 인수에서 참조됩니다. `ENTRYPOINT` 명령은 서비스를 시작하는 명령 및 명령줄 옵션을 Docker에 알립니다. 

## <a name="building-and-running-the-image-in-a-container"></a>컨테이너에서 이미지 빌드 및 실행

이미지를 빌드하고 Docker 컨테이너 내의 서비스를 실행해 보겠습니다. 로컬 디렉터리의 모든 파일을 이미지에 복사하려고 하지는 않을 것입니다. 대신 컨테이너에서 응용 프로그램에 빌드합니다. `.dockerignore` 파일을 만들고 이미지로 복사되지 않는 디렉토리를 지정합니다. 빌드 자산은 복사하고 싶지 않을 수 있습니다. 빌드를 지정하고 디렉터리를 `.dockerignore` 파일에 게시합니다.

```
bin/*
obj/*
out/*
```

`docker build` 명령을 사용하여 이미지를 빌드합니다. 코드를 포함하는 디렉터리에서 다음 명령을 실행합니다.

```console
docker build -t weather-microservice .
```

이 명령은 Dockerfile의 모든 정보를 기반으로 컨테이너 이미지를 빌드합니다. `-t` 인수는 이 컨테이너 이미지에 대한 태그 또는 이름을 제공합니다. 위의 명령줄에서 Docker 컨테이너에 사용되는 태그는 `weather-microservice`입니다. 이 명령이 완료되면 컨테이너에서 새 서비스를 실행할 준비가 된 것입니다. 

다음 명령을 실행하여 컨테이너를 시작하고 서비스를 실행합니다.

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

`-d` 옵션은 현재 터미널에서 분리된 컨테이너를 실행하는 것을 의미합니다. 즉, 터미널에 명령 출력에 표시되지 않습니다. `-p` 옵션은 서비스와 호스트 사이의 포트 매핑을 나타냅니다. 여기서는 포트 80으로 들어오는 모든 요청이 컨테이너의 포트 5000으로 전달되어야 한다고 표시됩니다. 5000을 사용하면 서비스가 위의 Dockerfile에 지정된 명령줄 인수에서 수신을 대기하는 포트가 검색됩니다. `--name` 인수는 실행 중인 컨테이너의 이름을 지정합니다. 해당 컨테이너 관련 작업을 수행할 때 사용할 수 있는 편리한 이름입니다. 

다음 명령을 확인하여 이미지가 실행 중인지 알아볼 수 있습니다.

```console
docker ps
```

컨테이너가 실행 중인 경우 실행 중인 프로세스에서 해당 컨테이너를 나열하는 줄이 표시됩니다. (하나만 있을 수 있음).

브라우저를 열고 localhost로 이동한 후 위도 및 경도를 지정하여 서비스를 테스트할 수 있습니다.

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a>실행 중인 컨테이너에 연결

명령 창에서 서비스를 실행할 때는 각 요청에 대해 출력되는 진단 정보를 볼 수 있습니다. 컨테이너가 분리 모드에서 실행 중인 경우에는 해당 정보가 표시되지 않습니다. Docker attach 명령을 사용하면 실행 중인 컨테이너에 연결하여 로그 정보를 볼 수 있습니다.  명령 창에서 다음 명령을 실행합니다.

```console
docker attach --sig-proxy=false hello-docker
```

`--sig-proxy=false` 인수는 `Ctrl-C` 명령이 컨테이너 프로세스에 전송되지 않고 오히려 `docker attach` 명령을 중지함을 의미합니다. 마지막 인수는 `docker run` 명령에서 컨테이너에 지정된 이름입니다. 

> [!NOTE]
> 또한 Docker 할당 컨테이너 ID를 사용하여 컨테이너를 나타낼 수도 있습니다. `docker run`에서 컨테이너의 이름을 지정하지 않은 경우 컨테이너 ID를 사용해야 합니다.

브라우저를 열고 서비스로 이동합니다. 연결된 실행 중인 컨테이너에서 명령 창의 진단 메시지를 확인합니다.

`Ctrl-C`를 눌러 연결 프로세스를 중지합니다.

컨테이너 작업이 끝났으면 중지할 수 있습니다.

```console
docker stop hello-docker
```

컨테이너와 이미지는 여전히 다시 시작하는 데 사용할 수 있습니다.  컴퓨터에서 컨테이너를 제거하려는 경우 다음 명령을 사용합니다.

```console
docker rm hello-docker
```

컴퓨터에서 사용하지 않은 이미지를 제거하려는 경우 다음 명령을 사용합니다.

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a>결론 

이 자습서에서는 ASP.NET Core 마이크로 서비스를 빌드하고 몇 가지 간단한 기능을 추가했습니다.

해당 서비스에 대해 Docker 컨테이너 이미지를 빌드하고 컴퓨터에서 해당 컨테이너를 실행했습니다. 터미널 창을 서비스에 연결하고 서비스에서 진단 메시지를 확인했습니다.

그 과정에서 C# 언어의 일부 기능이 사용되는 것을 확인했습니다.
