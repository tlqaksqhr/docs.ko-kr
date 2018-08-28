---
title: 선택적 단위 테스트 실행
description: 필터 식을 사용하여 dotnet 명령으로 선택적 단위 테스트를 실행하는 방법을 보여 줍니다.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: 428e31014f5d8d487deb7c4b4317ebcef13c294d
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935182"
---
# <a name="running-selective-unit-tests"></a>선택적 단위 테스트 실행

다음 예제에서는 `dotnet test`를 사용합니다. `vstest.console.exe`를 사용하는 경우 `--filter `를 `--testcasefilter:`로 바꾸세요.

## <a name="mstest"></a>MSTest

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| 식 | 결과 |
| ---------- | ------ |
| `dotnet test --filter Method` | `FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다. `vstest 15.1+`에서 사용 가능합니다. |
| `dotnet test --filter Name~TestMethod1` | 이름에 `TestMethod1`이 포함된 테스트를 실행합니다. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | 클래스 `MSTestNamespace.UnitTest1`에 속하는 테스트를 실행합니다.<br>**참고:** `ClassName` 값에는 네임스페이스가 있어야 하므로, `ClassName=UnitTest1`이 작동하지 않습니다. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | `MSTestNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다. |
| `dotnet test --filter TestCategory=CategoryA` | `[TestCategory("CategoryA")]`로 주석이 추가된 테스트를 실행합니다. |
| `dotnet test --filter Priority=2` | `[Priority(2)]`로 주석이 추가된 테스트를 실행합니다.<br>

**조건 연산자 | 및 &amp; 사용**

| 식 | 결과 |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | `FullyQualifiedName`에 `UnitTest1`이 **있거나** `TestCategory`가 `CategoryA`인 테스트를 실행합니다. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | `FullyQualifiedName`에 `UnitTest1`**이 있고** `TestCategory`가 `CategoryA`인 테스트를 실행합니다. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | `UnitTest1`을 포함하는 `FullyQualifiedName`**이 있고**`TestCategory`가 `CategoryA`**이거나** `Priority`가 1인 테스트를 실행합니다. |

## <a name="xunit"></a>xUnit

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| 식 | 결과 |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | `XUnitNamespace.TestClass1.Test1` 테스트를 하나만 실행합니다. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | `XUnitNamespace.TestClass1.Test1`을 제외한 모든 테스트를 실행합니다. |
| `dotnet test --filter DisplayName~TestClass1` | 표시 이름에 `TestClass1`이 포함된 테스트를 실행합니다. |

코드 예제에서 `Category` 및 `Priority` 키로 정의된 특성은 필터링에 사용할 수 있습니다.

| 식 | 결과 |
| ---------- | ------ |
| `dotnet test --filter XUnit` | `FullyQualifiedName`에 `XUnit`가 포함된 테스트를 실행합니다.  `vstest 15.1+`에서 사용 가능합니다. |
| `dotnet test --filter Category=CategoryA` | `[Trait("Category", "CategoryA")]`가 있는 테스트를 실행합니다. |

**조건 연산자 | 및 &amp; 사용**

| 식 | 결과 |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | `FullyQualifiedName`에 `TestClass1`이 **있거나**`Category`가 `CategoryA`인 테스트를 실행합니다. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | `FullyQualifiedName`에 `TestClass1`**이 있고** `Category`가 `CategoryA`인 테스트를 실행합니다. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | `TestClass1`을 포함하는 `FullyQualifiedName`**이** 있고 `Category`가 `CategoryA`**이거나** `Priority`가 1인 테스트를 실행합니다. |

## <a name="nunit"></a>NUnit

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| 식 | 결과 |
| ---------- | ------ |
| `dotnet test --filter Method` | `FullyQualifiedName`에 `Method`가 포함된 테스트를 실행합니다. `vstest 15.1+`에서 사용 가능합니다. |
| `dotnet test --filter Name~TestMethod1` | 이름에 `TestMethod1`이 포함된 테스트를 실행합니다. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | 클래스 `NUnitNamespace.UnitTest1`에 속하는 테스트를 실행합니다.<br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | `NUnitNamespace.UnitTest1.TestMethod1`을 제외한 모든 테스트를 실행합니다. |
| `dotnet test --filter TestCategory=CategoryA` | `[Category("CategoryA")]`로 주석이 추가된 테스트를 실행합니다. |
| `dotnet test --filter Priority=2` | `[Priority(2)]`로 주석이 추가된 테스트를 실행합니다.<br>

**조건 연산자 | 및 &amp; 사용**

| 식 | 결과 |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | `FullyQualifiedName`에 `UnitTest1`이 **있거나** `TestCategory`가 `CategoryA`인 테스트를 실행합니다. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | `FullyQualifiedName`에 `UnitTest1`**이 있고** `TestCategory`가 `CategoryA`인 테스트를 실행합니다. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | `UnitTest1`을 포함하는 `FullyQualifiedName`**이** 있고 `TestCategory`가 `CategoryA`**이거나** `Priority`가 1인 테스트를 실행합니다. |
