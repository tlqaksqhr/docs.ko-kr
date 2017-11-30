---
title: "언어 기능 및 라이브러리 형식 간의 관계 | Microsoft Docs"
description: "언어 기능 구현에 대 한 형식 라이브러리를 종종 의존합니다. 해당 관계를 이해 합니다."
keywords: "C# 언어 디자인 표준 라이브러리"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 93fd26a72743fcf45df3904cb8d0c787d8a228a8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2017
---
# <a name="relationships-between-language-features-and-library-types"></a><span data-ttu-id="df250-105">언어 기능 및 라이브러리 형식 간의 관계</span><span class="sxs-lookup"><span data-stu-id="df250-105">Relationships between language features and library types</span></span>

<span data-ttu-id="df250-106">이러한 형식에 특정 형식 및 액세스할 수 있는 특정 멤버를 표준 라이브러리를 필요로 하는 C# 언어 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="df250-106">The C# language definition requires a standard library to have certain types and certain accessible members on those types.</span></span> <span data-ttu-id="df250-107">컴파일러는 많은 다양 한 언어 기능에 필요한 이러한 형식과 멤버를 사용 하는 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-107">The compiler generates code that uses these required types and members for many different language features.</span></span> <span data-ttu-id="df250-108">필요한 경우에 여기서 해당 형식이 나 멤버 배포 되지 않았습니다. 아직 환경에 대 한 코드를 작성할 때 최신 버전의 언어에 필요한 형식을 포함 하는 NuGet 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-108">When necessary, there are NuGet packages that contain types needed for newer versions of the language when writing code for environments where those types or members have not been deployed yet.</span></span>

<span data-ttu-id="df250-109">표준 라이브러리 기능에 대 한이 종속성은 첫 번째 버전부터 C# 언어의 일부를 했습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-109">This dependency on standard library functionality has been part of the C# language since its first version.</span></span> <span data-ttu-id="df250-110">해당 버전의 예제가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-110">In that version, examples included:</span></span>

* <span data-ttu-id="df250-111"><xref:System.Exception>-컴파일러에서 생성 하는 모든 예외에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-111"><xref:System.Exception> - used for all compiler generated exceptions.</span></span>
* <span data-ttu-id="df250-112"><xref:System.String>-C# `string` 에 대 한 동의어 <xref:System.String>합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-112"><xref:System.String> - the C# `string` type is a synonym for <xref:System.String>.</span></span>
* <span data-ttu-id="df250-113"><xref:System.Int32>-의 동의어 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-113"><xref:System.Int32> - synonym of `int`.</span></span>

<span data-ttu-id="df250-114">첫 번째 버전은 간단한 작업 이었습니다: 컴파일러 및 표준 라이브러리 함께 제공 되 고 하나의 버전만 했습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-114">That first version was simple: the compiler and the standard library shipped together, and there was only one version of each.</span></span>

<span data-ttu-id="df250-115">후속 버전의 C# 종속성을 새 형식 또는 멤버를 추가 가끔 했습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-115">Subsequent versions of C# have occasionally added new types or members to the dependencies.</span></span> <span data-ttu-id="df250-116">예를 들면: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> 및 <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-116">Examples include: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> and <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>.</span></span> <span data-ttu-id="df250-117">C# 7.0에 종속성을 추가 하 여이 계속 <xref:System.ValueTuple> 구현 하는 [튜플](../tuples.md) 언어 기능.</span><span class="sxs-lookup"><span data-stu-id="df250-117">C# 7.0 continues this by adding a dependency on <xref:System.ValueTuple> to implement the [tuples](../tuples.md) language feature.</span></span>

<span data-ttu-id="df250-118">언어 디자인 팀은 형식과 호환 표준 라이브러리에 필요한 멤버의 노출 영역을 최소화 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-118">The language design team works to minimize the surface area of the types and members required in a compliant standard library.</span></span> <span data-ttu-id="df250-119">그 목표에 해당 언어에 새 라이브러리 기능 원활 하 게 통합 하는 단순한 디자인에 따라 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df250-119">That goal is balanced against a clean design where new library features are incorporated seamlessly into the language.</span></span> <span data-ttu-id="df250-120">새 형식이 필요로 하는 이후 버전의 C#의 새로운 기능 및 표준 라이브러리의 멤버가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df250-120">There will be new features in future versions of C# that require new types and members in a standard library.</span></span> <span data-ttu-id="df250-121">작업에서 해당 종속성을 관리 하는 방법을 이해 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-121">It's important to understand how to manage those dependencies in your work.</span></span>

## <a name="managing-your-dependencies"></a><span data-ttu-id="df250-122">종속성 관리</span><span class="sxs-lookup"><span data-stu-id="df250-122">Managing your dependencies</span></span>

<span data-ttu-id="df250-123">C# 컴파일러 도구는 이제 지원 되는 플랫폼에.NET 라이브러리의 릴리스 주기에서 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df250-123">C# compiler tools are now decoupled from the release cycle of the .NET libraries on supported platforms.</span></span> <span data-ttu-id="df250-124">사실, 서로 다른.NET 라이브러리는 다른 릴리스 주기: Windows에서.NET Framework는 Windows 업데이트와 relesed,.NET Core는 별도 일정 및 Xamarin 버전 각 대상 플랫폼에 대 한 Xamarin 도구로 라이브러리 업데이트 제공의 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-124">In fact, different .NET libraries have different release cycles: the .NET Framework on Windows is relesed as a Windows Update, .NET Core ships on a separate schedule, and the Xamarin versions of library updates ship with the Xamarin tools for each target platform.</span></span>

<span data-ttu-id="df250-125">시간의 대부분을 이러한 변경 내용을 발견 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-125">The majority of time, you won't notice these changes.</span></span> <span data-ttu-id="df250-126">그러나 해당 플랫폼에서.NET 라이브러리에는 아직 하지 기능을 필요로 하는 언어의 최신 버전을 사용 하는 경우 이러한 새 유형을 제공 하는 NuGet 패키지를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-126">However, when you are working with a newer version of the language that requires features not yet in the .NET libraries on that platform, you'll reference the NuGet packages to provide those new types.</span></span>
<span data-ttu-id="df250-127">사용자 응용 프로그램이 지 원하는 새 프레임 워크를 설치 하 여 업데이트 되는 플랫폼으로 추가 참조를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df250-127">As the platforms your app supports are updated with new framework installations, you can remove the extra reference.</span></span>

<span data-ttu-id="df250-128">이러한 분리는 해당 프레임 워크에 없을 수도 있는 컴퓨터를 대상으로 하는 경우에 새로운 언어 기능을 사용할 수를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="df250-128">This separation means you can use new language features even when you are targeting machines that may not have the corresponding framework.</span></span>
