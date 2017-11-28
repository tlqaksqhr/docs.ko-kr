---
title: ".NET Core 도구에서 종속성 관리"
description: ".NET Core 도구로 종속성을 관리하는 방법을 설명합니다."
keywords: "CLI, 확장성, 사용자 지정 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 74b87cdb-a244-4c13-908c-539118bfeef9
ms.openlocfilehash: 21f42bbf4693c78a5be271b7769ef4489ed6d476
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="managing-dependencies-with-net-core-sdk-10"></a><span data-ttu-id="2782a-104">.NET Core SDK 1.0으로 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="2782a-104">Managing dependencies with .NET Core SDK 1.0</span></span>

<span data-ttu-id="2782a-105">.NET Core 프로젝트가 project.json에서 csproj 및 MSBuild로 전환하면서 상당한 투자가 발생했으며, 그 결과 종속성 추적을 허용하는 프로젝트 파일과 자산 통합이 이루어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-105">With the move of .NET Core projects from project.json to csproj and MSBuild, a significant investment also happened that resulted in unification of the project file and assets that allow tracking of dependencies.</span></span> <span data-ttu-id="2782a-106">.NET Core 프로젝트의 경우 project.json의 경우와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-106">For .NET Core projects this is similar to what project.json did.</span></span> <span data-ttu-id="2782a-107">NuGet 종속성을 추적하는 별도 JSON 또는 XML 파일이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-107">There is no separate JSON or XML file that tracks NuGet dependencies.</span></span> <span data-ttu-id="2782a-108">이 변경으로 `<PackageReference>`라는 csproj 구문에 대한 다른 *참조* 형식도 소개하였습니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-108">With this change, we've also introduced another type of *reference* into the csproj syntax called the `<PackageReference>`.</span></span> 

<span data-ttu-id="2782a-109">이 문서에서는 새 참조 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-109">This document describes the new reference type.</span></span> <span data-ttu-id="2782a-110">또한 프로젝트에 대한 이 새 참조 형식을 사용하여 패키지 종속성을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-110">It also shows how to add a package dependency using this new reference type to your project.</span></span> 

## <a name="the-new-packagereference-element"></a><span data-ttu-id="2782a-111">새 \<PackageReference> 요소</span><span class="sxs-lookup"><span data-stu-id="2782a-111">The new \<PackageReference> element</span></span>
<span data-ttu-id="2782a-112">`<PackageReference>`의 기본 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-112">The `<PackageReference>` has the following basic structure:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

<span data-ttu-id="2782a-113">MSBuild에 익숙한 경우 이미 존재하는 다른 참조 형식에 익숙할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-113">If you are familiar with MSBuild, it will look familiar to the other reference types that already exist.</span></span> <span data-ttu-id="2782a-114">키는 프로젝트에 추가할 패키지 ID를 지정하는 `Include` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-114">The key is the `Include` statement which specifies the package id that you wish to add to the project.</span></span> <span data-ttu-id="2782a-115">`<Version>` 자식 요소는 가져올 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-115">The `<Version>` child element specifies the version to get.</span></span> <span data-ttu-id="2782a-116">버전은 [NuGet 버전 규칙](/nuget/create-packages/dependency-versions#version-ranges)에 따라 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-116">The versions are specified as per [NuGet version rules](/nuget/create-packages/dependency-versions#version-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="2782a-117">전체 `csproj` 구문에 대해 잘 알고 있지 않은 경우 자세한 내용은[MSBuild 프로젝트 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference) 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2782a-117">If you are not familiar with the overall `csproj` syntax, see the [MSBuild project reference](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation for more information.</span></span>  

<span data-ttu-id="2782a-118">특정 대상에만 사용할 수 있는 종속성을 추가하려면 다음 예와 같은 조건을 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-118">Adding a dependency that is available only in a specific target is done using conditions like in the following example:</span></span>

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp1.0'" />
```

<span data-ttu-id="2782a-119">위의 예는 지정된 대상에 대해 빌드가 발생한 경우에만 종속성이 유효하다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-119">The above means that the dependency will only be valid if the build is happening for that given target.</span></span> <span data-ttu-id="2782a-120">조건에서 `$(TargetFramework)`는 프로젝트에 설정 되는 MSBuild 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-120">The `$(TargetFramework)` in the condition is a MSBuild property that is being set in the project.</span></span> <span data-ttu-id="2782a-121">가장 일반적인.NET Core 응용 프로그램의 경우 이 작업을 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-121">For most common .NET Core applications, you will not need to do this.</span></span> 

## <a name="adding-a-dependency-to-your-project"></a><span data-ttu-id="2782a-122">프로젝트에 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="2782a-122">Adding a dependency to your project</span></span>
<span data-ttu-id="2782a-123">프로젝트에 종속성을 추가하는 작업은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-123">Adding a dependency to your project is straightforward.</span></span> <span data-ttu-id="2782a-124">다음은 Json.NET 버전 `9.0.1`을 프로젝트에 추가하는 방법을 보여 주는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-124">Here is an example of how to add Json.NET version `9.0.1` to your project.</span></span> <span data-ttu-id="2782a-125">물론, 다른 NuGet 종속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-125">Of course, it is applicable to any other NuGet dependency.</span></span> 

<span data-ttu-id="2782a-126">프로젝트 파일을 열면 `<ItemGroup>` 노드가 두 개 이상 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-126">When you open your project file, you will see two or more `<ItemGroup>` nodes.</span></span> <span data-ttu-id="2782a-127">노드 중 하나에 이미 `<PackageReference>` 요소가 있다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-127">You will notice that one of the nodes already has `<PackageReference>` elements in it.</span></span> <span data-ttu-id="2782a-128">이 노드에 새 종속성을 추가하거나 새로 만들 수 있습니다. 둘 중 어떤 방법을 사용해도 결과는 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-128">You can add your new dependency to this node, or create a new one; it is completely up to you as the result will be the same.</span></span> 

<span data-ttu-id="2782a-129">이 예제에서는 `dotnet new console`에서 삭제된 기본 템플릿을 사용해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-129">In this example we will use the default template that is dropped by `dotnet new console`.</span></span> <span data-ttu-id="2782a-130">이는 간단한 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-130">This is a simple console application.</span></span> <span data-ttu-id="2782a-131">프로젝트를 열면 먼저 이미 기존 `<PackageReference>`에 `<ItemGroup>`이 있음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-131">When we open up the project, we first find the `<ItemGroup>` with already existing `<PackageReference>` in it.</span></span> <span data-ttu-id="2782a-132">그리고 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-132">We then add the following to it:</span></span>

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```
<span data-ttu-id="2782a-133">이렇게 되면 프로젝트를 저장하고 `dotnet restore` 명령을 실행하여 종속성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-133">After this, we save the project and run the `dotnet restore` command to install the dependency.</span></span> 

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2782a-134">전체 프로젝트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-134">The full project looks like this:</span></span>

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

## <a name="removing-a-dependency-from-the-project"></a><span data-ttu-id="2782a-135">프로젝트에서 종속성 제거</span><span class="sxs-lookup"><span data-stu-id="2782a-135">Removing a dependency from the project</span></span>
<span data-ttu-id="2782a-136">프로젝트 파일에서 종속성을 제거하는 작업은 프로젝트 파일에서 `<PackageReference>`를 단순히 제거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2782a-136">Removing a dependency from the project file involves simply removing the `<PackageReference>` from the project file.</span></span>
