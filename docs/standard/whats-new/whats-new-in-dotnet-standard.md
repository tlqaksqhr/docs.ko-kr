---
title: .NET Standard의 새로운 기능
description: 이 문서에는 .NET Standard의 각 새 버전에 있는 새로운 기능과 향상된 기능이 요약되어 있습니다.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e422e6ff65439d105020a6305b66a8192586a8f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33591491"
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="6637b-103">.NET Standard의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6637b-103">What's new in the .NET Standard</span></span>

<span data-ttu-id="6637b-104">.NET Standard는 해당 버전의 표준에 부합하는 .NET 구현에서 사용할 수 있어야 하는 버전이 지정된 API 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-104">The .NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="6637b-105">.NET 표준은 라이브러리 개발자에서 대상으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-105">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="6637b-106">.NET Standard 버전을 대상으로 하는 라이브러리는 Standard의 해당 버전을 지원하는 모든 .NET Framework, .NET Core 또는 Xamarin 구현에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="6637b-107">.NET Standard의 최신 버전은 2.0입니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-107">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="6637b-108">이 버전은 .NET Core 워크로드가 설치된 Visual Studio 2017 버전 15.3은 물론 .NET Core 2.0 SDK에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-108">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="6637b-109">지원되는 .NET 구현</span><span class="sxs-lookup"><span data-stu-id="6637b-109">Supported .NET implementations</span></span>

<span data-ttu-id="6637b-110">.NET Standard 2.0은 다음 .NET 구현에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-110">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="6637b-111">.NET Core 2.0 이상</span><span class="sxs-lookup"><span data-stu-id="6637b-111">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="6637b-112">.NET Framework 4.6.1 이상</span><span class="sxs-lookup"><span data-stu-id="6637b-112">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="6637b-113">Mono 5.4 이상</span><span class="sxs-lookup"><span data-stu-id="6637b-113">Mono 5.4 or later</span></span>
- <span data-ttu-id="6637b-114">Xamarin.iOS 10.14 이상</span><span class="sxs-lookup"><span data-stu-id="6637b-114">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="6637b-115">Xamarin.Mac 3.8 이상</span><span class="sxs-lookup"><span data-stu-id="6637b-115">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="6637b-116">Xamarin.Android 8.0 이상</span><span class="sxs-lookup"><span data-stu-id="6637b-116">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="6637b-117">유니버설 Windows 플랫폼 10.0.16299 이상</span><span class="sxs-lookup"><span data-stu-id="6637b-117">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="6637b-118">.NET Standard 2.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="6637b-118">What's new in the .NET Standard 2.0</span></span>

<span data-ttu-id="6637b-119">.NET Standard 2.0에는 다음과 같은 새로운 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-119">The .NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="6637b-120">매우 폭넓은 API 집합</span><span class="sxs-lookup"><span data-stu-id="6637b-120">A vastly expanded set of APIs</span></span>

