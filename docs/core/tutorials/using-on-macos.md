---
title: macOS에서 .NET Core 시작
description: 이 문서에서는 Visual Studio Code를 사용하여 .NET Core 솔루션을 만드는 단계와 워크플로를 제공합니다.
author: bleroy
ms.author: mairaw
ms.date: 03/23/2017
ms.openlocfilehash: 5a4b2734137f59b29535f302dd17fb94329d676f
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245593"
---
# <a name="getting-started-with-net-core-on-macos"></a><span data-ttu-id="d3ecf-103">macOS에서 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="d3ecf-103">Getting started with .NET Core on macOS</span></span>

<span data-ttu-id="d3ecf-104">이 문서에서는 macOS용 .NET Core 솔루션을 만드는 단계와 워크플로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="d3ecf-105">프로젝트 및 단위 테스트를 만들고, 디버깅 도구를 사용하고, [NuGet](https://www.nuget.org/)을 통해 타사 라이브러리를 통합하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="d3ecf-106">이 문서에서는 macOS의 [Visual Studio Code](http://code.visualstudio.com)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-106">This article uses [Visual Studio Code](http://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3ecf-107">전제 조건</span><span class="sxs-lookup"><span data-stu-id="d3ecf-107">Prerequisites</span></span>

<span data-ttu-id="d3ecf-108">[.NET Core SDK](https://www.microsoft.com/net/core)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-108">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="d3ecf-109">.NET Core SDK에는 최신 버전의 .NET Core 프레임워크 및 런타임이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="d3ecf-110">[Visual Studio Code](http://code.visualstudio.com)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-110">Install [Visual Studio Code](http://code.visualstudio.com).</span></span> <span data-ttu-id="d3ecf-111">이 문서를 진행하면서 .NET Core 개발자 환경을 개선하는 Visual Studio Code 확장도 설치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="d3ecf-112">Visual Studio Code 팔레트를 열려면 Visual Studio Code를 열고 <kbd>F1</kbd> 키를 눌러 Visual Studio Code C# 확장을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="d3ecf-113">**ext install**을 입력하여 확장 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="d3ecf-114">C# 확장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-114">Select the C# extension.</span></span> <span data-ttu-id="d3ecf-115">Visual Studio Code를 다시 시작하여 확장을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="d3ecf-116">자세한 내용은 [Visual Studio Code C# 확장 문서](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="getting-started"></a><span data-ttu-id="d3ecf-117">시작</span><span class="sxs-lookup"><span data-stu-id="d3ecf-117">Getting started</span></span>

<span data-ttu-id="d3ecf-118">이 자습서에서는 라이브러리 프로젝트, 해당 라이브러리 프로젝트에 대한 테스트, 라이브러리를 사용하는 콘솔 응용 프로그램 등 프로젝트 3개를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="d3ecf-119">GitHub의 dotnet/samples 리포지토리에서 이 항목에 대한 [소스를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/golden)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this topic at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="d3ecf-120">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="d3ecf-121">Visual Studio Code를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-121">Start Visual Studio Code.</span></span> <span data-ttu-id="d3ecf-122"><kbd>Ctrl</kbd>+<kbd>\`</kbd> 키(역따옴표 또는 억음 문자)를 누르거나 메뉴에서 **보기 > 통합 터미널**을 선택하여 Visual Studio Code에서 포함된 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-122">Press <kbd>Ctrl</kbd>+<kbd>\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="d3ecf-123">Visual Studio Code 외부에서 작업하려는 경우 탐색기 **명령 프롬프트에서 열기** 명령(Mac 또는 Linux에서는 **터미널에서 열기**)을 사용하여 외부 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="d3ecf-124">하나 이상의 .NET Core 프로젝트에 대한 컨테이너로 사용되는 솔루션 파일을 먼저 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="d3ecf-125">터미널에서 *golden* 폴더를 만들고 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-125">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="d3ecf-126">이 폴더는 솔루션의 루트입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-126">This folder is the root of your solution.</span></span> <span data-ttu-id="d3ecf-127">[`dotnet new`](../tools/dotnet-new.md) 명령을 실행하여 *golden.sln*이라는 새 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-127">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="d3ecf-128">*golden* 폴더에서 다음 명령을 실행하여 *library* 폴더에 두 파일 *library.csproj* 및 *Class1.cs*를 생성하는 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-128">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="d3ecf-129">[`dotnet sln`](../tools/dotnet-sln.md) 명령을 실행하여 새로 만든 *library.csproj* 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-129">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="d3ecf-130">*library.csproj* 파일에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-130">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="d3ecf-131">라이브러리 메서드는 JSON 형식으로 개체를 직렬화 및 deserialize합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-131">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="d3ecf-132">JSON serialization 및 deserialization을 지원하려면 `Newtonsoft.Json` NuGet 패키지에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-132">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="d3ecf-133">`dotnet add` 명령은 프로젝트에 새 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-133">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="d3ecf-134">NuGet 패키지에 대한 참조를 추가하려면 [`dotnet add package`](../tools/dotnet-add-package.md) 명령을 사용하고 패키지 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-134">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="d3ecf-135">그러면 `Newtonsoft.Json` 및 해당 종속성이 라이브러리 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-135">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="d3ecf-136">또는 *library.csproj* 파일을 수동으로 편집하고 다음 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-136">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="d3ecf-137">종속성을 복원하고 *library* 내에 *obj* 폴더를 만드는 [`dotnet restore`](../tools/dotnet-restore.md)([참고 참조](#dotnet-restore-note))를 실행합니다. 이 폴더 안에는 *project.assets.json* 파일을 비롯한 세 개의 파일이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-137">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="d3ecf-138">*library* 폴더에서 *Class1.cs* 파일의 이름을 *Thing.cs*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-138">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="d3ecf-139">코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-139">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="d3ecf-140">`Thing` 클래스에는 공용 메서드 `Get`이 포함되어 있습니다. 이 메서드는 두 숫자의 합계를 반환하지만, 이 작업을 위해 합계를 문자열로 변환한 다음 정수로 deserialize합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-140">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="d3ecf-141">여기에는 [`using static` 지시문](../../csharp/language-reference/keywords/using-static.md), [식 본문 멤버](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), [문자열 보간](../../csharp/language-reference/tokens/interpolated.md) 등 많은 최신 C# 기능이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-141">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="d3ecf-142">[`dotnet build`](../tools/dotnet-build.md) 명령을 사용하여 라이브러리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-142">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="d3ecf-143">그러면 *golden/library/bin/Debug/netstandard1.4* 아래에 *library.dll* 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-143">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="d3ecf-144">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="d3ecf-144">Create the test project</span></span>

<span data-ttu-id="d3ecf-145">라이브러리에 대한 테스트 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-145">Build a test project for the library.</span></span> <span data-ttu-id="d3ecf-146">*golden* 폴더에서 새 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-146">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="d3ecf-147">테스트 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-147">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="d3ecf-148">컴파일러가 라이브러리 프로젝트를 찾아서 사용할 수 있도록 이전 섹션에서 만든 라이브러리에 대한 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-148">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="d3ecf-149">[`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-149">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="d3ecf-150">또는 *test-library.csproj* 파일을 수동으로 편집하고 다음 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-150">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="d3ecf-151">이제 종속성이 제대로 구성되었으므로 라이브러리에 대한 테스트를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-151">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="d3ecf-152">*UnitTest1.cs*를 열고 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-152">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="d3ecf-153">단위 테스트를 처음 만들 때는 값 42가 19+23(또는 42)과 같지 않다고 어설션하며(`Assert.NotEqual`) 이는 실패하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-153">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="d3ecf-154">단위 테스트 빌드 시 중요한 단계는 테스트 논리를 확인하기 위해 처음에 한 번 실패하는 테스트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-154">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="d3ecf-155">*golden* 폴더에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-155">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="d3ecf-156">이러한 명령은 모든 프로젝트를 재귀적으로 찾아 종속성을 복원하고 빌드한 다음 xUnit Test Runner를 활성화하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-156">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="d3ecf-157">예상대로 단일 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-157">The single test fails, as you expect.</span></span>

<span data-ttu-id="d3ecf-158">*UnitTest1.cs* 파일을 편집하고 어설션을 `Assert.NotEqual`에서 `Assert.Equal`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-158">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="d3ecf-159">*golden* 폴더에서 다음 명령을 실행하여 테스트를 다시 실행합니다. 이번에는 테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-159">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="d3ecf-160">콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="d3ecf-160">Create the console app</span></span>

<span data-ttu-id="d3ecf-161">다음 단계에 따라 만든 콘솔 앱은 이전에 만든 라이브러리 프로젝트에 대한 종속성을 가지며, 실행 시 해당 라이브러리 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-161">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="d3ecf-162">이 개발 패턴을 사용하면 여러 프로젝트에 재사용 가능한 라이브러리를 만드는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-162">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="d3ecf-163">*golden* 폴더에서 새 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-163">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="d3ecf-164">콘솔 앱 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-164">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="d3ecf-165">`dotnet add reference` 명령을 실행하여 라이브러리에 대한 종속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-165">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="d3ecf-166">`dotnet restore`([참고 참조](#dotnet-restore-note))를 실행하여 솔루션에 있는 세 프로젝트의 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-166">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="d3ecf-167">*Program.cs*를 열고 `Main` 메서드의 내용을 다음 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-167">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="d3ecf-168">*Program.cs* 파일의 맨 위에 두 개의 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-168">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="d3ecf-169">다음 `dotnet run` 명령을 실행하여 실행 파일을 실행합니다. 여기서 `dotnet run`에 대한 `-p` 옵션은 주 응용 프로그램에 대한 프로젝트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-169">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="d3ecf-170">앱이 "The answer is 42" 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-170">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="d3ecf-171">응용 프로그램 디버그</span><span class="sxs-lookup"><span data-stu-id="d3ecf-171">Debug the application</span></span>

<span data-ttu-id="d3ecf-172">`Main` 메서드의 `WriteLine` 문에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-172">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="d3ecf-173">이렇게 하려면 `WriteLine` 줄에 커서를 놓고 <kbd>F9</kbd> 키를 누르거나 중단점을 설정할 줄의 왼쪽 여백에서 마우스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-173">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="d3ecf-174">코드 줄 옆의 여백에 빨간색 원이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-174">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="d3ecf-175">중단점에 도달하면 중단점 줄이 실행되기 *전에* 코드 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-175">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="d3ecf-176">Visual Studio Code 도구 모음에서 디버그 아이콘을 선택하거나, 메뉴 모음에서 **보기 > 디버그**를 선택하거나, 바로 가기 키 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>를 사용하여 디버거 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-176">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Visual Studio Code 디버거](./media/using-on-macos/vscodedebugger.png)

<span data-ttu-id="d3ecf-178">디버거에서 응용 프로그램을 시작하려면 재생 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-178">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="d3ecf-179">앱이 실행을 시작하고 중단점까지 실행되며, 여기서 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-179">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="d3ecf-180">`Get` 메서드를 단계별로 실행하며 올바른 인수를 전달했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-180">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="d3ecf-181">응답이 42인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3ecf-181">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]