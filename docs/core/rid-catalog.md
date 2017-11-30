---
title: ".NET Core RID(런타임 식별자) 카탈로그"
description: "RID(런타임 식별자) 및 .NET Core에서 RID의 사용 방법에 관해 알아봅니다."
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 067f9cfc283a14b7ea59a7454b7f593ce6eb5806
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="321e6-103">.NET Core RID 카탈로그</span><span class="sxs-lookup"><span data-stu-id="321e6-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="321e6-104">RID는 *Runtime IDentifier(런타임 식별자)*의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="321e6-105">RID 값은 응용 프로그램을 실행하는 대상 플랫폼을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="321e6-106">NuGet 패키지에서 .NET 패키지의 플랫폼 관련 자산을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="321e6-107">RID 값의 예로 `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, `osx.10.12-x64` 등을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="321e6-108">기본 종속성이 있는 패키지의 경우 RID는 패키지를 복원할 수 있는 플랫폼을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="321e6-109">RID는 프로젝트 파일의 `<RuntimeIdentifier>` 요소에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-109">RIDs can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="321e6-110">다음과 같은 [.NET Core CLI 명령](./tools/index.md)을 사용하여 `--runtime` 옵션을 통해서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-110">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="321e6-111">dotnet build</span><span class="sxs-lookup"><span data-stu-id="321e6-111">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="321e6-112">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="321e6-112">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="321e6-113">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="321e6-113">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="321e6-114">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="321e6-114">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="321e6-115">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="321e6-115">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="321e6-116">dotnet run</span><span class="sxs-lookup"><span data-stu-id="321e6-116">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="321e6-117">dotnet store</span><span class="sxs-lookup"><span data-stu-id="321e6-117">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="321e6-118">구체적인 운영 체제를 나타내는 RID는 일반적으로 `[os].[version]-[architecture]-[additional qualifiers]`의 패턴을 따릅니다. 각각은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-118">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="321e6-119">`[os]` - 운영 체제/플랫폼 모니커입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-119">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="321e6-120">예를 들어, `ubuntu`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-120">For example, `ubuntu`.</span></span>

- <span data-ttu-id="321e6-121">`[version]` - 점으로 구분된(`.`) 버전 번호 형식의 운영 체제 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-121">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="321e6-122">예를 들어, `15.10`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-122">For example, `15.10`.</span></span>

  - <span data-ttu-id="321e6-123">버전은 마케팅 버전이어서는 **안 됩니다**. 마케팅 버전은 종종 다양한 플랫폼 API 노출 영역이 있는 운영 체제의 여러 개별 버전을 나타내기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-123">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="321e6-124">`[architecture]` - 프로세서 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-124">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="321e6-125">예를 들면 `x86`, `x64`, `arm`, `arm64` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-125">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="321e6-126">`[additional qualifiers]` - 다른 플랫폼을 추가로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-126">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="321e6-127">예를 들면 `aot` 또는 `corert` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-127">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="321e6-128">RID 그래프</span><span class="sxs-lookup"><span data-stu-id="321e6-128">RID graph</span></span>

