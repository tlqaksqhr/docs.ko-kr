---
title: ".NET Core 버전 관리"
description: ".NET Core 버전 관리의 작동 방식을 이해합니다."
author: bleroy
ms.author: mairaw
ms.date: 08/25/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f6f684b1-1d2c-4105-8376-7c1959e23803
ms.workload: dotnetcore
ms.openlocfilehash: 369d280268123a69ae9458a2c47e45396728deb5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="net-core-versioning"></a><span data-ttu-id="6b517-103">.NET Core 버전 관리</span><span class="sxs-lookup"><span data-stu-id="6b517-103">.NET Core versioning</span></span>

<span data-ttu-id="6b517-104">.NET Core는 [NuGet 패키지](../packages.md), 도구 및 하나의 단위로 배포되는 프레임워크로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-104">.NET Core is made of [NuGet packages](../packages.md), tools, and frameworks that are distributed as a unit.</span></span> <span data-ttu-id="6b517-105">각 플랫폼 계층에 대해 개별적으로 버전 관리가 가능하므로 보다 나은 유연성을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-105">Each of these platform layers can be versioned separately, enabling better agility.</span></span> <span data-ttu-id="6b517-106">그 점과 관련하여 버전 관리 유연성도 중요하지만 제품을 더 쉽게 이해하기 위해 플랫폼의 버전을 하나의 단위로 관리하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-106">While there is significant versioning flexibility in that regard, there's also a desire to version the platform as a unit to make the product easier to understand.</span></span>

<span data-ttu-id="6b517-107">이 문서에서는 .NET Core SDK 및 런타임 버전이 어떻게 관리되는지에 대해 명확히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-107">This article aims at clarifying how the .NET Core SDK and runtime are versioned.</span></span>

<span data-ttu-id="6b517-108">.NET Core에는 독립적으로 버전 관리가 이루어지는 작동 부분이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-108">There are lots of moving parts that version independently in .NET Core.</span></span> <span data-ttu-id="6b517-109">그러나 .NET Core 2.0부터는 최상위 버전 번호를 이해하기 쉬우므로 “.NET Core”의 버전임을 누구나 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-109">However, starting with .NET Core 2.0, there is an easy to understand top-level version number that everybody understands to be *the* version of ".NET Core" as a whole.</span></span> <span data-ttu-id="6b517-110">이 문서의 나머지 부분에서는 모든 부품의 버전 관리에 대해 구체적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-110">The rest of this document goes into the details of the versioning of all those parts.</span></span> <span data-ttu-id="6b517-111">패키지 관리자인 경우에는 이러한 세부 정보가 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-111">These details can be important if you're a package manager, for example.</span></span>

## <a name="versioning-details"></a><span data-ttu-id="6b517-112">버전 관리 정보</span><span class="sxs-lookup"><span data-stu-id="6b517-112">Versioning details</span></span>

<span data-ttu-id="6b517-113">.NET Core 2.0부터는 다운로드 파일 이름에 단일 버전 번호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-113">Starting with .NET Core 2.0, downloads show a single version number in their file name.</span></span> <span data-ttu-id="6b517-114">다음 버전 번호가 통합되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-114">The following version numbers were unified:</span></span>

* <span data-ttu-id="6b517-115">공유 프레임워크 및 관련된 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-115">The shared framework and associated runtime.</span></span>
* <span data-ttu-id="6b517-116">.NET Core SDK 및 관련된 .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="6b517-116">The .NET Core SDK and associated .NET Core CLI.</span></span>
* <span data-ttu-id="6b517-117">`Microsoft.NETCore.App` 메타패키지</span><span class="sxs-lookup"><span data-stu-id="6b517-117">The `Microsoft.NETCore.App` metapackage.</span></span>

<span data-ttu-id="6b517-118">단일 버전 번호를 사용하면 어떤 버전의 SDK를 사용자의 개발 컴퓨터에 설치해야 할지 그리고 프로덕션 환경이 프로비전되는 시점에 공유 프레임워크의 해당 버전이 무엇이 되어야 할지를 보다 쉽게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-118">The use of a single version number makes it easier for users to know what version of the SDK to install on their dev machines, and what the corresponding version of the shared framework should be when time comes to provision a production environment.</span></span> <span data-ttu-id="6b517-119">SDK 또는 런타임을 다운로드할 때 표시되는 버전 번호가 동일하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-119">When downloading an SDK or runtime, the version number you see is going to be the same.</span></span>

### <a name="installers"></a><span data-ttu-id="6b517-120">설치 관리자</span><span class="sxs-lookup"><span data-stu-id="6b517-120">Installers</span></span>

