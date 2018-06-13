---
title: 플랫폼 간 도구로 NuGet 패키지 만들기
description: "'dotnet pack' 명령을 사용하여 NuGet 패키지를 만드는 방법에 관해 알아봅니다."
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 6be94c2e2cef443f69b2d6df7c2d490cb1fb629d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33219458"
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="4460b-103">플랫폼 간 도구로 NuGet 패키지를 만드는 방법</span><span class="sxs-lookup"><span data-stu-id="4460b-103">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="4460b-104">다음에서는 Unix를 사용하는 명령줄 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-104">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="4460b-105">여기에 표시된 `dotnet pack` 명령은 Windows에서와 동일한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="4460b-106">.NET Core 1.0의 경우 라이브러리가 NuGet 패키지로 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-106">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="4460b-107">이는 실제로 모든 .NET 표준 라이브러리가 배포되고 사용되는 방법이며,</span><span class="sxs-lookup"><span data-stu-id="4460b-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="4460b-108">`dotnet pack` 명령을 사용하여 가장 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="4460b-109">NuGet을 통해 배포하려는 놀라운 새 라이브러리를 작성했다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4460b-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="4460b-110">플랫폼 간 도구를 사용하여 NuGet 패키지를 만들면 이 작업을 정확하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="4460b-111">다음 예제에서는 `netstandard1.0`을 대상으로 하는 **SuperAwesomeLibrary**라는 라이브러리를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="4460b-112">전이적 종속성 즉, 다른 프로젝트에 종속되어 있는 프로젝트가 있는 경우 NuGet 패키지를 만들기 전에 `dotnet restore` 명령을 사용하여 전체 솔루션에 대한 패키지를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-112">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="4460b-113">이렇게 복원하지 않으면 `dotnet pack` 명령이 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


<span data-ttu-id="4460b-114">패키지가 복원되었는지 확인한 후 라이브러리가 있는 디렉터리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="4460b-115">그러면 명령줄에서 단일 명령만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-115">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="4460b-116">이제 `/bin/Debug` 폴더가 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-116">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="4460b-117">그러면 디버그할 수 있는 패키지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-117">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="4460b-118">릴리스 이진 파일과 함께 NuGet 패키지를 빌드하려면 `-c`/`--configuration` 스위치를 추가하고 `release`를 인수로 사용하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-118">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="4460b-119">이제 `/bin` 폴더에 릴리스 이진 파일과 함께 NuGet 패키지를 포함하는 `release` 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-119">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="4460b-120">또한 NuGet 패키지를 게시하는 데 필요한 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="4460b-121">`dotnet pack`을 다음과 혼동하지 마세요.`dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="4460b-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="4460b-122">어떤 지점에서도 `dotnet publish` 명령은 관련되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="4460b-123">`dotnet publish` 명령은 동일한 번들에 있는 모든 종속성과 함께 응용 프로그램을 배포하기 위한 것이며 NuGet을 통해 배포하고 사용할 NuGet 패키지를 생성하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4460b-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>
