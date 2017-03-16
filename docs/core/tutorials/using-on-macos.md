---
title: "macOS에서 .NET Core 시작"
description: "Visual Studio Code를 사용하여 macOS에서 .NET Core 시작"
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 02/08/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8ad82148-dac8-4b31-9128-b0e9610f4d9b
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: c4d1b7690ca87f2a1a9ced4d82e47aee2f7ecc9f
ms.lasthandoff: 03/07/2017

---

# <a name="getting-started-with-net-core-on-macos-using-visual-studio-code"></a>Visual Studio Code를 사용하여 macOS에서 .NET Core 시작

이 문서에서는 [Visual Studio Code](http://code.visualstudio.com)를 사용하여 .NET Core 솔루션을 만드는 단계와 워크플로를 안내합니다.
프로젝트 만들기, 단위 테스트 만들기, 디버깅 도구 사용, [NuGet](http://nuget.org)을 통해 타사 라이브러리 통합 등을 배웁니다.

이 문서에서는 Mac OS에서 Visual Studio Code를 사용합니다. 차이가 있는 경우 Windows 플랫폼에 대한 차이를 가리킵니다.

## <a name="prerequisites"></a>필수 조건

시작하기 전에, [.NET Core SDK](https://www.microsoft.com/net/core)를 설치해야 합니다. .NET Core SDK에는 최신 버전의 .NET Core 프레임워크 및 런타임이 포함되어 있습니다.

[Visual Studio Code](http://code.visualstudio.com)도 설치해야 합니다.
이 문서를 진행하면서 .NET Core 개발자 환경을 개선할 확장도 설치하게 됩니다.

## <a name="getting-started"></a>시작

이 자습서의 소스는 [GitHub](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/golden)에서 이용할 수 있습니다.

Visual Studio Code를 시작합니다. Ctrl + '\`'(역따옴표)를 눌러 VS Code에서 포함된 터미널을 엽니다. 또는 원하는 경우 별도의 터미널 창을 사용할 수도 있습니다.

작업을 완료하면 세 개의 프로젝트, 즉 라이브러리 프로젝트, 해당 라이브러리 프로젝트에 대한 테스트, 그리고 라이브러리를 사용할 수 있게 하는 콘솔 응용 프로그램을 만들게 됩니다. 

폴더를 만드는 것으로 시작해 보겠습니다. 터미널에서 'golden' 디렉터리를 만듭니다. VS Code에서 *golden* 디렉터리를 엽니다. 이 디렉터리는 솔루션의 루트입니다. [`dotnet new`](../tools/dotnet-new.md) 명령을 실행하여 새 솔루션을 만듭니다.

```
dotnet new sln
```

이 명령은 전체 솔루션에 대한 *golden.sln* 파일을 만듭니다.

다음 작업은 라이브러리를 만드는 것입니다. 터미널 창(VS Code의 포함된 터미널 또는 다른 터미널)에서 *golden/*으로 이동하고 다음 명령을 입력합니다.

```
dotnet new classlib -o library
```

그러면 두 개의 파일(*library.csproj* 및 *Class1.cs*)과 함께 라이브러리 프로젝트가 *library* 디렉터리에 생성됩니다. 해당 라이브러리 프로젝트를 솔루션에 포함할 수 있습니다. [`dotnet sln`](../tools/dotnet-sln.md) 명령을 실행하여 새로 만든 *library.csproj* 프로젝트를 솔루션에 추가합니다.

```
dotnet sln add library/library.csproj
```

만든 프로젝트를 검토해 봅시다. *library.csproj* 파일에는 다음 정보가 들어 있습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

이 프로젝트는 개체의 JSON 표현 방식을 사용하므로, 사용자는 `Newtonsoft.Json` NuGet 패키지에 참조를 추가할 수 있습니다. `dotnet add` 명령은 프로젝트에 새 항목을 추가합니다. NuGet 패키지에 참조를 추가하려면 `package` 명령을 사용하여 패키지의 이름을 지정합니다. 

```
dotnet add library package Newtonsoft.Json
```

그러면 `Newtonsoft.Json` 및 해당 종속성이 라이브러리 프로젝트에 추가됩니다. 또는 *library.csproj* 파일을 수동으로 편집하고 다음 노드를 추가할 수 있습니다.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json">
    <Version>9.0.1</Version>
  </PackageReference>
</ItemGroup>
```

이러한 종속성 추가를 완료한 후 작업 영역에 패키지를 설치해야 합니다. `dotnet restore` 명령을 실행하여 모든 종속성을 업데이트하고, *obj/project.assets.json* 파일을 만들어 프로젝트 디렉터리에 저장합니다. 이 파일에는 프로젝트의 모든 종속성에 대한 전체 종속성 트리가 포함됩니다. 이 파일을 읽을 필요는 없습니다. .NET Core SDK의 도구에서 이 파일을 사용합니다.

이제 C# 코드를 업데이트해 보겠습니다. 하나의 공용 메서드를 포함하는 `Thing` 클래스를 만들어 보겠습니다. 이 메서드는 두 숫자의 합을 반환하지만, 그 과정에서 해당 숫자를 JSON 문자열로 변환하고 역직렬화합니다. *Class1.cs* 파일의 이름을 *Thing.cs*로 바꿉니다. 그런 다음 기존 코드(템플릿에서 생성된 Class1)를 다음으로 바꿉니다.

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

여기에는 static 사용, 식 본문 멤버, 보간된 문자열 등 최신 C# 기능이 사용되며, 이러한 기능은 [C# 배우기](../../csharp/index.md) 섹션에서 배울 수 있습니다.

이제 코드를 업데이트했으므로 `dotnet build`를 사용하여 라이브러리를 빌드할 수 있습니다.

이제 *golden/library/bin/Debug/netstandard1.4*에 *library.dll* 파일을 만들었습니다.

### <a name="writing-the-test-project"></a>테스트 프로젝트 작성

빌드한 라이브러리에 대한 테스트 프로젝트를 빌드해 보겠습니다. *golden* 디렉터리로 변경합니다. `dotnet new xunit -o test-library`를 실행하여 새 테스트 프로젝트를 만듭니다. `dotnet sln add test-library/test-library.csproj`를 실행하여 이 프로젝트를 솔루션에 추가할 수도 있습니다.

위 단계에서 작성한 라이브러리에 대한 종속성 노드를 추가해야 합니다. `dotnet add reference` 명령은 다음 작업을 수행합니다.

```
dotnet add test-library/test-library.csproj reference library/library.csproj
```

또는 *test-library.csproj* 파일을 수동으로 편집하고 다음 노드를 추가할 수 있습니다.

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

`library` 노드는 이 종속성을 현재 작업 영역의 프로젝트로 확인해야 함을 지정합니다. 이를 명시적으로 지정하지 않으면 테스트 프로젝트가 같은 이름의 NuGet 패키지에 대해 빌드될 수 있습니다.

이제 종속성은 제대로 구성되었으므로 라이브러리에 대한 테스트를 만들어 보겠습니다. *UnitTest1.cs*를 열고 내용을 다음 코드로 바꿉니다.

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.Equal(42, new Thing().Get(19, 23));
        }
    }
}
```

이제 `dotnet restore` 및 `dotnet build`를 실행합니다. 이러한 명령은 모든 프로젝트를 재귀적으로 찾아 종속성을 복원하고 빌드합니다.
마지막으로 `dotnet test test-library/test-library.csproj`를 실행하여 테스트를 실행합니다.
xUnit 콘솔 Test Runner가 하나의 테스트를 실행하고 통과를 보고합니다. 

### <a name="writing-the-console-app"></a>콘솔 앱 작성

터미널에서 `dotnet new console -o app`을 실행하여 새 콘솔 응용 프로그램을 만듭니다. 또한 이 프로젝트는 솔루션의 일부이므로 `dotnet sln add app/app.csproj`를 실행하여 솔루션에 프로젝트를 추가합니다.

콘솔 응용 프로그램은 이전 단계에서 빌드하고 테스트한 라이브러리에 종속됩니다. `dotnet add reference`를 다시 실행하여 나타내야 합니다.

```
dotnet add app/app.csproj reference library/library.csproj
```

`dotnet restore`를 실행하여 모든 종속성을 복원합니다. *program.cs*를 열고 `Main` 메서드의 내용을 다음 줄로 바꿉니다.

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

파일 상단에 `using` 지시문 두 줄을 추가해야 합니다.

```csharp
using static System.Console;
using Library;
```

그런 다음 `dotnet build`를 실행합니다. 어셈블리가 만들어지며 `dotnet run -p app/app.csproj`을 입력하여 실행 파일을 실행할 수 있습니다.
`dotnet run`에 대한 `-p` 인수는 주 응용 프로그램에 대한 프로젝트를 지정합니다.

### <a name="debugging-your-application"></a>응용 프로그램 디버깅

C# 확장을 통해 VS Code에서 코드를 디버깅할 수 있습니다.
`F1`을 눌러 VS Code 팔레트를 열어서 이 확장을 설치합니다. `ext install`을 입력하여 확장의 목록을 표시합니다. C# 확장을 선택합니다. 자세한 내용은 [Visual Studio Code C# 확장 문서](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) 페이지를 참조하세요.

확장을 설치하면 VS Code가 응용 프로그램을 다시 시작하여 새 확장을 로드할지를 물어봅니다. 확장이 설치되면 디버거 탭을 열 수 있습니다(그림 참조).

![VS Code 디버거](./media/using-on-macos/vscodedebugger.png)

`Main`의 `WriteLine` 문에 중단점을 설정합니다. `F9` 키를 누르거나 중단점을 추가할 줄의 왼쪽 여백에서 마우스를 클릭하면 됩니다. VS Code 화면 왼쪽에 있는 디버그 아이콘을 눌러 디버거를 엽니다(그림 참조). 디버거에서 응용 프로그램을 시작하려면 재생 단추를 누릅니다.

중단점에 도달합니다. `Get` 메서드를 단계별로 실행하며 올바른 인수를 전달했는지 확인합니다. 답이 실제로 42인지 확인합니다.

