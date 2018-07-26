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
# <a name="get-started-with-f-with-the-net-core-cli"></a>.NET Core CLI와 함께 F # 시작

이 문서에서는 어떻게 시작할 수 있습니다 F #을 사용한.NET Core CLI를 사용 하 여 모든 운영 체제 (Windows, macOS 또는 Linux)에서 다룹니다. 콘솔 응용 프로그램에 의해 호출 되는 클래스 라이브러리를 사용 하 여 다중 프로젝트 솔루션 빌드를 거치게 됩니다.

## <a name="prerequisites"></a>전제 조건

시작 하려면 최신 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download/)합니다.

이 문서는 방법을 알고 있다고 가정 하 고 명령줄을 사용 하 여 원하는 텍스트 편집기. 이미 사용 하지 않는 경우 [Visual Studio Code](get-started-vscode.md) F #에 대 한 텍스트 편집기로 유용한 옵션입니다.

## <a name="build-a-simple-multi-project-solution"></a>간단한 다중 프로젝트 솔루션을 구축

명령 프롬프트/터미널을 열고 사용 합니다 [새 dotnet](../../core/tools/dotnet-new.md) 이라는 새 솔루션 파일을 만들려면 명령 `FSNetCore`:

```console
dotnet new sln -o FSNetCore
```

이전 명령을 실행 한 후 다음 디렉터리 구조가 생성 됩니다.

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>클래스 라이브러리 작성

디렉터리를 변경 *FSNetCore*합니다.

사용 합니다 `dotnet new` 명령, 클래스 라이브러리 프로젝트를 만들기는 **src** 라이브러리 라는 폴더입니다.

```console
dotnet new lib -lang F# -o src/Library
```

이전 명령을 실행 한 후 다음 디렉터리 구조가 생성 됩니다.

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

내용을 바꿉니다 `Library.fs` 다음 코드를 사용 하 여:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

라이브러리 프로젝트에 Newtonsoft.Json NuGet 패키지를 추가 합니다.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

추가 합니다 `Library` 프로젝트를 합니다 `FSNetCore` 사용 하 여 솔루션을 [dotnet sln 추가](../../core/tools/dotnet-sln.md) 명령:

```console
dotnet sln add src/Library/Library.fsproj
```

실행 `dotnet build` 프로젝트를 빌드합니다. 확인 되지 않은 종속성을 빌드할 때 복원 됩니다.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>클래스 라이브러리를 사용 하는 콘솔 응용 프로그램 작성

사용 합니다 `dotnet new` 명령에서 콘솔 응용 프로그램을 만들기는 **src** 앱 라는 폴더입니다.

```console
dotnet new console -lang F# -o src/App
```

이전 명령을 실행 한 후 다음 디렉터리 구조가 생성 됩니다.

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

내용을 대체 합니다 `Program.fs` 를 다음 코드로 파일:

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

에 대 한 참조를 추가 합니다 `Library` 사용 하 여 프로젝트 [참조를 추가 하는 dotnet](../../core/tools/dotnet-add-reference.md)합니다.

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

추가 합니다 `App` 프로젝트를 합니다 `FSNetCore` 사용 하 여 솔루션을 `dotnet sln add` 명령:

```console
dotnet sln add src/App/App.fsproj
```

NuGet 종속성을 복원 `dotnet restore` ([참고](#dotnet-restore-note))를 실행 하 고 `dotnet build` 프로젝트를 빌드합니다.

디렉터리를 변경 합니다 `src/App` 전달 프로젝트를 실행 하 고 프로젝트를 콘솔 `Hello World` 인수로:

```console
cd src/App
dotnet run Hello World
```

다음과 같은 결과가 표시 됩니다.

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>다음 단계

다음으로 체크 아웃 합니다 [F # 둘러보기](../tour.md) 다양 한 F # 기능에 자세히 알아보려면 합니다.