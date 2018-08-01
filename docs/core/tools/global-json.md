---
title: global.json 개요
description: .NET Core CLI 명령을 실행할 때 global.json 파일을 사용하여 .NET Core SDK 버전을 설정하는 방법에 대해 알아보세요.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.custom: updateeachrelease
ms.openlocfilehash: a7c9301e1beea49eebace5c8f8a7d159a8c12466
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936973"
---
# <a name="globaljson-overview"></a><span data-ttu-id="7b2d6-103">global.json 개요</span><span class="sxs-lookup"><span data-stu-id="7b2d6-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="7b2d6-104">*global.json* 파일을 사용하면 .NET Core CLI 명령을 실행할 때 어떤 .NET Core SDK 버전을 사용할지 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="7b2d6-105">.NET Core SDK를 선택하는 것은 프로젝트가 대상으로 하는 런타임을 지정하는 것과는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="7b2d6-106">.NET Core SDK 버전은 사용된 .NET Core CLI 도구의 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="7b2d6-107">일반적으로 최신 버전의 도구를 사용하려고 하기 때문에 *global.json* 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="7b2d6-108">대신 런타임 지정에 대한 자세한 내용은 [대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="7b2d6-109">.NET Core SDK는 현재 작업 디렉터리(반드시 프로젝트 디렉터리와 동일하지는 않음) 또는 상위 디렉터리 중 하나에서 *global.json* 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="7b2d6-110">global.json 스키마</span><span class="sxs-lookup"><span data-stu-id="7b2d6-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="7b2d6-111">sdk</span><span class="sxs-lookup"><span data-stu-id="7b2d6-111">sdk</span></span>

<span data-ttu-id="7b2d6-112">형식: Object</span><span class="sxs-lookup"><span data-stu-id="7b2d6-112">Type: Object</span></span>

<span data-ttu-id="7b2d6-113">선택할 .NET Core SDK에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="7b2d6-114">버전</span><span class="sxs-lookup"><span data-stu-id="7b2d6-114">version</span></span>

<span data-ttu-id="7b2d6-115">형식: String</span><span class="sxs-lookup"><span data-stu-id="7b2d6-115">Type: String</span></span>

<span data-ttu-id="7b2d6-116">사용할 .NET Core SDK의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="7b2d6-117">이 필드의 특징은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-117">Note that this field:</span></span>

