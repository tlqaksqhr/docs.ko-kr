---
title: .NET Framework의 응용 프로그램 호환성
ms.date: 05/19/2017
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b75429d0de69c60e7c24551bf1d9218e74d0c5ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="application-compatibility-in-the-net-framework"></a><span data-ttu-id="b1d2e-102">.NET Framework의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="b1d2e-102">Application Compatibility in the .NET Framework</span></span>

## <a name="introduction"></a><span data-ttu-id="b1d2e-103">소개</span><span class="sxs-lookup"><span data-stu-id="b1d2e-103">Introduction</span></span>
<span data-ttu-id="b1d2e-104">호환성은 각 .NET 릴리스의 매우 중요한 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-104">Compatibility is a very important goal of each .NET release.</span></span> <span data-ttu-id="b1d2e-105">호환성이 있으면 각 버전이 누적되므로 이전 버전이 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-105">Compatibility ensures that each version is additive, so previous versions will still work.</span></span> <span data-ttu-id="b1d2e-106">반면, 성능 향상, 보안 문제 해결 또는 버그 수정을 위해 이전 기능이 변경되면 이후 버전에서 실행되는 기존 코드 또는 기존 응용 프로그램에서 호환성 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-106">On the other hand, changes to previous functionality (to improve performance, address security issues, or fix bugs) can cause compatibility problems in existing code or existing applications that run under a later version.</span></span> <span data-ttu-id="b1d2e-107">.NET Framework는 대상 다시 지정 변경 내용 및 런타임 변경 내용을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-107">The .NET Framework recognizes retargeting changes and runtime changes.</span></span> <span data-ttu-id="b1d2e-108">대상 다시 지정 변경 내용은 .NET Framework의 특정 버전을 대상으로 지정하지만 이후 버전에서 실행되는 응용 프로그램에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-108">Retargeting changes affect applications that target a specific version of the .NET Framework but are running on a later version.</span></span> <span data-ttu-id="b1d2e-109">런타임 변경 내용은 특정 버전에서 실행되는 모든 응용 프로그램에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-109">Runtime changes affect all applications running on a particular version.</span></span>

<span data-ttu-id="b1d2e-110">각 앱은 .NET Framework의 특정 버전을 대상으로 하며, 다음을 통해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-110">Each app targets a specific version of the .NET Framework, which can be specified by:</span></span>

* <span data-ttu-id="b1d2e-111">Visual Studio에서 대상 프레임워크 정의</span><span class="sxs-lookup"><span data-stu-id="b1d2e-111">Defining a target framework in Visual Studio.</span></span>
* <span data-ttu-id="b1d2e-112">프로젝트 파일에서 대상 프레임워크 지정</span><span class="sxs-lookup"><span data-stu-id="b1d2e-112">Specifying the target framework in a project file.</span></span>
* <span data-ttu-id="b1d2e-113">소스 코드에 <xref:System.Runtime.Versioning.TargetFrameworkAttribute> 적용</span><span class="sxs-lookup"><span data-stu-id="b1d2e-113">Applying a <xref:System.Runtime.Versioning.TargetFrameworkAttribute> to the source code.</span></span>

<span data-ttu-id="b1d2e-114">대상으로 지정된 버전보다 더 새로운 버전에서 실행될 경우 .NET Framework는 특수 동작을 사용하여 대상으로 지정된 이전 버전을 모방합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-114">When running on a newer version than what was targeted, the .NET Framework will use quirked behavior to mimic the older targeted version.</span></span> <span data-ttu-id="b1d2e-115">즉, 앱은 Framework의 더 새로운 버전에서 실행되지만 이전 버전에서 실행되는 것처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-115">In other words, the app will run on the newer version of the Framework, but act as if it's running on the older version.</span></span> <span data-ttu-id="b1d2e-116">.NET Framework 버전 간의 대부분의 호환성 문제는 이 특수 모델을 통해 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-116">Many of the compatibility issues between versions of the .NET Framework are mitigated through this quirking model.</span></span>

## <a name="runtime-changes"></a><span data-ttu-id="b1d2e-117">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="b1d2e-117">Runtime changes</span></span>

