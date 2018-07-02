---
title: Microsoft WCF dotnet-svcutil 도구
description: .NET Framework 프로젝트용 WCF svcutil 도구와 유사하게, .NET Core 및 ASP.NET Core 프로젝트 기능을 추가하는 Microsoft WCF dotnet-svcutil 도구에 대한 개요입니다.
author: mlacouture
ms.author: jralexander
ms.date: 06/04/2018
ms.openlocfilehash: c40dd9b437afe7381244b944228b6b2efe046eb2
ms.sourcegitcommit: d8bf4976eafe3289275be3811e7cb721bfff7e1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753424"
---
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a>Microsoft WCF dotnet-svcutil 도구

WCF(Windows Communication Foundation) **dotnet-svcutil** 도구는 네트워크 위치의 웹 서비스 또는 WSDL 파일에서 메타데이터를 검색하고, 해당 웹 서비스 작업에 액세스하는 클라이언트 프록시 메서드가 포함된 WCF 클래스를 생성하는 .NET Core CLI 도구입니다.

.NET Framework 프로젝트용 [**서비스 모델 메타데이터 - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구와 비슷하게, **dotnet-svcutil**은 .NET Core 및 .NET Standard 프로젝트와 호환되는 웹 서비스 참조를 생성하기 위한 명령줄 도구입니다.

**dotnet-svcutil** 도구는 Visual Studio 2017 v15.5와 함께 처음 제공된 [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio 연결 서비스 공급자에 대한 대체 옵션입니다. .NET Core CLI 도구인 **dotnet svcutil** 도구는 Linux, macOS, Windows에서 플랫폼 간에 사용할 수 있습니다.

> [!IMPORTANT]
> 신뢰할 수 있는 원본의 서비스만 참조해야 합니다. 신뢰할 수 없는 원본에서 참조를 추가하면 보안이 손상될 수 있습니다.

## <a name="prerequisites"></a>전제 조건

* [.NET Core SDK](https://www.microsoft.com/net/download) v1.0.4 이상 버전
* 선호하는 코드 편집기

## <a name="getting-started"></a>시작

다음 예제에서는 .NET Core 콘솔 프로젝트에 웹 서비스 참조를 추가하고 서비스를 호출하는 데 필요한 단계를 안내합니다. _HelloSvcutil_이라는 .NET Core 콘솔 응용 프로그램을 만들고 다음 계약을 구현하는 웹 서비스에 대한 참조를 추가합니다.

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

이 예제에서는 웹 서비스가 `http://contoso.com/SayHello.svc` 주소에서 호스트되는 것으로 가정합니다.

Windows, macOS 또는 Linux 명령 창에서 다음 단계를 수행합니다.

1. 프로젝트에 대해 _HelloSvcutil_ 디렉터리를 만들고 다음 예제와 같이 현재 디렉터리로 설정합니다.

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. 다음과 같이 [`dotnet new`](../tools/dotnet-new.md) 명령을 사용하여 해당 디렉터리에서 새 C# 콘솔 프로젝트를 만듭니다.

```console
dotnet new console
```

3. 편집기에서 `HelloSvcutil.csproj` 프로젝트 파일을 열고, `Project` 요소를 편집하고, 다음 코드를 사용하여 [`dotnet-svcutil` NuGet 패키지](https://nuget.org/packages/dotnet-svcutil)를 CLI 도구 참조로 추가합니다.

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.0" />
</ItemGroup>
```

4. 다음과 같이 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 사용하여 _dotnet-svcutil_ 패키지를 복원합니다.

```console
dotnet restore
```

5. _svcutil_ 명령과 함께 _dotnet_을 실행하여 다음과 같이 웹 서비스 참조 파일을 생성합니다.

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
생성된 파일은 _HelloSvcutil/ServiceReference1/Reference.cs_로 저장됩니다. 또한 _dotnet_svcutil_ 도구는 프록시 코드에 필요한 적절한 WCF 패키지를 프로젝트에 패키지 참조로 추가합니다.

6. 다음과 같이 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 사용하여 WCF 패키지를 복원합니다.

```console
dotnet restore
```

7. 편집기에서 `Program.cs` 파일을 열고, `Main()` 메서드를 편집하고, 자동 생성된 코드를 다음 코드로 바꿔서 웹 서비스를 호출합니다.

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. 다음과 같이 [`dotnet run`](../tools/dotnet-run.md) 명령을 사용하여 응용 프로그램을 실행합니다.

```console
dotnet run
```
“Hello dotnet-svcutil!” 출력이 표시됩니다.

`dotnet-svcutil` 도구 매개 변수에 대한 자세한 설명을 보려면 다음과 같이 help 매개 변수를 전달하는 도구를 호출합니다.

```console
dotnet svcutil --help
```

## <a name="next-steps"></a>다음 단계

### <a name="feedback--questions"></a>사용자 의견 및 질문

질문이나 의견이 있는 경우 [GitHub에서 문제를 엽니다](https://github.com/dotnet/wcf/issues/new). 또한 [GitHub의 WCF 리포지토리에서](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling) 기존 질문이나 문제를 검토할 수 있습니다.

### <a name="release-notes"></a>릴리스 정보

* 알려진 문제를 비롯한 업데이트된 릴리스 정보는 [릴리스 정보](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md)를 참조하세요.

### <a name="information"></a>정보

* [dotnet-svcutil NuGet 패키지](https://nuget.org/packages/dotnet-svcutil)
