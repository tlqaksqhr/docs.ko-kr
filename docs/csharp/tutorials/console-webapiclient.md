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
ms.openlocfilehash: 22391c4db3027c0fad2115c767b5e2808fee28a0
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="rest-client"></a><span data-ttu-id="f1c0e-104">REST 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f1c0e-104">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="f1c0e-105">소개</span><span class="sxs-lookup"><span data-stu-id="f1c0e-105">Introduction</span></span>
<span data-ttu-id="f1c0e-106">이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="f1c0e-107">다음을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-107">You’ll learn:</span></span>
*   <span data-ttu-id="f1c0e-108">.NET Core CLI(명령줄 인터페이스)의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="f1c0e-108">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="f1c0e-109">C# 언어 기능의 개요</span><span class="sxs-lookup"><span data-stu-id="f1c0e-109">An overview of C# Language features.</span></span>
*   <span data-ttu-id="f1c0e-110">NuGet으로 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="f1c0e-110">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="f1c0e-111">HTTP 통신</span><span class="sxs-lookup"><span data-stu-id="f1c0e-111">HTTP Communications</span></span>
*   <span data-ttu-id="f1c0e-112">JSON 정보 처리</span><span class="sxs-lookup"><span data-stu-id="f1c0e-112">Processing JSON information</span></span>
*   <span data-ttu-id="f1c0e-113">특성을 사용하여 구성 관리</span><span class="sxs-lookup"><span data-stu-id="f1c0e-113">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="f1c0e-114">GitHub에서 REST 서비스에 HTTP 요청을 실행하는 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-114">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="f1c0e-115">JSON 형식의 정보를 읽은 후 해당 JSON 패킷을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-115">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="f1c0e-116">마지막으로 C# 개체를 사용하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-116">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="f1c0e-117">이 자습서에는 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-117">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="f1c0e-118">하나씩 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-118">Let’s build them one by one.</span></span>