<span data-ttu-id="b1d2e-118">런타임 문제는 새 런타임이 컴퓨터에서 발생하고 같은 이진 파일이 실행되지만 다른 동작이 확인될 경우 발생하는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-118">Runtime issues are those that arise when a new runtime is placed on a machine and the same binaries are run, but different behavior is seen.</span></span> <span data-ttu-id="b1d2e-119">.NET Framework 4.0용으로 컴파일된 이진 파일은 4.5 이상 버전의 .NET Framework 4.0 호환성 모드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-119">If a binary was compiled for .NET Framework 4.0 it will run in .NET Framework 4.0 compatibility mode on 4.5 or later versions.</span></span> <span data-ttu-id="b1d2e-120">4.5에 영향을 미치는 대부분의 변경 내용은 4.0용으로 컴파일된 이진 파일에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-120">Many of the changes that affect 4.5 will not affect a binary compiled for 4.0.</span></span> <span data-ttu-id="b1d2e-121">이 내용은 AppDomain에만 적용되고 항목 어셈블리의 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-121">This is specific to the AppDomain and depends on the settings of the entry assembly.</span></span>

## <a name="retargeting-changes"></a><span data-ttu-id="b1d2e-122">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="b1d2e-122">Retargeting changes</span></span>

<span data-ttu-id="b1d2e-123">대상 다시 지정 문제는 4.0을 대상으로 하는 어셈블리가 4.5를 대상으로 지정하도록 설정된 경우 발생하는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-123">Retargeting issues are those that arise when an assembly that was targeting 4.0 is now set to target 4.5.</span></span> <span data-ttu-id="b1d2e-124">이제 어셈블리는 이전 기능에 대한 잠재적인 호환성 문제뿐 아니라 새로운 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-124">Now the assembly opts into the new features as well as potential compatibility issues to old features.</span></span> <span data-ttu-id="b1d2e-125">또한 이것은 어셈블리를 사용하는 콘솔 앱 또는 어셈블리를 참조하는 웹 사이트와 같은 항목 어셈블리에 의해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-125">Again, this is dictated by the entry assembly, so the console app that uses the assembly, or the website that references the assembly.</span></span>

## <a name="net-compatibility-diagnostics"></a><span data-ttu-id="b1d2e-126">.NET 호환성 진단</span><span class="sxs-lookup"><span data-stu-id="b1d2e-126">.NET Compatibility Diagnostics</span></span>

<span data-ttu-id="b1d2e-127">.NET 호환성 진단은 .NET Framework 버전 간에 응용 프로그램 호환성 문제를 식별할 수 있도록 하는 Roslyn 기반 분석기입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-127">The .NET Compatibility Diagnostics are Roslyn-powered analyzers that help identify application compatibility issues between versions of the .NET Framework.</span></span> <span data-ttu-id="b1d2e-128">이 목록은 사용할 수 있는 모든 분석기를 포함하지만, 한 하위 집합은 특정 마이그레이션에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-128">This list contains all of the analyzers available, although only a subset will apply to any specific migration.</span></span> <span data-ttu-id="b1d2e-129">분석기는 예정된 마이그레이션에 적용되는 문제를 확인하고 해당 문제만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-129">The analyzers will determine which issues are applicable for the planned migration and will only surface those.</span></span>

<span data-ttu-id="b1d2e-130">각 문제는 다음과 같은 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-130">Each issue includes the following information:</span></span>

-   <span data-ttu-id="b1d2e-131">이전 버전에서 변경된 내용에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-131">The description of what has changed from a previous version.</span></span>

-   <span data-ttu-id="b1d2e-132">변경 내용이 고객에 미치는 영향 및 버전 간 호환성을 유지하기 위한 사용할 수 있는 해결 방법의 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-132">How the change affects customers and whether any workarounds are available to preserve compatibility across versions.</span></span>

