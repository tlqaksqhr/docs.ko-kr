---
title: NUnit 및 .NET Core를 사용한 C# 유닛 테스트
description: dotnet test 및 NUnit을 사용하여 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 C# 및 .NET Core의 단위 테스트 개념을 알아봅니다.
author: rprouse
ms.date: 12/01/2017
ms.openlocfilehash: 8cf9e28353dd4dad6143f0dc3f8c0a8245715ea2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214408"
---
# <a name="unit-testing-c-with-nunit-and-net-core"></a>NUnit 및 .NET Core를 사용한 C# 유닛 테스트

이 자습서에서는 샘플 솔루션을 단계별로 빌드하는 대화형 환경을 통해 단위 테스트 개념을 알아볼 수 있습니다. 미리 빌드된 솔루션을 사용하여 이 자습서를 진행하려는 경우 시작하기 전에 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/). 다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.

## <a name="creating-the-source-project"></a>소스 프로젝트 만들기

셸 창을 엽니다. 솔루션을 저장하기 위한 *unit-testing-using-nunit*라는 디렉터리를 만듭니다. 이 새 디렉터리 내에서 [`dotnet new sln`](../tools/dotnet-new.md)을 실행하여 클래스 라이브러리 및 테스트 프로젝트에 대한 새 솔루션 파일을 만듭니다. 다음으로 *PrimeService* 디렉터리를 만듭니다. 다음 개요에는 지금까지의 디렉터리 및 파일 구조가 나와 있습니다.

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
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

디렉터리를 다시 *unit-testing-using-nunit* 디렉터리로 변경합니다. [`dotnet sln add PrimeService/PrimeService.csproj`](../tools/dotnet-sln.md)를 실행하여 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.

## <a name="install-the-nunit-project-template"></a>NUnit 프로젝트 템플릿 설치

NUnit 테스트 프로젝트 템플릿은 테스트 프로젝트를 만들기 전에 설치해야 합니다. 이러한 작업은 새 NUnit 프로젝트를 만들 각 개발자 컴퓨터에서 한 번만 수행합니다. [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md)를 실행하여 NUnit 템플릿을 설치합니다.

```
dotnet new -i NUnit3.DotNetNew.Template
```

### <a name="creating-the-test-project"></a>테스트 프로젝트 만들기

다음으로 *PrimeService.Tests* 디렉터리를 만듭니다. 다음 개요에는 디렉터리 구조가 나와 있습니다.

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

*PrimeService.Tests* 디렉터리를 현재 디렉터리로 만들고 [`dotnet new nunit`](../tools/dotnet-new.md)를 사용하여 새 프로젝트를 만듭니다. dotnet new 명령은 NUnit를 테스트 라이브러리로 사용하는 테스트 프로젝트를 만듭니다. 생성된 템플릿이 *PrimeServiceTests.csproj* 파일에 Test Runner를 구성했습니다.

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다. 이전 단계의 `dotnet new`는 Microsoft 테스트 SDK, NUnit 테스트 프레임워크 및 NUnit 테스트 어댑터를 추가했습니다. 이제 `PrimeService` 클래스 라이브러리를 프로젝트에 다른 종속성으로 추가합니다. [`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

GitHub의 [샘플 리포지토리](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService.Tests.csproj)에서 전체 파일을 볼 수 있습니다.

다음 개요에는 최종 솔루션 레이아웃이 나와 있습니다.

```
/unit-testing-using-nunit
    unit-testing-using-nunit.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

*unit-testing-using-dotnet-test* 디렉터리에서 [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj`](../tools/dotnet-sln.md)를 실행합니다.

## <a name="creating-the-first-test"></a>첫 번째 테스트 만들기

TDD 접근 방식에서는 하나의 실패 테스트를 작성하고, 통과시키고, 이 프로세스를 반복해야 합니다. *PrimeService.Tests* 디렉터리에서 *UnitTest1.cs*를 제거하고 다음과 같은 내용으로 새 C# 파일 *PrimeService_IsPrimeShould.cs*를 만듭니다.

```csharp
using NUnit.Framework;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestFixture]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Test]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, "1 should not be prime");
        }
    }
}
```

`[TestFixture]` 특성은 단위 테스트가 포함된 클래스를 나타냅니다. `[Test]` 특성은 메서드가 테스트 메서드임을 나타냅니다.

이 파일을 저장하고 [`dotnet test`](../tools/dotnet-test.md)를 실행하여 테스트 및 클래스 라이브러리를 빌드한 다음 테스트를 실행합니다. NUnit Test Runner에는 테스트를 실행할 프로그램 진입점이 포함되어 있습니다. `dotnet test`는 만든 단위 테스트 프로젝트를 사용하여 Test Runner를 시작합니다.

테스트가 실패합니다. 구현은 아직 만들지 않았습니다. `PrimeService` 클래스에서 작동하는 가장 간단한 코드를 작성하여 이 테스트를 통과시킵니다.

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

*unit-testing-using-nunit* 디렉터리에서 `dotnet test`를 다시 실행합니다. `dotnet test` 명령은 `PrimeService` 프로젝트에 대한 빌드를 실행한 다음 `PrimeService.Tests` 프로젝트에 대한 빌드를 실행합니다. 두 프로젝트를 모두 빌드한 후 이 단일 테스트를 실행합니다. 전달합니다.

## <a name="adding-more-features"></a>더 많은 기능 추가

이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다. 소수에 대한 몇 가지 다른 간단한 사례가 있습니다(0, -1). 새 테스트를 `[Test]` 특성과 함께 추가할 수도 있지만, 이렇게 하면 금방 지루해질 수 있습니다. 유사한 테스트 모음을 작성하는 데 사용할 수 있는 다른 NUnit 특성이 있습니다.  `[TestCase]` 특성은 같은 코드를 실행하는 테스트 모음을 만드는 데 사용되지만, 서로 다른 입력 인수를 가지고 있습니다. `[TestCase]` 특성을 사용하여 그러한 입력의 값을 지정할 수 있습니다.

새 테스트를 만드는 대신 이 특성을 적용하여 단일 데이터 기반 테스트를 만듭니다. 이 데이터 기반 테스트는 가장 작은 소수인 2보다 작은 몇 가지 값을 테스트하는 메서드입니다.

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

`dotnet test`를 실행합니다. 그러면 이러한 테스트 중 2개가 실패합니다. 모든 테스트가 통과하도록 하려면 메서드의 시작 부분에서 `if` 절을 변경합니다.

```csharp
if (candidate < 2)
```

기본 라이브러리에서 더 많은 테스트, 더 많은 이론, 더 많은 코드를 추가하여 계속 반복합니다. [테스트의 완료된 버전](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.cs) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-nunit/PrimeService/PrimeService.cs)을 얻게 됩니다.

작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다. 새 패키지 및 테스트 추가가 정상 워크플로에 포함되도록 솔루션을 구조화했습니다. 응용 프로그램의 목표를 해결하는 데 대부분의 시간과 노력을 들였습니다.
