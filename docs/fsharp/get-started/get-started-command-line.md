---
title: 'F #을 사용한 명령줄 도구 시작'
description: '.NET Core CLI를 사용 하 여 모든 운영 체제 (Windows, macOs 또는 Linux)에서 F #에서 간단한 다중 프로젝트 솔루션을 구축 하는 방법에 알아봅니다.'
ms.date: 03/26/2018
ms.openlocfilehash: 35ec2313742a0b14c92f3de2662a16aff389b214
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562039"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="c6363-103">F #으로.NET Core CLI 시작</span><span class="sxs-lookup"><span data-stu-id="c6363-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="c6363-104">이 문서에서는 어떻게 시작할 수 있는 F #을 사용한.NET Core CLI 모든 운영 체제 (Windows, macOS 등 또는 Linux)에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="c6363-105">콘솔 응용 프로그램에 의해 호출 되는 클래스 라이브러리와 다중 프로젝트 솔루션을 구축를 거치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6363-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="c6363-106">Prerequisites</span></span>

<span data-ttu-id="c6363-107">를 시작 하려면 설치 해야는 [.NET Core SDK 1.0 이상](https://www.microsoft.com/net/download/)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-107">To begin, you must install the [.NET Core SDK 1.0 or later](https://www.microsoft.com/net/download/).</span></span> <span data-ttu-id="c6363-108">함께 설치를 지 원하는.NET Core SDK의 이전 버전을 제거할 않아도가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-108">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="c6363-109">이 문서는 방법을 알고 있다고 가정 하는 명령줄을 사용 하 고 기본 텍스트 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-109">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="c6363-110">이미 사용 하지 않으면 [Visual Studio Code](https://code.visualstudio.com) F #에 대 한 텍스트 편집기로 유용한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-110">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="c6363-111">IntelliSense, 더 나은 구문 강조 표시 등에 같은 훌륭한 기능을 가져오려면 다운로드할 수 있습니다는 [Ionide 확장](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-111">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="c6363-112">단순한 다중 프로젝트 솔루션을 구축</span><span class="sxs-lookup"><span data-stu-id="c6363-112">Build a simple multi-project solution</span></span>

<span data-ttu-id="c6363-113">명령 프롬프트/터미널을 열고 사용는 [dotnet 새](../../core/tools/dotnet-new.md) 라는 솔루션 파일을 새 명령을 `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="c6363-113">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="c6363-114">다음과 같은 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-114">The following directory structure is produced after running the previous command:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="c6363-115">클래스 라이브러리 작성</span><span class="sxs-lookup"><span data-stu-id="c6363-115">Write a class library</span></span>

<span data-ttu-id="c6363-116">디렉터리 *FSNetCore*합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-116">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="c6363-117">사용 하 여는 `dotnet new` 명령에서 클래스 라이브러리 프로젝트를 만들기는 **src** 라이브러리 라는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-117">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```
dotnet new lib -lang F# -o src/Library
```

<span data-ttu-id="c6363-118">다음과 같은 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-118">The following directory structure is produced after running the previous command:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="c6363-119">내용을 대체 `Library.fs` 를 다음 코드로:</span><span class="sxs-lookup"><span data-stu-id="c6363-119">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="c6363-120">라이브러리 프로젝트에서 Newtonsoft.Json NuGet 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-120">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="c6363-121">추가 `Library` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 [dotnet sln 추가](../../core/tools/dotnet-sln.md) 명령:</span><span class="sxs-lookup"><span data-stu-id="c6363-121">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="c6363-122">사용 하 여 NuGet 종속성을 복원는 `dotnet restore` 명령 ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-122">Restore the NuGet dependencies using the `dotnet restore` command ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="c6363-123">클래스 라이브러리를 사용 하는 콘솔 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="c6363-123">Write a console application that consumes the class library</span></span>

<span data-ttu-id="c6363-124">사용 하 여는 `dotnet new` 명령에서 콘솔 응용 프로그램을 만듭니다는 **src** 앱 라는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-124">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```
dotnet new console -lang F# -o src/App
```

<span data-ttu-id="c6363-125">다음과 같은 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-125">The following directory structure is produced after running the previous command:</span></span>

```
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

<span data-ttu-id="c6363-126">내용을 대체는 `Program.fs` 를 다음 코드로 파일:</span><span class="sxs-lookup"><span data-stu-id="c6363-126">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="c6363-127">에 대 한 참조 추가 `Library` 를 사용 하 여 프로젝트 [dotnet 참조 추가](../../core/tools/dotnet-add-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-127">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="c6363-128">추가 `App` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 `dotnet sln add` 명령:</span><span class="sxs-lookup"><span data-stu-id="c6363-128">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="c6363-129">NuGet 종속성을 복원 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-129">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="c6363-130">디렉터리를 변경 하는 `src/App` 프로젝트 콘솔을 전달 하 여 프로젝트를 실행 `Hello World` 인수로:</span><span class="sxs-lookup"><span data-stu-id="c6363-130">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```
cd src/App
dotnet run Hello World
```

<span data-ttu-id="c6363-131">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c6363-131">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]