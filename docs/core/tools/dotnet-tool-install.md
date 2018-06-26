---
title: dotnet tool install 명령 - .NET Core CLI
description: dotnet tool install 명령은 컴퓨터에 지정한 .NET Core Global 도구를 설치합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: f3068848910d6672a10ecfb639bac8e18a72818d
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697289"
---
# <a name="dotnet-tool-install"></a><span data-ttu-id="24b60-103">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="24b60-103">dotnet tool install</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="24b60-104">name</span><span class="sxs-lookup"><span data-stu-id="24b60-104">Name</span></span>

<span data-ttu-id="24b60-105">`dotnet tool install` - 컴퓨터에 지정된 [.NET Core Global 도구](global-tools.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-105">`dotnet tool install` - Installs the specified [.NET Core Global Tool](global-tools.md) on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="24b60-106">개요</span><span class="sxs-lookup"><span data-stu-id="24b60-106">Synopsis</span></span>

```
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a><span data-ttu-id="24b60-107">설명</span><span class="sxs-lookup"><span data-stu-id="24b60-107">Description</span></span>

<span data-ttu-id="24b60-108">`dotnet tool install` 명령은 컴퓨터에서 .NET Core Global 도구를 설치하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-108">The `dotnet tool install` command provides a way for you to install .NET Core Global Tools on your machine.</span></span> <span data-ttu-id="24b60-109">이 명령을 사용하려면 `--global` 옵션을 사용하여 사용자 전체 설치를 원한다고 지 정하거나 `--tool-path` 옵션을 사용하여 도구를 설치할 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-109">To use the command, you either have to specify that you want a user-wide installation using the `--global` option or you specify a path to install it using the `--tool-path` option.</span></span>

<span data-ttu-id="24b60-110">전역 도구는 `-g`(또는 `--global`) 옵션을 지정할 때 기본적으로 다음 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-110">Global Tools are installed in the following directories by default when you specify the `-g` (or `--global`) option:</span></span>

| <span data-ttu-id="24b60-111">OS</span><span class="sxs-lookup"><span data-stu-id="24b60-111">OS</span></span>          | <span data-ttu-id="24b60-112">Path</span><span class="sxs-lookup"><span data-stu-id="24b60-112">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="24b60-113">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="24b60-113">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="24b60-114">Windows</span><span class="sxs-lookup"><span data-stu-id="24b60-114">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a><span data-ttu-id="24b60-115">인수</span><span class="sxs-lookup"><span data-stu-id="24b60-115">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="24b60-116">설치할 .NET Core Global 도구를 포함하는 NuGet 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-116">Name/ID of the NuGet package that contains the .NET Core Global Tool to install.</span></span>

## <a name="options"></a><span data-ttu-id="24b60-117">옵션</span><span class="sxs-lookup"><span data-stu-id="24b60-117">Options</span></span>

`--add-source <SOURCE>`

<span data-ttu-id="24b60-118">설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-118">Adds an additional NuGet package source to use during installation.</span></span>

`--configfile <FILE>`

<span data-ttu-id="24b60-119">사용할 NuGet 구성(*nuget.config*) 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-119">The NuGet configuration (*nuget.config*) file to use.</span></span>

`--framework <FRAMEWORK>`

<span data-ttu-id="24b60-120">도구를 설치할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-120">Specifies the [target framework](../../standard/frameworks.md) to install the tool for.</span></span> <span data-ttu-id="24b60-121">기본적으로 .NET Core SDK는 가장 적합한 대상 프레임워크를 선택하도록 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-121">By default, the .NET Core SDK tries to choose the most appropriate target framework.</span></span>

`-g|--global`

<span data-ttu-id="24b60-122">사용자 전체 설치임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-122">Specifies that the installation is user wide.</span></span> <span data-ttu-id="24b60-123">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-123">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="24b60-124">이 옵션을 지정하지 않으면 `--tool-path` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-124">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="24b60-125">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-125">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="24b60-126">전역 도구를 설치할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-126">Specifies the location where to install the Global Tool.</span></span> <span data-ttu-id="24b60-127">경로는 절대 또는 상대 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-127">PATH can be absolute or relative.</span></span> <span data-ttu-id="24b60-128">경로가 존재하지 않는 경우 이 명령은 해당 경로를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-128">If PATH doesn't exist, the command tries to create it.</span></span> <span data-ttu-id="24b60-129">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-129">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="24b60-130">이 옵션을 지정하지 않으면 `--global` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-130">If you don't specify this option, you must specify the `--global` option.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="24b60-131">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-131">Sets the verbosity level of the command.</span></span> <span data-ttu-id="24b60-132">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-132">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version <VERSION_NUMBER>`

<span data-ttu-id="24b60-133">설치할 도구의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-133">The version of the tool to install.</span></span> <span data-ttu-id="24b60-134">기본적으로 안정적인 최신 버전이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-134">By default, the latest stable package version is installed.</span></span> <span data-ttu-id="24b60-135">도구의 미리 보기 또는 이전 버전을 설치할 경우 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-135">Use this option to install preview or older versions of the tool.</span></span>

## <a name="examples"></a><span data-ttu-id="24b60-136">예제</span><span class="sxs-lookup"><span data-stu-id="24b60-136">Examples</span></span>

<span data-ttu-id="24b60-137">기본 위치에 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-137">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool in the default location:</span></span>

`dotnet tool install -g dotnetsay`

<span data-ttu-id="24b60-138">특정 Windows 폴더에서 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-138">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Windows folder:</span></span>

`dotnet tool install dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="24b60-139">특정 Linux/macOS 폴더에서 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-139">Installs the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool on a specific Linux/macOS folder:</span></span>

`dotnet tool install dotnetsay --tool-path ~/bin`

<span data-ttu-id="24b60-140">[dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구 버전 2.0.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="24b60-140">Installs version 2.0.0 of the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="24b60-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24b60-141">See also</span></span>

[<span data-ttu-id="24b60-142">.NET Core Global 도구</span><span class="sxs-lookup"><span data-stu-id="24b60-142">.NET Core Global Tools</span></span>](global-tools.md)