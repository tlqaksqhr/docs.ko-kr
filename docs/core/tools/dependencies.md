---
title: .NET Core 도구에서 종속성 관리
description: .NET Core 도구로 종속성을 관리하는 방법을 설명합니다.
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 5da4f5e4d837be874323ef700093b0d01c8ac98f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="86de1-103">.NET Core SDK 1.0으로 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="86de1-103">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="86de1-104">.NET Core 프로젝트가 project.json에서 csproj 및 MSBuild로 전환하면서 상당한 투자가 발생했으며, 그 결과 종속성 추적을 허용하는 프로젝트 파일과 자산 통합이 이루어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-104">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="86de1-105">.NET Core 프로젝트의 경우 project.json의 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-105">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="86de1-106">NuGet 종속성을 추적하는 별도 JSON 또는 XML 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-106">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="86de1-107">이 변경으로 `<PackageReference>`라는 csproj 구문에 대한 다른 *참조* 형식도 소개하였습니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-107">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="86de1-108">이 문서에서는 새 참조 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-108">This document describes the new reference type.</span></span> <span data-ttu-id="86de1-109">또한 프로젝트에 대한 이 새 참조 형식을 사용하여 패키지 종속성을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-109">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="86de1-110">새 \<PackageReference> 요소</span><span class="sxs-lookup"><span data-stu-id="86de1-110">The new \<PackageReference> element</span></span>
<span data-ttu-id="86de1-111">`<PackageReference>`의 기본 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-111">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="86de1-112">MSBuild에 익숙한 경우 이미 존재하는 다른 참조 형식에 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-112">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="86de1-113">키는 프로젝트에 추가할 패키지 ID를 지정하는 `Include` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-113">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="86de1-114">`<Version>` 자식 요소는 가져올 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-114">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="86de1-115">버전은 [NuGet 버전 규칙](/nuget/create-packages/dependency-versions#version-ranges)에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-115">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="86de1-116">전체 `csproj` 구문에 대해 잘 알고 있지 않은 경우 자세한 내용은[MSBuild 프로젝트 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86de1-116">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="86de1-117">특정 대상에만 사용할 수 있는 종속성을 추가하려면 다음 예와 같은 조건을 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-117">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

<span data-ttu-id="86de1-118">위의 예는 지정된 대상에 대해 빌드가 발생한 경우에만 종속성이 유효하다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-118">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="86de1-119">조건에서 `$(TargetFramework)`는 프로젝트에 설정 되는 MSBuild 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-119">The `$(TargetFramework)` in the condition is a MSBuild property that is being set in the project.</span></span> <span data-ttu-id="86de1-120">가장 일반적인.NET Core 응용 프로그램의 경우 이 작업을 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-120">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="86de1-121">프로젝트에 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="86de1-121">Adding a dependency to your project</span></span>
<span data-ttu-id="86de1-122">프로젝트에 종속성을 추가하는 작업은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-122">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="86de1-123">다음은 Json.NET 버전 `9.0.1`을 프로젝트에 추가하는 방법을 보여 주는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-123">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="86de1-124">물론, 다른 NuGet 종속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-124">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="86de1-125">프로젝트 파일을 열면 `<ItemGroup>` 노드가 두 개 이상 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-125">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="86de1-126">노드 중 하나에 이미 `<PackageReference>` 요소가 있다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-126">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="86de1-127">이 노드에 새 종속성을 추가하거나 새로 만들 수 있습니다. 둘 중 어떤 방법을 사용해도 결과는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-127">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="86de1-128">이 예제에서는 `dotnet new console`에서 삭제된 기본 템플릿을 사용해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-128">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="86de1-129">이는 간단한 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-129">This is a simple console application.</span></span> <span data-ttu-id="86de1-130">프로젝트를 열면 먼저 이미 기존 `<PackageReference>`에 `<ItemGroup>`이 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-130">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="86de1-131">그리고 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-131">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
<span data-ttu-id="86de1-132">이렇게 되면 프로젝트를 저장하고 `dotnet restore` 명령을 실행하여 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-132">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="86de1-133">전체 프로젝트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-133">The full project looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="86de1-134">프로젝트에서 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="86de1-134">Removing a dependency from the project</span></span>
<span data-ttu-id="86de1-135">프로젝트 파일에서 종속성을 제거하는 작업은 프로젝트 파일에서 `<PackageReference>`를 단순히 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86de1-135">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
