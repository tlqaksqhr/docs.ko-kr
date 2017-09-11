---
title: "CLI 도구를 사용한 .NET Core 앱 배포"
description: "CLI(명령줄 인터페이스) 도구를 사용한 .NET Core 앱 배포에 대해 알아봅니다."
keywords: ".NET, .NET Core, .NET Core 배포"
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 82ebe16d-5e1c-46cc-91e8-71974296429c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 005355868eefdbf21e3107f6db5230d7952276b2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a><span data-ttu-id="d90b9-104">CLI(명령줄 인터페이스) 도구를 사용하여 .NET Core 앱 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-104">Deploying .NET Core apps with command-line interface (CLI) tools</span></span>

<span data-ttu-id="d90b9-105">.NET Core 응용 프로그램은 응용 프로그램 이진을 포함하지만 대상 시스템에 .NET Core가 있는지 여부에 따라 달라지는 *프레임워크 종속 배포* 또는 응용 프로그램과 .NET Core 이진을 모두 포함하는 *자체 포함 배포*로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-105">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and the .NET Core binaries.</span></span> <span data-ttu-id="d90b9-106">개요는 [.NET Core 응용 프로그램 배포](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d90b9-106">For an overview, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="d90b9-107">다음 섹션에서는 [.NET Core 명령줄 인터페이스 도구](../tools/index.md)를 사용하여 다음과 같은 종류의 배포를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-107">The following sections show how to use [.NET Core command-line interface tools](../tools/index.md) to create the following kinds of deployments:</span></span>

