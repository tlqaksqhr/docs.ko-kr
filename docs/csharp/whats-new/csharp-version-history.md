---
title: "C#-C# 가이드의 기록"
description: "어떤 않은 언어 모양을 좋은지의 초기 버전에서 그리고 어떻게가 것 발전 하 고 이후?"
keywords: "C#,.NET,.NET Core를 새로운 기능, C# 기록"
author: erikdietrich
ms.author: wiwagn
ms.date: 09/20/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 207c97c5dd7e04f815da61bff7f44393aea86222
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="the-history-of-c"></a>C#의 기록 #

언어 모양을 가장 오래 된 버전에서 무엇을 않은 선택 하십시오. 어떻게 것에서 발전을 이후 년?

## <a name="c-version-10"></a>C# 버전 1.0

이전 단계로 이동 하 고 확인 하는 경우 C# 버전 1.0은 많은 Java 다음과 같았습니다. 으로 [ECMA의 언급 된 디자인 목표의 일부로](http://feeldotneteasy.blogspot.com/2011/01/c-design-goals.html), 있는 "단순, 최신, 일반 용도 개체 지향 언어 여야 합니다."를 검색  당시에 Java 의미 것 처럼 보일 이러한 초기 디자인 목표를 달성 합니다.

하지만 다시 C# 1.0에 이제을 보면 주시기 바랍니다 직접 약간 어지러워 합니다. 기본 제공 비동기 기능과 부여에 대해 수행 하는 제네릭 주위 편리한 기능 중 일부 없었습니다. 으로 사실, 부족 했습니다 제네릭을 완전히 합니다.  및 [LINQ](../linq/index.md)? 사용할 수 없는 아직 있습니다. 숫자를 몇 년 동안 수행 합니다.

C# 버전 1.0 오늘날에 비해 기능의 훼손 찾습니다. 자세한 일부 코드를 작성 하면서 찾게 됩니다. 하지만 아직 위치를 시작 해야 합니다. C# 버전 1.0 Java Windows 플랫폼에서 실행 가능한 대안이 했습니다.

## <a name="c-version-20"></a>C# 버전 2.0

이제 시작 했습니다 흥미롭습니다. C# 2.0에서는 Visual Studio 2005와 함께 2005에 릴리스의 몇 가지 주요 기능에 살펴보겠습니다.