- <span data-ttu-id="7b2d6-118">globbing을 지원하지 않습니다. 즉, 전체 버전 번호가 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="7b2d6-119">버전 범위를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="7b2d6-120">다음 예제에서는 *global.json* 파일의 내용을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.1.300"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="7b2d6-121">global.json 및 .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="7b2d6-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="7b2d6-122">*global.json* 파일에서 어떤 버전을 설정할 수 있는지 알고 있으면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="7b2d6-123">[.NET 다운로드](https://www.microsoft.com/net/download/all) 사이트에서 지원되는 사용 가능한 SDK의 전체 목록을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-123">You can find the full list of supported available SDKs at the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span> <span data-ttu-id="7b2d6-124">.NET Core SDK 2.1부터는 다음 명령을 실행하여 머신에 이미 설치된 SDK 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-124">Starting with .NET Core SDK 2.1, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```console
dotnet --list-sdks
```

<span data-ttu-id="7b2d6-125">머신에 추가 .NET Core SDK 버전을 설치하려면 [.NET 다운로드](https://www.microsoft.com/net/download/all) 사이트를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-125">To install additional .NET Core SDK versions on your machine, visit the [.NET Downloads](https://www.microsoft.com/net/download/all) site.</span></span>

<span data-ttu-id="7b2d6-126">다음 예제와 비슷한 [dotnet new](dotnet-new.md) 명령을 실행하여 현재 디렉터리에서 *global.json* 파일을 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```console
dotnet new globaljson --sdk-version 2.1.300
```

## <a name="matching-rules"></a><span data-ttu-id="7b2d6-127">일치 규칙</span><span class="sxs-lookup"><span data-stu-id="7b2d6-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="7b2d6-128">일치 규칙은 .NET Core 런타임의 일부인 apphost에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="7b2d6-129">호스트의 최신 버전은 여러 런타임이 나란히 설치되어 있는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="7b2d6-130">.NET Core 2.0부터는 어떤 SDK 버전을 사용할지 결정할 때 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="7b2d6-131">*global.json* 파일이 없거나 *global.json*이 SDK 버전을 지정하지 않으면 최신 설치된 SDK 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="7b2d6-132">최신 SDK 버전은 릴리스나 시험판일 수 있으며, 이 중에 높은 버전 번호가 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="7b2d6-133">*global.json*이 SDK 버전을 지정하는 경우</span><span class="sxs-lookup"><span data-stu-id="7b2d6-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="7b2d6-134">지정된 SDK 버전이 머신에서 발견되면 정확한 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="7b2d6-135">지정된 SDK 버전이 시스템에서 발견되지 않으면 해당 버전의 최신 **패치 버전**이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="7b2d6-136">설치된 최신 SDK **패치 버전**은 릴리스나 시험판일 수 있으며, 이 중에 높은 버전 번호가 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="7b2d6-137">.NET Core 2.1 이상에서는 지정된 **패치 버전**보다 낮은 **패치 버전**은 SDK 선택에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="7b2d6-138">지정된 SDK 버전과 적절한 SDK **패치 버전**을 찾을 수 없으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="7b2d6-139">SDK 버전은 현재 다음과 같은 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="7b2d6-140">.NET Core SDK의 **기능 릴리스**는 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 첫 번째 자리(`x`)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="7b2d6-141">일반적으로 .NET Core SDK는 .NET Core보다 릴리스 주기가 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="7b2d6-142">**패치 버전**은 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 마지막 두 자리(`yz`)로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="7b2d6-143">예를 들어, SDK 버전으로 `2.1.300`을 지정하면 SDK 선택은 최대 `2.1.399`까지 찾지만 `2.1.400`은 `2.1.300`의 패치 버전으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="7b2d6-144">`2.1.100`부터 `2.1.201`까지의 .NET Core SDK 버전은 버전 번호 체계가 전환되는 중에 릴리스되었으며 `xyz` 표기법을 올바르게 처리하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="7b2d6-145">*global.json* 파일에서 이 버전을 지정하면 지정된 버전이 대상 머신에 있는지 확인할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="7b2d6-146">.NET Core SDK 1.x에서는 버전을 지정하고 정확히 일치하는 버전이 발견되지 않은 경우 최신 설치된 SDK 버전이 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="7b2d6-147">최신 SDK 버전은 릴리스나 시험판일 수 있으며, 이 중에 높은 버전 번호가 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="7b2d6-148">빌드 경고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7b2d6-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="7b2d6-149">.NET Core SDK의 미리보기 버전으로 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="7b2d6-150">SDK 버전은 현재 프로젝트의 global.json 파일을 통해 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="7b2d6-151">자세한 내용은 https://go.microsoft.com/fwlink/?linkid=869452 참조</span><span class="sxs-lookup"><span data-stu-id="7b2d6-151">More at https://go.microsoft.com/fwlink/?linkid=869452</span></span>

<span data-ttu-id="7b2d6-152">이 경고는 [일치 규칙](#matching-rules) 섹션에서 설명한대로 .NET Core SDK의 미리보기 버전을 사용하여 프로젝트가 컴파일되고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="7b2d6-153">.NET Core SDK 버전은 높은 품질의 기록과 약정을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="7b2d6-154">그러나 미리보기 버전을 사용하지 않으려면 프로젝트 계층 구조에 *global.json* 파일을 추가하여 사용할 SDK 버전을 지정하고 `dotnet --list-sdks`를 사용하여 머신에 설치된 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="7b2d6-155">새 버전이 릴리스되었을 때 새 버전을 사용하려면 *global.json* 파일을 제거하거나 최신 버전을 사용하도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="7b2d6-156">스타트업 프로젝트 '{startupProject}'는 '.NETCoreApp' 버전 '{targetFrameworkVersion}' 프레임워크를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="7b2d6-157">이 버전의 Entity Framework Core .NET 명령줄 도구는 버전 2.0 이상만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="7b2d6-158">이전 버전의 도구 사용에 대한 자세한 내용은 https://go.microsoft.com/fwlink/?linkid=871254를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-158">For information on using older versions of the tools, see https://go.microsoft.com/fwlink/?linkid=871254</span></span>

<span data-ttu-id="7b2d6-159">.NET Core SDK 2.1(v.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-159">Starting with .NET Core SDK 2.1 (v.</span></span> <span data-ttu-id="7b2d6-160">2.1.300)부터는 `dotnet ef` 명령이 SDK에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-160">2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="7b2d6-161">이 경고는 프로젝트가 EF Core 1.0 또는 1.1을 대상으로 하고 .NET Core SDK 2.1 이상 버전과 호환되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-161">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core SDK 2.1 and later versions.</span></span> <span data-ttu-id="7b2d6-162">프로젝트를 컴파일하려면 .NET Core SDK 2.0(v.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-162">To compile your project, install .NET Core SDK 2.0 (v.</span></span> <span data-ttu-id="7b2d6-163">2.1.201) 이전 버전을 머신에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-163">2.1.201) and earlier on your machine.</span></span> <span data-ttu-id="7b2d6-164">자세한 내용은 [EF Core .NET 명령줄 도구](/ef/core/miscellaneous/cli/dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b2d6-164">For more information, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b2d6-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b2d6-165">See also</span></span>

[<span data-ttu-id="7b2d6-166">프로젝트 SDK를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="7b2d6-166">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)