- <span data-ttu-id="d90b9-108">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-108">Framework-dependent deployment</span></span>
- <span data-ttu-id="d90b9-109">타사 종속성이 있는 프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-109">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="d90b9-110">자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-110">Self-contained deployment</span></span>
- <span data-ttu-id="d90b9-111">타사 종속성이 있는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-111">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="d90b9-112">명령줄에서 작업하는 경우 선택한 프로그램 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-112">When working from the command line, you can use a program editor of your choice.</span></span> <span data-ttu-id="d90b9-113">프로그램 편집기가 [Visual Studio Code](https://code.visualstudio.com)인 경우 **보기** > **통합 터미널**을 선택하여 Visual Studio Code 환경 내에서 명령 콘솔을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-113">If your program editor is [Visual Studio Code](https://code.visualstudio.com), you can open a command console inside your Visual Studio Code environment by selecting **View** > **Integrated Terminal**.</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="d90b9-114">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-114">Framework-dependent deployment</span></span>

<span data-ttu-id="d90b9-115">타사 종속성이 없는 프레임워크 종속 배포에는 앱의 빌드, 테스트 및 게시만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-115">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="d90b9-116">C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-116">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="d90b9-117">프로젝트 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-117">Create a project directory.</span></span>

   <span data-ttu-id="d90b9-118">프로젝트에 대한 디렉터리를 만들고 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-118">Create a directory for your project and make it your current directory.</span></span>

1. <span data-ttu-id="d90b9-119">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-119">Create the project.</span></span>

   <span data-ttu-id="d90b9-120">명령줄에서 [dotnet new console](../tools/dotnet-new.md)을 입력하여 해당 디렉터리에 새 C# 콘솔 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-120">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="d90b9-121">응용 프로그램의 소스 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-121">Add the application's source code.</span></span>

   <span data-ttu-id="d90b9-122">편집기에서 *Program.cs* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-122">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="d90b9-123">텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-123">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="d90b9-124">정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-124">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="d90b9-125">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="d90b9-125">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="d90b9-126">프로젝트의 종속성 및 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-126">Update the project's dependencies and tools.</span></span>
 
   <span data-ttu-id="d90b9-127">[dotnet restore](../tools/dotnet-restore.md) 명령을 실행하여 프로젝트에 지정된 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-127">Run the [dotnet restore](../tools/dotnet-restore.md) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="d90b9-128">앱의 디버그 빌드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-128">Create a Debug build of your app.</span></span>

   <span data-ttu-id="d90b9-129">[dotnet build](../tools/dotnet-build.md) 명령을 사용하여 응용 프로그램을 빌드하거나 [dotnet run](../tools/dotnet-run.md) 명령을 사용하여 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-129">Use the [dotnet build](../tools/dotnet-build.md) command to build your application or the [dotnet run](../tools/dotnet-run.md) command to build and run it.</span></span>

1. <span data-ttu-id="d90b9-130">앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-130">Deploy your app.</span></span>

   <span data-ttu-id="d90b9-131">프로그램을 디버그하고 테스트한 후 다음 명령을 사용하여 배포를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-131">After you've debugged and tested the program, create the deployment by using the following command:</span></span>

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   <span data-ttu-id="d90b9-132">그러면 앱의 디버그가 아닌 릴리스 버전이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-132">This creates a Release (rather than a Debug) version of your app.</span></span> <span data-ttu-id="d90b9-133">결과 파일은 프로젝트 *bin* 디렉터리의 하위 디렉터리에 있는 *publish*라는 디렉터리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-133">The resulting files are placed in a directory named *publish* that's in a subdirectory of your project's *bin* directory.</span></span>

<span data-ttu-id="d90b9-134">게시 프로세스에서는 응용 프로그램의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-134">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="d90b9-135">이 파일은 주로 예외 디버그에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-135">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="d90b9-136">응용 프로그램 파일과 함께 배포하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-136">You can choose not to distribute it with your application's files.</span></span> <span data-ttu-id="d90b9-137">하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-137">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="d90b9-138">응용 프로그램 파일의 전체 집합을 원하는 방식으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-138">You can deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="d90b9-139">예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-139">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="d90b9-140">설치되고 나면 사용자가 `dotnet` 명령을 사용하고 `dotnet fdd.dll` 등의 응용 프로그램 파일 이름을 제공하여 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-140">Once installed, users can execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="d90b9-141">설치 관리자는 응용 프로그램 이진 외에도 공유 프레임워크 설치 관리자를 번들로 제공하거나 응용 프로그램 설치의 일부로 필수 조건을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-141">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="d90b9-142">공유 프레임워크 설치에는 관리자/루트 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-142">Installation of the shared framework requires Administrator/root access.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="d90b9-143">타사 종속성이 있는 프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-143">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="d90b9-144">하나 이상의 타사 종속성이 있는 프레임워크 종속 배포를 배포하려면 프로젝트에서 해당 종속성을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-144">Deploying a framework-dependent deployment with one or more third-party dependencies requires that those dependencies be available to your project.</span></span> <span data-ttu-id="d90b9-145">다음 두 가지 추가 단계를 수행해야 `dotnet restore` 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-145">Two additional steps are required before you can run the `dotnet restore` command:</span></span>

1. <span data-ttu-id="d90b9-146">필요한 타사 라이브러리에 대한 참조를 *csproj* 파일의 `<ItemGroup>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-146">Add references to required third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="d90b9-147">다음 `<ItemGroup>` 섹션에는 [Json.NET](http://www.newtonsoft.com/json)에 대한 종속성이 타사 라이브러리로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-147">The following `<ItemGroup>` section contains a dependency on [Json.NET](http://www.newtonsoft.com/json) as a third-party library:</span></span>

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. <span data-ttu-id="d90b9-148">타사 종속성을 포함하는 NuGet 패키지를 아직 다운로드하지 않은 경우 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-148">If you haven't already, download the NuGet package containing the third-party dependency.</span></span> <span data-ttu-id="d90b9-149">패키지를 다운로드하려면 종속성을 추가한 후 `dotnet restore` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-149">To download the package, execute the `dotnet restore` command after adding the dependency.</span></span> <span data-ttu-id="d90b9-150">종속성은 게시 시간에 로컬 NuGet 캐시에서 확인되므로 시스템에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-150">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="d90b9-151">타사 종속성이 있는 프레임워크 종속 배포는 타사 종속성만큼만 이식 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-151">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="d90b9-152">예를 들어 타사 라이브러리에서 macOS를 지원하는 경우 Windows 시스템에 앱을 이식할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-152">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="d90b9-153">이러한 현상은 타사 종속성 자체가 네이티브 코드에 종속된 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-153">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="d90b9-154">관련된 좋은 예로 [libuv](https://github.com/libuv/libuv)에 대한 기본 종속성이 필요한 [Kestrel 서버](/aspnet/core/fundamentals/servers/kestrel)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-154">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="d90b9-155">이런 종류의 타사 종속성이 있는 응용 프로그램에 대해 FDD를 만들면 게시된 출력에는 기본 종속성에서 지원하고 NuGet 패키지에 있는 각 [RID(런타임 식별자)](../rid-catalog.md#what-are-rids)에 대한 폴더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-155">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md#what-are-rids) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <span data-ttu-id="d90b9-156"><a name="simpleSelf"></a> 타사 종속성이 없는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-156"><a name="simpleSelf"></a> Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="d90b9-157">타사 종속성이 없는 자체 포함 배포에는 프로젝트 만들기, *csproj* 파일 수정, 앱 빌드, 테스트 및 게시가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-157">Deploying a self-contained deployment without third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="d90b9-158">C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-158">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="d90b9-159">이 예제는 명령줄에서 [dotnet 유틸리티](../tools/dotnet.md)를 사용하여 자체 포함 배포를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-159">The example shows how to create a self-contained deployment using the [dotnet utility](../tools/dotnet.md) from the command line.</span></span>

1. <span data-ttu-id="d90b9-160">프로젝트에 대한 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-160">Create a directory for the project.</span></span>

   <span data-ttu-id="d90b9-161">프로젝트에 대한 디렉터리를 만들고 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-161">Create a directory for your project, and make it your current directory.</span></span>

1. <span data-ttu-id="d90b9-162">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-162">Create the project.</span></span>

   <span data-ttu-id="d90b9-163">명령줄에서 [dotnet new console](../tools/dotnet-new.md)을 입력하여 해당 디렉터리에 새 C# 콘솔 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-163">From the command line, type [dotnet new console](../tools/dotnet-new.md) to create a new C# console project in that directory.</span></span>

1. <span data-ttu-id="d90b9-164">응용 프로그램의 소스 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-164">Add the application's source code.</span></span>

   <span data-ttu-id="d90b9-165">편집기에서 *Program.cs* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-165">Open the *Program.cs* file in your editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="d90b9-166">텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-166">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="d90b9-167">정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-167">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="d90b9-168">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="d90b9-168">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="d90b9-169">앱의 대상 플랫폼을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-169">Define the platforms that your app will target.</span></span>

   <span data-ttu-id="d90b9-170">*csproj* 파일의 `<PropertyGroup>` 섹션에서 앱의 대상 플랫폼을 정의하는 `<RuntimeIdentifiers>` 태그를 만들고 각 대상 플랫폼의 RID(런타임 식별자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-170">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets and specify the runtime identifier (RID) for each platform that you target.</span></span> <span data-ttu-id="d90b9-171">RID를 구분하려면 세미콜론도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-171">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="d90b9-172">런타임 식별자 목록은 [런타임 식별자 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d90b9-172">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="d90b9-173">예를 들어 다음 `<PropertyGroup>` 섹션은 앱이 64비트 Windows 10 운영 체제 및 64비트 OS X 버전 10.11 운영 체제에서 실행됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-173">For example, the following `<PropertyGroup>` section indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   <span data-ttu-id="d90b9-174">`<RuntimeIdentifiers>` 요소는 *csproj* 파일에 있는 모든 `<PropertyGroup>`에 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-174">Note that the `<RuntimeIdentifiers>` element can appear in any `<PropertyGroup>` in your *csproj* file.</span></span> <span data-ttu-id="d90b9-175">전체 샘플 *csproj* 파일은 이 섹션의 뒷부분에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-175">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="d90b9-176">프로젝트의 종속성 및 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-176">Update the project's dependencies and tools.</span></span>

   <span data-ttu-id="d90b9-177">[dotnet restore](../tools/dotnet-restore.md) 명령을 실행하여 프로젝트에 지정된 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-177">Run the [dotnet restore](../tools/dotnet-restore.md) command to restore the dependencies specified in your project.</span></span>

1. <span data-ttu-id="d90b9-178">앱의 디버그 빌드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-178">Create a Debug build of your app.</span></span>

   <span data-ttu-id="d90b9-179">명령줄에서 [dotnet build](../tools/dotnet-build.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-179">From the command line, use the [dotnet build](../tools/dotnet-build.md) command.</span></span>

1. <span data-ttu-id="d90b9-180">프로그램을 디버그하고 테스트한 후에는 각 대상 플랫폼에 대해 앱과 함께 배포할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-180">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="d90b9-181">다음과 같이 두 대상 플랫폼에 대해 `dotnet publish` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-181">Use the `dotnet publish` command for both target platforms as follows:</span></span>

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   <span data-ttu-id="d90b9-182">그러면 각 대상 플랫폼에 대해 앱의 디버그가 아닌 릴리스 버전이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-182">This creates a Release (rather than a Debug) version of your app for each target platform.</span></span> <span data-ttu-id="d90b9-183">결과 파일은 프로젝트 *.\bin\Release\netcoreapp1.1\<runtime_identifier>* 하위 디렉터리의 하위 디렉터리에 있는 *publish*라는 하위 디렉터리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-183">The resulting files are placed in a subdirectory named *publish* that's in a subdirectory of your project's *.\bin\Release\netcoreapp1.1\<runtime_identifier>* subdirectory.</span></span> <span data-ttu-id="d90b9-184">각 하위 디렉터리에는 앱을 시작하는 데 필요한 전체 파일 집합(앱 파일 및 모든 .NET Core 파일)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-184">Note that each subdirectory contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="d90b9-185">게시 프로세스에서는 응용 프로그램의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-185">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="d90b9-186">이 파일은 주로 예외 디버그에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-186">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="d90b9-187">응용 프로그램 파일과 함께 패키지하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-187">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="d90b9-188">하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-188">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="d90b9-189">게시된 파일을 원하는 방식으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-189">Deploy the published files in any way you like.</span></span> <span data-ttu-id="d90b9-190">예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-190">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="d90b9-191">다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-191">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="d90b9-192">타사 종속성이 있는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d90b9-192">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="d90b9-193">하나 이상의 타사 종속성이 있는 자체 포함 배포에는 종속성 추가가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-193">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="d90b9-194">다음 두 가지 추가 단계를 수행해야 `dotnet restore` 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-194">Two additional steps are required before you can run the `dotnet restore` command:</span></span>

1. <span data-ttu-id="d90b9-195">모든 타사 라이브러리에 대한 참조를 *csproj* 파일의 `<ItemGroup>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-195">Add references to any third-party libraries to the `<ItemGroup>` section of your *csproj* file.</span></span> <span data-ttu-id="d90b9-196">다음 `<ItemGroup>` 섹션에서는 Json.NET을 타사 라이브러리로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-196">The following `<ItemGroup>` section uses Json.NET as a third-party library.</span></span>

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. <span data-ttu-id="d90b9-197">타사 종속성을 포함하는 NuGet 패키지를 시스템에 아직 다운로드하지 않은 경우 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-197">If you haven't already, download the NuGet package containing the third-party dependency to your system.</span></span> <span data-ttu-id="d90b9-198">앱에서 종속성을 사용할 수 있도록 하려면 종속성을 추가한 후 `dotnet restore` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-198">To make the dependency available to your app, execute the `dotnet restore` command after adding the dependency.</span></span> <span data-ttu-id="d90b9-199">종속성은 게시 시간에 로컬 NuGet 캐시에서 확인되므로 시스템에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-199">Because the dependency is resolved out of the local NuGet cache at publish time, it must be available on your system.</span></span>

<span data-ttu-id="d90b9-200">다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-200">The following is the complete *csproj* file for this project:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="d90b9-201">응용 프로그램을 배포하면 앱에서 사용된 타사 종속성도 응용 프로그램 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-201">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="d90b9-202">타사 라이브러리는 앱이 실행되는 시스템에 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-202">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="d90b9-203">타사 라이브러리가 있는 자체 포함 배포는 해당 라이브러리에서 지원하는 플랫폼에만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-203">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="d90b9-204">이 배포는 기본 종속성과 함께 타사 종속성이 있는 프레임워크 종속 배포와 유사하며, 기본 종속성이 앱을 배포할 플랫폼과 호환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90b9-204">This is similar to having third-party dependencies with native dependencies in a framework-dependent deployment, where the native dependencies must be compatible with the platform to which the app is deployed.</span></span>

# <a name="see-also"></a><span data-ttu-id="d90b9-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d90b9-205">See also</span></span>

<span data-ttu-id="d90b9-206">[.NET Core 응용 프로그램 배포](index.md) </span><span class="sxs-lookup"><span data-stu-id="d90b9-206">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="d90b9-207">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="d90b9-207">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   

