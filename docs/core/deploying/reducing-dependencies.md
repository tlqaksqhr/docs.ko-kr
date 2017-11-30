---
title: "project.json으로 패키지 종속성 감소"
description: "Project.json 기반의 라이브러리를 만들 때 패키지 종속성이 감소합니다."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 916251e3-87f9-4eee-81ec-94076215e6fa
ms.openlocfilehash: e09b6f9124ec7614ab2e847d686435d74b00b336
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="reducing-package-dependencies-with-projectjson"></a><span data-ttu-id="418f8-104">project.json으로 패키지 종속성 감소</span><span class="sxs-lookup"><span data-stu-id="418f8-104">Reducing Package Dependencies with project.json</span></span>

<span data-ttu-id="418f8-105">이 문서에서는 `project.json` 라이브러리를 작성할 때 패키지 종속성을 줄이는 방법에 대해 알아야 할 내용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-105">This article covers what you need to know about reducing your package dependencies when authoring `project.json` libraries.</span></span> <span data-ttu-id="418f8-106">이 문서를 마칠 때는 필요한 종속성만을 사용하도록 라이브러리를 작성하는 방법을 이해하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-106">By the end of this article, you will learn how to compose your library such that it only uses the dependencies it needs.</span></span> 

## <a name="why-its-important"></a><span data-ttu-id="418f8-107">중요한 이유</span><span class="sxs-lookup"><span data-stu-id="418f8-107">Why it's Important</span></span>

<span data-ttu-id="418f8-108">.NET Core는 NuGet 패키지로 구성된 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-108">.NET Core is a product made up of NuGet packages.</span></span>  <span data-ttu-id="418f8-109">필수 패키지는 [.NET 표준 라이브러리 메타패키지](https://www.nuget.org/packages/NETStandard.Library)입니다. 이는 다른 패키지들로 구성된 NuGet 패키지로,</span><span class="sxs-lookup"><span data-stu-id="418f8-109">An essential package is the [.NETStandard.Library metapackage](https://www.nuget.org/packages/NETStandard.Library), which is a NuGet package composed of other packages.</span></span>  <span data-ttu-id="418f8-110">.NET Framework, .NET Core 및 Xamarin/Mono 같은 여러 .NET 구현에서 작업할 수 있도록 보장하는 패키지 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-110">It provides you with the set of packages that are guaranteed to work on multiple .NET implementations, such as .NET Framework, .NET Core and Xamarin/Mono.</span></span>

<span data-ttu-id="418f8-111">그러나 라이브러리에서 포함된 모든 패키지를 사용하지는 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-111">However, there's a good chance that your library won't use every single package it contains.</span></span>  <span data-ttu-id="418f8-112">라이브러리를 작성하여 NuGet을 통해 배포할 때, 실제로 사용하는 패키지만으로 종속성을 "잘라내는" 것이 가장 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-112">When authoring a library and distributing it over NuGet, it's a best practice to "trim" your dependencies down to only the packages you actually use.</span></span>  <span data-ttu-id="418f8-113">이렇게 하면 NuGet 패키지에서 전체적인 공간을 적게 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-113">This results in a smaller overall footprint for NuGet packages.</span></span>

## <a name="how-to-do-it"></a><span data-ttu-id="418f8-114">방법</span><span class="sxs-lookup"><span data-stu-id="418f8-114">How to do it</span></span>

<span data-ttu-id="418f8-115">현재로서는 패키지 참조를 잘라내는 공식 `dotnet` 명령이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-115">Currently, there is no official `dotnet` command which trims package references.</span></span>  <span data-ttu-id="418f8-116">이 작업을 수동으로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-116">Instead, you'll have to do it manually.</span></span>  <span data-ttu-id="418f8-117">일반적인 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-117">The general process looks like the following:</span></span>