<span data-ttu-id="6b517-121">.NET Core 2.0부터는 [일별 빌드](https://github.com/dotnet/core-setup#daily-builds) 및 [Microsoft 릴리스](https://www.microsoft.com/net/download/core)의 다운로드가 보다 이해하기 쉬운 새 명명 체계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-121">Starting with .NET Core 2.0, downloads for our [daily builds](https://github.com/dotnet/core-setup#daily-builds) and [our releases](https://www.microsoft.com/net/download/core) adhere to a new naming scheme that is easier to understand.</span></span>
<span data-ttu-id="6b517-122">이 다운로드의 설치 관리자 UI는 설치되는 구성 요소의 이름과 버전을 명확히 제공하도록 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-122">The installer UI in those downloads were also modified to clearly present the names and versions of the components being installed.</span></span> <span data-ttu-id="6b517-123">특히 제목은 다운로드의 파일 이름에 있는 것과 동일한 버전 번호를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-123">In particular, titles now show the same version number that is in the download's file name.</span></span>

#### <a name="file-name-format"></a><span data-ttu-id="6b517-124">파일 이름 형식</span><span class="sxs-lookup"><span data-stu-id="6b517-124">File name format</span></span>

`[product]-[component]-[major].[minor].[patch]-[previewN]-[optional build #]-[rid].[file ext]`

<span data-ttu-id="6b517-125">다음은 이 형식의 몇 가지 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-125">Here are some examples of this format:</span></span>

```
dotnet-runtime-2.0.4-macos.10.12-x64.pkg            # Mac runtime installer
dotnet-sdk-2.0.4-win10-x64.exe                      # Windows SDK installer
dotnet-sdk-2.0.4-fedora.24-x64.tar.gz               # Fedora 24 binary archive

#Ubuntu file set needed for the SDK
dotnet-host-2.0.4-ubuntu.16.04-x64.deb              # Host / muxer and host policy
dotnet-runtime-2.0.4-ubuntu.16.04-x64.deb           # runtime
dotnet-sdk-2.0.4-ubuntu.16.04-x64.deb               # SDK tools
```

<span data-ttu-id="6b517-126">형식은 읽기가 가능하며, 다운로드하는 내용, 그 버전 그리고 어디에 사용할 수 있는지를 명확히 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-126">The format is readable and clearly shows what you're downloading, what version it is, and where you can use it.</span></span> <span data-ttu-id="6b517-127">런타임 패키지 이름에는 `runtime`이 포함되며 SDK에는 `SDK`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-127">The runtime package name includes `runtime`, and the SDK includes `SDK`.</span></span>

#### <a name="ui-string-format"></a><span data-ttu-id="6b517-128">UI 문자열 형식</span><span class="sxs-lookup"><span data-stu-id="6b517-128">UI string format</span></span>

<span data-ttu-id="6b517-129">설치 관리자의 모든 웹 사이트 설명 및 UI 문자열은 일관적이고 정확하며 간단하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-129">All web site descriptions and UI strings in the installers are kept consistent, accurate, and simple.</span></span> <span data-ttu-id="6b517-130">다음 표는 몇 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-130">The following table shows some examples:</span></span>

| <span data-ttu-id="6b517-131">Installer</span><span class="sxs-lookup"><span data-stu-id="6b517-131">Installer</span></span> | <span data-ttu-id="6b517-132">창 제목</span><span class="sxs-lookup"><span data-stu-id="6b517-132">Window Title</span></span>                          | <span data-ttu-id="6b517-133">설치 관리자의 다른 내용</span><span class="sxs-lookup"><span data-stu-id="6b517-133">Other content in installer</span></span> | <span data-ttu-id="6b517-134">설치된 기능</span><span class="sxs-lookup"><span data-stu-id="6b517-134">What is installed</span></span>                               |
| :--       | :--                                   | :--                        | :--                                             |
| <span data-ttu-id="6b517-135">SDK</span><span class="sxs-lookup"><span data-stu-id="6b517-135">SDK</span></span>       | <span data-ttu-id="6b517-136">.NET Core 2.0 SDK(x64) 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="6b517-136">.NET Core 2.0 SDK (x64) Installer</span></span>     | <span data-ttu-id="6b517-137">.NET Core 2.0.4 SDK</span><span class="sxs-lookup"><span data-stu-id="6b517-137">.NET Core 2.0.4 SDK</span></span>        | <span data-ttu-id="6b517-138">.NET Core 2.0.4 도구 + .NET Core 2.0.4 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-138">.NET Core 2.0.4 Tools + .NET Core 2.0.4 Runtime</span></span> |
| <span data-ttu-id="6b517-139">런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-139">Runtime</span></span>   | <span data-ttu-id="6b517-140">.NET Core 2.0 런타임(x64) 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="6b517-140">.NET Core 2.0 Runtime (x64) Installer</span></span> | <span data-ttu-id="6b517-141">.NET Core 2.0.4 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-141">.NET Core 2.0.4 Runtime</span></span>    | <span data-ttu-id="6b517-142">.NET Core 2.0.4 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-142">.NET Core 2.0.4 Runtime</span></span>                         |

<span data-ttu-id="6b517-143">미리 보기 릴리스는 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-143">Preview releases differ only slightly:</span></span>

| <span data-ttu-id="6b517-144">Installer</span><span class="sxs-lookup"><span data-stu-id="6b517-144">Installer</span></span> | <span data-ttu-id="6b517-145">창 제목</span><span class="sxs-lookup"><span data-stu-id="6b517-145">Window Title</span></span>                                    | <span data-ttu-id="6b517-146">설치 관리자의 다른 내용</span><span class="sxs-lookup"><span data-stu-id="6b517-146">Other content in installer</span></span>        | <span data-ttu-id="6b517-147">설치된 기능</span><span class="sxs-lookup"><span data-stu-id="6b517-147">What is installed</span></span>                                                   |
| :--       | :--                                             | :--                               | :--                                                                 |
| <span data-ttu-id="6b517-148">SDK</span><span class="sxs-lookup"><span data-stu-id="6b517-148">SDK</span></span>       | <span data-ttu-id="6b517-149">.NET Core 2.0 미리 보기 1 SDK(x64) 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="6b517-149">.NET Core 2.0 Preview 1 SDK (x64) Installer</span></span>     | <span data-ttu-id="6b517-150">.NET Core 2.0.0 미리 보기 1 SDK</span><span class="sxs-lookup"><span data-stu-id="6b517-150">.NET Core 2.0.0 Preview 1 SDK</span></span>     | <span data-ttu-id="6b517-151">.NET Core 2.0.0 미리 보기 1 도구 + .NET Core 2.0.0 미리 보기 1 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-151">.NET Core 2.0.0 Preview 1 Tools + .NET Core 2.0.0 Preview 1 Runtime</span></span> |
| <span data-ttu-id="6b517-152">런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-152">Runtime</span></span>   | <span data-ttu-id="6b517-153">.NET Core 2.0 미리 보기 1 런타임(x64) 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="6b517-153">.NET Core 2.0 Preview 1 Runtime (x64) Installer</span></span> | <span data-ttu-id="6b517-154">.NET Core 2.0.0 미리 보기 1 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-154">.NET Core 2.0.0 Preview 1 Runtime</span></span> | <span data-ttu-id="6b517-155">.NET Core 2.0.0 미리 보기 1 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-155">.NET Core 2.0.0 Preview 1 Runtime</span></span>                                   |

<span data-ttu-id="6b517-156">SDK 릴리스에는 런타임 버전이 하나 이상 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-156">It may happen that an SDK release contains more than one version of the runtime.</span></span> <span data-ttu-id="6b517-157">이 경우 설치 관리자 UX는 다음과 같습니다(SDK 버전만 표시되고 설치된 런타임 버전은 Windows 및 Mac에서 설치 프로세스의 끝에 있는 요약 페이지에 표시됩니다.).</span><span class="sxs-lookup"><span data-stu-id="6b517-157">When that happens, the installer UX looks like the following (only the SDK version is shown and the installed Runtime versions are shown on a summary page at the end of the installation process on Windows and Mac):</span></span>

| <span data-ttu-id="6b517-158">Installer</span><span class="sxs-lookup"><span data-stu-id="6b517-158">Installer</span></span> | <span data-ttu-id="6b517-159">창 제목</span><span class="sxs-lookup"><span data-stu-id="6b517-159">Window Title</span></span>                      | <span data-ttu-id="6b517-160">설치 관리자의 다른 내용</span><span class="sxs-lookup"><span data-stu-id="6b517-160">Other content in installer</span></span>                                   | <span data-ttu-id="6b517-161">설치된 기능</span><span class="sxs-lookup"><span data-stu-id="6b517-161">What is installed</span></span>                                                         |
| :--       | :--                               | :--                                                          | :--                                                                       |
| <span data-ttu-id="6b517-162">SDK</span><span class="sxs-lookup"><span data-stu-id="6b517-162">SDK</span></span>       | <span data-ttu-id="6b517-163">.NET Core 2.1 SDK(x64) 설치 관리자</span><span class="sxs-lookup"><span data-stu-id="6b517-163">.NET Core 2.1 SDK (x64) Installer</span></span> | <span data-ttu-id="6b517-164">.NET Core 2.1.1 SDK</span><span class="sxs-lookup"><span data-stu-id="6b517-164">.NET Core 2.1.1 SDK</span></span> <br> <span data-ttu-id="6b517-165">.NET Core 2.1.1 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-165">.NET Core 2.1.1 Runtime</span></span> <br> <span data-ttu-id="6b517-166">.NET Core 2.0.6 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-166">.NET Core 2.0.6 Runtime</span></span> | <span data-ttu-id="6b517-167">.NET Core 2.1.1 도구 + .NET Core 2.1.1 런타임 + .NET Core 2.0.6 런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-167">.NET Core 2.1.1 Tools + .NET Core 2.1.1 Runtime + .NET Core 2.0.6 Runtime</span></span> |

<span data-ttu-id="6b517-168">.NET Core 도구를 런타임 변경 없이 업데이트해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-168">It's also possible that .NET Core Tools need to be updated, without runtime changes.</span></span> <span data-ttu-id="6b517-169">이 경우 SDK 버전이 예를 들어 2.1.2로 높아지면 다음에 출시될 때 런타임이 이에 따라 높아집니다(즉, 런타임과 SDK가 2.1.3으로 출시됨).</span><span class="sxs-lookup"><span data-stu-id="6b517-169">In that case, the SDK version is increased (for example, to 2.1.2) and then the Runtime catches up the next time it ships (for example, both the Runtime and SDK ship the next time as 2.1.3).</span></span>

### <a name="package-managers"></a><span data-ttu-id="6b517-170">패키지 관리자</span><span class="sxs-lookup"><span data-stu-id="6b517-170">Package managers</span></span>

<span data-ttu-id="6b517-171">Microsoft가 아닌 엔터티가 .NET Core를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-171">.NET Core can be distributed by other entities than Microsoft.</span></span> <span data-ttu-id="6b517-172">특히 Linux 배포 소유자 및 패키지 유지 관리자가 .NET Core 패키지를 그들의 패키지 관리자에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-172">In particular, Linux distribution owners and package maintainers may add .NET Core packages to their package managers.</span></span> <span data-ttu-id="6b517-173">해당 패키지의 이름 지정 및 버전 관리 방법에 대한 권장 사항을 보려면 [.NET Core 배포 패키징](../build/distribution-packaging.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b517-173">For recommendations on how those packages should be named and versioned, see [.NET Core distribution packaging](../build/distribution-packaging.md).</span></span>

#### <a name="minimum-package-set"></a><span data-ttu-id="6b517-174">최소 패키지 집합</span><span class="sxs-lookup"><span data-stu-id="6b517-174">Minimum package set</span></span>

* <span data-ttu-id="6b517-175">`dotnet-runtime-[major].[minor]`: 지정된 버전의 런타임(패키지 관리자에서는 지정된 주+부 조합의 최신 패치 버전만 사용 가능해야 함).</span><span class="sxs-lookup"><span data-stu-id="6b517-175">`dotnet-runtime-[major].[minor]`: a runtime with the specified version (only the latest patch version for a given major+minor combination should be available in the package manager).</span></span> <span data-ttu-id="6b517-176">새 패치 버전은 패키지를 업데이트하지만 새 주 버전 또는 부 버전은 별도의 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-176">New patch versions update the package, but new minor or major versions are separate packages.</span></span>
 
  <span data-ttu-id="6b517-177">**종속성**: `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="6b517-177">**Dependencies**: `dotnet-host`</span></span>

* <span data-ttu-id="6b517-178">`dotnet-sdk`: 최신 SDK.</span><span class="sxs-lookup"><span data-stu-id="6b517-178">`dotnet-sdk`: the latest SDK.</span></span> <span data-ttu-id="6b517-179">`update`는 주 버전, 부 버전 및 패치 버전을 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-179">`update` rolls forward major, minor, and patch versions.</span></span>

  <span data-ttu-id="6b517-180">**종속성**: 최신 `dotnet-sdk-[major].[minor]`.</span><span class="sxs-lookup"><span data-stu-id="6b517-180">**Dependencies**: the latest `dotnet-sdk-[major].[minor]`.</span></span>

* <span data-ttu-id="6b517-181">`dotnet-sdk-[major].[minor]`: 지정된 버전의 SDK.</span><span class="sxs-lookup"><span data-stu-id="6b517-181">`dotnet-sdk-[major].[minor]`: the SDK with the specified version.</span></span> <span data-ttu-id="6b517-182">지정된 버전은 포함된 공유 프레임워크 중 최고 포함 버전이므로 사용자가 SDK를 공유 프레임워크에 쉽게 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-182">The version specified is the highest included version of included shared frameworks, so that users can easily relate an SDK to a shared framework.</span></span> <span data-ttu-id="6b517-183">새 패치 버전은 패키지를 업데이트하지만 새 주 버전 또는 부 버전은 별도의 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-183">New patch versions update the package, but new minor or major versions are separate packages.</span></span>

  <span data-ttu-id="6b517-184">**종속성**: `dotnet-host`, 하나 이상의 `dotnet-runtime-[major].[minor]`(런타임 중 하나는 SDK 코드 자체에 의해 사용되며 나머지는 사용자가 빌드하고 실행하는 데 사용됨).</span><span class="sxs-lookup"><span data-stu-id="6b517-184">**Dependencies**: `dotnet-host`, one or more `dotnet-runtime-[major].[minor]` (one of those is used by the SDK code itself, the others are here for users to build and run against).</span></span>

* <span data-ttu-id="6b517-185">`dotnet-host`: 최신 호스트</span><span class="sxs-lookup"><span data-stu-id="6b517-185">`dotnet-host`: the latest host.</span></span>

##### <a name="preview-versions"></a><span data-ttu-id="6b517-186">미리 보기 버전</span><span class="sxs-lookup"><span data-stu-id="6b517-186">Preview versions</span></span>

<span data-ttu-id="6b517-187">패키지 유지 관리자는 런타임 및 SDK의 미리 보기 버전을 포함하도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-187">Package maintainers may decide to include preview versions of the runtime and SDK.</span></span> <span data-ttu-id="6b517-188">버전이 지정되지 않은 `dotnet-sdk` 패키지에 이러한 미리 보기 버전을 포함해서는 안 되지만, 이름의 주 버전 및 부 버전 섹션에 추가 미리 보기 마커를 추가하여 버전이 지정된 패키지로서 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-188">Don't include those preview versions in the unversioned `dotnet-sdk` package, but you can release them as versioned packages with an additional preview marker appended to the major and minor version sections of the name.</span></span> <span data-ttu-id="6b517-189">예를 들어 `dotnet-sdk-2.0-preview1-final` 패키지가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-189">For example, there may be a `dotnet-sdk-2.0-preview1-final` package.</span></span>

### <a name="docker"></a><span data-ttu-id="6b517-190">Docker</span><span class="sxs-lookup"><span data-stu-id="6b517-190">Docker</span></span>

<span data-ttu-id="6b517-191">일반 Docker 태그 명명 규칙은 버전 번호를 구성 요소 이름 앞에 놓는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-191">A general Docker tag naming convention is to place the version number before the component name.</span></span> <span data-ttu-id="6b517-192">이 규칙을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-192">This convention may continue to be utilized.</span></span> <span data-ttu-id="6b517-193">현재 태그는 다음과 같이 런타임 버전만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-193">The current tags include only the Runtime version as follows.</span></span>

* <span data-ttu-id="6b517-194">1.0.8-runtime</span><span class="sxs-lookup"><span data-stu-id="6b517-194">1.0.8-runtime</span></span>
* <span data-ttu-id="6b517-195">1.0.8-sdk</span><span class="sxs-lookup"><span data-stu-id="6b517-195">1.0.8-sdk</span></span>
* <span data-ttu-id="6b517-196">2.0.4-runtime</span><span class="sxs-lookup"><span data-stu-id="6b517-196">2.0.4-runtime</span></span>
* <span data-ttu-id="6b517-197">2.0.4-sdk</span><span class="sxs-lookup"><span data-stu-id="6b517-197">2.0.4-sdk</span></span>
* <span data-ttu-id="6b517-198">2.1.1-runtime</span><span class="sxs-lookup"><span data-stu-id="6b517-198">2.1.1-runtime</span></span>
* <span data-ttu-id="6b517-199">2.1.1-sdk</span><span class="sxs-lookup"><span data-stu-id="6b517-199">2.1.1-sdk</span></span>

<span data-ttu-id="6b517-200">런타임 대신 SDK 버전을 나타내기 위해 SDK 태그를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-200">The SDK tags should be updated to represent the SDK version rather than Runtime.</span></span>

<span data-ttu-id="6b517-201">.NET Core 도구를 수정해야 하지만 기존의 런타임을 다시 출시해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-201">It's also possible that we need to fix the .NET Core Tools but reship an existing runtime.</span></span> <span data-ttu-id="6b517-202">이 경우 SDK 버전이 예를 들어 2.1.2로 높아지면 다음에 출시될 때 런타임이 이에 따라 높아집니다(즉, 런타임과 SDK가 2.1.3으로 출시됨).</span><span class="sxs-lookup"><span data-stu-id="6b517-202">In that case, the SDK version is increased (for example, to 2.1.2) and then the Runtime catches up the next time it ships (for example, both the Runtime and SDK ship the following time as 2.1.3).</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="6b517-203">유의적 버전</span><span class="sxs-lookup"><span data-stu-id="6b517-203">Semantic Versioning</span></span>

<span data-ttu-id="6b517-204">.NET Core는 [유의적 버전(SemVer)](http://semver.org/)을 사용하여 `MAJOR.MINOR.PATCH` 버전 관리를 사용하고 버전 번호의 다양한 부분으로 변경의 수준 및 종류를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-204">.NET Core uses [Semantic Versioning (SemVer)](http://semver.org/), adopting the use of `MAJOR.MINOR.PATCH` versioning, using the various parts of the version number to describe the degree and type of change.</span></span>

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

<span data-ttu-id="6b517-205">선택적 `PRERELEASE` 및 `BUILDNUMBER` 부분은 지원되는 버전의 일부가 되지 않으며, 소스 대상에서 로컬로 빌드되는 야간 빌드 및 지원되지 않는 미리 보기 릴리스에만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-205">The optional `PRERELEASE` and `BUILDNUMBER` parts will never be part of supported releases, and only exist on nightly builds, locally built from source targets, and unsupported preview releases.</span></span>

### <a name="how-version-numbers-are-incremented"></a><span data-ttu-id="6b517-206">버전 번호는 어떻게 높아지나요?</span><span class="sxs-lookup"><span data-stu-id="6b517-206">How version numbers are incremented?</span></span>

<span data-ttu-id="6b517-207">다음 경우에는 `MAJOR`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-207">`MAJOR` is incremented when:</span></span>
  - <span data-ttu-id="6b517-208">이전 버전이 더 이상 지원되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-208">An old version is no longer supported.</span></span>
  - <span data-ttu-id="6b517-209">기존 종속성의 최신 `MAJOR` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-209">A newer `MAJOR` version of an existing dependency is adopted.</span></span>
  - <span data-ttu-id="6b517-210">호환성 쿼크의 기본 설정이 “off”로 변경된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-210">The default setting of a compatibility quirk is changed to "off."</span></span>

<span data-ttu-id="6b517-211">다음 경우에는 `MINOR`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-211">`MINOR` is incremented when:</span></span>
  - <span data-ttu-id="6b517-212">공용 API 노출 영역이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-212">Public API surface area is added.</span></span>
  - <span data-ttu-id="6b517-213">새 동작이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-213">A new behavior is added.</span></span>
  - <span data-ttu-id="6b517-214">기존 종속성의 최신 `MINOR` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-214">A newer `MINOR` version of an existing dependency is adopted.</span></span>
  - <span data-ttu-id="6b517-215">새 종속성이 도입된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-215">A new dependency is introduced.</span></span>
  
<span data-ttu-id="6b517-216">다음 경우에는 `PATCH`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-216">`PATCH` is incremented when:</span></span>
  - <span data-ttu-id="6b517-217">버그 수정이 이루어진 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-217">Bug fixes are made.</span></span>
  - <span data-ttu-id="6b517-218">최신 플랫폼에 대한 지원이 추가된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-218">Support for a newer platform is added.</span></span>
  - <span data-ttu-id="6b517-219">기존 종속성의 최신 `PATCH` 버전이 채택된 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-219">A newer `PATCH` version of an existing dependency is adopted.</span></span>
  - <span data-ttu-id="6b517-220">이전의 경우와 맞지 않는 다른 변경 사항이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="6b517-220">Any other change that doesn't fit one of the previous cases.</span></span>

<span data-ttu-id="6b517-221">여러 가지 변경이 이루어진 경우에는 개별 변경의 영향을 받는 가장 높은 요소가 증가되고 다음은 0으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-221">When there are multiple changes, the highest element affected by individual changes is incremented, and the following ones are reset to zero.</span></span> <span data-ttu-id="6b517-222">예를 들어 `MAJOR`가 증가하면 `MINOR` 및 `PATCH`는 0으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-222">For example, when `MAJOR` is incremented, `MINOR` and `PATCH` are reset to zero.</span></span> <span data-ttu-id="6b517-223">`MINOR`가 증가하면 `PATCH`는 0으로 다시 설정되지만 `MAJOR`는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-223">When `MINOR` is incremented, `PATCH` is reset to zero while `MAJOR` is left untouched.</span></span>

### <a name="preview-versions"></a><span data-ttu-id="6b517-224">미리 보기 버전</span><span class="sxs-lookup"><span data-stu-id="6b517-224">Preview versions</span></span>

<span data-ttu-id="6b517-225">미리 보기 버전에는 `-preview[number]-([build]|"final")`이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-225">Preview versions have a `-preview[number]-([build]|"final")` appended to the version.</span></span> <span data-ttu-id="6b517-226">예를 들어, `2.0.0-preview1-final`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-226">For example, `2.0.0-preview1-final`.</span></span>

### <a name="servicing-versions"></a><span data-ttu-id="6b517-227">서비스 버전</span><span class="sxs-lookup"><span data-stu-id="6b517-227">Servicing versions</span></span>

<span data-ttu-id="6b517-228">릴리스가 출시된 후에 릴리스 분기는 일반적으로 매일 빌드 만들기를 중지하고 대신 서비스 빌드를 만들기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-228">After a release goes out, the release branches generally stop producing daily builds and instead start producing servicing builds.</span></span> <span data-ttu-id="6b517-229">서비스 버전에는 `-servicing-[number]`이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-229">Servicing versions have a `-servicing-[number]` appended to the version.</span></span> <span data-ttu-id="6b517-230">예를 들어, `2.0.1-servicing-006924`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-230">For example, `2.0.1-servicing-006924`.</span></span>

### <a name="lts-vs-current"></a><span data-ttu-id="6b517-231">LTS 및 Current</span><span class="sxs-lookup"><span data-stu-id="6b517-231">LTS vs. current</span></span>

<span data-ttu-id="6b517-232">.NET Core에는 Long Term Support(LTS) 및 Current의 두 가지 릴리스 학습이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-232">There are two trains of releases for .NET Core: Long Term Support (LTS) and Current.</span></span> <span data-ttu-id="6b517-233">사용자는 원하는 안정성 수준과 새 기능을 선택할 수 있으며 지원은 계속 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-233">That enables users to pick the level of stability and new features they want, while still being supported.</span></span>

- <span data-ttu-id="6b517-234">LTS를 이용하면 새로운 기능을 얻는 빈도가 적더라도 더 안정적인 플랫폼을 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-234">LTS means you get new features less frequently, but you have a more mature platform.</span></span> <span data-ttu-id="6b517-235">또한 LTS의 지원 기간이 더 깁니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-235">LTS also has a longer period of support.</span></span>
- <span data-ttu-id="6b517-236">Current를 이용하면 새 기능과 API를 더 자주 얻을 수 있지만 업데이트를 설치할 수 있는 시간 창이 더 짧고 그러한 업데이트가 보다 자주 이루어진다는 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-236">Current means you get new features and APIs more frequently, but the disadvantage is that you have a shorter window of time to install updates, and those updates happen more frequently.</span></span> <span data-ttu-id="6b517-237">또한 Current는 전체가 지원되지만 지원 기간은 LTS보다 짧습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-237">Current is also fully supported but the support period is shorter than LTS.</span></span>

<span data-ttu-id="6b517-238">“Current” 버전을 LTS로 승격시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-238">A "Current" version may get promoted to LTS.</span></span>

<span data-ttu-id="6b517-239">“LTS” 및 “Current”는 관련된 지원 수준에 대한 문을 작성하기 위해 특정 릴리스에 넣을 레이블로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-239">"LTS" and "Current" should be considered as labels that we put on specific releases to make a statement about the associated level of support.</span></span>

<span data-ttu-id="6b517-240">자세한 내용은 [.NET Core 지원 수명 주기 팩트 시트](https://www.microsoft.com/net/core/support)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b517-240">For more information, see [.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support).</span></span>

## <a name="versioning-scheme-details"></a><span data-ttu-id="6b517-241">버전 관리 체계 세부 정보</span><span class="sxs-lookup"><span data-stu-id="6b517-241">Versioning scheme details</span></span>

<span data-ttu-id="6b517-242">.NET core는 다음 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-242">.NET Core is made of the following parts:</span></span>

- <span data-ttu-id="6b517-243">호스트(muxer라고도 함): `hostfxr` 정책 라이브러리를 포함한 `dotnet.exe`</span><span class="sxs-lookup"><span data-stu-id="6b517-243">A host (also known as muxer): `dotnet.exe` with `hostfxr` policy libraries.</span></span>
- <span data-ttu-id="6b517-244">SDK(개발자의 컴퓨터에 필요하지만 프로덕션에는 필요하지 않은 도구 집합)</span><span class="sxs-lookup"><span data-stu-id="6b517-244">An SDK (the set of tools necessary on a developer's machine, but not in production).</span></span>
- <span data-ttu-id="6b517-245">런타임</span><span class="sxs-lookup"><span data-stu-id="6b517-245">A runtime.</span></span>
- <span data-ttu-id="6b517-246">패키지로 배포되는 공유 프레임워크 구현.</span><span class="sxs-lookup"><span data-stu-id="6b517-246">A shared framework implementation, distributed as packages.</span></span> <span data-ttu-id="6b517-247">특히 패치 버전 관리의 경우 각 패키지 버전을 독립적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-247">Each package is versioned independently, particularly for patch versioning.</span></span>
- <span data-ttu-id="6b517-248">세분화된 패키지를 버전이 있는 단위로 참조하는 선택적 [메타패키지](../packages.md) 집합.</span><span class="sxs-lookup"><span data-stu-id="6b517-248">Optionally, a set of [metapackages](../packages.md) that reference fine-grained packages as a versioned unit.</span></span> <span data-ttu-id="6b517-249">메타패키지는 패키지와 별도로 버전 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-249">Metapackages can be versioned separately from packages.</span></span>

<span data-ttu-id="6b517-250">.NET Core에는 버전 번호가 증가함에 따라 점점 커지는 API 집합을 나타내는 대상 프레임워크 집합(예를 들어 `netstandard` 또는 `netcoreapp`)도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-250">.NET Core also includes a set of target frameworks (for example, `netstandard` or `netcoreapp`) that represent a progressively larger API set, as version numbers are incremented.</span></span>

### <a name="net-standard"></a><span data-ttu-id="6b517-251">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="6b517-251">.NET Standard</span></span>

<span data-ttu-id="6b517-252">.NET Standard는 `MAJOR.MINOR` 버전 관리 체계를 사용해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-252">.NET Standard has been using a `MAJOR.MINOR` versioning scheme.</span></span> <span data-ttu-id="6b517-253">`PATCH` 수준은 덜 빈번하게 반복되며 실제 구현과 동일한 버전 관리 요건을 제시하지 않는 계약 집합을 표현하므로 .NET Standard에 유용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-253">`PATCH` level isn't useful for .NET Standard because it expresses a set of contracts that are iterated on less often and doesn't present the same requirements for versioning as an actual implementation.</span></span>

<span data-ttu-id="6b517-254">.NET Standard 버전과 .NET Core 버전 간에는 실제 결합이 없습니다. .NET Core 2.0은 .NET Standard 2.0을 구현하기도 하지만 향후 .NET Core 버전이 동일한 .NET Standard 버전으로 매핑된다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-254">There is no real coupling between .NET Standard versions and .NET Core versions: .NET Core 2.0 happens to implement .NET Standard 2.0, but there is no guarantee that future versions of .NET Core will map to the same .NET Standard version.</span></span> <span data-ttu-id="6b517-255">.NET Core는 .NET Standard에 의해 정의되지 않는 API를 출시하므로 새 .NET Standard 없이 새로운 버전을 출시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-255">.NET Core can ship APIs that aren't defined by .NET Standard, and, as such, may ship new versions without requiring a new .NET Standard.</span></span> <span data-ttu-id="6b517-256">.NET Standard는 그 개시는 .NET Core와 일치했다 하더라도 .NET Framework 또는 Mono 등의 다른 대상에 적용되는 개념이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-256">.NET Standard is also a concept that applies to other targets, such as .NET Framework or Mono, even if its inception happened to coincide with that of .NET Core.</span></span>

### <a name="packages"></a><span data-ttu-id="6b517-257">패키지</span><span class="sxs-lookup"><span data-stu-id="6b517-257">Packages</span></span>

<span data-ttu-id="6b517-258">라이브러리 패키지는 독립적으로 발전하고 버전 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-258">Library packages evolve and version independently.</span></span> <span data-ttu-id="6b517-259">.NET Framework System.\* 어셈블리와 겹치는 패키지는 일반적으로 .NET Framework 4.x 버전 관리(기록 선택)를 지원하는 4.x 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-259">Packages that overlap with .NET Framework System.\* assemblies typically use 4.x versions, aligning with the .NET Framework 4.x versioning (a historical choice).</span></span> <span data-ttu-id="6b517-260">.NET Framework 라이브러리(예: [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata))와 겹치지 않는 패키지는 일반적으로 1.0에서 시작하여 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-260">Packages that do not overlap with the .NET Framework libraries (for example, [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata)) typically start at 1.0 and increment from there.</span></span>

<span data-ttu-id="6b517-261">[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library)에 설명된 패키지는 플랫폼의 맨 아래에 있기 때문에 특별하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-261">The packages described by [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) are treated specially due to being at the base of the platform.</span></span>

<span data-ttu-id="6b517-262">`NETStandard.Library` 패키지는 해당 패키지 간에 구현 수준 종속성이 있기 때문에 일반적으로 집합으로 버전 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-262">`NETStandard.Library` packages will typically version as a set, since they have implementation-level dependencies between them.</span></span>

### <a name="metapackages"></a><span data-ttu-id="6b517-263">메타패키지</span><span class="sxs-lookup"><span data-stu-id="6b517-263">Metapackages</span></span>

<span data-ttu-id="6b517-264">.NET Core 메타패키지에 대한 버전 관리는 해당 메타패키지의 일부인 .NET Core 버전을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-264">Versioning for .NET Core metapackages is based on the .NET Core version they are a part of.</span></span>

<span data-ttu-id="6b517-265">예를 들어 .NET Core 2.1.3의 메타패키지의 `MAJOR` 및 `MINOR` 버전 번호는 모두 2.1이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-265">For instance, the metapackages in .NET Core 2.1.3 should all have 2.1 as their `MAJOR` and `MINOR` version numbers.</span></span>

<span data-ttu-id="6b517-266">메타패키지의 패치 버전은 참조된 패키지가 업데이트될 때마다 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-266">The patch version for the metapackage is incremented every time any referenced package is updated.</span></span> <span data-ttu-id="6b517-267">패치 버전에는 업데이트된 프레임워크 버전이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-267">Patch versions don't include an updated framework version.</span></span> <span data-ttu-id="6b517-268">결과적으로 메타패키지의 버전 관리 체계에서는 기본 패키지의 변경 수준을 나타내지 않고 주로 API 수준을 나타내기 때문에 메타패키지는 엄격하게 SemVer 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-268">As a result, the metapackages aren't strictly SemVer-compliant because their versioning scheme doesn't represent the degree of change in the underlying packages, but primarily the API level.</span></span> 

<span data-ttu-id="6b517-269">현재 .NET Core에 대한 주 메타패키지는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-269">There are currently two primary metapackages for .NET Core:</span></span>

<span data-ttu-id="6b517-270">**Microsoft.NETCore.App**</span><span class="sxs-lookup"><span data-stu-id="6b517-270">**Microsoft.NETCore.App**</span></span>

- <span data-ttu-id="6b517-271">.NET Core 1.0 기준 v1.0(이러한 버전은 일치함).</span><span class="sxs-lookup"><span data-stu-id="6b517-271">v1.0 as of .NET Core 1.0 (these versions match).</span></span>
- <span data-ttu-id="6b517-272">`netcoreapp` 프레임워크에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-272">Maps to the `netcoreapp` framework.</span></span>
- <span data-ttu-id="6b517-273">.NET Core 배포의 패키지를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-273">Describes the packages in the .NET Core distribution.</span></span>

<span data-ttu-id="6b517-274">참고: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility)는 .NET의 이전 .NET Standard 구현과의 호환이 가능하도록 하기 위해 존재하는 다른 .NET Core 메타패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-274">Note: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) is another .NET Core metapackage that exists to enable compatibility with pre-.NET Standard implementation of .NET.</span></span> <span data-ttu-id="6b517-275">이것은 특정 프레임워크에 매핑되지 않으므로 패키지처럼 버전 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-275">It doesn't map to a particular framework, so it versions like a package.</span></span>

<span data-ttu-id="6b517-276">**NETStandard.Library**</span><span class="sxs-lookup"><span data-stu-id="6b517-276">**NETStandard.Library**</span></span>

<span data-ttu-id="6b517-277">[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library)는 [.NET Standard](../../standard/library.md)의 일부인 라이브러리를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-277">[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) describes the libraries that are part of the [.NET Standard](../../standard/library.md).</span></span> <span data-ttu-id="6b517-278">.NET Standard를 지원하는 모든 .NET 구현(예: .NET Framework, .NET Core 및 Mono)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-278">Applies to all .NET implementations that support .NET Standard, such as .NET Framework, .NET Core, and Mono.</span></span>

### <a name="target-frameworks"></a><span data-ttu-id="6b517-279">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="6b517-279">Target frameworks</span></span>

<span data-ttu-id="6b517-280">대상 프레임워크 버전은 새 API가 추가될 때 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-280">Target framework versions are updated when new APIs are added.</span></span> <span data-ttu-id="6b517-281">이러한 버전은 구현 관련 사항이 아닌 API 셰이프를 나타내므로 패치 버전에 대한 개념이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-281">They have no concept of patch version, since they represent API shape and not implementation concerns.</span></span> <span data-ttu-id="6b517-282">주 버전 및 부 버전 관리는 이전에 지정한 SemVer 규칙을 따르며 이를 구현하는 .NET Core 배포의 `MAJOR` 및 `MINOR` 번호와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-282">Major and minor versioning follows the SemVer rules specified earlier, and coincides with the `MAJOR` and `MINOR` numbers of the .NET Core distributions that implement them.</span></span>

## <a name="versioning-in-practice"></a><span data-ttu-id="6b517-283">실제 버전 관리</span><span class="sxs-lookup"><span data-stu-id="6b517-283">Versioning in practice</span></span>

<span data-ttu-id="6b517-284">.NET Core를 다운로드하면 다운로드한 파일 이름에 버전이 추가됩니다(예: `dotnet-sdk-2.0.4-win10-x64.exe`).</span><span class="sxs-lookup"><span data-stu-id="6b517-284">When you download .NET Core, the name of the file you download carries the version, for example, `dotnet-sdk-2.0.4-win10-x64.exe`.</span></span>

<span data-ttu-id="6b517-285">GitHub의 .NET Core 리포지토리에는 매일 많은 라이브러리의 새로운 빌드를 생성하는 커밋 및 끌어오기 요청이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-285">There are commits and pull requests on .NET Core repos on GitHub on a daily basis, resulting in new builds of many libraries.</span></span> <span data-ttu-id="6b517-286">.NET Core의 모든 변경 내용에 대해 새로운 공개 버전을 만드는 것은 실용적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-286">It isn't practical to create new public versions of .NET Core for every change.</span></span> <span data-ttu-id="6b517-287">대신 확정적이지 않은 일정 기간(예: 주 또는 월) 동안 변경 내용을 집계한 후 .NET Core의 안정적인 새 공개 버전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-287">Instead, changes are aggregated over an undetermined period of time (for example, weeks or months) before making a new public stable .NET Core version.</span></span>

<span data-ttu-id="6b517-288">.NET Core의 새 버전은 다음과 같은 여러 가지를 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-288">A new version of .NET Core could mean several things:</span></span>

- <span data-ttu-id="6b517-289">패키지 및 메타패키지의 새 버전.</span><span class="sxs-lookup"><span data-stu-id="6b517-289">New versions of packages and metapackages.</span></span>
- <span data-ttu-id="6b517-290">새 API의 추가를 가정하는 다양한 프레임워크의 새 버전.</span><span class="sxs-lookup"><span data-stu-id="6b517-290">New versions of various frameworks, assuming the addition of new APIs.</span></span>
- <span data-ttu-id="6b517-291">.NET Core 배포의 새 버전.</span><span class="sxs-lookup"><span data-stu-id="6b517-291">New version of the .NET Core distribution.</span></span>

### <a name="shipping-a-patch-release"></a><span data-ttu-id="6b517-292">패치 릴리스 전달</span><span class="sxs-lookup"><span data-stu-id="6b517-292">Shipping a patch release</span></span>

<span data-ttu-id="6b517-293">버전 2.0.0과 같은 주요 .NET Core 릴리스를 전달한 후 버그를 수정하고 성능 및 안정성을 개선하기 위해 .NET Core 라이브러리에 대해 패치 수준 변경을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-293">After shipping a major release of .NET Core, such as version 2.0.0, patch-level changes are made to .NET Core libraries to fix bugs and improve performance and reliability.</span></span> <span data-ttu-id="6b517-294">따라서 새로운 API는 도입되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-294">That means that no new APIs are introduced.</span></span> <span data-ttu-id="6b517-295">다양한 메타패키지가 업데이트된 .NET Core 라이브러리 패키지를 참조하도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-295">The various metapackages are updated to reference the updated .NET Core library packages.</span></span> <span data-ttu-id="6b517-296">메타패키지는 패치 업데이트로 버전 관리됩니다(`MAJOR.MINOR.PATCH`).</span><span class="sxs-lookup"><span data-stu-id="6b517-296">The metapackages are versioned as patch updates (`MAJOR.MINOR.PATCH`).</span></span> <span data-ttu-id="6b517-297">대상 프레임워크는 패치 릴리스의 일부로 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-297">Target frameworks are never updated as part of patch releases.</span></span> <span data-ttu-id="6b517-298">새 .NET Core 배포는 `Microsoft.NETCore.App` 메타패키지와 일치하는 버전 번호로 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-298">A new .NET Core distribution is released with a version number that matches that of the `Microsoft.NETCore.App` metapackage.</span></span>

### <a name="shipping-a-minor-release"></a><span data-ttu-id="6b517-299">부 릴리스 전달</span><span class="sxs-lookup"><span data-stu-id="6b517-299">Shipping a minor release</span></span>

<span data-ttu-id="6b517-300">증가된 `MAJOR` 버전 번호를 가진 .NET Core 버전을 전달한 후에는 새 시나리오를 이용할 수 있도록 새로운 API가 .NET Core 라이브러리에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-300">After shipping a .NET Core version with an incremented `MAJOR` version number, new APIs are added to .NET Core libraries to enable new scenarios.</span></span> <span data-ttu-id="6b517-301">다양한 메타패키지가 업데이트된 .NET Core 라이브러리 패키지를 참조하도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-301">The various metapackages are updated to reference the updated .NET Core library packages.</span></span> <span data-ttu-id="6b517-302">메타패키지는 `MAJOR` 및 `MINOR` 버전 번호가 새 프레임워크 버전과 일치하는 패치 업데이트로 버전 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-302">The metapackages are versioned as patch updates with `MAJOR` and `MINOR` version numbers matching the new framework version.</span></span> <span data-ttu-id="6b517-303">새 `MAJOR.MINOR` 버전의 새로운 대상 프레임워크 이름이 새로운 API를 설명하기 위해 추가됩니다(예: `netcoreapp2.1`).</span><span class="sxs-lookup"><span data-stu-id="6b517-303">New target framework names with the new `MAJOR.MINOR` version are added to describe the new APIs (for example, `netcoreapp2.1`).</span></span> <span data-ttu-id="6b517-304">새로운 .NET Core 배포가 `Microsoft.NETCore.App` 메타패키지와 일치하는 버전 번호로 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-304">A new .NET Core distribution is released with a matching version number to the `Microsoft.NETCore.App` metapackage.</span></span>

### <a name="shipping-a-major-release"></a><span data-ttu-id="6b517-305">주 릴리스 전달</span><span class="sxs-lookup"><span data-stu-id="6b517-305">Shipping a major release</span></span>

<span data-ttu-id="6b517-306">.NET Core의 새로운 주 버전이 출시될 때마다 `MAJOR` 버전 번호는 증가하고 `MINOR` 버전 번호는 0으로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-306">Every time a new major version of .NET Core ships, the `MAJOR` version number gets incremented, and the `MINOR` version number gets reset to zero.</span></span> <span data-ttu-id="6b517-307">새 주 버전에는 이전의 주 버전 이후 부 릴리스에 의해 추가된 모든 API가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-307">The new major version contains at least all the APIs that were added by minor releases after the previous major version.</span></span> <span data-ttu-id="6b517-308">새 주 버전은 중요한 새 시나리오를 사용하도록 설정해야 하며 이전 플랫폼에 대한 지원을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-308">A new major version should enable important new scenarios, and it may also drop support for an older platform.</span></span>

<span data-ttu-id="6b517-309">다양한 메타패키지가 업데이트된 .NET Core 라이브러리 패키지를 참조하도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-309">The various metapackages are updated to reference the updated .NET Core library packages.</span></span> <span data-ttu-id="6b517-310">[`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) 메타패키지 및 `netcore` 대상 프레임워크는 새 릴리스의 `MAJOR` 버전 번호와 일치하는 주 업데이트로 버전 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b517-310">The [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) metapackage and the `netcore` target framework are versioned as a major update matching the `MAJOR` version number of the new release.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b517-311">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b517-311">See also</span></span>
<span data-ttu-id="6b517-312">[대상 프레임워크](../../standard/frameworks.md) </span><span class="sxs-lookup"><span data-stu-id="6b517-312">[Target frameworks](../../standard/frameworks.md) </span></span>  
<span data-ttu-id="6b517-313">[.NET Core 배포 패키징](../build/distribution-packaging.md) </span><span class="sxs-lookup"><span data-stu-id="6b517-313">[.NET Core distribution packaging](../build/distribution-packaging.md) </span></span>  
<span data-ttu-id="6b517-314">[.NET Core 지원 수명 주기 팩트 시트](https://www.microsoft.com/net/core/support) </span><span class="sxs-lookup"><span data-stu-id="6b517-314">[.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support) </span></span>  
[<span data-ttu-id="6b517-315">.NET Core 2+ 버전 바인딩</span><span class="sxs-lookup"><span data-stu-id="6b517-315">.NET Core 2+ Version Binding</span></span>](https://github.com/dotnet/designs/issues/3)   
