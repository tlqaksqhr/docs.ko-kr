---
title: "dotnet 테스트를 사용하여 .NET Core에서 유닛 테스트 | Microsoft 문서"
description: "Dotnet 테스트를 사용하여 .NET Core에서 단위 테스트"
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 002/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: cd860241f5f20b6a4f1ccfec60e0c9cd5079152a
ms.lasthandoff: 03/07/2017

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Dotnet 테스트를 사용하여 .NET Core에서 단위 테스트

작성자: [Steve Smith](http://ardalis.com) 및 [Bill Wagner](https://github.com/BillWagner)

[샘플 코드 보기 또는 다운로드](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test)

## <a name="creating-the-projects"></a>프로젝트 만들기

[플랫폼 간 도구로 라이브러리 작성](../tutorials/libraries.md)에서는 소스와 테스트 모두의 다중 프로젝트 솔루션 구성에 대한 정보를 제공합니다. 이 문서는 그러한 규칙을 따릅니다. 최종 프로젝트 구조는 다음과 같습니다.

```
/unit-testing-using-dotnet-test
|__/PrimeService
   |__Source Files
   |__PrimeService.csproj
|__/PrimeService.Tests
   |__Test Files
   |__PrimeService.csproj
```

### <a name="creating-the-source-project"></a>소스 프로젝트 만들기

`unit-testing-using-dotnet-test` 디렉터리에서 시작하여 `PrimeService` 디렉터리를 만듭니다.
해당 디렉터리로 이동하고 `dotnet new classib`를 실행하여 소스 프로젝트를 만듭니다.


`Class1.cs`의 이름을 `PrimeService.cs`로 바꿉니다. TDD(테스트 기반 개발)를 사용하기 위해 `PrimeService` 클래스의 실패 구현을 만듭니다.

```cs
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

### <a name="creating-the-test-project"></a>테스트 프로젝트 만들기

다음으로 'unit-testing-using-dotnet-test' 디렉터리로 돌아가고 `PrimeServices.Tests` 디렉터리를 만듭니다.
`PrimeService.Tests` 디렉터리로 이동하고 `dotnet new xunit`를 사용하여 새 프로젝트를 만듭니다. `dotnet xunit`는 xUnit을 테스트 라이브러리로 사용하는 테스트 프로젝트를 만듭니다. 

생성된 템플릿이 PrimeServiceTests.csproj에 Test Runner를 구성했습니다.

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-preview-20170125-04" />
    <PackageReference Include="xunit" Version="2.2.0-beta5-build3474" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-beta5-build1225" />
  </ItemGroup>
```

테스트 프로제트는 다른 패키지에 단위 테스트를 만들고 실행하도록 요구합니다.
`dotnet new`는 xUnit 및 xUnit runner를 추가했습니다. PrimeService 패키지를 또 다른 종속성으로 프로젝트에 추가해야 합니다. 이 경우 `dotnet` CLI를 사용하면 됩니다.

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

또는 `PrimeService.Tests.csproj` 파일을 직접 편집할 수 있습니다.
첫 번째 `<ItemGroup>` 노드 바로 아래에서 참조와 함께 다른 `<ItemGroup>` 노드를 라이브러리 프로젝트에 추가합니다.

```xml
  <ItemGroup>
    <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
  </ItemGroup>
```

GitHub의 [샘플 리포지토리](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj)에서 전체 파일을 볼 수 있습니다.

이 초기 구조가 자리 잡으면 첫 번째 테스트를 작성할 수 있습니다.
첫 번째 단위 테스트를 확인한 후에는 모든 것이 구성되며 기능과 테스트를 추가할 때 원활하게 실행됩니다.

## <a name="creating-the-first-test"></a>첫 번째 테스트 만들기

라이브러리 또는 테스트를 빌드하기 전에 `PrimeService` 및 `PrimeService.Tests` 디렉터리에서 `dotnet restore`를 실행해야 합니다. 이 명령은 각 프로젝트에 대해 필요한 모든 NuGet 패키지를 복원합니다.

TDD 접근 방식에서는 하나의 실패 테스트를 작성하고, 통과시키고, 이 프로세스를 반복해야 합니다. 따라서 하나의 실패 테스트를 작성하겠습니다. `PrimeService.Tests` 디렉터리에서 `UnitTest1.cs`를 제거하고 다음과 같은 내용으로 `PrimeService_IsPrimeShould.cs`라는 새 C# 파일을 만듭니다.

```cs
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

`[Fact]` 특성은 메서드를 단일 테스트로 나타냅니다. 

이 파일을 저장한 다음 `dotnet build`를 실행하여 테스트 프로젝트를 빌드합니다.
`PrimeService` 프로젝트를 아직 빌드하지 않은 경우, 이 프로젝트는 테스트 프로젝트의 종속성이기 때문에 빌드 시스템이 이를 탐지하고 빌드합니다.

이제 `dotnet test`를 실행하여 콘솔에서 테스트를 실행합니다.
xUnit Test Runner에는 콘솔에서 테스트를 실행할 프로그램 진입점이 있습니다. `dotnet test`는 Test Runner를 시작하고, 테스트가 포함된 어셈블리를 나타내는 testrunner에 명령줄 인수를 제공합니다.

테스트가 실패합니다. 구현은 아직 만들지 않았습니다.
이 하나의 테스트를 통과시킬 가장 간단한 코드를 작성합니다.

```cs
public bool IsPrime(int candidate) 
{
    if(candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

### <a name="adding-more-features"></a>더 많은 기능 추가

이제 하나의 테스트를 통과했으므로 더 작성할 수 있습니다.
소수에 대한 몇 가지 다른 간단한 사례가 있습니다(0, -1). 이들을 `[Fact]` 특성과 함께 새 테스트로 추가할 수도 있지만, 이렇게 하면 금방 지루해질 수 있습니다. 비슷한 테스트 모음을 작성하는 데 사용할 수 있는 다른 xUnit 특성이 있습니다.  `Theory`는 같은 코드를 실행하는 테스트 모음을 나타내지만, 서로 다른 입력 인수를 가지고 있습니다.
`[InlineData]` 특성을 사용하여 그러한 입력의 값을 지정할 수 있습니다. 
 
 새 테스트를 만드는 대신 이 두 가지 특성을 사용하여 2보다 작은 일부 값(가장 낮은 소수)을 테스트하는 단일 이론을 만듭니다.

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs#Sample_TestCode "첫 번째 테스트")]
```

Run `dotnet test` and you'll see that two of these tests fail.
You can make them pass by changing the service. You need to change
the `if` clause at the beginning of the method:

```cs
if(candidate < 2)
```

이제 이러한 테스트가 모두 통과됩니다.

기본 라이브러리에서 더 많은 테스트, 더 많은 이론, 더 많은 코드를 추가하여 계속 반복합니다. [테스트의 완료된 버전](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) 및 [라이브러리의 완전한 구현](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/src/PrimeService/PrimeService.cs)으로 신속하게 종료하게 됩니다.

작은 라이브러리 및 이 라이브러리에 대한 단위 테스트 집합을 작성했습니다.
새 패키지와 테스트를 원활하게 추가할 수 있도록 이 솔루션을 구성했으므로 이제 당면한 문제에 집중할 수 있습니다. 도구는 자동으로 실행됩니다.

