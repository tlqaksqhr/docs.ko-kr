---
title: "Visual Studio를 사용한 .NET Core 앱 배포"
description: "Visual Studio를 사용한 .NET Core 앱 배포에 대해 알아봅니다."
keywords: ".NET, .NET Core, .NET Core 배포"
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 01049a21-fd50-4419-9ab2-0e4a2e091050
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5cc9de1371ba90532e20c11c9f82002ad5a5fa92
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="deploying-net-core-apps-with-visual-studio"></a><span data-ttu-id="d3fc9-104">Visual Studio를 사용하여 .NET Core 앱 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-104">Deploying .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="d3fc9-105">.NET Core 응용 프로그램은 응용 프로그램 이진을 포함하지만 대상 시스템에 .NET Core가 있는지 여부에 따라 달라지는 *프레임워크 종속 배포* 또는 응용 프로그램과 .NET Core 이진을 모두 포함하는 *자체 포함 배포*로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-105">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and .NET Core binaries.</span></span> <span data-ttu-id="d3fc9-106">.NET Core 응용 프로그램 배포 개요는 [.NET Core 응용 프로그램 배포](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-106">For an overview of .NET Core application deployment, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="d3fc9-107">다음 섹션에서는 Microsoft Visual Studio를 사용하여 다음과 같은 종류의 배포를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-107">The following sections show how to use Microsoft Visual Studio to create the following kinds of deployments:</span></span>

- <span data-ttu-id="d3fc9-108">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-108">Framework-dependent deployment</span></span>
- <span data-ttu-id="d3fc9-109">타사 종속성이 있는 프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-109">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="d3fc9-110">자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-110">Self-contained deployment</span></span>
- <span data-ttu-id="d3fc9-111">타사 종속성이 있는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-111">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="d3fc9-112">Visual Studio를 사용하여 .NET Core 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [Windows의 .NET Core에 대한 필수 조건](../windows-prerequisites.md#prerequisites-with-visual-studio-2017)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-112">For information on using Visual Studio to develop .NET Core applications, see [Prerequisites for .NET Core on Windows](../windows-prerequisites.md#prerequisites-with-visual-studio-2017).</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="d3fc9-113">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-113">Framework-dependent deployment</span></span>

<span data-ttu-id="d3fc9-114">타사 종속성이 없는 프레임워크 종속 배포에는 앱의 빌드, 테스트 및 게시만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-114">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="d3fc9-115">C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-115">A simple example written in C# illustrates the process.</span></span>  

1. <span data-ttu-id="d3fc9-116">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-116">Create the project.</span></span>

   <span data-ttu-id="d3fc9-117">**파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-117">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="d3fc9-118">**새 프로젝트** 대화 상자의 **설치됨** 프로젝트 형식 창에서 **.NET Core**를 선택한 다음 가운데 창에서 **콘솔 앱(.NET Core)** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-118">In the **New Project** dialog, select **.NET Core** in the **Installed** project types pane, and select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="d3fc9-119">**이름** 텍스트 상자에 "FDD" 등의 프로젝트 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-119">Enter a project name, such as "FDD", in the **Name** text box.</span></span> <span data-ttu-id="d3fc9-120">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-120">Select the **OK** button.</span></span>

1. <span data-ttu-id="d3fc9-121">응용 프로그램의 소스 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-121">Add the application's source code.</span></span>

   <span data-ttu-id="d3fc9-122">편집기에서 *Program.cs* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-122">Open the *Program.cs* file in the editor and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="d3fc9-123">텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-123">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="d3fc9-124">정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-124">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="d3fc9-125">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3fc9-125">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="d3fc9-126">앱의 디버그 빌드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-126">Create a Debug build of your app.</span></span>

   <span data-ttu-id="d3fc9-127">**빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-127">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="d3fc9-128">**디버그** > **디버깅 시작**을 선택하여 응용 프로그램의 디버그 빌드를 컴파일하고 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-128">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="d3fc9-129">앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-129">Deploy your app.</span></span>

   <span data-ttu-id="d3fc9-130">프로그램을 디버그하고 테스트한 후에는 앱과 함께 배포할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-130">After you've debugged and tested the program, create the files to be deployed with your app.</span></span> <span data-ttu-id="d3fc9-131">Visual Studio에서 게시하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-131">To publish from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="d3fc9-132">도구 모음에서 솔루션 구성을 **디버그**에서 **릴리스**로 변경하여 앱의 릴리스(디버그 아님) 버전을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-132">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="d3fc9-133">**솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-133">Right-click on the project (not the solution) in **Solution Explorer**, and select **Publish**.</span></span>

      1. <span data-ttu-id="d3fc9-134">**게시** 탭에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-134">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="d3fc9-135">Visual Studio에서 응용 프로그램을 구성하는 파일을 로컬 파일 시스템에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-135">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="d3fc9-136">이제 **게시** 탭에 단일 프로필 **FolderProfile**이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-136">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="d3fc9-137">프로필의 구성 설정이 탭의 **요약** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-137">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span>

   <span data-ttu-id="d3fc9-138">결과 파일은 프로젝트 *.\bin\release* 하위 디렉터리의 하위 디렉터리에 있는 `PublishOutput`이라는 디렉터리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-138">The resulting files are placed in a directory named `PublishOutput` that is in a subdirectory of your project's *.\bin\release* subdirectory.</span></span>

<span data-ttu-id="d3fc9-139">게시 프로세스에서는 응용 프로그램의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-139">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="d3fc9-140">이 파일은 주로 예외 디버그에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-140">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="d3fc9-141">응용 프로그램 파일과 함께 패키지하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-141">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="d3fc9-142">하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-142">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="d3fc9-143">응용 프로그램 파일의 전체 집합을 원하는 방식으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-143">Deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="d3fc9-144">예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-144">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="d3fc9-145">설치되고 나면 사용자가 `dotnet` 명령을 사용하고 `dotnet fdd.dll` 등의 응용 프로그램 파일 이름을 제공하여 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-145">Once installed, users can then execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="d3fc9-146">설치 관리자는 응용 프로그램 이진 외에도 공유 프레임워크 설치 관리자를 번들로 제공하거나 응용 프로그램 설치의 일부로 필수 조건을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-146">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="d3fc9-147">공유 프레임워크 설치는 시스템 수준이므로 관리자/루트 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-147">Installation of the shared framework requires Administrator/root access since it is machine-wide.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="d3fc9-148">타사 종속성이 있는 프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-148">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="d3fc9-149">하나 이상의 타사 종속성이 있는 프레임워크 종속 배포를 배포하려면 프로젝트에서 모든 종속성을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-149">Deploying a framework-dependent deployment with one or more third-party dependencies requires that any dependencies be available to your project.</span></span> <span data-ttu-id="d3fc9-150">다음 추가 단계를 수행해야 앱을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-150">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="d3fc9-151">**NuGet 패키지 관리자**를 사용하여 NuGet 패키지에 대한 참조를 프로젝트에 추가하고, 시스템에서 패키지를 사용할 수 없는 경우 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-151">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="d3fc9-152">패키지 관리자를 열려면 **도구** > **NuGet 패키지 관리자** > **솔루션용 NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-152">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="d3fc9-153">`Newtonsoft.Json`이 시스템에 설치되어 있는지 확인하고, 설치되지 않은 경우 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-153">Confirm that `Newtonsoft.Json` is installed on your system and, if it is not, install it.</span></span> <span data-ttu-id="d3fc9-154">**설치됨** 탭에 시스템에 설치된 NuGet 패키지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-154">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="d3fc9-155">`Newtonsoft.Json`이 탭에 표시되지 않는 경우 **찾아보기** 탭을 선택하고 검색 상자에 "Newtonsoft.Json"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-155">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="d3fc9-156">`Newtonsoft.Json`을 선택하고 오른쪽 창에서 해당 프로젝트를 선택한 후 **설치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-156">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="d3fc9-157">`Newtonsoft.Json`이 시스템에 이미 설치되어 있는 경우 **솔루션용 패키지 관리** 탭의 오른쪽 창에서 해당 프로젝트를 선택하여 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-157">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of hte **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="d3fc9-158">타사 종속성이 있는 프레임워크 종속 배포는 타사 종속성만큼만 이식 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-158">Note that a framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="d3fc9-159">예를 들어 타사 라이브러리에서 macOS를 지원하는 경우 Windows 시스템에 앱을 이식할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-159">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="d3fc9-160">이러한 현상은 타사 종속성 자체가 네이티브 코드에 종속된 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-160">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="d3fc9-161">관련된 좋은 예로 [libuv](https://github.com/libuv/libuv)에 대한 기본 종속성이 필요한 [Kestrel 서버](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-161">A good example of this is [Kestrel server](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="d3fc9-162">이런 종류의 타사 종속성이 있는 응용 프로그램에 대해 FDD를 만들면 게시된 출력에는 기본 종속성에서 지원하고 NuGet 패키지에 있는 각 [RID(런타임 식별자)](../rid-catalog.md#what-are-rids)에 대한 폴더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-162">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md#what-are-rids) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <span data-ttu-id="d3fc9-163"><a name="simpleSelf"></a> 타사 종속성이 없는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-163"><a name="simpleSelf"></a> Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="d3fc9-164">타사 종속성이 없는 자체 포함 배포에는 프로젝트 만들기, *csproj* 파일 수정, 앱 빌드, 테스트 및 게시가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-164">Deploying a self-contained deployment with no third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="d3fc9-165">C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-165">A simple example written in C# illustrates the process.</span></span> 

1. <span data-ttu-id="d3fc9-166">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-166">Create the project.</span></span>

   <span data-ttu-id="d3fc9-167">**파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-167">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="d3fc9-168">**새 프로젝트 추가** 대화 상자의 **설치됨** 프로젝트 형식 창에서 **.NET Core**를 선택한 다음 가운데 창에서 **콘솔 앱(.NET Core)** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-168">In the **Add New Project** dialog, select **.NET Core** in the **Installed** project types pane, and select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="d3fc9-169">**이름** 텍스트 상자에 "SCD" 등의 프로젝트 이름을 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-169">Enter a project name, such as "SCD", in the **Name** text box, and select the **OK** button.</span></span>

1. <span data-ttu-id="d3fc9-170">응용 프로그램의 소스 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-170">Add the application's source code.</span></span>

   <span data-ttu-id="d3fc9-171">편집기에서 *Program.cs* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-171">Open the *Program.cs* file in your editor, and replace the auto-generated code with the following code.</span></span> <span data-ttu-id="d3fc9-172">텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-172">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="d3fc9-173">정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-173">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   <span data-ttu-id="d3fc9-174">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span><span class="sxs-lookup"><span data-stu-id="d3fc9-174">[!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]</span></span>

1. <span data-ttu-id="d3fc9-175">앱의 대상 플랫폼을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-175">Define the platforms that your app will target.</span></span>

   1. <span data-ttu-id="d3fc9-176">**솔루션 탐색기**에서 해당 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **SCD.csproj 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-176">Right-click on your project (not the solution) In **Solution Explorer**, and select **Edit SCD.csproj**.</span></span>

   1. <span data-ttu-id="d3fc9-177">*csproj* 파일의 `<PropertyGroup>` 섹션에서 앱의 대상 플랫폼을 정의하는 `<RuntimeIdentifiers>` 태그를 만들고 각 대상 플랫폼의 RID(런타임 식별자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-177">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets, and specify the runtime identifier (RID) of each platform that you target.</span></span> <span data-ttu-id="d3fc9-178">RID를 구분하려면 세미콜론도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-178">Note that you also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="d3fc9-179">런타임 식별자 목록은 [런타임 식별자 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-179">See [Runtime IDentifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span> 

   <span data-ttu-id="d3fc9-180">예를 들어 다음 예에서는 앱이 64비트 Windows 10 운영 체제 및 64비트 OS X 버전 10.11 운영 체제에서 실행됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-180">For example, the following example indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

```xml
<PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
</PropertyGroup>
```
   <span data-ttu-id="d3fc9-181">`<RuntimeIdentifiers>` 요소는 *csproj* 파일에 있는 `<PropertyGroup>`으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-181">Note that the `<RuntimeIdentifiers>` element can go into any `<PropertyGroup>` that you have in your *csproj* file.</span></span> <span data-ttu-id="d3fc9-182">전체 샘플 *csproj* 파일은 이 섹션의 뒷부분에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-182">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="d3fc9-183">앱의 디버그 빌드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-183">Create a Debug build of your app.</span></span>

   <span data-ttu-id="d3fc9-184">**빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-184">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="d3fc9-185">**디버그** > **디버깅 시작**을 선택하여 응용 프로그램의 디버그 빌드를 컴파일하고 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-185">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="d3fc9-186">앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-186">Publish your app.</span></span>

   <span data-ttu-id="d3fc9-187">프로그램을 디버그하고 테스트한 후에는 각 대상 플랫폼에 대해 앱과 함께 배포할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-187">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="d3fc9-188">Visual Studio에서 앱을 게시하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-188">To publish your app from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="d3fc9-189">도구 모음에서 솔루션 구성을 **디버그**에서 **릴리스**로 변경하여 앱의 릴리스(디버그 아님) 버전을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-189">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="d3fc9-190">**솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-190">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span> 

      1. <span data-ttu-id="d3fc9-191">**게시** 탭에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-191">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="d3fc9-192">Visual Studio에서 응용 프로그램을 구성하는 파일을 로컬 파일 시스템에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-192">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="d3fc9-193">이제 **게시** 탭에 단일 프로필 **FolderProfile**이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-193">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="d3fc9-194">프로필의 구성 설정이 탭의 **요약** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-194">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span> <span data-ttu-id="d3fc9-195">**대상 런타임**은 게시된 런타임을 식별하고, **대상 위치**는 자체 포함 배포의 파일이 작성된 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-195">**Target Runtime** identifies which runtime has been published, and **Target Location** identifies where the files for the self-contained deployment were written.</span></span>

      1. <span data-ttu-id="d3fc9-196">Visual Studio는 기본적으로 게시된 모든 파일을 단일 디렉터리에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-196">Visual Studio by default writes all published files to a single directory.</span></span> <span data-ttu-id="d3fc9-197">편의상, 각 대상 런타임에 대해 별도 프로필을 만들고 게시된 파일을 플랫폼별 디렉터리에 배치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-197">For convenience, it's best to create separate profiles for each target runtime and to place published files in a platform-specific directory.</span></span> <span data-ttu-id="d3fc9-198">이렇게 하려면 각 대상 플랫폼에 대해 별도 게시 프로필을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-198">This involves creating a separate publishing profile for each target platform.</span></span> <span data-ttu-id="d3fc9-199">따라서 이제 다음을 수행하여 각 플랫폼용 응용 프로그램을 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-199">So now rebuild the application for each platform by doing the following:</span></span>

         1. <span data-ttu-id="d3fc9-200">**게시** 대화 상자에서 **새 프로필 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-200">Select **Create new profile** in the **Publish** dialog.</span></span>

         1. <span data-ttu-id="d3fc9-201">**게시 대상 선택** 대화 상자에서 **폴더 선택** 위치를 *bin\Release\PublishOutput\win10-x64*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-201">In the **Pick a publish target** dialog, change the **Choose a folder** location to *bin\Release\PublishOutput\win10-x64*.</span></span> <span data-ttu-id="d3fc9-202">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-202">Select **OK**.</span></span>

         1. <span data-ttu-id="d3fc9-203">프로필 목록에서 새 프로필(**FolderProfile1**)을 선택하고, **대상 런타임**이 `win10-x64`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-203">Select the new profile (**FolderProfile1**) in the list of profiles, and make sure that the **Target Runtime** is `win10-x64`.</span></span> <span data-ttu-id="d3fc9-204">아닌 경우 **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-204">If it isn't, select **Settings**.</span></span> <span data-ttu-id="d3fc9-205">**프로필 설정** 대화 상자에서 **대상 런타임**을 `win10-x64`로 변경하고 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-205">In the **Profile Settings** dialog, change the **Target Runtime** to `win10-x64` and select **Save**.</span></span> <span data-ttu-id="d3fc9-206">그렇지 않으면 **취소**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-206">Otherwise, select **Cancel**.</span></span>

         1. <span data-ttu-id="d3fc9-207">**게시**를 선택하여 64비트 Windows 10 플랫폼용 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-207">Select **Publish** to publish your app for 64-bit Windows 10 platforms.</span></span>

         1. <span data-ttu-id="d3fc9-208">앞의 단계를 다시 수행하여 `osx.10.11-x64` 플랫폼용 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-208">Follow the previous steps again to create a profile for the `osx.10.11-x64` platform.</span></span> <span data-ttu-id="d3fc9-209">**대상 위치**는 *bin\Release\PublishOutput\osx.10.11-x64*이고, **대상 런타임**은 `osx.10.11-x64`입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-209">The **Target Location** is *bin\Release\PublishOutput\osx.10.11-x64*, and the **Target Runtime** is `osx.10.11-x64`.</span></span> <span data-ttu-id="d3fc9-210">Visual Studio에서 이 프로필에 할당하는 이름은 **FolderProfile2**입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-210">The name that Visual Studio assigns to this profile is **FolderProfile2**.</span></span>

      <span data-ttu-id="d3fc9-211">각 대상 위치에는 앱을 시작하는 데 필요한 전체 파일 집합(앱 파일 및 모든 .NET Core 파일)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-211">Note that each target location contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="d3fc9-212">게시 프로세스에서는 응용 프로그램의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-212">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="d3fc9-213">이 파일은 주로 예외 디버그에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-213">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="d3fc9-214">응용 프로그램 파일과 함께 패키지하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-214">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="d3fc9-215">하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-215">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="d3fc9-216">게시된 파일을 원하는 방식으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-216">Deploy the published files in any way you like.</span></span> <span data-ttu-id="d3fc9-217">예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-217">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="d3fc9-218">다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-218">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="d3fc9-219">타사 종속성이 있는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="d3fc9-219">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="d3fc9-220">하나 이상의 타사 종속성이 있는 자체 포함 배포에는 종속성 추가가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-220">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="d3fc9-221">다음 추가 단계를 수행해야 앱을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-221">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="d3fc9-222">**NuGet 패키지 관리자**를 사용하여 NuGet 패키지에 대한 참조를 프로젝트에 추가하고, 시스템에서 패키지를 사용할 수 없는 경우 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-222">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="d3fc9-223">패키지 관리자를 열려면 **도구** > **NuGet 패키지 관리자** > **솔루션용 NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-223">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="d3fc9-224">`Newtonsoft.Json`이 시스템에 설치되어 있는지 확인하고, 설치되지 않은 경우 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-224">Confirm that `Newtonsoft.Json` is installed on your system and, if it is not, install it.</span></span> <span data-ttu-id="d3fc9-225">**설치됨** 탭에 시스템에 설치된 NuGet 패키지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-225">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="d3fc9-226">`Newtonsoft.Json`이 탭에 표시되지 않는 경우 **찾아보기** 탭을 선택하고 검색 상자에 "Newtonsoft.Json"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-226">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="d3fc9-227">`Newtonsoft.Json`을 선택하고 오른쪽 창에서 해당 프로젝트를 선택한 후 **설치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-227">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="d3fc9-228">`Newtonsoft.Json`이 시스템에 이미 설치되어 있는 경우 **솔루션용 패키지 관리** 탭의 오른쪽 창에서 해당 프로젝트를 선택하여 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-228">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="d3fc9-229">다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-229">The following is the complete *csproj* file for this project:</span></span>

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

<span data-ttu-id="d3fc9-230">응용 프로그램을 배포하면 앱에서 사용된 타사 종속성도 응용 프로그램 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-230">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="d3fc9-231">타사 라이브러리는 앱이 실행되는 시스템에 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-231">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="d3fc9-232">타사 라이브러리가 있는 자체 포함 배포는 해당 라이브러리에서 지원하는 플랫폼에만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-232">Note that you can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="d3fc9-233">이 배포는 기본 종속성과 함께 타사 종속성이 있는 프레임워크 종속 배포와 유사하며, 이전에 설치되지 않은 경우 대상 플랫폼에는 기본 종속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-233">This is similar to having third-party dependencies with native dependencies in your framework-dependent deployment, where the native dependencies won't exist on the target platform unless they were previously installed there.</span></span>

# <a name="see-also"></a><span data-ttu-id="d3fc9-234">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3fc9-234">See also</span></span>
<span data-ttu-id="d3fc9-235">[.NET Core 응용 프로그램 배포](index.md) </span><span class="sxs-lookup"><span data-stu-id="d3fc9-235">[.NET Core Application Deployment](index.md) </span></span>  
[<span data-ttu-id="d3fc9-236">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="d3fc9-236">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)   

