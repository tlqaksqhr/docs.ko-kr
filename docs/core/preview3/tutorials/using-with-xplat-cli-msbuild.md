---
title: "명령줄(SDK Preview 3)을 사용하여 Windows/Linux/macOS에서 .NET Core 시작"
description: "CLI(명령줄 인터페이스)를 사용하여 Windows, Linux 또는 macOS에서 .NET Core 시작"
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: be988f09-7349-43b0-97fb-3a703d4587ce
translationtype: Human Translation
ms.sourcegitcommit: ab71aab99505f211fe4adc86957eda4707761f1c
ms.openlocfilehash: 01b17021e79bcdb2dc69f97b709f4aa63dbab9aa

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line-sdk-preview-3"></a>명령줄(SDK Preview 3)을 사용하여 Windows/Linux/macOS에서 .NET Core 시작

이 가이드에서는 .NET Core CLI 도구를 사용하여 플랫폼 간 콘솔 앱을 빌드하는 방법을 보여 줍니다.  가장 기본적인 콘솔 앱으로 시작하여 테스트를 비롯한 여러 프로젝트로 확장됩니다. 이러한 기능을 단계별로 추가하며, 이미 확인하고 빌드한 것 위에서 빌드하게 됩니다.

.NET Core CLI 도구 집합에 익숙하지 않은 경우 [.NET Core SDK 개요](../tools/dotnet.md)를 읽어 보세요.

## <a name="prerequisites"></a>필수 구성 요소

