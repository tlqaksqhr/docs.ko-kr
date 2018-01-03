---
title: ".NET Core의 단위 테스트"
description: "유닛 테스트가 아주 쉬워졌습니다. .NET Core 및 .NET Standard 프로젝트에서 유닛 테스트를 사용하는 방법을 참조하세요."
keywords: ".NET, .NET Core, .NET Standard, 유닛 테스트"
author: ardalis
ms.author: wiwagn
ms.date: 08/30/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 815ac74c-4bd9-4a94-a87c-78288b27c0e2
ms.workload: dotnetcore
ms.openlocfilehash: cb78a66a3a6a7158a86a76d62e5230c75b51a416
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="unit-testing-in-net-core-and-net-standard"></a>.NET Core 및 .NET Standard의 유닛 테스트

.NET Core는 테스트 가능성을 염두에 두고 설계되어 이전보다 더 쉽게 응용 프로그램에 대한 단위 테스트를 만들 수 있습니다. 이 문서에서는 단위 테스트 및 이 테스트가 다른 종류의 테스트와 어떻게 다른지에 대해 간략하게 소개합니다. 연결된 리소스에서는 테스트 프로젝트를 솔루션에 추가한 다음, 명령줄이나 Visual Studio를 사용하여 단위 테스트를 실행하는 방법을 보여 줍니다.

.NET Core 2.0에서는 [.NET Standard 2.0](../../standard/net-standard.md)이 지원됩니다. 이 섹션에서 유닛 테스트를 보여주기 위해 사용하는 라이브러리는 .NET Standard를 사용하며 다른 프로젝트 형식에서도 작동합니다.

.NET Core 2.0부터는 C#뿐만 아니라 Visual Basic과 F#에 대한 단위 테스트 프로젝트 템플릿이 포함됩니다.

## <a name="getting-started-with-testing"></a>테스트 시작

자동화된 테스트 모음이 있다면 소프트웨어 응용 프로그램이 작성자가 의도한 대로 수행되는지 확인하는 최선의 방법 중 하나입니다. 통합 테스트, 웹 테스트, 부하 테스트 등 소프트웨어 응용 프로그램에 대한 다양한 종류의 테스트가 있습니다. 개별 소프트웨어의 구성 요소나 메서드를 테스트하는 단위 테스트는 가장 낮은 수준의 테스트입니다. 단위 테스트에서는 개발자의 제어 수준 내에서만 코드를 테스트하며 데이터베이스, 파일 시스템, 네트워크 리소스 등의 인프라 문제는 테스트하지 않습니다. 단위 테스트는 [TDD(테스트 기반 개발)](http://deviq.com/test-driven-development/)를 사용하여 작성하거나, 기존 코드에 추가하여 정확성을 확인할 수 있습니다. 두 경우 모두 변경 내용을 프로젝트의 공유 코드 리포지토리로 푸시하기 전에 수백 개의 테스트를 실행할 수 있어야 하므로, 작고 신속해야 하며 이름을 잘 지정해야 합니다.

> [!NOTE]
> 개발자는 종종 테스트 클래스 및 메서드에 적합한 이름을 찾으려고 노력합니다. 시작점으로 ASP.NET 제품 팀은 [이러한 규칙](https://github.com/aspnet/Home/wiki/Engineering-guidelines#unit-tests-and-functional-tests)을 따릅니다.

단위 테스트를 작성할 때 실수로 인프라에 대한 종속성이 생성되지 않도록 주의하세요. 이러한 테스트는 속도가 느려지고 불안정해지는 경향이 있으므로 통합 테스트용으로 예약해야 합니다. [명시적 종속성 원칙](http://deviq.com/explicit-dependencies-principle/)을 따르고 [종속성 주입](/aspnet/core/fundamentals/dependency-injection)을 사용하여 프레임워크에서 종속성을 요청하면 응용 프로그램 코드에서 숨겨진 종속성을 방지할 수 있습니다. 또한 단위 테스트를 통합 테스트와 별도의 프로젝트에 유지하고 단위 테스트 프로젝트에 인프라 패키지에 대한 참조나 종속성이 없도록 할 수 있습니다.

.NET Core 프로젝트의 단위 테스트에 대한 자세한 내용은 다음을 참조하세요.

.NET Core에 대한 단위 테스트 프로젝트는 [C#](../../csharp/index.md), [F#](../../fsharp/index.md) 및 [Visual Basic](../../visual-basic/index.md)에 지원됩니다. 또한 [xUnit](http://xunit.github.io), [NUnit](http://nunit.org) 및 [MSTest](https://github.com/Microsoft/vstest-docs) 중에서 선택할 수 있습니다.

다음 연습에서 이러한 조합에 관해 알아볼 수 있습니다.

* .NET Core CLI와 함께 [*XUnit* 및 *C#*을 사용하여 단위 테스트 만들기](unit-testing-with-dotnet-test.md)
* .NET Core CLI와 함께 [*NUnit* 및 *C#*을 사용하여 단위 테스트 만들기](unit-testing-with-nunit.md)
* .NET Core CLI와 함께 [*MSTest* 및 *C#*을 사용하여 단위 테스트 만들기](unit-testing-with-mstest.md)
* .NET Core CLI와 함께 [*XUnit* 및 *F#*을 사용하여 단위 테스트 만들기](unit-testing-fsharp-with-dotnet-test.md)
* .NET Core CLI와 함께 [*NUnit* 및 *F#*을 사용하여 단위 테스트 만들기](unit-testing-fsharp-with-nunit.md)
* .NET Core CLI와 함께 [*MSTest* 및 *F#*을 사용하여 단위 테스트 만들기](unit-testing-fsharp-with-mstest.md)
* .NET Core CLI와 함께 [*XUnit* 및 *Visual Basic*을 사용하여 단위 테스트 만들기](unit-testing-visual-basic-with-dotnet-test.md)
* .NET Core CLI와 함께 [*NUnit* 및 *Visual Basic*을 사용하여 단위 테스트 만들기](unit-testing-visual-basic-with-nunit.md)
* .NET Core CLI와 함께 [*MSTest* 및 *Visual Basic*을 사용하여 단위 테스트 만들기](unit-testing-visual-basic-with-mstest.md)

클래스 라이브러리 및 단위 테스트 라이브러리에 대해 다른 언어를 선택할 수 있습니다. 위에서 참조된 연습을 혼합하고 일치시켜 방법을 알 수 있습니다.

* Visual Studio Enterprise는 .NET Core를 위한 훌륭한 테스트 도구를 제공합니다. [Live Unit Testing](/visualstudio/test/live-unit-testing) 또는 [ 코드 검사](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage)를 통해 자세히 알아보세요.
* 선택적 단위 테스트 필터링을 사용하는 방법에 관한 추가 정보 및 예제는 [선택적 단위 테스트 실행](selective-unit-tests.md) 또는 [Visual Studio를 사용하여 테스트 포함 및 제외](/visualstudio/test/live-unit-testing#including-and-excluding-test-projects-and-test-methods)를 참조하세요.
* XUnit 팀은 [.NET Core 및 Visual Studio에서 xUnit을 사용하는 방법](http://xunit.github.io/docs/getting-started-dotnet-core.html)을 보여 주는 자습서를 작성했습니다.