<span data-ttu-id="f1c0e-119">이 항목에 대한 [최종 샘플](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient)을 따르려는 경우 해당 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-119">If you prefer to follow along with the [final sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="f1c0e-120">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1c0e-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f1c0e-121">Prerequisites</span></span>
<span data-ttu-id="f1c0e-122">.NET Core를 실행하려면 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-122">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="f1c0e-123">[.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-123">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="f1c0e-124">Windows, Linux, macOS 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-124">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="f1c0e-125">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-125">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="f1c0e-126">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-126">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="f1c0e-127">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-127">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="f1c0e-128">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="f1c0e-128">Create the Application</span></span>
<span data-ttu-id="f1c0e-129">첫 번째 단계에서는 새 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-129">The first step is to create a new application.</span></span> <span data-ttu-id="f1c0e-130">명령 프롬프트를 열고 응용 프로그램에 대한 새 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-130">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="f1c0e-131">해당 디렉터리를 현재 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-131">Make that the current directory.</span></span> <span data-ttu-id="f1c0e-132">명령 프롬프트에 명령 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-132">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="f1c0e-133">이렇게 하면 기본 "Hello World" 응용 프로그램에 대한 시작 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-133">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="f1c0e-134">파일 수정을 시작하기 전에 간단한 Hello World 응용 프로그램을 실행하는 단계를 진행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-134">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="f1c0e-135">응용 프로그램을 만든 후에 명령 프롬프트에서 `dotnet restore`([참고 참조](#dotnet-restore-note))를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-135">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="f1c0e-136">이 명령은 NuGet 패키지 복원 프로세스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-136">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="f1c0e-137">NuGet은 .NET 패키지 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-137">NuGet is a .NET package manager.</span></span> <span data-ttu-id="f1c0e-138">이 명령은 프로젝트에 대한 누락된 종속성 중 하나를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-138">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="f1c0e-139">이 프로젝트는 새 프로젝트이므로 어떤 종속성도 없습니다. 따라서 처음 실행하면 .NET Core 프레임워크가 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-139">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="f1c0e-140">이 초기 단계 후에 새 종속 패키지를 추가하거나 종속성 버전을 업데이트할 때 `dotnet restore`([참고 참조](#dotnet-restore-note))를 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-140">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="f1c0e-141">패키지를 복원한 후 `dotnet build`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-141">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="f1c0e-142">이렇게 하면 빌드 엔진이 실행되고 응용 프로그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-142">This executes the build engine and creates your application.</span></span> <span data-ttu-id="f1c0e-143">마지막으로 `dotnet run`을 실행하여 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-143">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="f1c0e-144">새 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="f1c0e-144">Adding New Dependencies</span></span>
<span data-ttu-id="f1c0e-145">.NET Core의 주요 디자인 목표 중 하나는 .NET Framework 설치의 크기를 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-145">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="f1c0e-146">.NET Core 응용 프로그램 프레임워크에는 .NET Full Framework의 가장 일반적인 요소만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-146">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="f1c0e-147">응용 프로그램에 일부 기능을 위해 추가 라이브러리가 필요한 경우 C# 프로젝트(\*.csproj) 파일에 해당 종속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-147">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="f1c0e-148">현재 예제에서는 응용 프로그램이 JSON 응답을 처리할 수 있도록 `System.Runtime.Serialization.Json` 패키지를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-148">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="f1c0e-149">`csproj` 프로젝트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-149">Open your `csproj` project file.</span></span> <span data-ttu-id="f1c0e-150">파일의 첫 번째 줄은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-150">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="f1c0e-151">이 줄 바로 뒤에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-151">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="f1c0e-152">대부분의 코드 편집기는 이러한 라이브러리의 완성된 다양한 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-152">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="f1c0e-153">일반적으로 추가하는 모든 패키지의 최신 버전을 사용하려고 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-153">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="f1c0e-154">그러나 모든 패키지의 버전이 일치하는지와 .NET Core 응용 프로그램 프레임워크의 버전도 일치하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-154">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="f1c0e-155">이러한 변경을 수행한 후에는 패키지가 시스템에 설치되도록 `dotnet restore`([참고 참조](#dotnet-restore-note))를 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-155">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="f1c0e-156">웹 요청 수행</span><span class="sxs-lookup"><span data-stu-id="f1c0e-156">Making Web Requests</span></span>
<span data-ttu-id="f1c0e-157">이제 웹에서 데이터 검색을 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-157">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="f1c0e-158">이 응용 프로그램에서는 [GitHub API](https://developer.github.com/v3/)에서 정보를 읽게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-158">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="f1c0e-159">[.NET Foundation](http://www.dotnetfoundation.org/) 상위 항목 아래에서 프로젝트에 대한 정보를 읽어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-159">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="f1c0e-160">먼저 GitHub API에 대해 요청을 수행하여 프로젝트에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-160">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="f1c0e-161">사용하게 될 끝점은 [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos)입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-161">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="f1c0e-162">이러한 프로젝트에 대해 모든 정보를 검색하려고 하므로 HTTP GET 요청을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-162">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="f1c0e-163">브라우저도 HTTP GET 요청을 사용하므로 해당 URL을 브라우저에 붙여 넣어 수신되고 처리 중인 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-163">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="f1c0e-164"><xref:System.Net.Http.HttpClient> 클래스를 사용하여 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-164">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="f1c0e-165">모든 최신 .NET API와 마찬가지로 <xref:System.Net.Http.HttpClient> 는 장기 실행되는 API에 대해 비동기 메서드만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-165">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="f1c0e-166">먼저 비동기 메서드를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-166">Start by making an async method.</span></span> <span data-ttu-id="f1c0e-167">응용 프로그램의 기능을 빌드할 때 구현을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-167">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="f1c0e-168">먼저 프로젝트 디렉터리에서 `program.cs` 파일을 열고 `Program` 클래스에 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-168">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="f1c0e-169">C# 컴파일러에서 <xref:System.Threading.Tasks.Task> 형식을 인식하도록 `using` 문을 `Main` 메서드 맨 위에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-169">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="f1c0e-170">이때 프로젝트를 빌드하면 이 메서드에는 `await` 연산자가 없어서 동기적으로 실행되므로 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-170">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="f1c0e-171">지금은 이 경고를 무시하세요. 메서드를 입력할 때 `await` 연산자를 추가할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-171">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="f1c0e-172">다음에는 `namespace` 문에 정의된 네임스페이스의 이름을 기본값인 `ConsoleApp`에서 `WebAPIClient`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-172">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="f1c0e-173">나중에 이 네임스페이스에서 `repo` 클래스를 정의할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-173">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="f1c0e-174">다음에는 `Main` 메서드를 업데이트하여 이 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-174">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="f1c0e-175">`ProcessRepositories` 메서드는 작업을 반환합니다. 이 작업이 완료되기 전에 프로그램을 종료하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-175">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="f1c0e-176">따라서 `Wait` 메서드를 사용하여 작업이 완료될 때까지 차단하고 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-176">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="f1c0e-177">이제 아무 작업도 수행하지 않지만 비동기적으로는 수행하는 프로그램이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-177">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="f1c0e-178">이것을 개선해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-178">Let's improve it.</span></span>

<span data-ttu-id="f1c0e-179">먼저 웹에서 데이터를 검색할 수 있는 개체가 필요합니다. 이를 위해 <xref:System.Net.Http.HttpClient>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-179">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="f1c0e-180">이 개체는 요청 및 응답을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-180">This object handles the request and the responses.</span></span> <span data-ttu-id="f1c0e-181">Program.cs 파일 내의 `Program` 클래스에서 해당 형식의 단일 인스턴스를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-181">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
        {
            //...
        }
    }
}
```

 <span data-ttu-id="f1c0e-182">다시 `ProcessRepositories` 메서드로 돌아가 첫 번째 버전을 채워 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-182">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="f1c0e-183">컴파일을 위해 파일 맨 위에 2개의 새 using 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-183">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="f1c0e-184">이 첫 번째 버전은 dotnet foundation 조직의 모든 리포지토리 목록을 읽으라는 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-184">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="f1c0e-185">(.NET Foundation의 gitHub ID는 'dotnet'임)</span><span class="sxs-lookup"><span data-stu-id="f1c0e-185">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="f1c0e-186">첫 몇 줄은 이 요청에 대해 <xref:System.Net.Http.HttpClient>를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-186">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="f1c0e-187">먼저 GitHub JSON 응답을 수락하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-187">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="f1c0e-188">이 형식은 단순히 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-188">This format is simply JSON.</span></span> <span data-ttu-id="f1c0e-189">다음 줄은 이 개체의 모든 요청에 사용자 에이전트 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-189">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="f1c0e-190">이러한 두 가지 헤더는 GitHub 서버 코드에서 확인되며 GitHub에서 정보를 검색하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-190">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="f1c0e-191"><xref:System.Net.Http.HttpClient> 를 구성한 후에는 웹 요청을 수행하고 응답을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-191">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="f1c0e-192">이 첫 번째 버전에서는 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 편의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-192">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="f1c0e-193">이 편의 메서드는 웹 요청을 수행하는 작업을 시작한 다음, 요청이 반환될 때 응답 스트림을 읽고 해당 스트림에서 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-193">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="f1c0e-194">응답의 본문은 <xref:System.String> 으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-194">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="f1c0e-195">작업이 완료되면 이 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-195">The string is available when the task completes.</span></span> 

<span data-ttu-id="f1c0e-196">이 메서드의 마지막 두 줄은 해당 작업을 대기하고 콘솔에 응답을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-196">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="f1c0e-197">앱을 빌드한 다음 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-197">Build the app, and run it.</span></span> <span data-ttu-id="f1c0e-198">`ProcessRepositories`에는 `await` 연산자가 포함되므로 이제 빌드 경고는 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-198">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="f1c0e-199">길게 표시되는 JSON 형식 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-199">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="f1c0e-200">JSON 결과 처리</span><span class="sxs-lookup"><span data-stu-id="f1c0e-200">Processing the JSON Result</span></span>

<span data-ttu-id="f1c0e-201">지금까지 웹 서버에서 응답을 검색하고 해당 응답에 포함된 텍스트를 표시하는 코드를 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-201">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="f1c0e-202">다음에는 JSON 응답을 C# 개체로 변환해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-202">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="f1c0e-203">JSON Serializer는 JSON 데이터를 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-203">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="f1c0e-204">가장 먼저 수행할 작업은 이 응답 중에서 사용하는 정보를 포함하는 C# 클래스 형식을 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-204">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="f1c0e-205">리포지토리 이름을 포함하는 간단한 C# 형식 먼저 시작하여 천천히 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-205">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

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

<span data-ttu-id="f1c0e-206">'repo.cs'라는 새 파일에 위 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-206">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="f1c0e-207">이 버전의 클래스는 JSON 데이터를 처리하는 가장 간단한 경로를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-207">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="f1c0e-208">클래스 이름 및 멤버 이름은 다음 C# 규칙 대신 JSON 패킷에 사용된 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-208">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="f1c0e-209">나중에 몇 가지 구성 특성을 제공하여 수정할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-209">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="f1c0e-210">이 클래스에서는 JSON serialization 및 deserialization의 또 다른 중요한 특징을 보여 줍니다. 즉, JSON 패킷의 모든 필드가 이 클래스에 속하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-210">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="f1c0e-211">JSON serializer는 사용되는 클래스 형식에 포함되지 않은 정보를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-211">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="f1c0e-212">이 특징 때문에 JSON 패킷의 필드 일부에만 작용하는 형식을 보다 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-212">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="f1c0e-213">이제 형식을 만들었으므로 deserialize를 수행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-213">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="f1c0e-214"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-214">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="f1c0e-215">이 개체는 검색하는 JSON 패킷에 필요한 CLR 형식을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-215">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="f1c0e-216">GitHub의 패킷에는 리포지토리 시퀀스가 포함되어 있으므로 `List<repo>`가 올바른 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-216">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="f1c0e-217">`ProcessRepositories` 메서드에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-217">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="f1c0e-218">두 개의 새 네임스페이스를 사용하고 있으므로 해당 네임스페이스도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-218">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="f1c0e-219">다음으로, serializer를 사용하여 JSON을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-219">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="f1c0e-220">`ProcessRepositories` 메서드의 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 호출을 다음 두 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-220">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="f1c0e-221">현재 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 대신 <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)>를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-221">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="f1c0e-222">serializer는 해당 소스로 문자열 대신 스트림을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-222">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="f1c0e-223">위의 두 번째 줄에서 사용되는 C# 언어의 몇 가지 기능에 대해 설명해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-223">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="f1c0e-224"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)>에 대한 인수는 `await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-224">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="f1c0e-225">지금까지는 대입문의 일부로만 볼 수 있었지만 Await 식은 코드의 거의 모든 위치에 나올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-225">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="f1c0e-226">둘째로 `as` 연산자는 컴파일 타임 형식 `object`에서 `List<repo>`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-226">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="f1c0e-227"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> 선언은 <xref:System.Object?displayProperty=nameWithType> 형식의 개체로 반환됨을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-227">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f1c0e-228"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)>는 사용자가 생성 시에 지정한 형식을 반환합니다(이 자습서에서는 `List<repo>`).</span><span class="sxs-lookup"><span data-stu-id="f1c0e-228"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="f1c0e-229">변환이 성공하지 못하면 `as` 연산자는 예외를 throw하는 대신 `null`을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-229">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="f1c0e-230">이 섹션이 거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-230">You're almost done with this section.</span></span> <span data-ttu-id="f1c0e-231">JSON을 C# 개체로 변환했으므로 각 리포지토리의 이름을 표시해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-231">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="f1c0e-232">다음 줄을</span><span class="sxs-lookup"><span data-stu-id="f1c0e-232">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="f1c0e-233">다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-233">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="f1c0e-234">응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-234">Compile and run the application.</span></span> <span data-ttu-id="f1c0e-235">.NET Foundation에 포함된 리포지토리의 이름이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-235">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="f1c0e-236">serialization 제어</span><span class="sxs-lookup"><span data-stu-id="f1c0e-236">Controlling Serialization</span></span>

<span data-ttu-id="f1c0e-237">더 많은 기능을 추가하기 전에 `repo` 형식의 주소를 지정하고 더 많은 표준 C# 규칙을 따르도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-237">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="f1c0e-238">이 작업을 위해 JSON Serializer가 작동하는 방식을 제어하는 *특성*을 `repo` 형식에 주석으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-238">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="f1c0e-239">여기서는 이러한 특성을 사용하여 JSON 키 이름과 C# 클래스 및 멤버 이름 간에 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-239">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="f1c0e-240">사용되는 2가지 특성은 `DataContract` 특성 및 `DataMember` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-240">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="f1c0e-241">규칙에 따라 모든 Attribute 클래스는 접미사 `Attribute`로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-241">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="f1c0e-242">그러나 특성을 적용할 때 해당 접미사를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-242">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="f1c0e-243">`DataContract` 및 `DataMember` 특성은 다른 라이브러리에 포함되므로 해당 라이브러리를 C# 프로젝트 파일에 종속성으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-243">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="f1c0e-244">다음 줄을 프로젝트 파일의 `<ItemGroup>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-244">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="f1c0e-245">파일을 저장한 후 `dotnet restore`([참고 참조](#dotnet-restore-note))를 실행하여 이 패키지를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-245">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="f1c0e-246">다음으로 `repo.cs` 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-246">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="f1c0e-247">이름을 파스칼식 대/소문자를 사용하도록 이름을 변경하고 `Repository`라고 정확히 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-247">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="f1c0e-248">여전히 JSON 'repo' 노드를 이 형식에 매핑하려고 하므로 `DataContract` 특성을 클래스 선언에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-248">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="f1c0e-249">이 특성의 `Name` 속성을 이 형식에 매핑되는 JSON 노드의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-249">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="f1c0e-250"><xref:System.Runtime.Serialization.DataContractAttribute> 는  <xref:System.Runtime.Serialization> 네임스페이스의 멤버이므로 파일 맨 위에 해당 `using` 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-250">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="f1c0e-251">`repo` 클래스의 이름을 `Repository`로 변경했으므로 Program.cs에서도 동일하게 이름을 변경해야 합니다(일부 편집기에서 이러한 변경을 자동으로 수행하는 이름 바꾸기 리팩터링이 지원될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="f1c0e-251">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="f1c0e-252">다음으로 <xref:System.Runtime.Serialization.DataMemberAttribute> 클래스를 사용하여 `name` 필드를 동일하게 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-252">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="f1c0e-253">repo.cs에서 `name` 필드의 선언을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-253">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="f1c0e-254">이렇게 변경할 경우 program.cs에서 각 리포지토리의 이름을 쓰는 코드를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-254">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="f1c0e-255">`dotnet build` 다음에 `dotnet run`을 수행하여 매핑이 올바르게 수행되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-255">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="f1c0e-256">이전과 동일한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-256">You should see the same output as before.</span></span> <span data-ttu-id="f1c0e-257">웹 서버의 더 많은 속성을 처리하기 전에 `Repository` 클래스를 한 가지 더 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-257">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="f1c0e-258">`Name` 멤버는 공개적으로 액세스할 수 있는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-258">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="f1c0e-259">그렇지만 적절한 개체 지향 방식은 아니므로 속성으로 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-259">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="f1c0e-260">이 예제에서는 속성을 가져오거나 설정할 때 특정 코드를 실행할 필요가 없으며 속성을 변경하여 `Repository` 클래스를 사용하는 코드를 중단하지 않고도 나중에 해당 변경 내용을 보다 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-260">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="f1c0e-261">필드 정의를 제거한 후 [자동 구현 속성](../programming-guide/classes-and-structs/auto-implemented-properties.md)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-261">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="f1c0e-262">컴파일러는 `get` 및 `set` 접근자의 본문 뿐만 아니라 이름을 저장하는 private 필드도 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-262">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="f1c0e-263">이 작업은 다음 코드를 직접 입력하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-263">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="f1c0e-264">새로운 기능을 추가하기 전에 한 가지 더 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-264">Let's make one more change before adding new features.</span></span> <span data-ttu-id="f1c0e-265">`ProcessRepositories` 메서드는 비동기 작업을 수행하고 리포지토리 컬렉션을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-265">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="f1c0e-266">이 메서드에서 `List<Repository>`로 돌아가 정보를 쓰는 코드를 `Main` 메서드로 이동해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-266">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="f1c0e-267">`ProcessRepositories`의 시그니처를 변경하여 `Repository` 개체의 목록을 해당 결과로 표시하는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-267">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="f1c0e-268">다음에는 JSON 응답을 처리한 후 리포지토리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-268">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="f1c0e-269">이 개체를 `async`로 표시했으므로 컴파일러는 해당 반환에 대한 `Task<T>` 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-269">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="f1c0e-270">그런 다음 해당 결과를 캡처하고 각 리포지토리 이름을 콘솔에 쓰도록 `Main` 메서드를 수정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-270">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="f1c0e-271">`Main` 메서드는 이제 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-271">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="f1c0e-272">작업이 완료될 때까지 Task의 `Result` 속성에 대한 액세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-272">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="f1c0e-273">일반적으로 `ProcessRepositories` 메서드에서와 같이 작업의 컴파일을 `await`하는 것을 선호하겠지만 `Main` 메서드에서는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-273">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="f1c0e-274">추가 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="f1c0e-274">Reading More Information</span></span>

<span data-ttu-id="f1c0e-275">GitHub API에서 전송되는 JSON 패킷에 있는 속성을 몇 가지 더 처리하는 것으로 마무리해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-275">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="f1c0e-276">모든 기능을 알 수는 없겠지만 일부 속성을 추가하면 C# 언어의 몇 가지 기능이 추가로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-276">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="f1c0e-277">먼저 `Repository` 클래스 정의에 몇 가지 간단한 형식을 더 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-277">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="f1c0e-278">해당 클래스에 다음 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-278">Add these properties to that class:</span></span>

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

<span data-ttu-id="f1c0e-279">이러한 속성은 기본적으로 문자열 형식(JSON 패킷에 포함된 형식)을 대상 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-279">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="f1c0e-280"><xref:System.Uri> 형식은 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-280">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="f1c0e-281">이 형식은 URI 또는 이 경우에는 URL을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-281">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="f1c0e-282">`Uri` 및 `int` 형식의 경우 JSON 패킷에 대상 형식으로 변환되지 않는 데이터가 포함되어 있으면 serialization 작업은 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-282">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="f1c0e-283">이러한 데이터를 추가한 경우에는 해당 요소를 표시하도록 `Main` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-283">Once you've added these, update the `Main` method to display those elements:</span></span>

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
<span data-ttu-id="f1c0e-284">마지막 단계로, 최종 밀어넣기 작업을 위한 정보를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-284">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="f1c0e-285">이 정보는 JSON 응답에서 다음 방식으로 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-285">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="f1c0e-286">해당 형식은 표준 .NET <xref:System.DateTime> 형식을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-286">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="f1c0e-287">따라서 사용자 지정 변환 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-287">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="f1c0e-288">또한 `Repository` 클래스 사용자에게 원시 문자열이 노출되는 것을 원하지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-288">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="f1c0e-289">특성도 이러한 작업을 제어하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-289">Attributes can help control that as well.</span></span> <span data-ttu-id="f1c0e-290">먼저 `Repository` 클래스에서 날짜/시간에 대한 문자열 표현을 포함할 `private` 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-290">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="f1c0e-291">`DataMember` 특성은 공용 멤버가 아니어도 처리되어야 함을 serializer에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-291">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="f1c0e-292">다음에는 문자열을 유효한 <xref:System.DateTime> 개체로 변환한 후 해당 <xref:System.DateTime>을 반환하는 공용 읽기 전용 속성을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-292">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

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

<span data-ttu-id="f1c0e-293">위의 새 구문을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-293">Let's go over the new constructs above.</span></span> <span data-ttu-id="f1c0e-294">`IgnoreDataMember` 특성은 이 형식을 임의 JSON 개체에 쓰거나 이 개체에서 읽지 않아야 함을 serializer에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-294">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="f1c0e-295">이 속성은 `get` 접근자만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-295">This property contains only a `get` accessor.</span></span> <span data-ttu-id="f1c0e-296">`set` 접근자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-296">There is no `set` accessor.</span></span> <span data-ttu-id="f1c0e-297">바로 C#에서 *읽기 전용* 속성을 정의하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-297">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="f1c0e-298">(C#에서 *쓰기 전용* 속성을 만들 수 있지만 해당 값은 제한됩니다.) <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> 메서드는 제공된 날짜 형식을 사용하여 문자열을 구문 분석하고 <xref:System.DateTime> 개체를 만들고, `CultureInfo` 개체를 사용하여 `DateTime`에 메타데이터를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-298">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="f1c0e-299">구문 분석 작업이 실패하는 경우 속성 접근자가 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-299">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="f1c0e-300"><xref:System.Globalization.CultureInfo.InvariantCulture> 를 사용하려면 `repo.cs`의 `using` 문에 <xref:System.Globalization> 네임스페이스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-300">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="f1c0e-301">마지막으로 콘솔에 output 문을 하나 더 추가하면 이 앱을 빌드하고 다시 실행할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-301">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="f1c0e-302">이제 해당 버전이 [완성된 샘플](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient)과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-302">Your version should now match the [finished sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="f1c0e-303">결론</span><span class="sxs-lookup"><span data-stu-id="f1c0e-303">Conclusion</span></span>

<span data-ttu-id="f1c0e-304">이 자습서에서는 웹 요청을 수행하고, 결과를 구문 분석하고, 해당 결과의 속성을 표시하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-304">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="f1c0e-305">또한 프로젝트에 종속성으로 새 패키지를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-305">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="f1c0e-306">개체 지향 기술을 지원하는 C# 언어의 일부 기능을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c0e-306">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