<span data-ttu-id="6637b-121">버전 1.6을 통해 .NET Standard에는 비교적 작은 API 하위 집합이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-121">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="6637b-122">이들 중 .NET Framework 또는 Xamarin에서 일반적으로 사용된 많은 API가 제외되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-122">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="6637b-123">이로 인해 개발이 복잡해집니다. 개발자들이 여러 .NET 구현을 대상으로 하는 응용 프로그램과 라이브러리를 개발할 때 친숙한 API에 대한 적합한 대체 API를 찾아야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-123">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="6637b-124">.NET Standard 2.0은 이전 Standard 버전인 .NET Standard 1.6에서 제공된 것보다 20,000개 더 많은 API를 추가하여 이 제한 사항을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-124">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="6637b-125">.NET Standard 2.0에 추가된 API의 목록은 [.NET Standard 2.0 및 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6637b-125">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="6637b-126">.NET Standard 2.0에서 <xref:System> 네임스페이스에 대한 일부 추가 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-126">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="6637b-127"><xref:System.AppDomain> 클래스에 대한 지원.</span><span class="sxs-lookup"><span data-stu-id="6637b-127">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="6637b-128"><xref:System.Array> 클래스에 있는 추가 멤버의 배열을 사용하기 위한 향상된 지원.</span><span class="sxs-lookup"><span data-stu-id="6637b-128">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="6637b-129"><xref:System.Attribute> 클래스에 있는 추가 멤버의 속성을 사용하기 위한 향상된 지원.</span><span class="sxs-lookup"><span data-stu-id="6637b-129">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="6637b-130"><xref:System.DateTime> 값에 대한 향상된 달력 지원 및 추가 서식 옵션.</span><span class="sxs-lookup"><span data-stu-id="6637b-130">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="6637b-131">추가 <xref:System.Decimal> 반올림 기능.</span><span class="sxs-lookup"><span data-stu-id="6637b-131">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="6637b-132"><xref:System.Environment> 클래스의 추가 기능.</span><span class="sxs-lookup"><span data-stu-id="6637b-132">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="6637b-133"><xref:System.GC> 클래스를 통해 가비지 수집기 제어 강화.</span><span class="sxs-lookup"><span data-stu-id="6637b-133">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="6637b-134"><xref:System.String> 클래스의 문자열 비교, 열거 및 정규화를 위한 향상된 지원.</span><span class="sxs-lookup"><span data-stu-id="6637b-134">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="6637b-135"><xref:System.TimeZoneInfo.AdjustmentRule> 및 <xref:System.TimeZoneInfo.TransitionTime> 클래스의 일광 절약 조정 및 전환 시간에 대한 지원.</span><span class="sxs-lookup"><span data-stu-id="6637b-135">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="6637b-136"><xref:System.Type> 클래스의 크게 향상된 기능.</span><span class="sxs-lookup"><span data-stu-id="6637b-136">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="6637b-137"><xref:System.Runtime.Serialization.SerializationInfo> 및 <xref:System.Runtime.Serialization.StreamingContext> 매개 변수를 통해 예외 생성자를 추가하여 예외 개체를 deserialize하는 기능에 대한 향상된 지원.</span><span class="sxs-lookup"><span data-stu-id="6637b-137">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="6637b-138">.NET Framework 라이브러리에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="6637b-138">Support for .NET Framework libraries</span></span>

<span data-ttu-id="6637b-139">압도적인 다수로 라이브러리는 .NET Standard가 아닌 .NET Framework를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-139">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="6637b-140">그러나 이러한 라이브러리에서 대부분의 호출은 .NET Standard 2.0에 포함된 API를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-140">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="6637b-141">.NET Standard 2.0부터는 [호환성 shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification)을 사용하여 .NET Standard 라이브러리에서 .NET Framework 라이브러리에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-141">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="6637b-142">이 호환성 레이어는 개발자에게 투명합니다. .NET Framework 라이브러리를 이용하기 위해 아무것도 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-142">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="6637b-143">하나의 요구 사항은 .NET Framework 클래스 라이브러리에서 호출하는 API가 .NET Standard 2.0에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-143">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="6637b-144">Visual Basic에 대한 지원</span><span class="sxs-lookup"><span data-stu-id="6637b-144">Support for Visual Basic</span></span>

<span data-ttu-id="6637b-145">이제 Visual Basic에서 .NET Standard 라이브러리를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-145">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="6637b-146">.NET Core 워크로드가 설치된 Visual Studio 2017 버전 15.3 이상을 사용하는 Visual Basic 개발자의 경우 이제 Visual Studio에는 .NET Standard 클래스 라이브러리 템플릿이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-146">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="6637b-147">다른 개발 도구와 환경을 사용하는 Visual Basic 개발자의 경우 [dotnet new](../../core/tools/dotnet-new.md) 명령을 사용하여 .NET Standard 라이브러리 프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-147">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="6637b-148">자세한 내용은 [.NET Standard 라이브러리에 대한 도구 지원](#tooling-support-for-net-standard-libraries)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6637b-148">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="6637b-149">.NET Standard 라이브러리에 대한 도구 지원</span><span class="sxs-lookup"><span data-stu-id="6637b-149">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="6637b-150">.NET Core 2.0 및 .NET Standard 2.0의 릴리스에서는 Visual Studio 2017 및 [.NET Core CLI(명령줄 인터페이스)](../../core/tools/index.md)에 둘 다 .NET Standard 라이브러리를 만들기 위한 도구 지원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-150">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="6637b-151">**.NET Core 플랫폼 간 개발** 워크로드를 통해 Visual Studio를 설치하는 경우 다음 그림과 같이 프로젝트 템플릿을 사용하여 .NET Standard 2.0 라이브러리 프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-151">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="6637b-152">C#</span><span class="sxs-lookup"><span data-stu-id="6637b-152">C#</span></span>](#tab/csharp)

![새 .NET Standard 라이브러리 프로젝트 추가](./media/std-project-cs.png)

<span data-ttu-id="6637b-154">.NET Core CLI를 사용하는 경우 다음 [dotnet new](../../core/tools/dotnet-new.md) 명령은 .NET Standard 2.0을 대상으로 하는 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-154">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```
dotnet new classlib
```

# <a name="visual-basictabvb"></a>[<span data-ttu-id="6637b-155">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6637b-155">Visual Basic</span></span>](#tab/vb)

![새 .NET Standard 라이브러리 프로젝트 추가](./media/std-project-vb.png)

<span data-ttu-id="6637b-157">.NET Core CLI를 사용하는 경우 다음 [dotnet new](../../core/tools/dotnet-new.md) 명령은 .NET Standard 2.0을 대상으로 하는 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6637b-157">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="6637b-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6637b-158">See also</span></span>

[<span data-ttu-id="6637b-159">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="6637b-159">.NET Standard</span></span>](../net-standard.md)  
[<span data-ttu-id="6637b-160">.NET Standard 소개</span><span class="sxs-lookup"><span data-stu-id="6637b-160">Introducing .NET Standard</span></span>](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
