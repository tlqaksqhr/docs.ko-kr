---
title: "Windows 호환 기능 팩을 사용 하 여-.NET Core로 이식"
description: "Windows 호환 기능 팩에 대 한 자세한 내용은 수 사용법.NET Core를 기존.NET Framework 코드를 이식 하 고"
keywords: ".NET,.NET core, Windows, 호환성"
author: terrajobst
ms.author: mairaw
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 5094baee77aba4d1e148f807d842a4a2d3405cf7
ms.sourcegitcommit: 86cf9b4c7104485a9870645705b9a1a4b6ca8e2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2017
---
# <a name="using-the-windows-compatibility-pack"></a><span data-ttu-id="6217e-104">Windows 호환 기능 팩을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="6217e-104">Using the Windows Compatibility Pack</span></span>

<span data-ttu-id="6217e-105">.NET Core는 기존 코드를 이식할 때 개발자가 직면 하는 가장 일반적인 문제 중 하나는 Api 및.NET Framework에만 존재 하는 기술에 종속 되입니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-105">One of the most common issues that developers face when porting their existing code to .NET Core is that they depend on APIs and technologies that only exist in the .NET Framework.</span></span> <span data-ttu-id="6217e-106">*Windows 호환 기능 팩* 되도록.NET Core 응용 프로그램 뿐만 아니라.NET 표준 라이브러리를 작성 합니다. 기존 코드에 대 한 실행 가능한 훨씬 더 다양 한 이러한 기술을 제공 하 려 합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-106">The *Windows Compatibility Pack* is about providing many of these technologies so that building .NET Core applications as well as .NET Standard libraries becomes much more viable for existing code.</span></span>

<span data-ttu-id="6217e-107">이 패키지는 논리적 [표준.NET 2.0의 확장](../whats-new/index.md#api-changes-and-library-support) 크게 증가 API 집합 및 기존 코드가 컴파일되는지 수정이 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-107">This package is a logical [extension of .NET Standard 2.0](../whats-new/index.md#api-changes-and-library-support) that significantly increases API set and existing code compiles with almost no modifications.</span></span> <span data-ttu-id="6217e-108">하지만 표준.NET에 대 한 약속을 유지 하기 위해 ("이는 모든.NET 구현이 제공 하는 Api 집합"), Windows Management Instrumentation (WMI), 레지스트리 등 모든 플랫폼에서 작동 하지 않을 기술이 포함 되어 있지이 또는 리플렉션 내보내기 Api입니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-108">But in order to keep the promise of .NET Standard ("it is the set of APIs that all .NET implementations provide"), this didn't include technologies that can't work across all platforms, such as registry, Windows Management Instrumentation (WMI), or reflection emit APIs.</span></span>

<span data-ttu-id="6217e-109">*Windows 호환 기능 팩* .NET 표준 위에 배치 하 고만 Windows 있는 기술에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-109">The *Windows Compatibility Pack* sits on top of .NET Standard and provides access to technologies that are Windows only.</span></span> <span data-ttu-id="6217e-110">.NET Core 하지만 첫 번째 단계는 Windows에 머물도록 하는 계획으로 이동 하려는 고객에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-110">It's especially useful for customers that want to move to .NET Core but plan to stay on Windows as a first step.</span></span> <span data-ttu-id="6217e-111">이 시나리오에서는 Windows 전용 기술을 사용할 수 없는 경우 0 아키텍처 이점을 마이그레이션 장애물만</span><span class="sxs-lookup"><span data-stu-id="6217e-111">In that scenario, not being able to use Windows-only technologies is only a migration hurdle with zero architectural benefits.</span></span>

## <a name="package-contents"></a><span data-ttu-id="6217e-112">패키지 내용</span><span class="sxs-lookup"><span data-stu-id="6217e-112">Package contents</span></span>

<span data-ttu-id="6217e-113">*Windows 호환 기능 팩* NuGet 패키지를 통해 제공 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) .NET Core 또는 표준.NET을 대상으로 하는 프로젝트에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-113">The *Windows Compatibility Pack* is provided via the NuGet Package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) and can be referenced from projects targeting .NET Core or .NET Standard.</span></span>

<span data-ttu-id="6217e-114">약 20, 000 제공 Api를 다음과 같은 기술 영역에서 Windows 전용으로 플랫폼 간 Api를 포함 하 여:</span><span class="sxs-lookup"><span data-stu-id="6217e-114">It provides about 20,000 APIs, including Windows-only as well as cross-platform APIs from the following technology areas:</span></span>

