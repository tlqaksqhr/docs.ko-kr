---
title: ".NET Core를 사용하여 REST 클라이언트 만들기"
description: "이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: bc74b644f432071dc2483e8df3e0938c9e9ee025
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2017
---
# <a name="rest-client"></a><span data-ttu-id="8848c-104">REST 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8848c-104">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="8848c-105">소개</span><span class="sxs-lookup"><span data-stu-id="8848c-105">Introduction</span></span>
<span data-ttu-id="8848c-106">이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="8848c-107">다음을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-107">You’ll learn:</span></span>
*   <span data-ttu-id="8848c-108">.NET Core CLI(명령줄 인터페이스)의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="8848c-108">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="8848c-109">C# 언어 기능의 개요</span><span class="sxs-lookup"><span data-stu-id="8848c-109">An overview of C# Language features.</span></span>
*   <span data-ttu-id="8848c-110">NuGet으로 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="8848c-110">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="8848c-111">HTTP 통신</span><span class="sxs-lookup"><span data-stu-id="8848c-111">HTTP Communications</span></span>
*   <span data-ttu-id="8848c-112">JSON 정보 처리</span><span class="sxs-lookup"><span data-stu-id="8848c-112">Processing JSON information</span></span>
*   <span data-ttu-id="8848c-113">특성을 사용하여 구성 관리</span><span class="sxs-lookup"><span data-stu-id="8848c-113">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="8848c-114">GitHub에서 REST 서비스에 HTTP 요청을 실행하는 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-114">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="8848c-115">JSON 형식의 정보를 읽은 후 해당 JSON 패킷을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-115">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="8848c-116">마지막으로 C# 개체를 사용하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-116">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="8848c-117">이 자습서에는 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-117">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="8848c-118">하나씩 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-118">Let’s build them one by one.</span></span>

