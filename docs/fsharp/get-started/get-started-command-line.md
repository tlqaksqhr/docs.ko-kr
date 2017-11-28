---
title: "F #을 사용한 명령줄 도구 시작"
description: "F # 플랫폼 간.NET Core CLI를 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍, .NET, .NET Core"
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: a23d4861ce599f20f37ecd0564a0187e7b9b739f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="eb46c-104">F #으로.NET Core CLI 시작</span><span class="sxs-lookup"><span data-stu-id="eb46c-104">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="eb46c-105">이 문서에서는 어떻게 시작할 수 있습니다를 사용 하 여 F #에서.NET Core와 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-105">This article covers how you can get started with using F# on .NET Core.</span></span> <span data-ttu-id="eb46c-106">콘솔 응용 프로그램에 의해 호출 되는 클래스 라이브러리와 다중 프로젝트 솔루션을 구축를 거치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-106">It will go through building a multi-project solution with a Class Library that is called by a Console Application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb46c-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="eb46c-107">Prerequisites</span></span>

<span data-ttu-id="eb46c-108">를 시작 하려면 설치 해야는 [.NET Core SDK 1.0 이상](https://dot.net/core)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-108">To begin, you must install the [.NET Core SDK 1.0 or later](https://dot.net/core).</span></span> <span data-ttu-id="eb46c-109">함께 설치를 지 원하는.NET Core SDK의 이전 버전을 제거할 않아도가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-109">There is no need to uninstall a previous version of the .NET Core SDK, as it supports side-by-side installations.</span></span>

<span data-ttu-id="eb46c-110">이 문서는 방법을 알고 있다고 가정 하는 명령줄을 사용 하 고 기본 텍스트 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-110">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="eb46c-111">이미 사용 하지 않으면 [Visual Studio Code](https://code.visualstudio.com) F #에 대 한 텍스트 편집기로 유용한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-111">If you don't already use it, [Visual Studio Code](https://code.visualstudio.com) is a great option as a text editor for F#.</span></span> <span data-ttu-id="eb46c-112">IntelliSense, 더 나은 구문 강조 표시 등에 같은 훌륭한 기능을 가져오려면 다운로드할 수 있습니다는 [Ionide 확장](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-112">To get awesome features like IntelliSense, better syntax highlighting, and more, you can download the [Ionide Extension](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span>

## <a name="building-a-simple-multi-project-solution"></a><span data-ttu-id="eb46c-113">단순한 다중 프로젝트 솔루션을 구축</span><span class="sxs-lookup"><span data-stu-id="eb46c-113">Building a Simple Multi-project Solution</span></span>

<span data-ttu-id="eb46c-114">명령 프롬프트/터미널을 열고 사용 하는 `dotnet new` 라는 솔루션 파일을 새 명령을 `FSNetCore`:</span><span class="sxs-lookup"><span data-stu-id="eb46c-114">Open a command prompt/terminal and use the `dotnet new` command to create new solution file called `FSNetCore`:</span></span>

```
dotnet new sln -o FSNetCore
```

<span data-ttu-id="eb46c-115">다음 디렉터리 구조 명령 완료의 결과로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-115">The folowing directory structure is produced as a result of the command completing:</span></span>

```
FSNetCore
    ├── FSNetCore.sln
```

<span data-ttu-id="eb46c-116">디렉터리 *FSNetCore* 솔루션 폴더에 프로젝트를 추가 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-116">Change directories to *FSNetCore* and start adding projects to the solution folder.</span></span>
 
### <a name="writing-a-class-library"></a><span data-ttu-id="eb46c-117">클래스 라이브러리 작성</span><span class="sxs-lookup"><span data-stu-id="eb46c-117">Writing a Class library</span></span>

<span data-ttu-id="eb46c-118">사용 하 여는 `dotnet new` 명령에서에서 클래스 라이브러리 프로젝트를 만들는 **src** 라이브러리 라는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-118">Use the `dotnet new` command, create a Class Library project in the **src** folder named Library.</span></span> 

```bash
dotnet new lib -lang F# -o src/Library 
```

<span data-ttu-id="eb46c-119">다음과 같은 디렉터리 구조 명령 완료의 결과로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-119">The following directory structure is produced as a result of the command completing:</span></span>

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="eb46c-120">내용을 대체 `Library.fs` 다음:</span><span class="sxs-lookup"><span data-stu-id="eb46c-120">Replace the contents of `Library.fs` with the following:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="eb46c-121">라이브러리 프로젝트에서 Newtonsoft.Json NuGet 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-121">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="eb46c-122">추가 `Library` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 `dotnet sln add` 명령:</span><span class="sxs-lookup"><span data-stu-id="eb46c-122">Add the `Library` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="eb46c-123">NuGet 종속성을 복원 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-123">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

### <a name="writing-a-console-application-which-consumes-the-class-library"></a><span data-ttu-id="eb46c-124">클래스 라이브러리를 사용 하는 콘솔 응용 프로그램을 작성</span><span class="sxs-lookup"><span data-stu-id="eb46c-124">Writing a Console Application which Consumes the Class Library</span></span>

<span data-ttu-id="eb46c-125">사용 하 여는 `dotnet new` 명령에의 콘솔 응용 프로그램 만들기는 **src** 앱 라는 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-125">Use the `dotnet new` command, create a Console app in the **src** folder named App.</span></span> 

```bash
dotnet new console -lang F# -o src/App 
```

<span data-ttu-id="eb46c-126">다음과 같은 디렉터리 구조 명령 완료의 결과로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-126">The following directory structure is produced as a result of the command completing:</span></span>

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

<span data-ttu-id="eb46c-127">변경 `Program.fs` 에:</span><span class="sxs-lookup"><span data-stu-id="eb46c-127">Change `Program.fs` to:</span></span>

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

<span data-ttu-id="eb46c-128">에 대 한 참조 추가 `Library` 를 사용 하 여 프로젝트 `dotnet add reference`합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-128">Add a reference to the `Library` project using `dotnet add reference`.</span></span>

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="eb46c-129">추가 `App` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 `dotnet sln add` 명령:</span><span class="sxs-lookup"><span data-stu-id="eb46c-129">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```bash
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="eb46c-130">NuGet 종속성을 복원 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-130">Restore the NuGet dependencies, `dotnet restore` ([see note](#dotnet-restore-note)) and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="eb46c-131">디렉터리를 변경 하는 `src/App` 프로젝트 콘솔을 전달 하 여 프로젝트를 실행 `Hello World` 인수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-131">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments.</span></span>

```bash
cd src/App
dotnet run Hello World
``` 

<span data-ttu-id="eb46c-132">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eb46c-132">You should see the following results:</span></span>

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]