- [제네릭](../programming-guide/generics/index.md)
- [부분 형식(Partial Type)](../programming-guide/classes-and-structs/partial-classes-and-methods.md#partial-classes)
- [무명 메서드](../programming-guide/statements-expressions-operators/anonymous-methods.md)
- [Nullable 형식](../programming-guide/nullable-types/index.md)
- [반복기](../programming-guide/concepts/iterators.md)
- [공 분산과 반공 분산](../programming-guide/concepts/covariance-contravariance/index.md)

C# 수는 매우 일반적인 개체 지향 (개체 지향) 언어로 시작 하는 동안 C# 버전 2.0에서에서 변경를 훑어보기만 합니다. 아래의 해당 feet 가졌던 후에 일부 심각한 개발자 문제점 후 발생 했습니다. 및 큰 방식으로 다음 참으로 합니다.

제네릭 형식 및 형식 안전성을 유지 하면서 임의의 형식에 대해 수행할 수 있는 메서드 수 있습니다. 따라서 예를 들어 있는 <xref:System.Collections.Generic.List%601> 사용 하면 `List<string>` 또는 `List<int>` 을 반복 하는 동안 이러한 문자열 또는 정수에 대 한 형식 안전 하 게 보호 작업을 수행 합니다. 이 만드는 것 보다 더 나은 `ListInt` 상속자 또는에서 캐스팅 `Object` 모든 작업에 대 한 합니다.

C# 버전 2.0 가져온 반복기입니다. 간결 하 게 배치, 이렇게 하면 항목의 모든 반복을 `List` (또는 다른 열거 가능한 형식)와 `foreach` 루프입니다. 언어의 첫 번째 클래스 일부로이 크게 향상 된 언어와의 사람들이 코드에 대 한 이유를 쉽게 읽을 수 있습니다.

고 아직, C# 계속 Java 따라잡 다소 재생할 수 있습니다. Java가 이미 제네릭 및 반복기를 포함 하는 버전을 릴리스 했습니다. 하지만 계속 떨어져 있는 발전해 왔습니다 언어 변경 곧 됩니다.

## <a name="c-version-30"></a>C# 버전 3.0

C# 버전 3.0 언어 기능의 전체 보트는 실제로 C# 버전 3.5에와 야 하지만 런타임에 2007에서는 Visual Studio 2008과 함께 제공 되었습니다. 이 버전으로 크게 변경 된 C#의 성장에 오류가 표시 됩니다. 설정할 C# 진정한 이었기 프로그래밍 언어로 합니다. 이 버전에서는 몇 가지 주요 기능 살펴보기를 보겠습니다.

- [자동 구현 속성](../programming-guide/classes-and-structs/auto-implemented-properties.md)
- [무명 형식](../programming-guide/classes-and-structs/anonymous-types.md)
- [쿼리 식](../linq/query-expression-basics.md)
- [람다 식](https://www.daedtech.com/introduction-to-c-lambda-expressions/)
- [식 트리](https://blogs.msdn.microsoft.com/charlie/2008/01/31/expression-tree-basics/)
- [확장 메서드](https://www.codeproject.com/Tips/709310/Extension-Method-In-Csharp)

에, 이러한 기능 중 대부분 울 불가피 한 및 분리 불가능 합니다. 이러한 모든 개념이 서로 전략적으로 합니다. 일반적으로 C# 버전의 기능도 라고도 LINQ (Language-Integrated Query) 쿼리 식, 했음을 생각 됩니다.

더 nuanced 보기 LINQ 생성 되는 기반으로 식 tress, 람다 식 및 익명 형식을 검사 합니다. 하지만, 두 경우 모두 C# 3.0 혁신적인 개념을 제공 합니다. C# 개체 지향 하이브리드도 전환 하기 위한 토대 C# 3.0 시작 / 기능 언어입니다.

특히, SQL 스타일, 무엇 보다도 컬렉션에 대 한 작업을 수행 하는 선언적 쿼리 작성할 수 있습니다. 작성 하는 대신 한 `for` 정수 목록의 평균을 계산 하는 루프에 있는 경우 이제에서 수행할 수 있습니다 간단 하 게으로 `list.Average()`합니다. 확장 메서드 및 쿼리 식 조합 수 있게 처럼 해당 정수 목록이 더 효율적인 훨씬을 수신 했습니다.

실제로 잡고 개념을 통합 하는 사용자를 위한 시간이 있지만 점진적으로 않았습니다. 이며 이제 년 후 코드 훨씬 더 간결 하 게 간단 하 고 작동 합니다.

## <a name="c-version-40"></a>C# 버전 4.0

C# 버전 4.0 했지만 이제 버전 3.0의 획기적인 상태로 미치는지에 어려운 시간입니다. 버전 3.0 이상에서는 C#에 언어 축소 모뎀과 컴퓨터에서 이동할의 Java와 함에 따라에 그림자입니다. 언어가 세련 되 신속 하 게 합니다.

다음 버전 주목할 만한 몇 가지 새로운 기능을 제공할 않았습니다.

- [동적 바인딩](../language-reference/keywords/dynamic.md)
- [명명 된/선택적 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- [제네릭 공변 및 반공 변](../../standard/generics/covariance-and-contravariance.md)
- [포함 된 interop 형식](https://stackoverflow.com/questions/20514240/whats-the-difference-setting-embed-interop-types-true-and-false-in-visual-studi)

포함 된 interop 형식 배당 배포 위해서입니다. 제네릭의 공 분산과 반공 분산 제공 제네릭을 사용 하는 데 더욱 강력한 하지만 약간 교육 및 아마도 프레임 워크 및 라이브러리 작성자가 가장 좋습니다. 명명 된 인수와 선택적 매개 변수를 사용 하 여 여러 개의 메서드 오버 로드가 제거 하 고 편리 하 게 제공할 수 있도록 합니다. 하지만 이러한 기능 중는 패러다임 정확 하 게 변경 합니다.

주요 기능이 도입 된는 `dynamic` 키워드입니다. `dynamic` 입력 컴파일 타임에 컴파일러를 재정의 하는 기능을 C# 버전 4.0 키워드가 도입 합니다. 동적 키워드를 사용 하 여 JavaScript와 같은 동적으로 형식화 된 언어와 유사한 구조를 만들 수 있습니다. 만들 수는 `dynamic x = "a string"` 다음 추가를 6 개 런타임에서 다음 수행할를 방지할 수까지 유지 합니다.

이렇게 하면 잠재적인 오류 뿐만 아니라 언어 내에서 훌륭한 기능에 대 한 합니다.

## <a name="c-version-50"></a>C# 버전 5.0

C# 버전 5.0 매우 집중 된 버전의 언어 했습니다. 해당 버전에 대 한 활동의 거의 전부 다른 획기적인 언어 개념에 오류가 발생 했습니다.  다음은 주요 기능 목록이입니다.

- [비동기 멤버](../async.md)
- [호출자 정보 특성](https://www.codeproject.com/Tips/606379/Caller-Info-Attributes-in-Csharp)

호출자 정보 특성을 사용 하면 쉽게 엄청난 양의 상용구 리플렉션 코드에 문의 하지 않고 실행 하는 컨텍스트에 대 한 정보를 검색할 수 있습니다. 진단 및 로깅 작업에 사용 되는 많은 가집니다.

하지만 `async` 및 `await` 이 릴리스의 실제 별 됩니다. 이러한 기능에 2012에서 출시, C# 변경 게임 다시 첫 번째 클래스 참여자로 언어로 비동기가 세. 장기 실행 작업 및 웹 콜백 구현을 사용 하 여 처리 하 한 적이 있는 경우이 언어 기능을 사랑 합니다.

## <a name="c-version-60"></a>C# 버전 6.0

3.0 버전 5.0, C#에 추가 몇 가지 멋진 기능 개체 지향 언어에서. 버전 6.0 것 기준 기능도 수행 하는 반대쪽 있으며 대신 언어의 사용자 만족 하 고 많은 기능을 해제 합니다. 다음은 그 중 일부입니다.

- [정적 가져오기](../language-reference/keywords/using-static.md)
- [예외 필터](https://www.thomaslevesque.com/2015/06/21/exception-filters-in-c-6/)
- [속성 이니셜라이저](http://geekswithblogs.net/WinAZ/archive/2015/06/30/whatrsquos-new-in-c-6.0-auto-property-initializers.aspx)
- [본문이 식 멤버](https://lostechies.com/jimmybogard/2015/12/17/c-6-feature-review-expression-bodied-function-members/)
- [Null 전파 자가](https://davefancher.com/2014/08/14/c-6-0-null-propagation-operator/)
- [문자열 보간](../language-reference/keywords/interpolated-strings.md)
- [nameof 연산자](https://stackoverflow.com/questions/31695900/what-is-the-purpose-of-nameof)
- [사전 이니셜라이저가](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md)

이러한 각 기능 그 자체로 흥미로운 부분입니다. 하지만 흥미로운 패턴 모두 확인해 보면 표시 합니다. 이 버전에서는 C#은 언어 상용구 더 간결 하 고 읽을 수 있는 코드를 제거 하 고 있습니다. 따라서 잘 정리 되 고 간단한 코드의 팬에이 언어 버전 엄청난 달성 했습니다.

자체의 기존 언어 기능 하지 않더라도 않았는데이 버전에서와 다른 한 가지입니다. 릴리스되 [Roslyn 컴파일러는 서비스로](https://github.com/dotnet/roslyn)합니다. C# 컴파일러는 이제 C#으로 작성 하 고 프로그래밍 노력의 일환으로 컴파일러를 사용할 수 있습니다.

## <a name="c-version-70"></a>C# 버전 7.0

가장 최근의 주 버전은 C# 버전 7.0. 이 버전에 약간의 혁신적인 및 쿨 내용을 컴파일러 하지 않고 C# 6.0의 맥락 서비스로 있습니다. 다음은 몇 가지 새 기능입니다.

- [변수](http://www.c-sharpcorner.com/article/out-variables-in-c-sharp-7-0/)
- [튜플 및 제거](https://www.thomaslevesque.com/2016/08/23/tuple-deconstruction-in-c-7/)
- [패턴 일치](./csharp-7.md#pattern-matching)
- [로컬 함수](http://www.infoworld.com/article/3182416/application-development/c-7-in-depth-exploring-local-functions.html)
- [확장 된 식 본문이 멤버](./csharp-7.md#more-expression-bodied-members)
- [Ref 지역 및 반환](./csharp-7.md#ref-locals-and-returns)

이러한 기능 중 모든 개발자와 그 어느 때 보다도 클리너 코드를 작성할 수 있는 기회를 위한 멋진 새로운 기능을 제공 합니다. 밝은 영역을 사용 하면 변수의 선언을 압축은 `out` 키워드 및 튜플을 통해 여러 개의 반환 값을 허용 하 여 합니다.

하지만 C#은 put 중인 현재까지 광범위 한 사용 합니다. .NET core 이제 모든 운영 체제를 대상으로 하며 해당 눈 모뎀과 클라우드 및 이식성에 합니다.  확실히 언어 디자이너 생각과 시간 이후의 새로운 기능을 사용 하는 것 외에도 열려 있어야 합니다.

_문서_ [ _원래 NDepend 블로그 게시_](https://blog.ndepend.com/c-versions-look-language-history/)_, Erik Dietrich 및 Patrick Smacchia 지도 제작 합니다._
