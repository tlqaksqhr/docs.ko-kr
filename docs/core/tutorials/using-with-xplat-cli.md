---
title: CLI를 사용하여 .NET Core 시작
description: .NET Core CLI(명령줄 인터페이스)를 사용하여 Windows, Linux 또는 macOS에서 .NET Core를 시작하는 방법을 보여 주는 단계별 자습서입니다.
author: cartermp
ms.author: mairaw
ms.date: 03/08/2017
ms.technology: dotnet-cli
ms.openlocfilehash: 57045a91ce62a730493d219bdf7c30e90fe57759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="b6ad6-103">명령줄을 사용하여 Windows/Linux/macOS에서 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="b6ad6-103">Getting started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="b6ad6-104">이 항목에서는 .NET Core CLI 도구를 사용하여 컴퓨터에서 플랫폼 간 앱 개발을 시작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-104">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="b6ad6-105">.NET Core CLI 도구 집합에 익숙하지 않은 경우 [.NET Core SDK 개요](../tools/index.md)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6ad6-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="b6ad6-106">Prerequisites</span></span>

- <span data-ttu-id="b6ad6-107">[.NET Core SDK 1.0](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="b6ad6-107">[.NET Core SDK 1.0](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="b6ad6-108">선택하는 텍스트 편집기 또는 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="b6ad6-109">Hello, 콘솔 앱!</span><span class="sxs-lookup"><span data-stu-id="b6ad6-109">Hello, Console App!</span></span>

<span data-ttu-id="b6ad6-110">GitHub의 dotnet/samples 리포지토리에서 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="b6ad6-111">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="b6ad6-112">명령 프롬프트를 열고 *Hello*라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="b6ad6-113">만든 폴더로 이동하고 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-113">Navigate to the folder you created and type the following:</span></span>

```
$ dotnet new console
$ dotnet restore
$ dotnet run
```

<span data-ttu-id="b6ad6-114">이제 간단한 연습을 해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-114">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="b6ad6-115">[`dotnet new`](../tools/dotnet-new.md)는 콘솔 앱을 빌드하는 데 필요한 종속성이 있는 최신 `Hello.csproj` 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-115">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="b6ad6-116">응용 프로그램에 대한 진입점을 포함하는 기본 파일인 `Program.cs`도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-116">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="b6ad6-117">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="b6ad6-117">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]   

   <span data-ttu-id="b6ad6-118">프로젝트 파일은 종속성을 복원하고 프로그램을 빌드하는 데 필요한 모든 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="b6ad6-119">`OutputType` 태그에서는 실행 파일, 즉 콘솔 응용 프로그램을 빌드하고 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-119">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="b6ad6-120">`TargetFramework` 태그에서는 대상으로 하는 .NET 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-120">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="b6ad6-121">고급 시나리오에서는 여러 대상 프레임워크를 지정하고 이 모든 프레임워크를 단일 작업으로 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="b6ad6-122">이 자습서에서는 .NET Core 1.0에 대해서만 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-122">In this tutorial, we'll stick to building only for .NET Core 1.0.</span></span>

   <span data-ttu-id="b6ad6-123">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="b6ad6-123">`Program.cs`:</span></span>

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]   

   <span data-ttu-id="b6ad6-124">프로그램은 `using System`으로 시작됩니다. 즉, "`System` 네임스페이스의 모든 항목을 이 파일 범위로 가져옵니다".</span><span class="sxs-lookup"><span data-stu-id="b6ad6-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="b6ad6-125">`System` 네임스페이스에는 `string` 또는 숫자 형식과 같은 기본 구문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-125">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="b6ad6-126">그런 다음 `Hello`라는 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="b6ad6-127">이 이름은 원하는 값으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-127">You can change this to anything you want.</span></span> <span data-ttu-id="b6ad6-128">`Program`이라는 클래스는 해당 네임스페이스 내에서 인수로 문자열 배열을 사용하는 `Main` 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="b6ad6-129">이 배열에는 컴파일된 프로그램을 호출할 때 전달된 인수 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-129">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="b6ad6-130">이 배열은 그대로 사용되지 않습니다. 프로그램은 모두 "Hello World!"를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-130">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="b6ad6-131">표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-131">to the console.</span></span> <span data-ttu-id="b6ad6-132">나중에 이 인수를 사용하는 코드를 변경할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

2. `$ dotnet restore`

   <span data-ttu-id="b6ad6-133">[`dotnet restore`](../tools/dotnet-restore.md)는 [NuGet](https://www.nuget.org/)(.NET 패키지 관리자)을 호출하여 종속성 트리를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-133">[`dotnet restore`](../tools/dotnet-restore.md) calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="b6ad6-134">NuGet은 *Hello.csproj* 파일을 분석하고, 파일에 명시된 종속성을 다운로드하고(또는 컴퓨터의 캐시에서 종속성을 가져오고), *obj/project.assets.json* 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-134">NuGet analyzes the *Hello.csproj* file, downloads the dependencies stated in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file.</span></span>  <span data-ttu-id="b6ad6-135">*project.assets.json* 파일은 컴파일 및 실행하려면 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-135">The *project.assets.json* file is necessary to be able to compile and run.</span></span>
   
   <span data-ttu-id="b6ad6-136">*project.assets.json* 파일은 NuGet 종속성 및 앱을 설명하는 기타 정보로 구성된 그래프의 지속적이고 전체적인 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-136">The *project.assets.json* file is a persisted and complete set of the graph of NuGet dependencies and other information describing an app.</span></span>  <span data-ttu-id="b6ad6-137">[`dotnet build`](../tools/dotnet-build.md) 및 [`dotnet run`](../tools/dotnet-run.md) 같은 다른 도구에서는 이 파일을 읽고, NuGet 종속성 및 바인딩 확인의 올바른 집합으로 소스 코드를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-137">This file is read by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), enabling them to process the source code with a correct set of NuGet dependencies and binding resolutions.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="b6ad6-138">[`dotnet run`](../tools/dotnet-run.md)은 [`dotnet build`](../tools/dotnet-build.md)를 호출하여 빌드 대상이 빌드되었는지를 확인하고 `dotnet <assembly.dll>`을 호출하여 대상 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-138">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
   
    ```
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="b6ad6-139">또한 [`dotnet build`](../tools/dotnet-build.md)를 실행하여 빌드 콘솔 응용 프로그램을 실행하지 않고 코드를 컴파일할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-139">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="b6ad6-140">이로 인해 Windows에서는 `dotnet bin\Debug\netcoreapp1.0\Hello.dll`로, 다른 시스템에서는 `/`로 실행할 수 있는 컴파일된 응용 프로그램이 DLL 파일로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-140">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp1.0\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="b6ad6-141">이 항목의 뒷부분에서 살펴보겠지만, 응용 프로그램에 인수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-141">You may also specify arguments to the application as you'll see later on the topic.</span></span>

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="b6ad6-142">고급 시나리오에서는 .NET Core를 설치하지 않아도 되는 컴퓨터에 배포하고 실행할 수 있는 자체 포함된 플랫폼별 파일로 응용 프로그램을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-142">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="b6ad6-143">자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-143">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="b6ad6-144">프로그램 보강</span><span class="sxs-lookup"><span data-stu-id="b6ad6-144">Augmenting the program</span></span>

<span data-ttu-id="b6ad6-145">프로그램을 조금 변경해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-145">Let's change the program a bit.</span></span> <span data-ttu-id="b6ad6-146">피보나치 숫자가 흥미로우므로, 인수 사용과 함께 피보나치 숫자를 추가하여 앱을 실행하는 사람을 맞이해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-146">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="b6ad6-147">*Program.cs* 파일의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-147">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]   

2. <span data-ttu-id="b6ad6-148">[ `dotnet build` ](../tools/dotnet-build.md)를 실행하여 변경 내용을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-148">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="b6ad6-149">앱에 매개 변수를 전달하는 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-149">Run the program passing a parameter to the app:</span></span>

   ```
   $ dotnet run -- John
   Hello John!
   Fibonacci Numbers 1-15:
   1: 0
   2: 1
   3: 1
   4: 2
   5: 3
   6: 5
   7: 8
   8: 13
   9: 21
   10: 34
   11: 55
   12: 89
   13: 144
   14: 233
   15: 377
   ```

<span data-ttu-id="b6ad6-150">됐습니다!</span><span class="sxs-lookup"><span data-stu-id="b6ad6-150">And that's it!</span></span>  <span data-ttu-id="b6ad6-151">원하는 대로 `Program.cs`를 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-151">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="b6ad6-152">여러 파일 작업</span><span class="sxs-lookup"><span data-stu-id="b6ad6-152">Working with multiple files</span></span>

<span data-ttu-id="b6ad6-153">단순한 일회용 프로그램의 경우 단일 파일이 괜찮지만, 좀 더 복잡한 앱을 빌드하는 경우 프로젝트에 소스 파일이 여러 개 있을 수 있습니다. 일부 피보나치 값을 캐시하고 일부 재귀적 기능을 추가하여 이전의 피보나치 예제를 빌드해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-153">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span> 

1. <span data-ttu-id="b6ad6-154">다음 코드를 사용하여 *Hello* 디렉터리 내에 *FibonacciGenerator.cs*라는 새 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-154">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]   

2. <span data-ttu-id="b6ad6-155">다음 예제에서처럼 *Program.cs* 파일의 `Main` 메서드를 변경하여 새 클래스를 인스턴스화하고 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-155">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="b6ad6-156">[ `dotnet build` ](../tools/dotnet-build.md)를 실행하여 변경 내용을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-156">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="b6ad6-157">[`dotnet run`](../tools/dotnet-run.md)을 실행하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-157">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="b6ad6-158">다음은 프로그램 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-158">The following shows the program output:</span></span>

   ```
   0
   1
   1
   2
   3
   5
   8
   13
   21
   34
   55
   89
   144
   233
   377
   ```

<span data-ttu-id="b6ad6-159">됐습니다!</span><span class="sxs-lookup"><span data-stu-id="b6ad6-159">And that's it!</span></span> <span data-ttu-id="b6ad6-160">이제 여기에서 배운 기본 개념을 활용하여 고유의 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-160">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

<span data-ttu-id="b6ad6-161">이 자습서에 나와 있는 응용 프로그램 실행을 위한 명령과 단계는 개발하는 동안에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-161">Note that the commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="b6ad6-162">앱을 배포할 준비가 되면 .NET Core 앱에 대한 여러 [배포 전략](../deploying/index.md) 및 [ `dotnet publish` ](../tools/dotnet-publish.md) 명령을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6ad6-162">Once you're ready to deploy your app, you'll want to take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6ad6-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6ad6-163">See also</span></span>

[<span data-ttu-id="b6ad6-164">.NET Core CLI 도구를 사용하여 프로젝트 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="b6ad6-164">Organizing and testing projects with the .NET Core CLI tools</span></span>](testing-with-cli.md)
