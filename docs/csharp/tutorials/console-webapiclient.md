---
title: .NET Core를 사용하여 REST 클라이언트 만들기
description: 이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다.
ms.date: 03/06/2017
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: bc3c23b277b233efba9f32cc49b29ac905f3abc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="rest-client"></a><span data-ttu-id="37cfd-103">REST 클라이언트</span><span class="sxs-lookup"><span data-stu-id="37cfd-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="37cfd-104">소개</span><span class="sxs-lookup"><span data-stu-id="37cfd-104">Introduction</span></span>
<span data-ttu-id="37cfd-105">이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="37cfd-106">다음을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-106">You’ll learn:</span></span>
*   <span data-ttu-id="37cfd-107">.NET Core CLI(명령줄 인터페이스)의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="37cfd-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="37cfd-108">C# 언어 기능의 개요</span><span class="sxs-lookup"><span data-stu-id="37cfd-108">An overview of C# Language features.</span></span>
*   <span data-ttu-id="37cfd-109">NuGet으로 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="37cfd-109">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="37cfd-110">HTTP 통신</span><span class="sxs-lookup"><span data-stu-id="37cfd-110">HTTP Communications</span></span>
*   <span data-ttu-id="37cfd-111">JSON 정보 처리</span><span class="sxs-lookup"><span data-stu-id="37cfd-111">Processing JSON information</span></span>
*   <span data-ttu-id="37cfd-112">특성을 사용하여 구성 관리</span><span class="sxs-lookup"><span data-stu-id="37cfd-112">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="37cfd-113">GitHub에서 REST 서비스에 HTTP 요청을 실행하는 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="37cfd-114">JSON 형식의 정보를 읽은 후 해당 JSON 패킷을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="37cfd-115">마지막으로 C# 개체를 사용하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="37cfd-116">이 자습서에는 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="37cfd-117">하나씩 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-117">Let’s build them one by one.</span></span>

