---
title: "언어 기능 및 라이브러리 형식 간의 관계 | Microsoft Docs"
description: "언어 기능은 종종 구현에 대한 라이브러리 형식에 의존합니다. 해당 관계를 이해합니다."
keywords: "C# 언어 디자인, 표준 라이브러리"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: b7de4fdb4356e8822dba6aaaf67d615980ff09cd
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="relationships-between-language-features-and-library-types"></a><span data-ttu-id="efbb7-105">언어 기능 및 라이브러리 형식 간의 관계</span><span class="sxs-lookup"><span data-stu-id="efbb7-105">Relationships between language features and library types</span></span>

<span data-ttu-id="efbb7-106">C# 언어 정의는 특정 형식 및 이러한 형식에서 액세스할 수 있는 특정 멤버를 갖는 표준 라이브러리를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-106">The C# language definition requires a standard library to have certain types and certain accessible members on those types.</span></span> <span data-ttu-id="efbb7-107">컴파일러는 다양한 많은 언어 기능에 이러한 필요한 이러한 형식과 멤버를 사용하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-107">The compiler generates code that uses these required types and members for many different language features.</span></span> <span data-ttu-id="efbb7-108">필요한 경우 해당 형식이나 멤버가 아직 배포되지 않은 환경에 대한 코드를 작성할 때 최신 버전의 언어에 필요한 형식을 포함하는 NuGet 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-108">When necessary, there are NuGet packages that contain types needed for newer versions of the language when writing code for environments where those types or members have not been deployed yet.</span></span>

<span data-ttu-id="efbb7-109">표준 라이브러리 기능에 대한 이 종속성은 첫 번째 버전부터 C# 언어의 일부였습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-109">This dependency on standard library functionality has been part of the C# language since its first version.</span></span> <span data-ttu-id="efbb7-110">해당 버전에서 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-110">In that version, examples included:</span></span>

* <span data-ttu-id="efbb7-111"><xref:System.Exception> - 모든 컴파일러 생성 예외에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-111"><xref:System.Exception> - used for all compiler generated exceptions.</span></span>
* <span data-ttu-id="efbb7-112"><xref:System.String> - C# `string` 형식은 <xref:System.String>의 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-112"><xref:System.String> - the C# `string` type is a synonym for <xref:System.String>.</span></span>
* <span data-ttu-id="efbb7-113"><xref:System.Int32> - `int`의 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-113"><xref:System.Int32> - synonym of `int`.</span></span>

<span data-ttu-id="efbb7-114">첫 번째 버전은 간단했습니다. 컴파일러 및 표준 라이브러리는 함께 제공되었고 각각 하나의 버전만 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-114">That first version was simple: the compiler and the standard library shipped together, and there was only one version of each.</span></span>

<span data-ttu-id="efbb7-115">후속 버전의 C#은 종속성에 가끔 새 형식 또는 멤버를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-115">Subsequent versions of C# have occasionally added new types or members to the dependencies.</span></span> <span data-ttu-id="efbb7-116">예를 들면 <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> 및 <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>입니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-116">Examples include: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> and <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>.</span></span> <span data-ttu-id="efbb7-117">C# 7.0은 <xref:System.ValueTuple>에 종속성을 추가하여 [튜플](../tuples.md) 언어 기능을 계속해서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-117">C# 7.0 continues this by adding a dependency on <xref:System.ValueTuple> to implement the [tuples](../tuples.md) language feature.</span></span>

<span data-ttu-id="efbb7-118">언어 디자인 팀은 호환 표준 라이브러리에 필요한 형식 및 멤버의 노출 영역을 최소화하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-118">The language design team works to minimize the surface area of the types and members required in a compliant standard library.</span></span> <span data-ttu-id="efbb7-119">해당 목표는 새 라이브러리 기능이 해당 언어로 원활하게 통합되는 단순한 디자인에 따라 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-119">That goal is balanced against a clean design where new library features are incorporated seamlessly into the language.</span></span> <span data-ttu-id="efbb7-120">표준 라이브러리에 새 형식 및 멤버를 필요로 하는 이후 버전의 C#에는 새 기능이 있을 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-120">There will be new features in future versions of C# that require new types and members in a standard library.</span></span> <span data-ttu-id="efbb7-121">작업에서 해당 종속성을 관리하는 방법을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-121">It's important to understand how to manage those dependencies in your work.</span></span>

## <a name="managing-your-dependencies"></a><span data-ttu-id="efbb7-122">종속성 관리</span><span class="sxs-lookup"><span data-stu-id="efbb7-122">Managing your dependencies</span></span>

<span data-ttu-id="efbb7-123">C# 컴파일러 도구는 이제 지원되는 플랫폼의 .NET 라이브러리의 릴리스 주기에서 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-123">C# compiler tools are now decoupled from the release cycle of the .NET libraries on supported platforms.</span></span> <span data-ttu-id="efbb7-124">사실상 서로 다른 .NET 라이브러리는 다른 릴리스 주기를 갖습니다. Windows에서 .NET Framework는 Windows 업데이트로 릴리스되고, .NET Core는 별도 일정으로 제공되며, Xamarin 버전의 라이브러리 업데이트는 각 대상 플랫폼에 대한 Xamarin 도구로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-124">In fact, different .NET libraries have different release cycles: the .NET Framework on Windows is released as a Windows Update, .NET Core ships on a separate schedule, and the Xamarin versions of library updates ship with the Xamarin tools for each target platform.</span></span>

<span data-ttu-id="efbb7-125">대부분의 시간에서 이러한 변경 내용이 발견되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-125">The majority of time, you won't notice these changes.</span></span> <span data-ttu-id="efbb7-126">그러나 해당 플랫폼의 .NET 라이브러리에 아직 없는 기능을 필요로 하는 언어의 최신 버전을 사용하는 경우 이러한 새 유형을 제공하는 NuGet 패키지를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-126">However, when you are working with a newer version of the language that requires features not yet in the .NET libraries on that platform, you'll reference the NuGet packages to provide those new types.</span></span>
<span data-ttu-id="efbb7-127">플랫폼으로서 앱 지원은 새 프레임워크를 설치로 업데이트되며 추가 참조를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-127">As the platforms your app supports are updated with new framework installations, you can remove the extra reference.</span></span>

<span data-ttu-id="efbb7-128">이러한 분리는 해당 프레임워크가 없을 수도 있는 컴퓨터를 대상으로 하는 경우에도 새로운 언어 기능을 사용할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="efbb7-128">This separation means you can use new language features even when you are targeting machines that may not have the corresponding framework.</span></span>
