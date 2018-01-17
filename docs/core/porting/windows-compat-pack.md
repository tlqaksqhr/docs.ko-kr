---
title: ".NET Core로 이식 - Windows 호환 기능 팩 사용"
description: "Windows 호환 기능 팩 및 이를 사용하여 기존 .NET Framework 코드를 .NET Core로 이식하는 방법에 대해 알아보기"
keywords: ".NET, .NET Core, Windows, 호환성"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 3b1fe02aad4f78499158ecb7fa9b8521cb7d992e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="852d8-104">Windows 호환 기능 팩 사용</span><span class="sxs-lookup"><span data-stu-id="852d8-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="852d8-105">개발자가 기존 코드를 .NET Core에 이식할 때 직면하는 가장 일반적인 문제 중 하나는 API 및 .NET Framework에만 존재하는 기술에 의존하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="852d8-106">*Windows 호환 기능 팩*은 .NET Core 응용 프로그램 뿐만 아니라 .NET Standard 라이브러리를 빌드하는 것이 기존 코드에 더욱 실행 가능할 수 있도록 이러한 많은 기술을 제공하는 것에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="852d8-107">이 패키지는 수정 없이 API 집합 및 기존 코드 컴파일을 크게 증가시키는 논리적 [.NET Standard 2.0의 확장](../whats-new/index.md#api-changes-and-library-support)입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="852d8-108">그러나 .NET Standard에 대한 약속을 지키기 위해("모든 .NET 구현이 제공하는 API의 집합") 레지스트리, WMI(Windows Management Instrumentation) 또는 리플렉션 내보내기 API와 같은 모든 플랫폼에서 작동할 수 없는 기술을 포함하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="852d8-109">*Windows 호환 기능 팩*은 .NET Standard의 위에 있으며 Windows에만 해당하는 기술에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="852d8-110">.NET Core로 이동하려고 하지만 첫 번째 단계로 Windows에 머물려는 고객에게 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="852d8-111">해당 시나리오에서 Windows 전용 기술을 사용할 수 없는 것은 아키텍처 이점이 없는 마이그레이션 장애물일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="852d8-112">패키지 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="852d8-112">Package contents</span></span>

<span data-ttu-id="852d8-113">*Windows 호환 기능 팩*은 NuGet 패키지 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)를 통해 제공되며 .NET Core 또는 .NET Standard를 대상으로 하는 프로젝트에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="852d8-114">Windows 전용을 포함하는 약 20,000 개의 API와 다음과 같은 기술 영역에서 플랫폼 간 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="852d8-115">코드 페이지</span><span class="sxs-lookup"><span data-stu-id="852d8-115">Code Pages</span></span>
* <span data-ttu-id="852d8-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="852d8-116">CodeDom</span></span>
* <span data-ttu-id="852d8-117">구성</span><span class="sxs-lookup"><span data-stu-id="852d8-117">Configuration</span></span>
* <span data-ttu-id="852d8-118">디렉터리 서비스</span><span class="sxs-lookup"><span data-stu-id="852d8-118">Directory Services</span></span>
* <span data-ttu-id="852d8-119">그리기</span><span class="sxs-lookup"><span data-stu-id="852d8-119">Drawing</span></span>
* <span data-ttu-id="852d8-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="852d8-120">ODBC</span></span>
* <span data-ttu-id="852d8-121">사용 권한</span><span class="sxs-lookup"><span data-stu-id="852d8-121">Permissions</span></span>
* <span data-ttu-id="852d8-122">포트</span><span class="sxs-lookup"><span data-stu-id="852d8-122">Ports</span></span>
* <span data-ttu-id="852d8-123">Windows ACL(액세스 제어 목록)</span><span class="sxs-lookup"><span data-stu-id="852d8-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="852d8-124">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="852d8-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="852d8-125">Windows Cryptography</span><span class="sxs-lookup"><span data-stu-id="852d8-125">Windows Cryptography</span></span>
* <span data-ttu-id="852d8-126">Windows EventLog</span><span class="sxs-lookup"><span data-stu-id="852d8-126">Windows EventLog</span></span>
* <span data-ttu-id="852d8-127">WMI(Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="852d8-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="852d8-128">Windows 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="852d8-128">Windows Performance Counters</span></span>
* <span data-ttu-id="852d8-129">Windows 레지스트리</span><span class="sxs-lookup"><span data-stu-id="852d8-129">Windows Registry</span></span>
* <span data-ttu-id="852d8-130">Windows 런타임 캐싱</span><span class="sxs-lookup"><span data-stu-id="852d8-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="852d8-131">Windows 서비스</span><span class="sxs-lookup"><span data-stu-id="852d8-131">Windows Services</span></span>

<span data-ttu-id="852d8-132">자세한 내용은 [호환 기능 팩의 사양](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="852d8-133">시작</span><span class="sxs-lookup"><span data-stu-id="852d8-133">Get started</span></span>

1. <span data-ttu-id="852d8-134">이식하기 전에 [이식 프로세스](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="852d8-135">기존 코드를 .NET Core 또는 .NET Standard로 이식하는 경우 NuGet 패키지 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="852d8-136">Windows에서 유지하려는 경우 모두 준비되었습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="852d8-137">Linux 또는 macOS에서 .NET Core 응용 프로그램 또는 .NET Standard 라이브러리를 실행하려는 경우 [API 분석기](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/)를 사용하여 플랫폼 간에 작동하지 않는 API의 사용량을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="852d8-138">이러한 API의 사용량을 제거하거나 플랫폼 간 대체 방법으로 바꾸거나 다음과 같은 플랫폼 검사를 사용하여 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="852d8-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

    ```csharp
    private static string GetLoggingPath()
    {
        // Verify the code is running on Windows.
        if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
        {
            using (var key = Registry.CurrentUser.OpenSubKey(@"Software\Fabrikam\AssetManagement"))
            {
                if (key?.GetValue("LoggingDirectoryPath") is string configuredPath)
                    return configuredPath;
            }
        }

        // This is either not running on Windows or no logging path was configured,
        // so just use the path for non-roaming user-specific data files.
        var appDataPath = Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData);
        return Path.Combine(appDataPath, "Fabrikam", "AssetManagement", "Logging");
    }
    ```

<span data-ttu-id="852d8-139">데모의 경우 [Windows 호환 기능 팩의 Channel 9 비디오](https://channel9.msdn.com/Events/Connect/2017/T123)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="852d8-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

