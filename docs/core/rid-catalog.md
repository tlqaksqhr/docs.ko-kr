---
title: ".NET Core RID(런타임 식별자) 카탈로그"
description: "RID(런타임 식별자) 및 .NET Core에서 RID의 사용 방법에 관해 알아봅니다."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/22/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b2032f5d-771f-48d9-917c-587d9509035c
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3490fb639efd223dc36190324bdf3a06bc23c10e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="net-core-runtime-identifier-rid-catalog"></a><span data-ttu-id="7b5e4-104">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="7b5e4-104">.NET Core Runtime IDentifier (RID) catalog</span></span>

## <a name="what-are-rids"></a><span data-ttu-id="7b5e4-105">RID란?</span><span class="sxs-lookup"><span data-stu-id="7b5e4-105">What are RIDs?</span></span>
<span data-ttu-id="7b5e4-106">RID는 *Runtime IDentifier(런타임 식별자)*의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-106">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="7b5e4-107">RID는 응용 프로그램 또는 자산(즉, 어셈블리)이 실행될 대상 운영 체제를 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-107">RIDs are used to identify target operating systems where an application or asset (that is, assembly) will run.</span></span> <span data-ttu-id="7b5e4-108">RID의 예를 들면 "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64"와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-108">They look like this: "ubuntu.14.04-x64", "win7-x64", "osx.10.11-x64".</span></span> <span data-ttu-id="7b5e4-109">기본 종속성이 있는 패키지의 경우 RID는 패키지를 복원할 수 있는 플랫폼을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-109">For the packages with native dependencies, it will designate on which platforms the package can be restored.</span></span> 