1. <span data-ttu-id="418f8-118">`project.json`의 `dependencies` 섹션에서 `NETStandard.Library` 버전 `1.6.0`을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-118">Reference `NETStandard.Library` version `1.6.0` in a `dependencies` section of your `project.json`.</span></span>
2. <span data-ttu-id="418f8-119">사용 하 여 패키지를 복원 `dotnet restore` ([참고](#dotnet-restore-note)) 명령줄에서.</span><span class="sxs-lookup"><span data-stu-id="418f8-119">Restore packages with `dotnet restore` ([see note](#dotnet-restore-note)) from the command line.</span></span>
3. <span data-ttu-id="418f8-120">`project.lock.json` 파일을 검사하고 `NETSTandard.Library` 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-120">Inspect the `project.lock.json` file and find the `NETSTandard.Library` section.</span></span>  <span data-ttu-id="418f8-121">파일의 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-121">It's near the beginning of the file.</span></span>
4. <span data-ttu-id="418f8-122">`dependencies` 아래에 나열된 모든 패키지를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-122">Copy all of the listed packages under `dependencies`.</span></span>
5. <span data-ttu-id="418f8-123">`.NETStandard.Library` 참조를 제거하고 복사된 패키지로 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-123">Remove the `.NETStandard.Library` reference and replace it with the copied packages.</span></span>
6. <span data-ttu-id="418f8-124">필요 없는 패키지에 대한 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-124">Remove references to packages you don't need.</span></span>


<span data-ttu-id="418f8-125">다음 방법 중 하나를 사용하여 필요 없는 패키지를 알아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-125">You can find out which packages you don't need by one of the following ways:</span></span>

1. <span data-ttu-id="418f8-126">시행착오.</span><span class="sxs-lookup"><span data-stu-id="418f8-126">Trial and error.</span></span>  <span data-ttu-id="418f8-127">패키지를 제거하고 복원하면서 여전히 컴파일되는지를 알아보고 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-127">This involves removing a package, restoring, seeing if your library still compiles, and repeating this process.</span></span>
2. <span data-ttu-id="418f8-128">참조를 피킹하여 실제로 어떤 코드가 사용되는지를 알아보기 위해 [ILSpy](http://ilspy.net) 또는 [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) 같은 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-128">Using a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to peek at references to see what your code is actually using.</span></span>  <span data-ttu-id="418f8-129">그런 다음 사용 중인 형식에 해당하지 않는 패키지를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-129">You can then remove packages which don't correspond to types you're using.</span></span>

## <a name="example"></a><span data-ttu-id="418f8-130">예제</span><span class="sxs-lookup"><span data-stu-id="418f8-130">Example</span></span> 

<span data-ttu-id="418f8-131">제네릭 컬렉션 형식에 추가 기능을 제공한 라이브러리를 작성했다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-131">Imagine that you wrote a library which provided additional functionality to generic collection types.</span></span>  <span data-ttu-id="418f8-132">그런 라이브러리는 `System.Collections` 같은 패키지에 종속되어야 하지만, `System.Net.Http` 같은 패키지에는 전혀 종속되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-132">Such a library would need to depend on packages such as `System.Collections`, but may not at all depend on packages such as `System.Net.Http`.</span></span>  <span data-ttu-id="418f8-133">따라서 이 라이브러리에 필요한 것으로만 패키지 종속성을 잘라낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-133">As such, it would be good to trim package dependencies down to only what this library required!</span></span>

<span data-ttu-id="418f8-134">이 라이브러리를 잘라내려면 `project.json` 파일로 시작해서 `NETStandard.Library` 버전 `1.6.0`에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-134">To trim this library, you start with the `project.json` file and add a reference to `NETStandard.Library` version `1.6.0`.</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="418f8-135">사용 하 여 패키지를 복원 하는 다음으로 `dotnet restore` ([참고 참조](#dotnet-restore-note)), 검사는 `project.lock.json` 파일, 및 복원에 대 한 모든 패키지를 찾을 `NETSTandard.Library`합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-135">Next, you restore packages with `dotnet restore` ([see note](#dotnet-restore-note)), inspect the `project.lock.json` file, and find all the packages restored for `NETSTandard.Library`.</span></span>

<span data-ttu-id="418f8-136">다음은 `netstandard1.0`을 대상으로 할 때 `project.lock.json` 파일의 관련 섹션이 어떤 모양인지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-136">Here's what the relevant section in the `project.lock.json` file looks like when targeting `netstandard1.0`:</span></span>

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

<span data-ttu-id="418f8-137">그런 다음, 라이브러리의 `project.json` 파일에 있는 `dependencies` 섹션으로 패키지 참조를 복사하여 `NETStandard.Library` 참조를 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-137">Next, copy over the package references into the `dependencies` section of the library's `project.json` file, replacing the `NETStandard.Library` reference:</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

<span data-ttu-id="418f8-138">패키지가 매우 많지만, 이중 다수는 확실히 컬렉션 형식의 확장에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-138">That's quite a lot of packages, many of which which certainly aren't necessary for extending collection types.</span></span>  <span data-ttu-id="418f8-139">패키지를 수동으로 제거하거나 [ILSpy](http://ilspy.net) 또는 [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector)와 같은 도구를 사용하여 코드가 실제로 사용하는 패키지를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-139">You can either remove packages manually or use a tool such as [ILSpy](http://ilspy.net) or [.NET Reflector](http://www.red-gate.com/products/dotnet-development/reflector) to identify which packages your code actually uses.</span></span>

<span data-ttu-id="418f8-140">잘라낸 패키지의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-140">Here's what a trimmed package could look like:</span></span>

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="418f8-141">이제 `NETStandard.Library` 메타패키지에 의존하는 경우 공간을 덜 차지하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="418f8-141">Now, it has a smaller footprint than if it had depended on the `NETStandard.Library` metapackage.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]