* <span data-ttu-id="6217e-115">코드 페이지</span><span class="sxs-lookup"><span data-stu-id="6217e-115">Code Pages</span></span>
* <span data-ttu-id="6217e-116">CodeDom</span><span class="sxs-lookup"><span data-stu-id="6217e-116">CodeDom</span></span>
* <span data-ttu-id="6217e-117">구성</span><span class="sxs-lookup"><span data-stu-id="6217e-117">Configuration</span></span>
* <span data-ttu-id="6217e-118">디렉터리 서비스</span><span class="sxs-lookup"><span data-stu-id="6217e-118">Directory Services</span></span>
* <span data-ttu-id="6217e-119">그리기</span><span class="sxs-lookup"><span data-stu-id="6217e-119">Drawing</span></span>
* <span data-ttu-id="6217e-120">ODBC</span><span class="sxs-lookup"><span data-stu-id="6217e-120">ODBC</span></span>
* <span data-ttu-id="6217e-121">사용 권한</span><span class="sxs-lookup"><span data-stu-id="6217e-121">Permissions</span></span>
* <span data-ttu-id="6217e-122">포트</span><span class="sxs-lookup"><span data-stu-id="6217e-122">Ports</span></span>
* <span data-ttu-id="6217e-123">Windows 액세스 제어 목록 (ACL)</span><span class="sxs-lookup"><span data-stu-id="6217e-123">Windows Access Control Lists (ACL)</span></span>
* <span data-ttu-id="6217e-124">WCF(Windows Communication Foundation)</span><span class="sxs-lookup"><span data-stu-id="6217e-124">Windows Communication Foundation (WCF)</span></span>
* <span data-ttu-id="6217e-125">Windows 암호화</span><span class="sxs-lookup"><span data-stu-id="6217e-125">Windows Cryptography</span></span>
* <span data-ttu-id="6217e-126">Windows 이벤트 로그</span><span class="sxs-lookup"><span data-stu-id="6217e-126">Windows EventLog</span></span>
* <span data-ttu-id="6217e-127">WMI(Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="6217e-127">Windows Management Instrumentation (WMI)</span></span>
* <span data-ttu-id="6217e-128">Windows 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="6217e-128">Windows Performance Counters</span></span>
* <span data-ttu-id="6217e-129">Windows 레지스트리</span><span class="sxs-lookup"><span data-stu-id="6217e-129">Windows Registry</span></span>
* <span data-ttu-id="6217e-130">Windows 런타임 캐싱</span><span class="sxs-lookup"><span data-stu-id="6217e-130">Windows Runtime Caching</span></span>
* <span data-ttu-id="6217e-131">Windows 서비스</span><span class="sxs-lookup"><span data-stu-id="6217e-131">Windows Services</span></span>

<span data-ttu-id="6217e-132">자세한 내용은 참조는 [호환 기능 팩의 사양](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-132">For more information, see the [spec of the compatibility pack](https://github.com/dotnet/designs/blob/master/accepted/compat-pack/compat-pack.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="6217e-133">시작</span><span class="sxs-lookup"><span data-stu-id="6217e-133">Get started</span></span>

1. <span data-ttu-id="6217e-134">이식 하기 전에 확인을 참조 하는 [포팅 프로세스](index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-134">Before porting, make sure to take a look at the [Porting Process](index.md).</span></span>

2. <span data-ttu-id="6217e-135">.NET Core 또는.NET 표준 기존 코드를 이식 하는 경우에 NuGet 패키지 설치 [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility)합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-135">When porting existing code to .NET Core or .NET Standard, install the NuGet package [Microsoft.Windows.Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility).</span></span>

3. <span data-ttu-id="6217e-136">Windows에서 유지 하려는 경우 모든 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-136">If you want to stay on Windows, you're all set.</span></span>

4. <span data-ttu-id="6217e-137">사용 하 여 Linux 또는 macOS에서.NET Core 응용 프로그램 또는 표준.NET 라이브러리를 실행 하려는 경우는 [API 분석기](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) 찾을 플랫폼 간에 작동 하지 않는 Api 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-137">If you want to run the .NET Core application or .NET Standard library on Linux or macOS, use the [API Analyzer](https://blogs.msdn.microsoft.com/dotnet/2017/10/31/introducing-api-analyzer/) to find usage of APIs that won't work cross-platform.</span></span>

5. <span data-ttu-id="6217e-138">이러한 Api의 사용을 제거, 플랫폼 간 대체 방법으로 바꾸려면 또는 같은 플랫폼 검사를 사용 하 여 보호:</span><span class="sxs-lookup"><span data-stu-id="6217e-138">Either remove the usages of those APIs, replace them with cross-platform alternatives, or guard them using a platform check, like:</span></span>

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

<span data-ttu-id="6217e-139">데모는 체크 아웃 된 [Windows 호환 기능 팩의 Channel 9 비디오](https://channel9.msdn.com/Events/Connect/2017/T123)합니다.</span><span class="sxs-lookup"><span data-stu-id="6217e-139">For a demo, check out the [Channel 9 video of the Windows Compatibility Pack](https://channel9.msdn.com/Events/Connect/2017/T123).</span></span>

