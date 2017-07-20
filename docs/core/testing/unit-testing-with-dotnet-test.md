---
title: "Dotnet 테스트 및 xUnit을 사용하여 .NET Core에서 단위 테스트 | Microsoft Docs"
description: "Dotnet 테스트를 사용하여 .NET Core에서 단위 테스트"
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
ms.translationtype: Human Translation
ms.sourcegitcommit: 06e1ecc181847f87df9ed3a527638008ca6857fc
ms.openlocfilehash: b5c6d162adf363da41c4c60fdd9fe38e1d58d27a
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
<a id="unit-testing-in-net-core-using-dotnet-test-and-xunit" class="xliff"></a>

# Dotnet 테스트 및 xUnit을 사용하여 .NET Core에서 단위 테스트

이 자습서에서는 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 단위 테스트 개념을 알아볼 수 있습니다. 미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려는 경우 시작하기 전에 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test/). 다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.

<a id="creating-the-source-project" class="xliff"></a>

### 소스 프로젝트 만들기

셸 창을 엽니다. 솔루션을 저장하기 위한 *unit-testing-using-dotnet-test*라는 디렉터리를 만듭니다. 이 새로운 디렉터리 내에 *PrimeService* 디렉터리를 만듭니다. 따라서 지금까지의 디렉터리 구조는 다음과 같습니다.

```
/unit-testing-using-dotnet-test
    /PrimeService
```

*PrimeService*를 현재 디렉터리로 만들고 [`dotnet new classlib`](../tools/dotnet-new.md)를 실행하여 소스 프로젝트를 만듭니다. *Class1.cs*의 이름을 *PrimeService.cs*로 바꿉니다. TDD(테스트 기반 개발)를 사용하기 위해 `PrimeService` 클래스의 실패 구현을 만듭니다.

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

<a id="creating-the-test-project" class="xliff"></a>

### 테스트 프로젝트 만들기

디렉터리를 다시 *unit-testing-using-dotnet-test* 디렉터리로 변경하고 *PrimeService.Tests* 디렉터리를 만듭니다. 디렉터리 구조는 다음과 같습니다.

```
/unit-testing-using-dotnet-test
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

*PrimeService.Tests* 디렉터리를 현재 디렉터리로 만들고 [`dotnet new xunit`](../tools/dotnet-new.md)를 사용하여 새 프로젝트를 만듭니다. xUnit을 테스트 라이브러리로 사용하는 테스트 프로젝트가 만들어집니다. 생성된 템플릿이 *PrimeServiceTests.csproj*에 Test Runner를 구성했습니다.

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다. 이전 단계의 `dotnet new`는 xUnit 및 xUnit runner를 추가했습니다. 이제 `PrimeService` 클래스 라이브러리를 프로젝트에 다른 종속성으로 추가합니다. [`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

또 다른 옵션은 *PrimeService.Tests.csproj* 파일을 편집하는 것입니다. 첫 번째 `<ItemGroup>` 노드 바로 아래에서 참조와 함께 다른 `<ItemGroup>` 노드를 라이브러리 프로젝트에 추가합니다.

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

GitHub의 [샘플 리포지토리](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj)에서 전체 파일을 볼 수 있습니다.

최종 솔루션 레이아웃은 다음과 같습니다.

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

<a id="creating-the-first-test" class="xliff"></a>

## 첫 번째 테스트 만들기

라이브러리 또는 테스트를 빌드하기 전에 *PrimeService.Tests* 디렉터리에서 [`dotnet restore`](../tools/dotnet-restore.md)을 실행합니다. 이 명령은 각 프로젝트에 대해 필요한 모든 NuGet 패키지를 복원합니다.

TDD 접근 방식에서는 하나의 실패 테스트를 작성하고, 통과시키고, 이 프로세스를 반복해야 합니다. *PrimeService.Tests* 디렉터리에서 *UnitTest1.cs*를 제거하고 다음과 같은 내용으로 새 C# 파일 *PrimeService_IsPrimeShould.cs*를 만듭니다.

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

`[Fact]` 특성은 메서드를 단일 테스트로 나타냅니다. [`dotnet test`](../tools/dotnet-test.md)를 실행하여 테스트 및 클래스 라이브러리를 빌드한 다음 테스트를 실행합니다. xUnit Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다. `dotnet test`는 Test Runner를 시작하고, 테스트가 포함된 어셈블리를 나타내는 Test Runner에 명령줄 인수를 제공합니다.

테스트가 실패합니다. 구현은 아직 만들지 않았습니다. 이 테스트를 통과시킬 가장 간단한 코드를 `PrimeService` 클래스에 작성합니다.

```csharp
public bool IsPrime(int candidate) 
{
    if (candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

*PrimeService.Tests* 디렉터리에서 `dotnet test`를 다시 실행합니다. `dotnet test` 명령은 `PrimeService` 프로젝트에 대한 빌드를 실행한 다음 `PrimeService.Tests` 프로젝트에 대한 빌드를 실행합니다. 두 프로젝트를 모두 빌드한 후 이 단일 테스트를 실행합니다. 전달합니다.

<a id="adding-more-features" class="xliff"></a>

### 더 많은 기능 추가

이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다. 소수에 대한 몇 가지 다른 간단한 사례가 있습니다(0, -1). 이들을 `[Fact]` 특성과 함께 새 테스트로 추가할 수도 있지만, 이렇게 하면 금방 지루해질 수 있습니다. 비슷한 테스트 모음을 작성하는 데 사용할 수 있는 다른 xUnit 특성이 있습니다.  `[Theory]` 특성은 같은 코드를 실행하는 테스트 모음을 나타내지만, 서로 다른 입력 인수를 가지고 있습니다. `[InlineData]` 특성을 사용하여 그러한 입력의 값을 지정할 수 있습니다. 
 
새 테스트를 만드는 대신 이 두 가지 특성을 사용하여 2보다 작은 일부 값(가장 낮은 소수)을 테스트하는 단일 이론을 만듭니다.

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

`dotnet test`를 실행합니다. 그러면 이러한 테스트 중 2개가 실패합니다. 모든 테스트가 통과하도록 하려면 메서드의 시작 부분에서 `if` 절을 변경합니다.

```csharp
if (candidate < 2)
```

기본 라이브러리에서 더 많은 테스트, 더 많은 이론, 더 많은 코드를 추가하여 계속 반복합니다. [테스트의 완료된 버전](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs)으로 종료하게 됩니다.

작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다. 새 패키지 및 테스트가 원활하게 진행되도록 솔루션을 구성했으므로 응용 프로그램의 목표를 해결하는 데 시간과 노력을 집중할 수 있습니다.