-   <span data-ttu-id="b1d2e-133">변경 내용의 중요성에 대한 평가입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-133">An assessment of how important the change is.</span></span> <span data-ttu-id="b1d2e-134">응용 프로그램 호환성 문제는 다음과 같이 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-134">Application compatibility issue are categorized as follows:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="b1d2e-135">주요함</span><span class="sxs-lookup"><span data-stu-id="b1d2e-135">Major</span></span>|<span data-ttu-id="b1d2e-136">다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-136">A significant change that affects a large number of apps or requires substantial modification of code.</span></span>|
    |<span data-ttu-id="b1d2e-137">부</span><span class="sxs-lookup"><span data-stu-id="b1d2e-137">Minor</span></span>|<span data-ttu-id="b1d2e-138">소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-138">A change that affects a small number of apps or that requires minor modification of code.</span></span>|
    |<span data-ttu-id="b1d2e-139">특별한 경우</span><span class="sxs-lookup"><span data-stu-id="b1d2e-139">Edge case</span></span>|<span data-ttu-id="b1d2e-140">매우 특별하고 일반적이지 않은 시나리오의 앱에 영향을 주는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-140">A change that affects apps under very specific, uncommon scenarios.</span></span>|
    |<span data-ttu-id="b1d2e-141">투명</span><span class="sxs-lookup"><span data-stu-id="b1d2e-141">Transparent</span></span>|<span data-ttu-id="b1d2e-142">응용 프로그램 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-142">A change with no noticeable effect on the application's developer or user.</span></span>|

-   <span data-ttu-id="b1d2e-143">버전은 변경 내용이 프레임워크에 처음 표시될 때를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-143">Version indicates when the change first appears in the framework.</span></span> <span data-ttu-id="b1d2e-144">일부 변경 내용이 특정 버전에 소개되고 이후 버전에서 되돌려지면 되돌려진 내용도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-144">Some of the changes are introduced in a particular version and reverted in a later version; that is indicated as well.</span></span>

-   <span data-ttu-id="b1d2e-145">변경 형식:</span><span class="sxs-lookup"><span data-stu-id="b1d2e-145">The type of change:</span></span>

    |   |   |
    |---|---|
    |<span data-ttu-id="b1d2e-146">대상 변경</span><span class="sxs-lookup"><span data-stu-id="b1d2e-146">Retargeting</span></span>|<span data-ttu-id="b1d2e-147">새 버전의 .NET Framework를 대상으로 다시 컴파일되는 앱에 변경 내용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-147">The change affects apps that are recompiled to target a new version of the .NET Framework.</span></span>|
    |<span data-ttu-id="b1d2e-148">런타임</span><span class="sxs-lookup"><span data-stu-id="b1d2e-148">Runtime</span></span>|<span data-ttu-id="b1d2e-149">이전 버전의 .NET Framework를 대상으로 하지만 이후 버전에서 실행되는 기존 앱에 변경 내용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-149">The change affects an existing app that targets a previous version of the .NET Framework but runs on a later version.</span></span>|

-   <span data-ttu-id="b1d2e-150">영향을 받는 API입니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="b1d2e-150">The affected APIS, if any.</span></span>

-   <span data-ttu-id="b1d2e-151">사용 가능한 진단의 ID</span><span class="sxs-lookup"><span data-stu-id="b1d2e-151">The IDs of the available diagnostics</span></span>

## <a name="usage"></a><span data-ttu-id="b1d2e-152">사용법</span><span class="sxs-lookup"><span data-stu-id="b1d2e-152">Usage</span></span>
<span data-ttu-id="b1d2e-153">시작하려면 아래에서 호환성 변경 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1d2e-153">To begin, select the type of compatibility change below:</span></span>

* [<span data-ttu-id="b1d2e-154">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="b1d2e-154">Retargeting Changes</span></span>](./retargeting/index.md)
* [<span data-ttu-id="b1d2e-155">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="b1d2e-155">Runtime Changes</span></span>](./runtime/index.md)


## <a name="see-also"></a><span data-ttu-id="b1d2e-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1d2e-156">See Also</span></span>

* [<span data-ttu-id="b1d2e-157">버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="b1d2e-157">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
* [<span data-ttu-id="b1d2e-158">새로운 기능</span><span class="sxs-lookup"><span data-stu-id="b1d2e-158">What's New</span></span>](../../../docs/framework/whats-new/index.md)
* [<span data-ttu-id="b1d2e-159">클래스 라이브러리의 사용되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="b1d2e-159">What's Obsolete in the Class Library</span></span>](../../../docs/framework/whats-new/whats-obsolete.md)
