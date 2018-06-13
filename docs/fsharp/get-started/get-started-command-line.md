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
# <a name="get-started-with-f-with-the-net-core-cli"></a>F #으로.NET Core CLI 시작

이 문서에서는 어떻게 시작할 수 있는 F #을 사용한.NET Core CLI 모든 운영 체제 (Windows, macOS 등 또는 Linux)에서 설명 합니다. 콘솔 응용 프로그램에 의해 호출 되는 클래스 라이브러리와 다중 프로젝트 솔루션을 구축를 거치게 됩니다.

## <a name="prerequisites"></a>전제 조건

를 시작 하려면 설치 해야는 [.NET Core SDK 1.0 이상](https://www.microsoft.com/net/download/)합니다. 함께 설치를 지 원하는.NET Core SDK의 이전 버전을 제거할 않아도가 됩니다.

이 문서는 방법을 알고 있다고 가정 하는 명령줄을 사용 하 고 기본 텍스트 편집기입니다. 이미 사용 하지 않으면 [Visual Studio Code](https://code.visualstudio.com) F #에 대 한 텍스트 편집기로 유용한 옵션입니다. IntelliSense, 더 나은 구문 강조 표시 등에 같은 훌륭한 기능을 가져오려면 다운로드할 수 있습니다는 [Ionide 확장](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다.

## <a name="build-a-simple-multi-project-solution"></a>단순한 다중 프로젝트 솔루션을 구축

명령 프롬프트/터미널을 열고 사용는 [dotnet 새](../../core/tools/dotnet-new.md) 라는 솔루션 파일을 새 명령을 `FSNetCore`:

```
dotnet new sln -o FSNetCore
```

다음과 같은 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.

```
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>클래스 라이브러리 작성

디렉터리 *FSNetCore*합니다.

사용 하 여는 `dotnet new` 명령에서 클래스 라이브러리 프로젝트를 만들기는 **src** 라이브러리 라는 폴더입니다.

```
dotnet new lib -lang F# -o src/Library
```

다음과 같은 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.

```
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

내용을 대체 `Library.fs` 를 다음 코드로:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

라이브러리 프로젝트에서 Newtonsoft.Json NuGet 패키지를 추가 합니다.

```
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

추가 `Library` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 [dotnet sln 추가](../../core/tools/dotnet-sln.md) 명령:

```
dotnet sln add src/Library/Library.fsproj
```

사용 하 여 NuGet 종속성을 복원는 `dotnet restore` 명령 ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>클래스 라이브러리를 사용 하는 콘솔 응용 프로그램 작성

사용 하 여는 `dotnet new` 명령에서 콘솔 응용 프로그램을 만듭니다는 **src** 앱 라는 폴더입니다.

```
dotnet new console -lang F# -o src/App
```

다음과 같은 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.

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

내용을 대체는 `Program.fs` 를 다음 코드로 파일:

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

에 대 한 참조 추가 `Library` 를 사용 하 여 프로젝트 [dotnet 참조 추가](../../core/tools/dotnet-add-reference.md)합니다.

```
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

추가 `App` 에 프로젝트는 `FSNetCore` 사용 하 여 솔루션의 `dotnet sln add` 명령:

```
dotnet sln add src/App/App.fsproj
```

NuGet 종속성을 복원 `dotnet restore` ([참고 참조](#dotnet-restore-note)) 및 실행 `dotnet build` 프로젝트를 빌드합니다.

디렉터리를 변경 하는 `src/App` 프로젝트 콘솔을 전달 하 여 프로젝트를 실행 `Hello World` 인수로:

```
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