<span data-ttu-id="7b5e4-110">RID는 실제로 불투명한 문자열이라는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-110">It is important to note that RIDs are really opaque strings.</span></span> <span data-ttu-id="7b5e4-111">즉, RID는 사용하는 작업에 대해 정확히 일치해야만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-111">This means that they have to match exactly for operations using them to work.</span></span> <span data-ttu-id="7b5e4-112">예를 들어, Ubuntu 14.04의 간단한 복제본인 [Elementary OS](https://elementary.io/)의 경우를 고려해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-112">As an example, let us consider the case of [Elementary OS](https://elementary.io/), which is a straightforward clone of Ubuntu 14.04.</span></span> <span data-ttu-id="7b5e4-113">.NET Core와 CLI는 Ubuntu의 14.04 버전에서 작동하지만, 수정 없이 Elementary OS에서 사용하려고 하면 패키지에 대한 복원 작업이 모두 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-113">Although .NET Core and CLI work on top of that version of Ubuntu, if you try to use them on Elementary OS without any modifications, the restore operation for any package will fail.</span></span> <span data-ttu-id="7b5e4-114">그 이유는 Elementary OS를 플랫폼으로 지정하는 RID가 현재 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-114">This is because we currently don't have a RID that designates Elementary OS as a platform.</span></span> 

<span data-ttu-id="7b5e4-115">구체적인 운영 체제를 나타내는 RID는 일반적으로 `[os].[version]-[arch]`의 패턴을 따릅니다. 각각은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-115">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[arch]` where:</span></span>
- <span data-ttu-id="7b5e4-116">`[os]` - 운영 체제 모니커입니다(예: `ubuntu`).</span><span class="sxs-lookup"><span data-stu-id="7b5e4-116">`[os]` is the operating system moniker, for example, `ubuntu`.</span></span>
- <span data-ttu-id="7b5e4-117">`[version]` - 점(`.`) 형태로 구분된 버전 번호 형식의 운영 체제 버전입니다(예: `15.10`). 자산이 해당 버전으로 표시되는 운영 체제 플랫폼 API를 대상으로 지정하도록 할 만큼 충분히 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-117">`[version]` is the operating system version in the form of a dot (`.`) separated version number, for example, `15.10`, accurate enough to reasonably enable assets to target operating system platform APIs represented by that version.</span></span>
  - <span data-ttu-id="7b5e4-118">이것은 마케팅 버전이어서는 **안 됩니다**. 마케팅 버전은 종종 다양한 플랫폼 API 노출 영역이 있는 운영 체제의 여러 개별 버전을 나타내기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-118">This **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>
- <span data-ttu-id="7b5e4-119">`[arch]` - 프로세서 아키텍처입니다(예: `x86`, `x64`, `arm`, `arm64` 등).</span><span class="sxs-lookup"><span data-stu-id="7b5e4-119">`[arch]` is the processor architecture, for example, `x86`, `x64`, `arm`, `arm64`, etc.</span></span>

<span data-ttu-id="7b5e4-120">RID 그래프는 `runtime.json`라는 파일의 `Microsoft.NETCore.Platforms`라는 패키지에서 정의됩니다. [CoreFX 리포지토리](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json)에서 이를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-120">The RID graph is defined in a package called `Microsoft.NETCore.Platforms` in a file called `runtime.json`, which you can see on the [CoreFX repo](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json).</span></span> <span data-ttu-id="7b5e4-121">이 파일을 사용하는 경우 일부 RID에 `"#import"` 문이 있는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-121">If you use this file, you will notice that some of the RIDs have an `"#import"` statement in them.</span></span> <span data-ttu-id="7b5e4-122">이러한 문은 호환성 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-122">These statements are compatibility statements.</span></span> <span data-ttu-id="7b5e4-123">즉, 가져온 RID를 포함하는 RID는 해당 RID용 패키지 복원을 위한 대상이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-123">That means that a RID that has an imported RID in it can be a target for restoring packages for that RID.</span></span> <span data-ttu-id="7b5e4-124">약간 복잡하지만 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-124">Slightly confusing, but let's look at an example.</span></span> <span data-ttu-id="7b5e4-125">macOS를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-125">Let's take a look at macOS:</span></span>

```json
"osx.10.11-x64": {
    "#import": [ "osx.10.11", "osx.10.10-x64" ]
}
```
<span data-ttu-id="7b5e4-126">위의 RID는 `osx.10.11-x64`가 `osx.10.10-x64`를 가져오도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-126">The above RID specifies that `osx.10.11-x64` imports `osx.10.10-x64`.</span></span> <span data-ttu-id="7b5e4-127">즉, 패키지를 복원할 때 NuGet은 `osx.10.11-x64`에 `osx.10.10-x64`가 필요함을 지정하는 패키지를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-127">This means that when restoring packages, NuGet will be able to restore packages that specify that they need `osx.10.10-x64` on `osx.10.11-x64`.</span></span>

<span data-ttu-id="7b5e4-128">다음은 약간 더 큰 RID 그래프의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-128">A slightly bigger example RID graph:</span></span>  

- `win10-arm`
  - `win10`
  - `win81-arm`
    - `win81`
    - `win8-arm`
      - `win8`
        - `win7`
          - `win`
            - `any`

<span data-ttu-id="7b5e4-129">모든 RID는 결국 루트 `any` RID에 다시 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-129">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="7b5e4-130">비록 사용하기 쉬워 보이지만, RID로 작업할 때 유의해야 할 몇 가지 특별한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-130">Although they look easy enough to use, there are some special things about RIDs that you have to keep in mind when working with them:</span></span>

* <span data-ttu-id="7b5e4-131">RID는 **불투명 문자열**이며 블랙박스로 취급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-131">They are **opaque strings** and should be treated as black boxes</span></span>
    * <span data-ttu-id="7b5e4-132">RID를 프로그래밍 방식으로 구성하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-132">You should not construct RIDs programmatically</span></span>
* <span data-ttu-id="7b5e4-133">플랫폼에 대해 이미 정의되어 있고 이 문서에서 보여준 RID를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-133">You need to use the RIDs that are already defined for the platform and this document shows that</span></span>
* <span data-ttu-id="7b5e4-134">RID는 구체적이어야 하므로 실제 RID 값에서 어떤 것도 가정해서는 안 됩니다. 특정 플랫폼에 어떤 RID가 필요한지를 확인하려면 이 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-134">The RIDs do need to be specific so don't assume anything from the actual RID value; please consult this document to determine which RID(s) you need for a given platform</span></span>

## <a name="using-rids"></a><span data-ttu-id="7b5e4-135">RID 사용</span><span class="sxs-lookup"><span data-stu-id="7b5e4-135">Using RIDs</span></span>
<span data-ttu-id="7b5e4-136">RID를 사용하려면 어떤 RID가 있는지를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-136">In order to use RIDs, you have to know which RIDs there are.</span></span> <span data-ttu-id="7b5e4-137">새 RID가 정기적으로 플랫폼에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-137">New RIDs are added regularly to the platform.</span></span> <span data-ttu-id="7b5e4-138">최신 버전을 보려면 CoreFX 리포지토리에서 [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-138">For the latest version, please check the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

> [!NOTE]
> <span data-ttu-id="7b5e4-139">이 정보를 좀 더 대화형 방식으로 얻을 수 있도록 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-139">We are working towards getting this information into a more interactive form.</span></span> <span data-ttu-id="7b5e4-140">그렇게 되면 이 페이지도 해당 도구 및/또는 사용 방법 문서를 안내하도록 업데이트될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b5e4-140">When that happens, this page will be updated to point to that tool and/or its usage documentation.</span></span> 

## <a name="windows-rids"></a><span data-ttu-id="7b5e4-141">Windows RID</span><span class="sxs-lookup"><span data-stu-id="7b5e4-141">Windows RIDs</span></span>

* <span data-ttu-id="7b5e4-142">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7b5e4-142">Windows 7 / Windows Server 2008 R2</span></span>
    * `win7-x64`
    * `win7-x86`
* <span data-ttu-id="7b5e4-143">Windows 8 / Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="7b5e4-143">Windows 8 / Windows Server 2012</span></span>
    * `win8-x64`
    * `win8-x86`
    * `win8-arm`
* <span data-ttu-id="7b5e4-144">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="7b5e4-144">Windows 8.1 / Windows Server 2012 R2</span></span>
    * `win81-x64`
    * `win81-x86`
    * `win81-arm`
* <span data-ttu-id="7b5e4-145">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="7b5e4-145">Windows 10 / Windows Server 2016</span></span>
    * `win10-x64`
    * `win10-x86`
    * `win10-arm`
    * `win10-arm64`

## <a name="linux-rids"></a><span data-ttu-id="7b5e4-146">Linux RID</span><span class="sxs-lookup"><span data-stu-id="7b5e4-146">Linux RIDs</span></span>

* <span data-ttu-id="7b5e4-147">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="7b5e4-147">Red Hat Enterprise Linux</span></span>
    * `rhel.7-x64`
* <span data-ttu-id="7b5e4-148">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7b5e4-148">Ubuntu</span></span>
    * `ubuntu.14.04-x64`
    * `ubuntu.14.10-x64`
    * `ubuntu.15.04-x64`
    * `ubuntu.15.10-x64`
    * `ubuntu.16.04-x64`
    * `ubuntu.16.10-x64`
* <span data-ttu-id="7b5e4-149">CentOS</span><span class="sxs-lookup"><span data-stu-id="7b5e4-149">CentOS</span></span>
    * `centos.7-x64`
* <span data-ttu-id="7b5e4-150">Debian</span><span class="sxs-lookup"><span data-stu-id="7b5e4-150">Debian</span></span>
    * `debian.8-x64`
* <span data-ttu-id="7b5e4-151">Fedora</span><span class="sxs-lookup"><span data-stu-id="7b5e4-151">Fedora</span></span>
    * `fedora.23-x64`
    * `fedora.24-x64`
* <span data-ttu-id="7b5e4-152">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="7b5e4-152">OpenSUSE</span></span>
    * `opensuse.13.2-x64`
    * `opensuse.42.1-x64`
* <span data-ttu-id="7b5e4-153">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="7b5e4-153">Oracle Linux</span></span>
    * `ol.7-x64`
    * `ol.7.0-x64`
    * `ol.7.1-x64`
    * `ol.7.2-x64`
* <span data-ttu-id="7b5e4-154">현재 지원되는 Ubuntu 파생 버전</span><span class="sxs-lookup"><span data-stu-id="7b5e4-154">Currently supported Ubuntu derivatives</span></span> 
    * `linuxmint.17-x64`
    * `linuxmint.17.1-x64`
    * `linuxmint.17.2-x64`
    * `linuxmint.17.3-x64`
    * `linuxmint.18-x64`

## <a name="os-x-rids"></a><span data-ttu-id="7b5e4-155">OS X RID</span><span class="sxs-lookup"><span data-stu-id="7b5e4-155">OS X RIDs</span></span>

* `osx.10.10-x64`
* `osx.10.11-x64`
* `osx.10.12-x64`

