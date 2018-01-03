---
title: "F #을 사용한 명령줄 도구 시작"
description: "플랫폼 간.NET Core CLI와 모든 OS (Windows, MacOS, Linux)에서 F #을 사용 하는 방법을 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍, .NET, .NET Core"
author: cartermp
ms.author: phcart
ms.date: 06/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 615db1ec-6ef3-4de2-bae6-4586affa9771
ms.openlocfilehash: 4820a8a306bd478429b497a8b7c70ff170c1c655
ms.sourcegitcommit: d095094e942eedf09530ea5636fbaf9029853027
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>F #으로.NET Core CLI 시작

이 문서에서는 어떻게 시작할 수 있습니다는 OS (Windows, macOS 등 또는 Linux)에서 F #.NET Core CLI를 사용 하 여 설명 합니다. 콘솔 응용 프로그램에 의해 호출 되는 클래스 라이브러리와 다중 프로젝트 솔루션을 구축를 거치게 됩니다.

## <a name="prerequisites"></a>필수 구성 요소

를 시작 하려면 설치 해야는 [.NET Core SDK 1.0 이상](https://dot.net/core)합니다. 함께 설치를 지 원하는.NET Core SDK의 이전 버전을 제거할 않아도가 됩니다.

이 문서는 방법을 알고 있다고 가정 하는 명령줄을 사용 하 고 기본 텍스트 편집기입니다. 이미 사용 하지 않으면 [Visual Studio Code](https://code.visualstudio.com) F #에 대 한 텍스트 편집기로 유용한 옵션입니다. IntelliSense, 더 나은 구문 강조 표시 등에 같은 훌륭한 기능을 가져오려면 다운로드할 수 있습니다는 [Ionide 확장](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다.

## <a name="building-a-simple-multi-project-solution"></a>단순한 다중 프로젝트 솔루션을 구축

명령 프롬프트/터미널을 열고 사용 하는 `dotnet new` 라는 솔루션 파일을 새 명령을 `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

다음 디렉터리 구조 명령 완료의 결과로 생성 됩니다.

```
FSNetCore
    ├── FSNetCore.sln
```

디렉터리 *FSNetCore* 솔루션 폴더에 프로젝트를 추가 하기 시작 합니다.
 
### <a name="writing-a-class-library"></a>클래스 라이브러리 작성

사용 하 여는 `dotnet new` 명령에서에서 클래스 라이브러리 프로젝트를 만들는 **src** 라이브러리 라는 폴더입니다. 

```bash
dotnet new lib -lang F# -o src/Library 
```

다음과 같은 디렉터리 구조 명령 완료의 결과로 생성 됩니다.

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

내용을 대체 `Library.fs` 다음:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value = 
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value  (JsonConvert.SerializeObject(value))
```

라이브러리 프로젝트에서 Newtonsoft.Json NuGet 패키지를 추가 합니다.

```bash
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

추가 `Library` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 `dotnet sln add` 명령:

```bash
dotnet sln add src/Library/Library.fsproj
```

NuGet 종속성을 복원 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.

### <a name="writing-a-console-application-which-consumes-the-class-library"></a>클래스 라이브러리를 사용 하는 콘솔 응용 프로그램을 작성

사용 하 여는 `dotnet new` 명령에의 콘솔 응용 프로그램 만들기는 **src** 앱 라는 폴더입니다. 

```bash
dotnet new console -lang F# -o src/App 
```

다음과 같은 디렉터리 구조 명령 완료의 결과로 생성 됩니다.

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

변경 `Program.fs` 에:

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

에 대 한 참조 추가 `Library` 를 사용 하 여 프로젝트 `dotnet add reference`합니다.

```bash
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

추가 `App` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 `dotnet sln add` 명령:

```bash
dotnet sln add src/App/App.fsproj
```

NuGet 종속성을 복원 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.

디렉터리를 변경 하는 `src/App` 프로젝트 콘솔을 전달 하 여 프로젝트를 실행 `Hello World` 인수로 합니다.

```bash
cd src/App
dotnet run Hello World
``` 

다음과 같은 결과가 나타납니다.

```
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```
<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