<span data-ttu-id="321e6-129">RID 그래프 또는 런타임 Fallback 그래프는 서로 호환되는 RID 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-129">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="321e6-130">RID는 [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 패키지에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-130">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="321e6-131">지원되는 RID 및 RID 그래프 목록은 CoreFX 리포지토리에 있는 [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-131">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="321e6-132">이 파일에서 기본 RID를 제외하고 모든 RID에 `"#import"` 문이 포함되어 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-132">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="321e6-133">이러한 문은 호환되는 RID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-133">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="321e6-134">NuGet에서 패키지를 복원할 때 지정된 런타임에 대한 정확한 일치를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-134">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="321e6-135">정확한 일치를 찾을 수 없는 경우 NuGet은 RID 그래프에 따라 가장 가까운 호환 시스템을 찾을 때까지 그래프를 다시 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-135">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="321e6-136">다음 예제는 `osx.10.12-x64` RID의 실제 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-136">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="321e6-137">위의 RID는 `osx.10.12-x64`가 `osx.10.11-x64`를 가져오도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-137">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="321e6-138">따라서 NuGet에서 패키지를 복원할 때 패키지에서 `osx.10.12-x64`와 정확히 일치하는 값을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-138">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="321e6-139">NuGet이 특정 런타임을 찾을 수 없는 경우 예를 들어 `osx.10.11-x64` 런타임을 지정하는 패키지를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-139">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="321e6-140">다음 예제에서는 마찬가지로 *runtime.json* 파일에 정의된 약간 더 큰 RID 그래프를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-140">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="321e6-141">모든 RID는 결국 루트 `any` RID에 다시 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-141">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="321e6-142">RID를 사용할 때는 RID에 대한 다음과 같은 몇 가지 고려 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-142">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="321e6-143">RID는 **불투명 문자열**이며 블랙 박스로 취급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-143">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="321e6-144">RID를 프로그래밍 방식으로 빌드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="321e6-144">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="321e6-145">플랫폼에 대해 이미 정의된 RID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-145">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="321e6-146">RID는 구체적이어야 하므로 실제 RID 값에서 어느 것도 가정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="321e6-146">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="321e6-147">RID 사용</span><span class="sxs-lookup"><span data-stu-id="321e6-147">Using RIDs</span></span>

<span data-ttu-id="321e6-148">RID를 사용할 수 있으려면 어떤 RID가 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-148">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="321e6-149">새 값이 플랫폼에 정기적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-149">New values are added regularly to the platform.</span></span>
<span data-ttu-id="321e6-150">최신의 완전한 버전을 보려면 CoreFX 리포지토리에서 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="321e6-150">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="321e6-151">.NET Core 2.0 SDK에서는 이식 가능 RID라는 개념을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-151">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="321e6-152">이식 가능 RID란 RID 그래프에 추가된 새 값인데 아직 특정 버전 또는 OS 배포에 연결되지 않은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-152">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="321e6-153">여러 Linux 배포판을 처리할 때 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-153">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="321e6-154">다음 목록에서는 각 OS에 사용되는 일반적인 RID를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-154">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="321e6-155">`arm` 또는 `corert` 값은 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-155">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="321e6-156">Windows RID</span><span class="sxs-lookup"><span data-stu-id="321e6-156">Windows RIDs</span></span>

- <span data-ttu-id="321e6-157">이식 가능</span><span class="sxs-lookup"><span data-stu-id="321e6-157">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="321e6-158">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="321e6-158">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="321e6-159">Windows 8 / Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="321e6-159">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="321e6-160">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="321e6-160">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="321e6-161">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="321e6-161">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="321e6-162">참조 [Windows에서.NET Core에 대 한 필수 구성 요소](windows-prerequisites.md) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-162">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="321e6-163">Linux RID</span><span class="sxs-lookup"><span data-stu-id="321e6-163">Linux RIDs</span></span>

- <span data-ttu-id="321e6-164">이식 가능</span><span class="sxs-lookup"><span data-stu-id="321e6-164">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="321e6-165">CentOS</span><span class="sxs-lookup"><span data-stu-id="321e6-165">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="321e6-166">Debian</span><span class="sxs-lookup"><span data-stu-id="321e6-166">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="321e6-167">Fedora</span><span class="sxs-lookup"><span data-stu-id="321e6-167">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="321e6-168">`fedora.25-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-168">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="321e6-169">`fedora.26-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-169">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="321e6-170">Gentoo(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-170">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="321e6-171">openSUSE</span><span class="sxs-lookup"><span data-stu-id="321e6-171">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="321e6-172">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="321e6-172">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="321e6-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="321e6-173">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="321e6-174">`rhel.6-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-174">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="321e6-175">`rhel.7.3-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-175">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="321e6-176">`rhel.7.4-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-176">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="321e6-177">Tizen(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-177">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="321e6-178">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="321e6-178">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="321e6-179">Ubuntu 파생 제품</span><span class="sxs-lookup"><span data-stu-id="321e6-179">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="321e6-180">`linuxmint.18.1-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-180">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="321e6-181">참조 [Linux에서.NET Core에 대 한 필수 구성 요소](linux-prerequisites.md) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-181">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="321e6-182">macOS Rid</span><span class="sxs-lookup"><span data-stu-id="321e6-182">macOS RIDs</span></span>

<span data-ttu-id="321e6-183">macOS Rid 이전에 수행 된 "OSX" 브랜드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-183">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="321e6-184">`osx-x64`(최소 버전은.NET core 2.0 또는 이후 버전 `osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="321e6-184">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="321e6-185">`osx.10.12-x64`(.NET Core 1.1 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-185">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="321e6-186">참조 [macOS에서.NET Core에 대 한 필수 구성 요소](macos-prerequisites.md) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="321e6-186">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="321e6-187">Android RID(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="321e6-187">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="321e6-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="321e6-188">See also</span></span>

[<span data-ttu-id="321e6-189">런타임 ID</span><span class="sxs-lookup"><span data-stu-id="321e6-189">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