<span data-ttu-id="37cfd-118">이 항목에 대한 [최종 샘플](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)을 따르려는 경우 해당 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="37cfd-119">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37cfd-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37cfd-120">전제 조건</span><span class="sxs-lookup"><span data-stu-id="37cfd-120">Prerequisites</span></span>
<span data-ttu-id="37cfd-121">.NET Core를 실행하려면 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="37cfd-122">[.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="37cfd-123">Windows, Linux, macOS 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="37cfd-124">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="37cfd-125">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="37cfd-126">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-126">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="37cfd-127">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="37cfd-127">Create the Application</span></span>
<span data-ttu-id="37cfd-128">첫 번째 단계에서는 새 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-128">The first step is to create a new application.</span></span> <span data-ttu-id="37cfd-129">명령 프롬프트를 열고 응용 프로그램에 대한 새 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="37cfd-130">해당 디렉터리를 현재 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-130">Make that the current directory.</span></span> <span data-ttu-id="37cfd-131">명령 프롬프트에 명령 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="37cfd-132">이렇게 하면 기본 "Hello World" 응용 프로그램에 대한 시작 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="37cfd-133">파일 수정을 시작하기 전에 간단한 Hello World 응용 프로그램을 실행하는 단계를 진행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-133">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="37cfd-134">응용 프로그램을 만든 후에 명령 프롬프트에서 `dotnet restore`([참고 참조](#dotnet-restore-note))를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-134">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="37cfd-135">이 명령은 NuGet 패키지 복원 프로세스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-135">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="37cfd-136">NuGet은 .NET 패키지 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-136">NuGet is a .NET package manager.</span></span> <span data-ttu-id="37cfd-137">이 명령은 프로젝트에 대한 누락된 종속성 중 하나를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-137">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="37cfd-138">이 프로젝트는 새 프로젝트이므로 어떤 종속성도 없습니다. 따라서 처음 실행하면 .NET Core 프레임워크가 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-138">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="37cfd-139">이 초기 단계 후에 새 종속 패키지를 추가하거나 종속성 버전을 업데이트할 때 `dotnet restore`([참고 참조](#dotnet-restore-note))를 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-139">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="37cfd-140">패키지를 복원한 후 `dotnet build`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="37cfd-141">이렇게 하면 빌드 엔진이 실행되고 응용 프로그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-141">This executes the build engine and creates your application.</span></span> <span data-ttu-id="37cfd-142">마지막으로 `dotnet run`을 실행하여 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-142">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="37cfd-143">새 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="37cfd-143">Adding New Dependencies</span></span>
<span data-ttu-id="37cfd-144">.NET Core의 주요 디자인 목표 중 하나는 .NET Framework 설치의 크기를 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-144">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="37cfd-145">.NET Core 응용 프로그램 프레임워크에는 .NET Full Framework의 가장 일반적인 요소만 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-145">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="37cfd-146">응용 프로그램에 일부 기능을 위해 추가 라이브러리가 필요한 경우 C# 프로젝트(\*.csproj) 파일에 해당 종속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-146">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="37cfd-147">현재 예제에서는 응용 프로그램이 JSON 응답을 처리할 수 있도록 `System.Runtime.Serialization.Json` 패키지를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-147">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="37cfd-148">`csproj` 프로젝트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-148">Open your `csproj` project file.</span></span> <span data-ttu-id="37cfd-149">파일의 첫 번째 줄은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-149">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="37cfd-150">이 줄 바로 뒤에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-150">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="37cfd-151">대부분의 코드 편집기는 이러한 라이브러리의 완성된 다양한 버전을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-151">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="37cfd-152">일반적으로 추가하는 모든 패키지의 최신 버전을 사용하려고 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-152">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="37cfd-153">그러나 모든 패키지의 버전이 일치하는지와 .NET Core 응용 프로그램 프레임워크의 버전도 일치하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-153">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="37cfd-154">이러한 변경을 수행한 후에는 패키지가 시스템에 설치되도록 `dotnet restore`([참고 참조](#dotnet-restore-note))를 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-154">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="37cfd-155">웹 요청 수행</span><span class="sxs-lookup"><span data-stu-id="37cfd-155">Making Web Requests</span></span>
<span data-ttu-id="37cfd-156">이제 웹에서 데이터 검색을 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-156">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="37cfd-157">이 응용 프로그램에서는 [GitHub API](https://developer.github.com/v3/)에서 정보를 읽게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-157">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="37cfd-158">[.NET Foundation](http://www.dotnetfoundation.org/) 상위 항목 아래에서 프로젝트에 대한 정보를 읽어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-158">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="37cfd-159">먼저 GitHub API에 대해 요청을 수행하여 프로젝트에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-159">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="37cfd-160">사용할 끝점은 [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos)입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-160">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="37cfd-161">이러한 프로젝트에 대해 모든 정보를 검색하려고 하므로 HTTP GET 요청을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-161">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="37cfd-162">브라우저도 HTTP GET 요청을 사용하므로 해당 URL을 브라우저에 붙여 넣어 수신되고 처리 중인 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-162">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="37cfd-163"><xref:System.Net.Http.HttpClient> 클래스를 사용하여 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-163">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="37cfd-164">모든 최신 .NET API와 마찬가지로 <xref:System.Net.Http.HttpClient> 는 장기 실행되는 API에 대해 비동기 메서드만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-164">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="37cfd-165">먼저 비동기 메서드를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-165">Start by making an async method.</span></span> <span data-ttu-id="37cfd-166">응용 프로그램의 기능을 빌드할 때 구현을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-166">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="37cfd-167">먼저 프로젝트 디렉터리에서 `program.cs` 파일을 열고 `Program` 클래스에 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-167">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="37cfd-168">C# 컴파일러에서 <xref:System.Threading.Tasks.Task> 형식을 인식하도록 `using` 문을 `Main` 메서드 맨 위에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-168">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="37cfd-169">이때 프로젝트를 빌드하면 이 메서드에는 `await` 연산자가 없어서 동기적으로 실행되므로 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-169">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="37cfd-170">지금은 이 경고를 무시하세요. 메서드를 입력할 때 `await` 연산자를 추가할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-170">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="37cfd-171">다음에는 `namespace` 문에 정의된 네임스페이스의 이름을 기본값인 `ConsoleApp`에서 `WebAPIClient`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-171">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="37cfd-172">나중에 이 네임스페이스에서 `repo` 클래스를 정의할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-172">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="37cfd-173">다음에는 `Main` 메서드를 업데이트하여 이 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-173">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="37cfd-174">`ProcessRepositories` 메서드는 작업을 반환합니다. 이 작업이 완료되기 전에 프로그램을 종료하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-174">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="37cfd-175">따라서 `Wait` 메서드를 사용하여 작업이 완료될 때까지 차단하고 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-175">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="37cfd-176">이제 아무 작업도 수행하지 않지만 비동기적으로는 수행하는 프로그램이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-176">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="37cfd-177">이것을 개선해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-177">Let's improve it.</span></span>

<span data-ttu-id="37cfd-178">먼저 웹에서 데이터를 검색할 수 있는 개체가 필요합니다. 이를 위해 <xref:System.Net.Http.HttpClient>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-178">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="37cfd-179">이 개체는 요청 및 응답을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-179">This object handles the request and the responses.</span></span> <span data-ttu-id="37cfd-180">Program.cs 파일 내의 `Program` 클래스에서 해당 형식의 단일 인스턴스를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-180">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

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

 <span data-ttu-id="37cfd-181">다시 `ProcessRepositories` 메서드로 돌아가 첫 번째 버전을 채워 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-181">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="37cfd-182">컴파일을 위해 파일 맨 위에 2개의 새 using 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-182">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="37cfd-183">이 첫 번째 버전은 dotnet foundation 조직의 모든 리포지토리 목록을 읽으라는 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-183">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="37cfd-184">(.NET Foundation의 gitHub ID는 'dotnet'임)</span><span class="sxs-lookup"><span data-stu-id="37cfd-184">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="37cfd-185">첫 몇 줄은 이 요청에 대해 <xref:System.Net.Http.HttpClient>를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-185">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="37cfd-186">먼저 GitHub JSON 응답을 수락하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-186">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="37cfd-187">이 형식은 단순히 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-187">This format is simply JSON.</span></span> <span data-ttu-id="37cfd-188">다음 줄은 이 개체의 모든 요청에 사용자 에이전트 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-188">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="37cfd-189">이러한 두 가지 헤더는 GitHub 서버 코드에서 확인되며 GitHub에서 정보를 검색하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-189">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="37cfd-190"><xref:System.Net.Http.HttpClient> 를 구성한 후에는 웹 요청을 수행하고 응답을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-190">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="37cfd-191">이 첫 번째 버전에서는 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 편의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-191">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="37cfd-192">이 편의 메서드는 웹 요청을 수행하는 작업을 시작한 다음, 요청이 반환될 때 응답 스트림을 읽고 해당 스트림에서 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-192">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="37cfd-193">응답의 본문은 <xref:System.String> 으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-193">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="37cfd-194">작업이 완료되면 이 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-194">The string is available when the task completes.</span></span> 

<span data-ttu-id="37cfd-195">이 메서드의 마지막 두 줄은 해당 작업을 대기하고 콘솔에 응답을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-195">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="37cfd-196">앱을 빌드한 다음 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-196">Build the app, and run it.</span></span> <span data-ttu-id="37cfd-197">`ProcessRepositories`에는 `await` 연산자가 포함되므로 이제 빌드 경고는 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-197">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="37cfd-198">길게 표시되는 JSON 형식 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-198">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="37cfd-199">JSON 결과 처리</span><span class="sxs-lookup"><span data-stu-id="37cfd-199">Processing the JSON Result</span></span>

<span data-ttu-id="37cfd-200">지금까지 웹 서버에서 응답을 검색하고 해당 응답에 포함된 텍스트를 표시하는 코드를 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-200">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="37cfd-201">다음에는 JSON 응답을 C# 개체로 변환해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-201">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="37cfd-202">JSON Serializer는 JSON 데이터를 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-202">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="37cfd-203">가장 먼저 수행할 작업은 이 응답 중에서 사용하는 정보를 포함하는 C# 클래스 형식을 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-203">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="37cfd-204">리포지토리 이름을 포함하는 간단한 C# 형식 먼저 시작하여 천천히 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-204">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

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

<span data-ttu-id="37cfd-205">'repo.cs'라는 새 파일에 위 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-205">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="37cfd-206">이 버전의 클래스는 JSON 데이터를 처리하는 가장 간단한 경로를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-206">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="37cfd-207">클래스 이름 및 멤버 이름은 다음 C# 규칙 대신 JSON 패킷에 사용된 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-207">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="37cfd-208">나중에 몇 가지 구성 특성을 제공하여 수정할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-208">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="37cfd-209">이 클래스에서는 JSON serialization 및 deserialization의 또 다른 중요한 특징을 보여 줍니다. 즉, JSON 패킷의 모든 필드가 이 클래스에 속하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-209">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="37cfd-210">JSON serializer는 사용되는 클래스 형식에 포함되지 않은 정보를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-210">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="37cfd-211">이 특징 때문에 JSON 패킷의 필드 일부에만 작용하는 형식을 보다 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-211">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="37cfd-212">이제 형식을 만들었으므로 deserialize를 수행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-212">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="37cfd-213"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-213">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="37cfd-214">이 개체는 검색하는 JSON 패킷에 필요한 CLR 형식을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-214">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="37cfd-215">GitHub의 패킷에는 리포지토리 시퀀스가 포함되어 있으므로 `List<repo>`가 올바른 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-215">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="37cfd-216">`ProcessRepositories` 메서드에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-216">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="37cfd-217">두 개의 새 네임스페이스를 사용하고 있으므로 해당 네임스페이스도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-217">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="37cfd-218">다음으로, serializer를 사용하여 JSON을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-218">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="37cfd-219">`ProcessRepositories` 메서드의 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 호출을 다음 두 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-219">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="37cfd-220">현재 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 대신 <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)>를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-220">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="37cfd-221">serializer는 해당 소스로 문자열 대신 스트림을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-221">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="37cfd-222">위의 두 번째 줄에서 사용되는 C# 언어의 몇 가지 기능에 대해 설명해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-222">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="37cfd-223"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)>에 대한 인수는 `await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-223">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="37cfd-224">지금까지는 대입문의 일부로만 볼 수 있었지만 Await 식은 코드의 거의 모든 위치에 나올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-224">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="37cfd-225">둘째로 `as` 연산자는 컴파일 타임 형식 `object`에서 `List<repo>`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-225">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="37cfd-226"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> 선언은 <xref:System.Object?displayProperty=nameWithType> 형식의 개체로 반환됨을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-226">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="37cfd-227"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)>는 사용자가 생성 시에 지정한 형식을 반환합니다(이 자습서에서는 `List<repo>`).</span><span class="sxs-lookup"><span data-stu-id="37cfd-227"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="37cfd-228">변환이 성공하지 못하면 `as` 연산자는 예외를 throw하는 대신 `null`을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-228">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="37cfd-229">이 섹션이 거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-229">You're almost done with this section.</span></span> <span data-ttu-id="37cfd-230">JSON을 C# 개체로 변환했으므로 각 리포지토리의 이름을 표시해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-230">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="37cfd-231">다음 줄을</span><span class="sxs-lookup"><span data-stu-id="37cfd-231">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="37cfd-232">다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-232">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="37cfd-233">응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-233">Compile and run the application.</span></span> <span data-ttu-id="37cfd-234">.NET Foundation에 포함된 리포지토리의 이름이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-234">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="37cfd-235">serialization 제어</span><span class="sxs-lookup"><span data-stu-id="37cfd-235">Controlling Serialization</span></span>

<span data-ttu-id="37cfd-236">더 많은 기능을 추가하기 전에 `repo` 형식의 주소를 지정하고 더 많은 표준 C# 규칙을 따르도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-236">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="37cfd-237">이 작업을 위해 JSON Serializer가 작동하는 방식을 제어하는 *특성*을 `repo` 형식에 주석으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-237">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="37cfd-238">여기서는 이러한 특성을 사용하여 JSON 키 이름과 C# 클래스 및 멤버 이름 간에 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-238">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="37cfd-239">사용되는 2가지 특성은 `DataContract` 특성 및 `DataMember` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-239">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="37cfd-240">규칙에 따라 모든 Attribute 클래스는 접미사 `Attribute`로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-240">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="37cfd-241">그러나 특성을 적용할 때 해당 접미사를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-241">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="37cfd-242">`DataContract` 및 `DataMember` 특성은 다른 라이브러리에 포함되므로 해당 라이브러리를 C# 프로젝트 파일에 종속성으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-242">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="37cfd-243">다음 줄을 프로젝트 파일의 `<ItemGroup>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-243">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="37cfd-244">파일을 저장한 후 `dotnet restore`([참고 참조](#dotnet-restore-note))를 실행하여 이 패키지를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-244">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="37cfd-245">다음으로 `repo.cs` 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-245">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="37cfd-246">이름을 파스칼식 대/소문자를 사용하도록 이름을 변경하고 `Repository`라고 정확히 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-246">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="37cfd-247">여전히 JSON 'repo' 노드를 이 형식에 매핑하려고 하므로 `DataContract` 특성을 클래스 선언에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-247">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="37cfd-248">이 특성의 `Name` 속성을 이 형식에 매핑되는 JSON 노드의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-248">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="37cfd-249"><xref:System.Runtime.Serialization.DataContractAttribute> 는  <xref:System.Runtime.Serialization> 네임스페이스의 멤버이므로 파일 맨 위에 해당 `using` 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-249">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="37cfd-250">`repo` 클래스의 이름을 `Repository`로 변경했으므로 Program.cs에서도 동일하게 이름을 변경해야 합니다(일부 편집기에서 이러한 변경을 자동으로 수행하는 이름 바꾸기 리팩터링이 지원될 수 있음).</span><span class="sxs-lookup"><span data-stu-id="37cfd-250">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="37cfd-251">다음으로 <xref:System.Runtime.Serialization.DataMemberAttribute> 클래스를 사용하여 `name` 필드를 동일하게 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-251">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="37cfd-252">repo.cs에서 `name` 필드의 선언을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-252">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="37cfd-253">이렇게 변경할 경우 program.cs에서 각 리포지토리의 이름을 쓰는 코드를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-253">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="37cfd-254">`dotnet build` 다음에 `dotnet run`을 수행하여 매핑이 올바르게 수행되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-254">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="37cfd-255">이전과 동일한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-255">You should see the same output as before.</span></span> <span data-ttu-id="37cfd-256">웹 서버의 더 많은 속성을 처리하기 전에 `Repository` 클래스를 한 가지 더 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-256">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="37cfd-257">`Name` 멤버는 공개적으로 액세스할 수 있는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-257">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="37cfd-258">그렇지만 적절한 개체 지향 방식은 아니므로 속성으로 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-258">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="37cfd-259">이 예제에서는 속성을 가져오거나 설정할 때 특정 코드를 실행할 필요가 없으며 속성을 변경하여 `Repository` 클래스를 사용하는 코드를 중단하지 않고도 나중에 해당 변경 내용을 보다 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-259">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="37cfd-260">필드 정의를 제거한 후 [자동 구현 속성](../programming-guide/classes-and-structs/auto-implemented-properties.md)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-260">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="37cfd-261">컴파일러는 `get` 및 `set` 접근자의 본문 뿐만 아니라 이름을 저장하는 private 필드도 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-261">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="37cfd-262">이 작업은 다음 코드를 직접 입력하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-262">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="37cfd-263">새로운 기능을 추가하기 전에 한 가지 더 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-263">Let's make one more change before adding new features.</span></span> <span data-ttu-id="37cfd-264">`ProcessRepositories` 메서드는 비동기 작업을 수행하고 리포지토리 컬렉션을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-264">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="37cfd-265">이 메서드에서 `List<Repository>`로 돌아가 정보를 쓰는 코드를 `Main` 메서드로 이동해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-265">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="37cfd-266">`ProcessRepositories`의 시그니처를 변경하여 `Repository` 개체의 목록을 해당 결과로 표시하는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-266">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="37cfd-267">다음에는 JSON 응답을 처리한 후 리포지토리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-267">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="37cfd-268">이 개체를 `async`로 표시했으므로 컴파일러는 해당 반환에 대한 `Task<T>` 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-268">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="37cfd-269">그런 다음 해당 결과를 캡처하고 각 리포지토리 이름을 콘솔에 쓰도록 `Main` 메서드를 수정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-269">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="37cfd-270">`Main` 메서드는 이제 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-270">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="37cfd-271">작업이 완료될 때까지 Task의 `Result` 속성에 대한 액세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-271">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="37cfd-272">일반적으로 `ProcessRepositories` 메서드에서와 같이 작업의 컴파일을 `await`하는 것을 선호하겠지만 `Main` 메서드에서는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-272">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="37cfd-273">추가 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="37cfd-273">Reading More Information</span></span>

<span data-ttu-id="37cfd-274">GitHub API에서 전송되는 JSON 패킷에 있는 속성을 몇 가지 더 처리하는 것으로 마무리해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-274">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="37cfd-275">모든 기능을 알 수는 없겠지만 일부 속성을 추가하면 C# 언어의 몇 가지 기능이 추가로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-275">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="37cfd-276">먼저 `Repository` 클래스 정의에 몇 가지 간단한 형식을 더 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-276">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="37cfd-277">해당 클래스에 다음 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-277">Add these properties to that class:</span></span>

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

<span data-ttu-id="37cfd-278">이러한 속성은 기본적으로 문자열 형식(JSON 패킷에 포함된 형식)을 대상 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-278">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="37cfd-279"><xref:System.Uri> 형식은 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-279">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="37cfd-280">이 형식은 URI 또는 이 경우에는 URL을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-280">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="37cfd-281">`Uri` 및 `int` 형식의 경우 JSON 패킷에 대상 형식으로 변환되지 않는 데이터가 포함되어 있으면 serialization 작업은 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-281">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="37cfd-282">이러한 데이터를 추가한 경우에는 해당 요소를 표시하도록 `Main` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-282">Once you've added these, update the `Main` method to display those elements:</span></span>

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
<span data-ttu-id="37cfd-283">마지막 단계로, 최종 밀어넣기 작업을 위한 정보를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-283">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="37cfd-284">이 정보는 JSON 응답에서 다음 방식으로 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-284">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="37cfd-285">해당 형식은 표준 .NET <xref:System.DateTime> 형식을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-285">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="37cfd-286">따라서 사용자 지정 변환 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-286">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="37cfd-287">또한 `Repository` 클래스 사용자에게 원시 문자열이 노출되는 것을 원하지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-287">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="37cfd-288">특성도 이러한 작업을 제어하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-288">Attributes can help control that as well.</span></span> <span data-ttu-id="37cfd-289">먼저 `Repository` 클래스에서 날짜/시간에 대한 문자열 표현을 포함할 `private` 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-289">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="37cfd-290">`DataMember` 특성은 공용 멤버가 아니어도 처리되어야 함을 serializer에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-290">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="37cfd-291">다음에는 문자열을 유효한 <xref:System.DateTime> 개체로 변환한 후 해당 <xref:System.DateTime>을 반환하는 공용 읽기 전용 속성을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-291">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

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

<span data-ttu-id="37cfd-292">위의 새 구문을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-292">Let's go over the new constructs above.</span></span> <span data-ttu-id="37cfd-293">`IgnoreDataMember` 특성은 이 형식을 임의 JSON 개체에 쓰거나 이 개체에서 읽지 않아야 함을 serializer에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-293">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="37cfd-294">이 속성은 `get` 접근자만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-294">This property contains only a `get` accessor.</span></span> <span data-ttu-id="37cfd-295">`set` 접근자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-295">There is no `set` accessor.</span></span> <span data-ttu-id="37cfd-296">바로 C#에서 *읽기 전용* 속성을 정의하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-296">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="37cfd-297">(C#에서 *쓰기 전용* 속성을 만들 수 있지만 해당 값은 제한됩니다.) <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> 메서드는 제공된 날짜 형식을 사용하여 문자열을 구문 분석하고 <xref:System.DateTime> 개체를 만들고, `CultureInfo` 개체를 사용하여 `DateTime`에 메타데이터를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-297">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="37cfd-298">구문 분석 작업이 실패하는 경우 속성 접근자가 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-298">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="37cfd-299"><xref:System.Globalization.CultureInfo.InvariantCulture> 를 사용하려면 `repo.cs`의 `using` 문에 <xref:System.Globalization> 네임스페이스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-299">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="37cfd-300">마지막으로 콘솔에 output 문을 하나 더 추가하면 이 앱을 빌드하고 다시 실행할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-300">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="37cfd-301">이제 해당 버전이 [완성된 샘플](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-301">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="37cfd-302">결론</span><span class="sxs-lookup"><span data-stu-id="37cfd-302">Conclusion</span></span>

<span data-ttu-id="37cfd-303">이 자습서에서는 웹 요청을 수행하고, 결과를 구문 분석하고, 해당 결과의 속성을 표시하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-303">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="37cfd-304">또한 프로젝트에 종속성으로 새 패키지를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-304">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="37cfd-305">개체 지향 기술을 지원하는 C# 언어의 일부 기능을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="37cfd-305">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