시작하기 전에 [.NET Core CLI 도구 Preview 3 이상](https://github.com/dotnet/core/blob/master/release-notes/preview3-download.md)이 있는지 확인합니다.  텍스트 편집기도 필요합니다.

## <a name="hello-console-app"></a>Hello, 콘솔 앱!

먼저, 원하는 이름의 폴더로 이동하거나 폴더를 새로 만듭니다.  "Hello"는 샘플 코드에 대해 선택한 이름으로, [여기](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild)서 찾을 수 있습니다.

명령 프롬프트를 열고 다음을 입력합니다.

```
$ dotnet new
$ dotnet restore
$ dotnet run
```

이제 간단한 연습을 해보겠습니다.

1. `$ dotnet new`

   [`dotnet new`](../tools/dotnet-new.md)는 콘솔 앱을 빌드하는 데 필요한 종속성이 있는 최신 `Hello.csproj` 프로젝트 파일입니다.  응용 프로그램에 대한 진입점을 포함하는 기본 파일인 `Program.cs`도 만듭니다.
   
   `Hello.csproj`:
   ```xml
    <Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
        <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
        
        <PropertyGroup>
            <OutputType>Exe</OutputType>
            <TargetFramework>netcoreapp1.0</TargetFramework>
        </PropertyGroup>

        <ItemGroup>
            <Compile Include="**\*.cs" />
            <EmbeddedResource Include="**\*.resx" />
        </ItemGroup>

        <ItemGroup>
            <PackageReference Include="Microsoft.NETCore.App">
                <Version>1.0.1</Version>
            </PackageReference>
            <PackageReference Include="Microsoft.NET.Sdk">
                <Version>1.0.0-alpha-20161104-2</Version>
                <PrivateAssets>All</PrivateAssets>
            </PackageReference>
        </ItemGroup>
        
        <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
   ```

   프로젝트 파일은 종속성을 복원하고 프로그램을 빌드하는 데 필요한 모든 항목을 지정합니다.

   * 모든 .NET Core 프로젝트에 공통된 일부 속성에는 `Import` 태그가 제공됩니다.
   * `OutputType` 태그에서는 실행 파일, 즉 콘솔 응용 프로그램을 빌드하고 있음을 지정합니다.
   * `TargetFramework` 태그는 대상으로 지정한 .NET 런타임을 지정합니다. 고급 시나리오에서는 여러 대상 프레임워크를 지정하고 이 모든 프레임워크를 단일 작업으로 빌드할 수 있습니다. 이 자습서에서는 .NET Core 1.0에 대해서만 빌드합니다.
   * `Compile` 태그는 컴파일러에서 `.cs` 파일 확장자가 있는 현재 디렉터리와 모든 하위 디렉터리에 모든 파일, 즉 프로젝트에 있는 모든 C# 파일을 빌드하도록 합니다. 고급 시나리오에서는 파일을 제외할 수 있지만 이 자습서와 대부분의 간단한 시나리오에서 이 줄은 변경되지 않고 유지될 수 있습니다.
   * `EmbeddedResource` 태그는 빌드 시스템이 `.resx` 확장명이 포함된 지역화 파일을 컴파일된 실행 파일에 포함하도록 지시합니다. 이 자습서에서는 해당 기능을 사용하지 않겠습니다.
   * `PackageReference` 태그는 응용 프로그램을 작성할 때 복원하고 포함해야 할 종속성 패키지를 지정합니다. 각 패키지 참조에서는 `Include` 특성 아래 패키지의 이름과 버전 번호를 지정합니다. 고급 시나리오에서는 패키지 참조가 더 추가됩니다. 디스크에서 다른 프로젝트를 참조하는 것도 가능합니다.

   `Program.cs`:
   ```csharp
   using System;

   namespace ConsoleApplication
   {
       public class Program
       {
           public static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   프로그램은 `using System`으로 시작됩니다. 즉, "`System` 네임스페이스의 모든 항목을 이 파일 범위로 가져옵니다". `System` 네임스페이스에는 `string` 또는 숫자 형식과 같은 기본 구문이 포함되어 있습니다.

   그런 다음 "ConsoleApplication"이라는 네임스페이스를 정의합니다. 이 이름은 원하는 값으로 변경할 수 있습니다. "프로그램"이라는 클래스는 해당 네임스페이스 내에서 인수로 문자열 배열을 사용하는 `Main` 메서드로 정의됩니다. 이 배열에는 컴파일된 프로그램을 호출할 때 전달된 인수 목록이 포함되어 있습니다. 이 배열은 그대로 사용되지 않습니다. 프로그램은 모두 "Hello World!"를 작성합니다. 표시합니다. `Console.WriteLine`을 다음 코드로 변경하여 좀 더 재미있게 만들 수 있습니다.

   ```csharp
   if (args.Length > 0)
   {
       Console.WriteLine($"Hello {args[0]}!");
   }
   else
   {
       Console.WriteLine("Hello World!");
   }
   ```

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md)는 [NuGet](http://nuget.org)(.NET의 패키지 관리자)을 호출하여 종속성 트리를 복원합니다. NuGet은 `Hello.csproj` 파일을 분석하고, 파일에 명시된 종속성을 다운로드하고(또는 컴퓨터의 캐시에서 종속성을 가져오고), `obj/project.assets.json` 파일을 작성합니다.  `project.assets.json` 파일은 컴파일 및 실행하려면 필요합니다.
   
   `project.assets.json` 파일은 NuGet 종속성 및 앱을 설명하는 기타 정보로 구성된 그래프의 지속적이고 전체적인 집합입니다.  `dotnet build` 및 `dotnet run` 같은 다른 도구에서는 이 파일을 읽고, NuGet 종속성 및 바인딩 확인의 올바른 집합으로 소스 코드를 처리합니다.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)은 `dotnet build`를 호출하여 빌드 대상이 빌드되었는지를 확인하고 `dotnet <assembly.dll>`을 호출하여 대상 응용 프로그램을 실행합니다.
   
    ```
    $ dotnet run
    Hello World!
    ```

    또한 [`dotnet build`](../tools/dotnet-build.md)를 실행하여 빌드 콘솔 응용 프로그램을 실행하지 않고 코드를 컴파일할 수도 있습니다. 이로 인해 Windows에서는 `dotnet bin\Debug\netcoreapp1.0\Hello.dll`로, 다른 시스템에서는 `dotnet bin/Debug/netcoreapp1.0/Hello.dll`로 실행할 수 있는 `bin/Debug/netcoreapp1.0/Hello.dll` 컴파일된 응용 프로그램이 만들어 집니다. 명령줄에서 추가 매개 변수를 지정할 수 있습니다(사용자가 Windows를 사용한다고 가정).

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll .NET
    Hello .NET!
    ```

    고급 시나리오에서는 .NET Core를 설치하지 않아도 되는 컴퓨터에 배포하고 실행할 수 있는 자체 포함된 플랫폼별 파일로 응용 프로그램을 빌드할 수 있습니다. 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.

### <a name="augmenting-the-program"></a>프로그램 보강

파일을 아주 조금만 변경하겠습니다.  피보나치(Fibonacci) 숫자가 흥미로우므로 시도해 보겠습니다.

`Program.cs`:

```csharp
using static System.Console;

namespace ConsoleApplication
{
    public class Program
    {
        public static int FibonacciNumber(int n)
        {
            int a = 0;
            int b = 1;
            int tmp;
            
            for (int i = 0; i < n; i++)
            {
                tmp = a;
                a = b;
                b += tmp;
            }
            
            return a;   
        }
        
        public static void Main(string[] args)
        {
            WriteLine("Hello World!");
            WriteLine("Fibonacci Numbers 1-15:");
            
            for (int i = 0; i < 15; i++)
            {
                WriteLine($"{i+1}: {FibonacciNumber(i)}");
            }
        }
    }
}
```

프로그램을 실행합니다(플랫폼은 Windows이며 프로젝트 디렉터리 이름을 Fibonacci로 변경한 것으로 가정).

```
$ dotnet build
$ dotnet bin\Debug\netcoreapp1.0\win10-x64\Fibonacci.exe
1: 0
2: 1
3: 1
4: 2
5: 3
6: 5
7: 8
8: 13
9: 21
10: 34
11: 55
12: 89
13: 144
14: 233
15: 377
```

됐습니다!  원하는 대로 `Program.cs`를 보강할 수 있습니다.

## <a name="adding-some-new-files"></a>몇 가지 새 파일 추가

단순한 일회용 프로그램에는 단일 파일도 괜찮지만, 여러 구성 요소가 있는 프로그램을 빌드하는 경우 기능을 여러 파일로 분할해야 할 수 있습니다.  여러 파일은 이런 경우에 사용합니다.

새 파일을 만들고 고유한 네임스페이스를 지정합니다.

```csharp
using System;

namespace NumberFun
{
    // code can go here
} 
```

이런 다음 `Program.cs` 파일에 포함합니다.

```csharp
using NumberFun;
```

마지막으로 파일을 빌드할 수 있습니다.

`$ dotnet build`

이제부터가 흥미로운 부분입니다. 새 파일로 작업을 수행하는 것입니다.

### <a name="example-a-fibonacci-sequence-generator"></a>예제: 피보나치 시퀀스 생성기

일부 피보나치 값을 캐시하여 이전 피보나치 예제에서 빌드하고 약간의 재귀 기능을 추가하려 한다고 가정해 보겠습니다.  [더 나은 피보나치 예제](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/FibonacciBetterMsBuild)에 대한 코드는 다음 코드로 새 `FibonacciGenerator.cs` 파일을 사용할 수도 있습니다.

```csharp
using System;
using System.Collections.Generic;

namespace NumberFun
{
    public class FibonacciGenerator
    {
        private Dictionary<int, int> _cache = new Dictionary<int, int>();
        
        private int Fib(int n) => n < 2 ? n : FibValue(n - 1) + FibValue(n - 2);
        
        private int FibValue(int n)
        {
            if (!_cache.ContainsKey(n))
            {
                _cache.Add(n, Fib(n));
            }
            
            return _cache[n];
        }
        
        public IEnumerable<int> Generate(int n)
        {
            for (int i = 0; i < n; i++)
            {
                yield return FibValue(i);
            }
        }
    }
}
```

이제 아래와 같이 `Program.cs` 파일에서 `Main()` 메서드를 조정합니다.

```csharp
using System;
using NumberFun;

class Program
{
    static void Main(string[] args)
    {
        var generator = new FibonacciGenerator();
        foreach (var digit in generator.Generate(15))
        {
            Console.WriteLine(digit);
        }
    }
}
```

마지막으로 실행합니다!

```
$ dotnet run
0
1
1
2
3
5
8
13
21
34
55
89
144
233
377
```

됐습니다!

## <a name="conclusion"></a>결론
 
이 가이드가 기본적인 사항에서 단위 테스트가 포함된 다중 프로젝트 시스템에 이르기까지 .NET Core 콘솔 앱을 만드는 방법을 배우는 데 도움이 되었길 바랍니다.  다음 단계는 자신만의 멋진 콘솔 앱을 만드는 것입니다.
 
흥미로운 고급 콘솔 앱의 예제를 보려면 [.NET Core 명령줄(SDK Preview 3)을 사용하여 프로젝트 구성 및 테스트](using-with-xplat-cli-msbuild-folders.md) 자습서를 참조하세요.



<!--HONumber=Nov16_HO3-->


