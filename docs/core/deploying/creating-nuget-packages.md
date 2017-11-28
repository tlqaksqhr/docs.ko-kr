---
title: "플랫폼 간 도구로 NuGet 패키지 만들기"
description: "'dotnet pack' 명령을 사용하여 NuGet 패키지를 만드는 방법에 관해 알아봅니다."
keywords: .NET, .NET Core, NuGet
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2f0415c1-110b-433d-87c1-ae3d543a8844
ms.openlocfilehash: a5738a4f3755a959660db4be683677673af61ef9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="f8d8c-104">플랫폼 간 도구로 NuGet 패키지를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="f8d8c-104">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="f8d8c-105">다음에서는 Unix를 사용하는 명령줄 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-105">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="f8d8c-106">여기에 표시된 `dotnet pack` 명령은 Windows에서와 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-106">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="f8d8c-107">.NET Core 1.0의 경우 라이브러리가 NuGet 패키지로 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-107">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="f8d8c-108">이는 실제로 모든 .NET 표준 라이브러리가 배포되고 사용되는 방법이며,</span><span class="sxs-lookup"><span data-stu-id="f8d8c-108">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="f8d8c-109">`dotnet pack` 명령을 사용하여 가장 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-109">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="f8d8c-110">NuGet을 통해 배포하려는 놀라운 새 라이브러리를 작성했다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-110">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="f8d8c-111">플랫폼 간 도구를 사용하여 NuGet 패키지를 만들면 이 작업을 정확하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-111">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="f8d8c-112">다음 예제에서는 `netstandard1.0`을 대상으로 하는 **SuperAwesomeLibrary**라는 라이브러리를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-112">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="f8d8c-113">전이적 종속성 즉, 다른 프로젝트에 종속되어 있는 프로젝트가 있는 경우 NuGet 패키지를 만들기 전에 `dotnet restore` 명령을 사용하여 전체 솔루션에 대한 패키지를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-113">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="f8d8c-114">이렇게 복원하지 않으면 `dotnet pack` 명령이 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-114">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


<span data-ttu-id="f8d8c-115">패키지가 복원되었는지 확인한 후 라이브러리가 있는 디렉터리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-115">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="f8d8c-116">그러면 명령줄에서 단일 명령만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-116">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="f8d8c-117">이제 `/bin/Debug` 폴더가 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-117">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="f8d8c-118">그러면 디버그할 수 있는 패키지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-118">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="f8d8c-119">릴리스 이진 파일과 함께 NuGet 패키지를 빌드하려면 `-c`/`--configuration` 스위치를 추가하고 `release`를 인수로 사용하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-119">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="f8d8c-120">이제 `/bin` 폴더에 릴리스 이진 파일과 함께 NuGet 패키지를 포함하는 `release` 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-120">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="f8d8c-121">또한 NuGet 패키지를 게시하는 데 필요한 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-121">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="f8d8c-122">`dotnet pack`을 다음과 혼동하지 마세요.`dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="f8d8c-122">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="f8d8c-123">어떤 지점에서도 `dotnet publish` 명령은 관련되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-123">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="f8d8c-124">`dotnet publish` 명령은 동일한 번들에 있는 모든 종속성과 함께 응용 프로그램을 배포하기 위한 것이며 NuGet을 통해 배포하고 사용할 NuGet 패키지를 생성하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f8d8c-124">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>