<span data-ttu-id="8848c-119">이 항목에 대한 [최종 샘플](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient)을 따르려는 경우 해당 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-119">If you prefer to follow along with the [final sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="8848c-120">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8848c-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8848c-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8848c-121">Prerequisites</span></span>
<span data-ttu-id="8848c-122">.NET Core를 실행하려면 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-122">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="8848c-123">[.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-123">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="8848c-124">Windows, Linux, macOS 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-124">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="8848c-125">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-125">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="8848c-126">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-126">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="8848c-127">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-127">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="8848c-128">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="8848c-128">Create the Application</span></span>
<span data-ttu-id="8848c-129">첫 번째 단계에서는 새 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-129">The first step is to create a new application.</span></span> <span data-ttu-id="8848c-130">명령 프롬프트를 열고 응용 프로그램에 대한 새 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-130">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="8848c-131">해당 디렉터리를 현재 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-131">Make that the current directory.</span></span> <span data-ttu-id="8848c-132">명령 프롬프트에 명령 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-132">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="8848c-133">이렇게 하면 기본 "Hello World" 응용 프로그램에 대한 시작 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-133">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="8848c-134">파일 수정을 시작하기 전에 간단한 Hello World 응용 프로그램을 실행하는 단계를 진행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-134">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="8848c-135">응용 프로그램을 만든 후 입력 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-135">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="8848c-136">이 명령은 NuGet 패키지 복원 프로세스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-136">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="8848c-137">NuGet은 .NET 패키지 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-137">NuGet is a .NET package manager.</span></span> <span data-ttu-id="8848c-138">이 명령은 프로젝트에 대한 누락된 종속성 중 하나를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-138">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="8848c-139">이 프로젝트는 새 프로젝트이므로 어떤 종속성도 없습니다. 따라서 처음 실행하면 .NET Core 프레임워크가 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-139">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="8848c-140">이 초기 단계 후 하기만 하면 됩니다 실행 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 새 종속 패키지를 추가 하거나는 종속성 버전을 업데이트할 때.</span><span class="sxs-lookup"><span data-stu-id="8848c-140">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="8848c-141">패키지를 복원한 후 `dotnet build`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-141">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="8848c-142">이렇게 하면 빌드 엔진이 실행되고 응용 프로그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-142">This executes the build engine and creates your application.</span></span> <span data-ttu-id="8848c-143">마지막으로 `dotnet run`을 실행하여 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-143">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="8848c-144">새 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="8848c-144">Adding New Dependencies</span></span>
<span data-ttu-id="8848c-145">.NET Core의 주요 디자인 목표 중 하나는 .NET Framework 설치의 크기를 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-145">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="8848c-146">.NET Core 응용 프로그램 프레임워크에는 .NET Full Framework의 가장 일반적인 요소만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-146">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="8848c-147">C# 프로젝트에 이러한 종속성을 추가할 응용 프로그램 기능 중 일부에 대 한 추가 라이브러리를 필요로 한다면 (\*.csproj) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-147">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="8848c-148">현재 예제에서는 응용 프로그램이 JSON 응답을 처리할 수 있도록 `System.Runtime.Serialization.Json` 패키지를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-148">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="8848c-149">`csproj` 프로젝트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-149">Open your `csproj` project file.</span></span> <span data-ttu-id="8848c-150">파일의 첫 번째 줄은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-150">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="8848c-151">이 줄 바로 뒤에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-151">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="8848c-152">대부분의 코드 편집기는 이러한 라이브러리의 완성된 다양한 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-152">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="8848c-153">일반적으로 추가하는 모든 패키지의 최신 버전을 사용하려고 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-153">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="8848c-154">그러나 모든 패키지의 버전이 일치하는지와 .NET Core 응용 프로그램 프레임워크의 버전도 일치하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-154">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="8848c-155">이러한 변경 내용을 변경한 후에 실행 해야 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 다시 시스템에 패키지가 설치 되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-155">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="8848c-156">웹 요청 수행</span><span class="sxs-lookup"><span data-stu-id="8848c-156">Making Web Requests</span></span>
<span data-ttu-id="8848c-157">이제 웹에서 데이터 검색을 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-157">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="8848c-158">이 응용 프로그램에서는 [GitHub API](https://developer.github.com/v3/)에서 정보를 읽게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-158">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="8848c-159">[.NET Foundation](http://www.dotnetfoundation.org/) 상위 항목 아래에서 프로젝트에 대한 정보를 읽어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-159">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="8848c-160">먼저 GitHub API에 대해 요청을 수행하여 프로젝트에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-160">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="8848c-161">사용하게 될 끝점은 [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos)입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-161">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="8848c-162">이러한 프로젝트에 대해 모든 정보를 검색하려고 하므로 HTTP GET 요청을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-162">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="8848c-163">브라우저도 HTTP GET 요청을 사용하므로 해당 URL을 브라우저에 붙여 넣어 수신되고 처리 중인 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-163">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="8848c-164"><xref:System.Net.Http.HttpClient> 클래스를 사용하여 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-164">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="8848c-165">모든 최신 .NET API와 마찬가지로 <xref:System.Net.Http.HttpClient> 는 장기 실행되는 API에 대해 비동기 메서드만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-165">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="8848c-166">먼저 비동기 메서드를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-166">Start by making an async method.</span></span> <span data-ttu-id="8848c-167">응용 프로그램의 기능을 빌드할 때 구현을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-167">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="8848c-168">먼저 프로젝트 디렉터리에서 `program.cs` 파일을 열고 `Program` 클래스에 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-168">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="8848c-169">C# 컴파일러에서 <xref:System.Threading.Tasks.Task> 형식을 인식하도록 `using` 문을 `Main` 메서드 맨 위에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-169">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="8848c-170">이때 프로젝트를 빌드하면 이 메서드에는 `await` 연산자가 없어서 동기적으로 실행되므로 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-170">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="8848c-171">지금은 이 경고를 무시하세요. 메서드를 입력할 때 `await` 연산자를 추가할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-171">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="8848c-172">다음에는 `namespace` 문에 정의된 네임스페이스의 이름을 기본값인 `ConsoleApp`에서 `WebAPIClient`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-172">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="8848c-173">나중에 이 네임스페이스에서 `repo` 클래스를 정의할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-173">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="8848c-174">다음에는 `Main` 메서드를 업데이트하여 이 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-174">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="8848c-175">`ProcessRepositories` 메서드는 작업을 반환합니다. 이 작업이 완료되기 전에 프로그램을 종료하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-175">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="8848c-176">따라서 `Wait` 메서드를 사용하여 작업이 완료될 때까지 차단하고 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-176">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
public static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="8848c-177">이제 아무 작업도 수행하지 않지만 비동기적으로는 수행하는 프로그램이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-177">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="8848c-178">다시 `ProcessRepositories` 메서드로 돌아가 첫 번째 버전을 채워 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-178">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    var client = new HttpClient();
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="8848c-179">컴파일을 위해 파일 맨 위에 2개의 새 using 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-179">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="8848c-180">이 첫 번째 버전은 dotnet foundation 조직의 모든 리포지토리 목록을 읽으라는 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-180">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="8848c-181">(.NET Foundation의 gitHub ID는 'dotnet'임)</span><span class="sxs-lookup"><span data-stu-id="8848c-181">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="8848c-182">먼저, 새 <xref:System.Net.Http.HttpClient> 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-182">First, you create a new <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="8848c-183">이 개체는 요청 및 응답을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-183">This object handles the request and the responses.</span></span> <span data-ttu-id="8848c-184">다음에 나오는 몇 개의 줄은 이 요청에 대해 <xref:System.Net.Http.HttpClient> 를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-184">The next few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="8848c-185">먼저 GitHub JSON 응답을 수락하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-185">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="8848c-186">이 형식은 단순히 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-186">This format is simply JSON.</span></span> <span data-ttu-id="8848c-187">다음 줄은 이 개체의 모든 요청에 사용자 에이전트 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-187">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="8848c-188">이러한 두 가지 헤더는 GitHub 서버 코드에서 확인되며 GitHub에서 정보를 검색하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-188">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="8848c-189"><xref:System.Net.Http.HttpClient> 를 구성한 후에는 웹 요청을 수행하고 응답을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-189">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="8848c-190">이 첫 번째 버전에서는 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 편의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-190">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="8848c-191">이 편의 메서드는 웹 요청을 수행하는 작업을 시작한 다음, 요청이 반환될 때 응답 스트림을 읽고 해당 스트림에서 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-191">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="8848c-192">응답의 본문은 <xref:System.String> 으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-192">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="8848c-193">작업이 완료되면 이 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-193">The string is available when the task completes.</span></span> 

<span data-ttu-id="8848c-194">이 메서드의 마지막 두 줄은 해당 작업을 대기하고 콘솔에 응답을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-194">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="8848c-195">앱을 빌드한 다음 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-195">Build the app, and run it.</span></span> <span data-ttu-id="8848c-196">`ProcessRepositories`에는 `await` 연산자가 포함되므로 이제 빌드 경고는 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-196">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="8848c-197">길게 표시되는 JSON 형식 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-197">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="8848c-198">JSON 결과 처리</span><span class="sxs-lookup"><span data-stu-id="8848c-198">Processing the JSON Result</span></span>

<span data-ttu-id="8848c-199">지금까지 웹 서버에서 응답을 검색하고 해당 응답에 포함된 텍스트를 표시하는 코드를 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-199">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="8848c-200">다음에는 JSON 응답을 C# 개체로 변환해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-200">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="8848c-201">JSON Serializer는 JSON 데이터를 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-201">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="8848c-202">가장 먼저 수행할 작업은 이 응답 중에서 사용하는 정보를 포함하는 C# 클래스 형식을 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-202">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="8848c-203">리포지토리 이름을 포함하는 간단한 C# 형식 먼저 시작하여 천천히 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-203">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

<span data-ttu-id="8848c-204">'repo.cs'라는 새 파일에 위 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-204">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="8848c-205">이 버전의 클래스는 JSON 데이터를 처리하는 가장 간단한 경로를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-205">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="8848c-206">클래스 이름 및 멤버 이름은 다음 C# 규칙 대신 JSON 패킷에 사용된 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-206">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="8848c-207">나중에 몇 가지 구성 특성을 제공하여 수정할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-207">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="8848c-208">이 클래스에서는 JSON serialization 및 deserialization의 또 다른 중요한 특징을 보여 줍니다. 즉, JSON 패킷의 모든 필드가 이 클래스에 속하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-208">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="8848c-209">JSON serializer는 사용되는 클래스 형식에 포함되지 않은 정보를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-209">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="8848c-210">이 특징 때문에 JSON 패킷의 필드 일부에만 작용하는 형식을 보다 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-210">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="8848c-211">이제 형식을 만들었으므로 deserialize를 수행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-211">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="8848c-212"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-212">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="8848c-213">이 개체는 검색하는 JSON 패킷에 필요한 CLR 형식을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-213">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="8848c-214">GitHub의 패킷에는 리포지토리 시퀀스가 포함되어 있으므로 `List<repo>`가 올바른 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-214">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="8848c-215">`ProcessRepositories` 메서드에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-215">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="8848c-216">두 개의 새 네임스페이스를 사용하고 있으므로 해당 네임스페이스도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-216">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="8848c-217">다음으로, serializer를 사용하여 JSON을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-217">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="8848c-218">호출을 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 에 프로그램 `ProcessRepositories` 메서드 다음의 두 줄으로:</span><span class="sxs-lookup"><span data-stu-id="8848c-218">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="8848c-219">지금 사용 하는 알림 <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> 대신 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-219">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="8848c-220">serializer는 해당 소스로 문자열 대신 스트림을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-220">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="8848c-221">위의 두 번째 줄에서 사용되는 C# 언어의 몇 가지 기능에 대해 설명해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-221">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="8848c-222">에 대 한 인수 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> 는 `await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-222">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="8848c-223">지금까지는 대입문의 일부로만 볼 수 있었지만 Await 식은 코드의 거의 모든 위치에 나올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-223">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="8848c-224">둘째로 `as` 연산자는 컴파일 타임 형식 `object`에서 `List<repo>`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-224">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="8848c-225">선언 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> 형식의 개체를 반환 하는지 선언 <xref:System.Object?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-225">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8848c-226"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)>형식을 반환 하는 것을 생성할 때 지정한 (`List<repo>` 이 자습서에서는).</span><span class="sxs-lookup"><span data-stu-id="8848c-226"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="8848c-227">변환이 성공하지 못하면 `as` 연산자는 예외를 throw하는 대신 `null`을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-227">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="8848c-228">이 섹션이 거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-228">You're almost done with this section.</span></span> <span data-ttu-id="8848c-229">JSON을 C# 개체로 변환했으므로 각 리포지토리의 이름을 표시해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-229">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="8848c-230">다음 줄을</span><span class="sxs-lookup"><span data-stu-id="8848c-230">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="8848c-231">다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-231">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="8848c-232">응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-232">Compile and run the application.</span></span> <span data-ttu-id="8848c-233">.NET Foundation에 포함된 리포지토리의 이름이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-233">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="8848c-234">serialization 제어</span><span class="sxs-lookup"><span data-stu-id="8848c-234">Controlling Serialization</span></span>

<span data-ttu-id="8848c-235">더 많은 기능을 추가하기 전에 `repo` 형식의 주소를 지정하고 더 많은 표준 C# 규칙을 따르도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-235">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="8848c-236">이 작업을 위해 JSON Serializer가 작동하는 방식을 제어하는 *특성*을 `repo` 형식에 주석으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-236">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="8848c-237">여기서는 이러한 특성을 사용하여 JSON 키 이름과 C# 클래스 및 멤버 이름 간에 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-237">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="8848c-238">사용되는 2가지 특성은 `DataContract` 특성 및 `DataMember` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-238">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="8848c-239">규칙에 따라 모든 Attribute 클래스는 접미사 `Attribute`로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-239">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="8848c-240">그러나 특성을 적용할 때 해당 접미사를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-240">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="8848c-241">`DataContract` 및 `DataMember` 특성은 다른 라이브러리에 포함되므로 해당 라이브러리를 C# 프로젝트 파일에 종속성으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-241">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="8848c-242">다음 줄을 프로젝트 파일의 `<ItemGroup>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-242">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="8848c-243">실행 파일을 저장 한 후 `dotnet restore` ([참고 참조](#dotnet-restore-note))이이 패키지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-243">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="8848c-244">다음으로 `repo.cs` 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-244">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="8848c-245">이름을 파스칼식 대/소문자를 사용하도록 이름을 변경하고 `Repository`라고 정확히 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-245">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="8848c-246">여전히 JSON 'repo' 노드를 이 형식에 매핑하려고 하므로 `DataContract` 특성을 클래스 선언에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-246">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="8848c-247">이 특성의 `Name` 속성을 이 형식에 매핑되는 JSON 노드의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-247">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="8848c-248"><xref:System.Runtime.Serialization.DataContractAttribute> 는  <xref:System.Runtime.Serialization> 네임스페이스의 멤버이므로 파일 맨 위에 해당 `using` 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-248">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="8848c-249">`repo` 클래스의 이름을 `Repository`로 변경했으므로 Program.cs에서도 동일하게 이름을 변경해야 합니다(일부 편집기에서 이러한 변경을 자동으로 수행하는 이름 바꾸기 리팩터링이 지원될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="8848c-249">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="8848c-250">다음으로 <xref:System.Runtime.Serialization.DataMemberAttribute> 클래스를 사용하여 `name` 필드를 동일하게 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-250">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="8848c-251">repo.cs에서 `name` 필드의 선언을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-251">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="8848c-252">이렇게 변경할 경우 program.cs에서 각 리포지토리의 이름을 쓰는 코드를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-252">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="8848c-253">`dotnet build` 다음에 `dotnet run`을 수행하여 매핑이 올바르게 수행되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-253">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="8848c-254">이전과 동일한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-254">You should see the same output as before.</span></span> <span data-ttu-id="8848c-255">웹 서버의 더 많은 속성을 처리하기 전에 `Repository` 클래스를 한 가지 더 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-255">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="8848c-256">`Name` 멤버는 공개적으로 액세스할 수 있는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-256">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="8848c-257">그렇지만 적절한 개체 지향 방식은 아니므로 속성으로 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-257">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="8848c-258">이 예제에서는 속성을 가져오거나 설정할 때 특정 코드를 실행할 필요가 없으며 속성을 변경하여 `Repository` 클래스를 사용하는 코드를 중단하지 않고도 나중에 해당 변경 내용을 보다 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-258">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="8848c-259">필드 정의를 제거한 후 [자동 구현 속성](../programming-guide/classes-and-structs/auto-implemented-properties.md)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-259">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="8848c-260">컴파일러는 `get` 및 `set` 접근자의 본문 뿐만 아니라 이름을 저장하는 private 필드도 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-260">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="8848c-261">이 작업은 다음 코드를 직접 입력하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-261">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="8848c-262">새로운 기능을 추가하기 전에 한 가지 더 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-262">Let's make one more change before adding new features.</span></span> <span data-ttu-id="8848c-263">`ProcessRepositories` 메서드는 비동기 작업을 수행하고 리포지토리 컬렉션을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-263">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="8848c-264">이 메서드에서 `List<Repository>`로 돌아가 정보를 쓰는 코드를 `Main` 메서드로 이동해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-264">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="8848c-265">`ProcessRepositories`의 시그니처를 변경하여 `Repository` 개체의 목록을 해당 결과로 표시하는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-265">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="8848c-266">다음에는 JSON 응답을 처리한 후 리포지토리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-266">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="8848c-267">이 개체를 `async`로 표시했으므로 컴파일러는 해당 반환에 대한 `Task<T>` 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-267">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="8848c-268">그런 다음 해당 결과를 캡처하고 각 리포지토리 이름을 콘솔에 쓰도록 `Main` 메서드를 수정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-268">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="8848c-269">`Main` 메서드는 이제 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-269">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="8848c-270">작업이 완료될 때까지 Task의 `Result` 속성에 대한 액세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-270">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="8848c-271">일반적으로 `ProcessRepositories` 메서드에서와 같이 작업의 컴파일을 `await`하는 것을 선호하겠지만 `Main` 메서드에서는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-271">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="8848c-272">추가 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8848c-272">Reading More Information</span></span>

<span data-ttu-id="8848c-273">GitHub API에서 전송되는 JSON 패킷에 있는 속성을 몇 가지 더 처리하는 것으로 마무리해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-273">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="8848c-274">모든 기능을 알 수는 없겠지만 일부 속성을 추가하면 C# 언어의 몇 가지 기능이 추가로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-274">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="8848c-275">먼저 `Repository` 클래스 정의에 몇 가지 간단한 형식을 더 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-275">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="8848c-276">해당 클래스에 다음 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-276">Add these properties to that class:</span></span>

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="8848c-277">이러한 속성은 기본적으로 문자열 형식(JSON 패킷에 포함된 형식)을 대상 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-277">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="8848c-278"><xref:System.Uri> 형식은 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-278">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="8848c-279">이 형식은 URI 또는 이 경우에는 URL을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-279">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="8848c-280">`Uri` 및 `int` 형식의 경우 JSON 패킷에 대상 형식으로 변환되지 않는 데이터가 포함되어 있으면 serialization 작업은 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-280">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="8848c-281">이러한 데이터를 추가한 경우에는 해당 요소를 표시하도록 `Main` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-281">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```
<span data-ttu-id="8848c-282">마지막 단계로, 최종 밀어넣기 작업을 위한 정보를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-282">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="8848c-283">이 정보는 JSON 응답에서 다음 방식으로 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-283">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="8848c-284">해당 형식은 표준 .NET <xref:System.DateTime> 형식을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-284">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="8848c-285">따라서 사용자 지정 변환 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-285">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="8848c-286">또한 `Repository` 클래스 사용자에게 원시 문자열이 노출되는 것을 원하지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-286">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="8848c-287">특성도 이러한 작업을 제어하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-287">Attributes can help control that as well.</span></span> <span data-ttu-id="8848c-288">먼저 `Repository` 클래스에서 날짜/시간에 대한 문자열 표현을 포함할 `private` 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-288">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="8848c-289">`DataMember` 특성은 공용 멤버가 아니어도 처리되어야 함을 serializer에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-289">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="8848c-290">유효한 문자열을 변환 하는 공용 읽기 전용 속성을 작성 해야 하는 다음으로 <xref:System.DateTime> 개체를 반환 하는 <xref:System.DateTime>:</span><span class="sxs-lookup"><span data-stu-id="8848c-290">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

<span data-ttu-id="8848c-291">위의 새 구문을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-291">Let's go over the new constructs above.</span></span> <span data-ttu-id="8848c-292">`IgnoreDataMember` 특성은 이 형식을 임의 JSON 개체에 쓰거나 이 개체에서 읽지 않아야 함을 serializer에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-292">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="8848c-293">이 속성은 `get` 접근자만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-293">This property contains only a `get` accessor.</span></span> <span data-ttu-id="8848c-294">`set` 접근자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-294">There is no `set` accessor.</span></span> <span data-ttu-id="8848c-295">바로 C#에서 *읽기 전용* 속성을 정의하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-295">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="8848c-296">(C#에서 *쓰기 전용* 속성을 만들 수 있지만 해당 값은 제한됩니다.) <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> 메서드 문자열을 구문 분석 하 고 만듭니다는 <xref:System.DateTime> 추가 메타 데이터를 추가 하 고 제공 된 날짜 형식을 사용 하 여 개체는 `DateTime` 를 사용 하는 `CultureInfo` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-296">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="8848c-297">구문 분석 작업이 실패하는 경우 속성 접근자가 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-297">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="8848c-298"><xref:System.Globalization.CultureInfo.InvariantCulture> 를 사용하려면 `repo.cs`의 `using` 문에 <xref:System.Globalization> 네임스페이스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-298">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="8848c-299">마지막으로 콘솔에 output 문을 하나 더 추가하면 이 앱을 빌드하고 다시 실행할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-299">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="8848c-300">이제 해당 버전이 [완성된 샘플](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient)과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-300">Your version should now match the [finished sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="8848c-301">결론</span><span class="sxs-lookup"><span data-stu-id="8848c-301">Conclusion</span></span>

<span data-ttu-id="8848c-302">이 자습서에서는 웹 요청을 수행하고, 결과를 구문 분석하고, 해당 결과의 속성을 표시하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-302">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="8848c-303">또한 프로젝트에 종속성으로 새 패키지를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-303">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="8848c-304">개체 지향 기술을 지원하는 C# 언어의 일부 기능을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="8848c-304">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
