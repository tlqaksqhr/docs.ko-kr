---
title: '명령줄 도구를 사용 하 여 F #을 사용 하 여 시작'
description: '.NET Core CLI를 사용 하 여 모든 운영 체제 (Windows, macOs 또는 Linux)에서 F #에서 간단한 다중 프로젝트 솔루션을 빌드하는 방법에 알아봅니다.'
ms.date: 03/26/2018
ms.openlocfilehash: 6cdb2b42781dba6ba00c03b20e6a76d033e03063
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37875016"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="cd5cd-103">.NET Core CLI와 함께 F # 시작</span><span class="sxs-lookup"><span data-stu-id="cd5cd-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="cd5cd-104">이 문서에서는 어떻게 시작할 수 있습니다 F #을 사용한.NET Core CLI를 사용 하 여 모든 운영 체제 (Windows, macOS 또는 Linux)에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="cd5cd-105">콘솔 응용 프로그램에 의해 호출 되는 클래스 라이브러리를 사용 하 여 다중 프로젝트 솔루션 빌드를 거치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd5cd-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="cd5cd-106">Prerequisites</span></span>

<span data-ttu-id="cd5cd-107">시작 하려면 최신 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download/)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-107">To begin, you must install the latest [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

<span data-ttu-id="cd5cd-108">이 문서는 방법을 알고 있다고 가정 하 고 명령줄을 사용 하 여 원하는 텍스트 편집기.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="cd5cd-109">이미 사용 하지 않는 경우 [Visual Studio Code](get-started-vscode.md) F #에 대 한 텍스트 편집기로 유용한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="cd5cd-110">간단한 다중 프로젝트 솔루션을 구축</span><span class="sxs-lookup"><span data-stu-id="cd5cd-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="cd5cd-111">명령 프롬프트/터미널을 열고 사용 합니다 [새 dotnet](../../core/tools/dotnet-new.md) 이라는 새 솔루션 파일을 만들려면 명령 `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="cd5cd-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```console
dotnet new sln -o FSNetCore
```

<span data-ttu-id="cd5cd-112">이전 명령을 실행 한 후 다음 디렉터리 구조가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="cd5cd-113">클래스 라이브러리 작성</span><span class="sxs-lookup"><span data-stu-id="cd5cd-113">Write a class library</span></span>

<span data-ttu-id="cd5cd-114">디렉터리를 변경 *FSNetCore*합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="cd5cd-115">사용 합니다 `dotnet new` 명령, 클래스 라이브러리 프로젝트를 만들기는 **src** 라이브러리 라는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```console
dotnet new lib -lang F# -o src/Library
```

<span data-ttu-id="cd5cd-116">이전 명령을 실행 한 후 다음 디렉터리 구조가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="cd5cd-117">내용을 바꿉니다 `Library.fs` 다음 코드를 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="cd5cd-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="cd5cd-118">라이브러리 프로젝트에 Newtonsoft.Json NuGet 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="cd5cd-119">추가 합니다 `Library` 프로젝트를 합니다 `FSNetCore` 사용 하 여 솔루션을 [dotnet sln 추가](../../core/tools/dotnet-sln.md) 명령:</span><span class="sxs-lookup"><span data-stu-id="cd5cd-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```console
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="cd5cd-120">실행 `dotnet build` 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="cd5cd-121">확인 되지 않은 종속성을 빌드할 때 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="cd5cd-122">클래스 라이브러리를 사용 하는 콘솔 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="cd5cd-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="cd5cd-123">사용 합니다 `dotnet new` 명령에서 콘솔 응용 프로그램을 만들기는 **src** 앱 라는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```console
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="cd5cd-124">이전 명령을 실행 한 후 다음 디렉터리 구조가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-124">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="cd5cd-125">내용을 대체 합니다 `Program.fs` 를 다음 코드로 파일:</span><span class="sxs-lookup"><span data-stu-id="cd5cd-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

<span data-ttu-id="cd5cd-126">에 대 한 참조를 추가 합니다 `Library` 사용 하 여 프로젝트 [참조를 추가 하는 dotnet](../../core/tools/dotnet-add-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="cd5cd-127">추가 합니다 `App` 프로젝트를 합니다 `FSNetCore` 사용 하 여 솔루션을 `dotnet sln add` 명령:</span><span class="sxs-lookup"><span data-stu-id="cd5cd-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```console
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="cd5cd-128">NuGet 종속성을 복원 `dotnet restore` ([참고](#dotnet-restore-note))를 실행 하 고 `dotnet build` 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-128">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="cd5cd-129">디렉터리를 변경 합니다 `src/App` 전달 프로젝트를 실행 하 고 프로젝트를 콘솔 `Hello World` 인수로:</span><span class="sxs-lookup"><span data-stu-id="cd5cd-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="cd5cd-130">다음과 같은 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="cd5cd-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="cd5cd-131">Next steps</span></span>

<span data-ttu-id="cd5cd-132">다음으로 체크 아웃 합니다 [F # 둘러보기](../tour.md) 다양 한 F # 기능에 자세히 알아보려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5cd-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>