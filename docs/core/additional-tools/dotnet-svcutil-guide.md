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
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a><span data-ttu-id="e135f-103">Microsoft WCF dotnet-svcutil 도구</span><span class="sxs-lookup"><span data-stu-id="e135f-103">Microsoft WCF dotnet-svcutil tool</span></span>

<span data-ttu-id="e135f-104">WCF(Windows Communication Foundation) **dotnet-svcutil** 도구는 네트워크 위치의 웹 서비스 또는 WSDL 파일에서 메타데이터를 검색하고, 해당 웹 서비스 작업에 액세스하는 클라이언트 프록시 메서드가 포함된 WCF 클래스를 생성하는 .NET Core CLI 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="e135f-105">.NET Framework 프로젝트용 [**서비스 모델 메타데이터 - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구와 비슷하게, **dotnet-svcutil**은 .NET Core 및 .NET Standard 프로젝트와 호환되는 웹 서비스 참조를 생성하기 위한 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="e135f-106">**dotnet-svcutil** 도구는 Visual Studio 2017 v15.5와 함께 처음 제공된 [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio 연결 서비스 공급자에 대한 대체 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="e135f-107">.NET Core CLI 도구인 **dotnet svcutil** 도구는 Linux, macOS, Windows에서 플랫폼 간에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-107">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e135f-108">신뢰할 수 있는 원본의 서비스만 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="e135f-109">신뢰할 수 없는 원본에서 참조를 추가하면 보안이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e135f-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="e135f-110">Prerequisites</span></span>

* <span data-ttu-id="e135f-111">[.NET Core SDK](https://www.microsoft.com/net/download) v1.0.4 이상 버전</span><span class="sxs-lookup"><span data-stu-id="e135f-111">[.NET Core SDK](https://www.microsoft.com/net/download) v1.0.4 or later versions</span></span>
* <span data-ttu-id="e135f-112">선호하는 코드 편집기</span><span class="sxs-lookup"><span data-stu-id="e135f-112">Your favorite code editor</span></span>

## <a name="getting-started"></a><span data-ttu-id="e135f-113">시작</span><span class="sxs-lookup"><span data-stu-id="e135f-113">Getting started</span></span>

<span data-ttu-id="e135f-114">다음 예제에서는 .NET Core 콘솔 프로젝트에 웹 서비스 참조를 추가하고 서비스를 호출하는 데 필요한 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-114">The following example walks you through the steps required to add a web service reference to a .NET Core console project and invoke the service.</span></span> <span data-ttu-id="e135f-115">_HelloSvcutil_이라는 .NET Core 콘솔 응용 프로그램을 만들고 다음 계약을 구현하는 웹 서비스에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-115">You will create a .NET Core console application named _HelloSvcutil_ and will add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="e135f-116">이 예제에서는 웹 서비스가 `http://contoso.com/SayHello.svc` 주소에서 호스트되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-116">For this example, the web service will be assumed to be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="e135f-117">Windows, macOS 또는 Linux 명령 창에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-117">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="e135f-118">프로젝트에 대해 _HelloSvcutil_ 디렉터리를 만들고 다음 예제와 같이 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-118">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. <span data-ttu-id="e135f-119">다음과 같이 [`dotnet new`](../tools/dotnet-new.md) 명령을 사용하여 해당 디렉터리에서 새 C# 콘솔 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-119">Create a new C# console project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

```console
dotnet new console
```

3. <span data-ttu-id="e135f-120">편집기에서 `HelloSvcutil.csproj` 프로젝트 파일을 열고, `Project` 요소를 편집하고, 다음 코드를 사용하여 [`dotnet-svcutil` NuGet 패키지](https://nuget.org/packages/dotnet-svcutil)를 CLI 도구 참조로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-120">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.0" />
</ItemGroup>
```

4. <span data-ttu-id="e135f-121">다음과 같이 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 사용하여 _dotnet-svcutil_ 패키지를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-121">Restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

5. <span data-ttu-id="e135f-122">_svcutil_ 명령과 함께 _dotnet_을 실행하여 다음과 같이 웹 서비스 참조 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-122">Run _dotnet_ with the _svcutil_ command to generate the web service reference file as follows:</span></span>

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
<span data-ttu-id="e135f-123">생성된 파일은 _HelloSvcutil/ServiceReference1/Reference.cs_로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-123">The generated file is saved as _HelloSvcutil/ServiceReference1/Reference.cs_.</span></span> <span data-ttu-id="e135f-124">또한 _dotnet_svcutil_ 도구는 프록시 코드에 필요한 적절한 WCF 패키지를 프로젝트에 패키지 참조로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-124">The _dotnet_svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

6. <span data-ttu-id="e135f-125">다음과 같이 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 사용하여 WCF 패키지를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-125">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

7. <span data-ttu-id="e135f-126">편집기에서 `Program.cs` 파일을 열고, `Main()` 메서드를 편집하고, 자동 생성된 코드를 다음 코드로 바꿔서 웹 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-126">Open the `Program.cs` file in your editor, edit the `Main()` method, and replace the auto-generated code with the following code to invoke the web service:</span></span>

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. <span data-ttu-id="e135f-127">다음과 같이 [`dotnet run`](../tools/dotnet-run.md) 명령을 사용하여 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-127">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

```console
dotnet run
```
<span data-ttu-id="e135f-128">“Hello dotnet-svcutil!” 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-128">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="e135f-129">`dotnet-svcutil` 도구 매개 변수에 대한 자세한 설명을 보려면 다음과 같이 help 매개 변수를 전달하는 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-129">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>

```console
dotnet svcutil --help
```

## <a name="next-steps"></a><span data-ttu-id="e135f-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e135f-130">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="e135f-131">사용자 의견 및 질문</span><span class="sxs-lookup"><span data-stu-id="e135f-131">Feedback & questions</span></span>

<span data-ttu-id="e135f-132">질문이나 의견이 있는 경우 [GitHub에서 문제를 엽니다](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="e135f-132">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="e135f-133">또한 [GitHub의 WCF 리포지토리에서](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling) 기존 질문이나 문제를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e135f-133">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="e135f-134">릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="e135f-134">Release notes</span></span>

* <span data-ttu-id="e135f-135">알려진 문제를 비롯한 업데이트된 릴리스 정보는 [릴리스 정보](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e135f-135">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

### <a name="information"></a><span data-ttu-id="e135f-136">정보</span><span class="sxs-lookup"><span data-stu-id="e135f-136">Information</span></span>

* [<span data-ttu-id="e135f-137">dotnet-svcutil NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="e135f-137">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)
