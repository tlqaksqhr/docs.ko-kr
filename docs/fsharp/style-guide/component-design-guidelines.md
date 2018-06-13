---
title: 'F # 구성 요소 디자인 지침'
description: '다른 호출자에 의해 사용 하도록 설계 된 F # 구성 요소를 작성 하는 것에 대 한 지침에 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458088"
---
# <a name="f-component-design-guidelines"></a>F # 구성 요소 디자인 지침

이 문서는 F # 프로그래밍, F # 구성 요소 디자인 지침, v14, Microsoft Research 기반에 대 한 구성 요소 디자인 지침 집합이 고 [다른 버전](https://fsharp.org/specs/component-design-guidelines/) 원래 큐 레이트 하 고 F # Software Foundation에서 유지 관리 합니다.

이 문서에서는 F # 프로그래밍에 익숙한 가정 합니다. F # 커뮤니티의 기여 하 고이 가이드의 다양 한 버전에 대 한 유용한 피드백에 대 한 도움을 주신 합니다.

## <a name="overview"></a>개요

이 문서는 F # 구성 요소 디자인 및 코딩와 관련 된 문제 중 일부를 살펴봅니다. 구성 요소는 다음 중 하나를 의미 합니다.

* 해당 프로젝트 내에서 외부 소비자가 있는 F # 프로젝트에는 계층입니다.
* 다른 어셈블리에서 F # 코드에서 사용 하도록 설계 된 라이브러리입니다.
* 다른 어셈블리에서 모든.NET 언어에서 사용 하도록 설계 된 라이브러리입니다.
* 와 같은 패키지 리포지토리를 통한 배포용 위한 라이브러리 [NuGet](https://nuget.org)합니다.

이 문서에서 설명 하는 방법에 따라는 [좋은 F # 코드의 5 개 원칙](index.md#five-principles-of-good-f-code)를 하 고 따라서 활용 기능 둘 다 고 적절 하 게 프로그래밍 개체입니다.

방법과 상관 없이 구성 요소 및 라이브러리 디자이너 개발자가 쉽게 사용할 수 있는 API를 만들 하려고 할 때 실용적이 고 사용할 수 있는 문제가 많이 직면 합니다. 인식 응용 프로그램은 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md) 즐겁게 소비할 수 있는 Api의 일관 된 집합을 만들 때 유도 합니다.

## <a name="general-guidelines"></a>일반 지침

F # 라이브러리에 라이브러리에 대 한 대상에 관계 없이 적용 되는 몇 가지 유니버설 지침 있습니다.

### <a name="learn-the-net-library-design-guidelines"></a>.NET 라이브러리 디자인 지침에 알아봅니다

F # 수행 하는 코딩의 종류에 관계 없이 하는 것이 한 작업 지식을 갖추고는 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)합니다. 대부분 다른 F # 및.NET 프로그래머에 게 이러한 지침에 잘 알고 되며.NET 코드에 대 한 준수를 예상 합니다.

.NET 라이브러리 디자인 지침 명명, 클래스 및 인터페이스, 멤버 디자인 (속성, 메서드, 이벤트 등) 및 기타를 디자인에 대 한 일반적인 지침을 제공 하며 다양 한 디자인 지침에 대 한 참조에 유용한 첫 번째 지점 합니다.

### <a name="add-xml-documentation-comments-to-your-code"></a>XML 문서 주석을 코드에 추가

공용 Api에 XML 문서는 라이브러리에 대 한 파일을 이러한 형식 및 멤버 및 사용 건물 설명서를 사용 하 여 때 유용한 Intellisense 및 요약 정보 사용자가 액세스할 수를 확인 합니다. 참조는 [XML 문서](../language-reference/xml-documentation.md) xmldoc 주석 내 추가 태그에 사용할 수 있는 다양 한 xml 태그에 대 한 합니다.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

약식 XML 주석을 사용할 수 있습니다 (`/// comment`), 또는 표준 XML 주석 (`///<summary>comment</summary>`).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>안정적인 라이브러리 및 Api 구성 요소에 대 한 명시적 서명 파일 (.fsi)를 사용 하는 것이 좋습니다.

이 두 가지 있는지 하면 라이브러리의 전체 공개 화면 알고으로 확실 하 게 구분 내부 및 공용 설명서 간의 제공 되도록 공용 API의 간단한 요약을 제공 명시적 서명 파일을 사용 하 여 F # 라이브러리의 구현 세부 정보입니다. Note 서명 파일 구현 및 서명 파일에 대해 적용할 변경 사항을 요구 하 여 공용 API를 변화 하는 마찰을 추가 합니다. 결과적으로, 서명 파일이 일반적으로 소개 해야 API 그 되 고는 더 이상 크게 변경 해야 합니다.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>항상 문자열을 사용 하 여.NET에 대 한 모범 사례를 따르십시오

에 따라 [.NET에서 문자열 사용에 대 한 유용한](../../standard/base-types/best-practices-strings.md) 지침. 특히, 항상 명시적으로 지정할 *문화적 의도* 변환 및 문자열의 비교에서 (있는 경우).

## <a name="guidelines-for-f-facing-libraries"></a>F #에 대 한 지침-라이브러리를 연결 합니다.

이 섹션에서는 공용 F #을 개발 하기 위한 권장 사항을-라이브러리; 연결 즉, 라이브러리를 F # 개발자가 사용 하기 위한 공용 Api를 노출 합니다. 적용할 특히 F # 라이브러리 디자인 권장 구성의 여러 가지가 있습니다. 에 나오는 특정 권장 사항은 없을 경우.NET 라이브러리 디자인 지침은 대체 (fallback)의 지침입니다.

### <a name="naming-conventions"></a>명명 규칙

#### <a name="use-net-naming-and-capitalization-conventions"></a>.NET 이름 지정 및 대/소문자 규칙을 사용 하 여

다음 표에서.NET 이름 지정 및 대/소문자 규칙을 따릅니다. F # 구문을 포함에 대 한 작은 추가 있습니다.

| 구문 | Case | 파트 | 예제 | 노트 |
|-----------|------|------|----------|-------|
| 구체적인 형식 | 표시 방법이 PascalCase | 명사 형용사 / | 목록, Double, 복잡 한 | 구체적인 유형은 구조체, 클래스, 열거형, 대리자, 레코드 및 공용 구조체입니다. 형식 이름은 OCaml에 일반적으로 소문자로, F #는 채택 했습니다 형식에 대 한.NET 이름 지정 체계를입니다.
| DLL           | 표시 방법이 PascalCase |                 | Fabrikam.Core.dll |  |
| 공용 구조체 태그     | 표시 방법이 PascalCase | 명사 | 일부 추가, 성공 | 공용 Api에서 접두사를 사용 하지 마십시오. 필요에 따라 내부와 같은 접두사를 사용 하 여 ' ' 팀 입력 TAlpha = | TBeta | TDelta. ' ' |
| 이벤트(event)          | 표시 방법이 PascalCase | 동사 | 재정의 / ValueChanging |  |
| 예외     | 표시 방법이 PascalCase |      | WebException | 이름 "예외"로 끝나야 합니다. |
| 필드          | 표시 방법이 PascalCase | 명사 | CurrentName  | |
| 인터페이스 형식 |  표시 방법이 PascalCase | 명사 형용사 / | IDisposable | 이름은 "I"로 시작 해야 합니다. |
| 메서드 |  표시 방법이 PascalCase |  동사 | ToString | |
| 네임스페이스 | 표시 방법이 PascalCase | | Microsoft.FSharp.Core | 일반적으로 사용 하 여 `<Organization>.<Technology>[.<Subnamespace>]`, 기술이 조직 으로부터 독립적인 경우 하지만 조직을 삭제 합니다. |
| 매개 변수 | camelCase | 명사 |  typeName, 변환, 범위 | |
| 값 (내부)를 사용 합니다. | camelCase 또는 표시 방법이 PascalCase | 명사 / 동사 |  getValue, myTable |
| 값 (외부)를 사용 합니다. | camelCase 또는 표시 방법이 PascalCase | 명사/동사  | List.map Dates.Today | let 바인딩 값 기존의 기능 디자인 패턴을 수행할 때 공용 많습니다. 그러나 일반적으로 사용 하 여 표시 방법이 PascalCase 식별자는 다른.NET 언어에서 사용할 수 있을 때. |
| 속성  | 표시 방법이 PascalCase  | 명사 형용사 /  | IsEndOfFile, BackColor  | 부울 속성 일반적으로 사용 되 고 수 IsEndOfFile, 하지 IsNotEndOfFile 에서처럼 찬성 이어야 합니다.

#### <a name="avoid-abbreviations"></a>약어를 방지 합니다.

.NET 지침 약어를 사용 하지 못하도록 (예를 들어 "사용 `OnButtonClick` 대신 `OnBtnClick`"). 일반적인 약어와 같은 `Async` 트랜잭션당 "비동기"에 대 한 합니다. 이 지침 함수형 프로그래밍;에 대 한 경우에 따라 무시 됩니다. 예를 들어 `List.iter` "반복"에 대 한 약어를 사용 합니다. 이러한 이유로 약어를 사용 하는 경향이 F #에 보다 심층적 허용 될-에-F # 프로그래밍 있지만 공용 구성 요소 디자인에서 여전히 일반적으로 사용 하지 않아야 합니다.

#### <a name="avoid-casing-name-collisions"></a>이름 충돌을 대/소문자 구분 하지 마십시오.

.NET 지침 예를 들어 일부 클라이언트 언어 (예를 들어 Visual Basic)은 대/소문자 구분 이름 충돌을 명확 하 게 대/소문자 구분 단독 사용할 수 없습니다.

#### <a name="use-acronyms-where-appropriate"></a>적합 한 머리글자어 사용

XML과 같은 머리글자어 약어 않으며 소문자로 시작된 양식 (Xml)에.NET 라이브러리에 널리 사용 됩니다. 만 널리 인정, 잘 알려진 약어를 사용 해야 합니다.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>제네릭 매개 변수 이름에 대 한 표시 방법이 PascalCase를 사용 하 여

F #에 대 한 포함 하는 공용 Api에서 제네릭 매개 변수 이름에 표시 방법이 PascalCase 사용-라이브러리를 연결 합니다. 특히,와 같은 이름을 사용 하 여 `T`, `U`, `T1`, `T2` 임의의 제네릭 매개 변수에 대 한 및 특정 이름이 의미가 다음 F #에 대 한-마주보 라이브러리와 같은 이름을 사용 하 여 `Key`, `Value`, `Arg`(하지만 하지 예를 들어 `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>공용 함수 및 F # 모듈의 값에 대 한 표시 방법이 PascalCase 또는 camelCase 중 하나를 사용 하 여

camelCase 공용 함수를 사용할 수 있도록 설계에 사용 되 정규화 되지 않은 (예를 들어 `invalidArg`), 및 (예: List.map) "표준 컬렉션 함수"에 대 한 합니다. 두이 경우 모두에서 함수 이름을 훨씬 언어의 키워드에에서 처럼 작동 합니다.

### <a name="object-type-and-module-design"></a>개체, 형식 및 모듈 디자인

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>네임 스페이스 또는 모듈을 사용 하 여 형식 및 모듈을 포함 하도록

각 F # 파일에서 구성 요소에서 네임 스페이스 선언 또는 모듈 선언으로 시작 해야 합니다.

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

또는

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

최상위 수준에서 코드를 구성 모듈 및 네임 스페이스를 사용 하 여 간의 차이점은 다음과 같습니다.

* 네임 스페이스는 여러 파일을 확장할 수 있습니다.
* 네임 스페이스는 내부 모듈 내에서 아니면 F # 함수를 포함할 수 없습니다.
* 지정 된 모든 모듈에 대 한 코드는 단일 파일에 포함 되어야 합니다.
* 최상위 모듈에는 F # 함수 내부 모듈에 대 한 필요 없이 포함 될 수 있습니다.

최상위 네임 스페이스 또는 모듈 간의 선택 코드의 컴파일된 형태에 영향을 줍니다 따라서 영향을 미칩니다 다른.NET 언어에서 보기 사용 해야 하 여 API 결국 F # 코드 외부에서.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>개체 형식에 내장 된 작업에 대 한 메서드 및 속성 사용

개체를 사용할 때 사용 될 기능 메서드 및 해당 형식에 대 한 속성으로 구현 됨을 확인 하는 것이 좋습니다.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

지정된 된 멤버에 대 한 기능 대량의 필요 하지 반드시 구현할 수 해당 멤버에 있지만 해당 기능에서 사용 될 수 있습니다 항목 이어야 합니다.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>클래스를 사용 하 여 변경 가능 상태를 캡슐화 합니다.

F #에서이 수행 해야 여기서 상태 클로저, 시퀀스 식에서 비동기 계산 등의 다른 언어 구문이 이미 캡슐화 되지 않습니다.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>그룹화 할 인터페이스를 사용 하 여 관련 작업

일련의 작업을 나타내는 인터페이스 형식을 사용 합니다. 이 함수는 튜플 또는 함수의 레코드 등의 다른 옵션에 선호 됩니다.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

우선적으로:

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

인터페이스는 어떤 함수는 일반적으로 사용 하면 달성 하기 위해 사용할 수 있는.NET에 대 한 주요 개념입니다. 또한 함수의 레코드 수 없습니다. 프로그램에 존재 하는 형식을 인코딩하는 데 사용할 수 수 있습니다.

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>컬렉션에 대해 작동 하는 그룹 함수에는 모듈을 사용 하 여

컬렉션 형식을 정의 하는 경우와 같은 표준 작업 집합이 제공 하십시오 `CollectionType.map` 및 `CollectionType.iter`)에 대 한 새 컬렉션 유형입니다.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

이러한 모듈을 포함 하는 경우 FSharp.Core에서 찾을 수 함수에 대 한 표준 명명 규칙을 따릅니다.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>특히 수학 및 DSL 라이브러리에서 일반적으로 정식 함수에 대 한 모듈 그룹 기능을 사용 하 여

예를 들어 `Microsoft.FSharp.Core.Operators` 은 자동으로 열리는 컬렉션 최상위 함수 (같은 `abs` 및 `sin`) FSharp.Core.dll에서 제공 합니다.

마찬가지로, 통계 라이브러리 함수를 사용 하 여 모듈을 포함할 수 있습니다 `erf` 및 `erfc`여기서이 모듈은 디자인 된 명시적으로 또는 자동으로 열 수 있습니다.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>신중 하 게 AutoOpen 특성을 적용 및 RequireQualifiedAccess를 사용 하는 것이 좋습니다.

추가 `[<RequireQualifiedAccess>]` 특성을 모듈에 모듈을 열 수 있습니다 하며 액세스를 한정 된 모듈의 요소에 대 한 참조가 필요 명시적 나타냅니다. 예를 들어는 `Microsoft.FSharp.Collections.List` 모듈에는이 특성입니다.

함수 및 모듈의 값에는 이름이 다른 모듈의 있는 이름과 충돌 가능성이 있는 경우에 유용 합니다. 정규화 된 액세스가 필요한 장기적인 유지 관리 및 라이브러리의 evolvability 크게 향상 시켜 합니다.

추가 `[<AutoOpen>]` 특성 모듈을 포함 하는 네임 스페이스를 열 때 모듈을 열 수는 것을 의미 합니다. `[<AutoOpen>]` 특성이 어셈블리를 참조할 때 자동으로 열려 있는 모듈을 표시 하기 위해 어셈블리에도 적용 될 수 있습니다.

예를 들어 통계 라이브러리 **MathsHeaven.Statistics** 포함 될 수 있습니다는 `module MathsHeaven.Statistics.Operators` 함수가 포함 된 `erf` 및 `erfc`합니다. 이 모듈을 표시 하려면이 `[<AutoOpen>]`합니다. 즉, `open MathsHeaven.Statistics` 이 모듈을 열고 및 이름을 상태로 `erf` 및 `erfc` 범위에 있습니다. 사용 된 다른 `[<AutoOpen>]` 확장 메서드를 포함 하는 모듈입니다.

과 용 `[<AutoOpen>]` 주의 하 여 잠재 고객 오염된 네임 스페이스 및 특성을 사용 해야 합니다. 특정 도메인에 적절 하 게 사용할 특정 라이브러리에 대 한 `[<AutoOpen>]` 성이 발생할 수 있습니다.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>잘 알려진 연산자를 사용 하는 적절 한 클래스에서 연산자 멤버를 정의 하는 것이 좋습니다.

경우에 따라 클래스 벡터와 같은 수학적 구문을 모델링 하는 데 사용 됩니다. 모델링 되는 도메인에 잘 알려진 연산자가 있을 때 유용 내장 함수는 클래스를 구성원으로 정의 합니다.

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

이 가이드는 이러한 형식에 대 한 일반적인.NET 지침에 해당합니다. 그러나 F #을 함께 F # 함수 및 메서드에서 List.sumBy 같은 멤버 제약 조건과 함께 사용할 이러한 형식에 허용이 코딩 또한 중요할 수 있습니다.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>CompiledName를 사용 하 여 제공 하는 합니다. 다른.NET 언어 소비자에 NET 이름

경우에 따라 있습니다 이름을 지정할 수 하나의 스타일에 F # 소비자에 대 한 (소문자로 표시 되도록 정적 멤버와 같은 모듈 바인딩된 함수 처럼)를 설치 했지만 다른 스타일 이름에 대 한 어셈블리로 컴파일할 때 합니다. 사용할 수는 `[<CompiledName>]` 특성을 비 F # 코드 어셈블리 사용에 대 한 다른 스타일을 제공 합니다.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

사용 하 여 `[<CompiledName>]`, 비 F # 어셈블리 소비자에 대 한.NET 명명 규칙을 사용할 수 있습니다.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>이렇게 하면 더 간단 하는 API를 제공 하는 경우 멤버 함수에 대 한 메서드 오버 로드 사용

메서드 오버 로드는 다양 한 옵션 또는 인수 하면서도 유사한 기능을 수행 해야 할 수 있는 API를 단순화 하기 위한 강력한 도구입니다.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

이 F #에서 인수의 형식 보다는 수의 인수에 오버 로드를 더 일반적입니다.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>레코드 및 공용 구조체 형식의 표현의 숨기는 이러한 종류의 디자인은 변경 될 수 있으므로

개체의 구체적인 표현을 노출 하지 마십시오. 예를 들어 구체적인 표현의 <xref:System.DateTime> 값이.NET 라이브러리 디자인의 외부, 공용 API에서 노출 되지 않습니다. 런타임 시 공용 언어 런타임 실행 전체에서 사용 하는 커밋된 구현을 알고 있습니다. 그러나 컴파일된 코드 자체는 선택 하지 않습니다 구체적인 표현에 대 한 종속성입니다.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>확장성에 대 한 구현 상속을 사용 하지 않도록

F #에서 구현 상속은 거의 사용 합니다. 또한 상속 계층 구조는 종종 복잡 하 고 새 요구 사항을 도착할 때 변경 하기 어렵습니다. 상속 구현 드문 경우에는 문제에 가장 적합 한 솔루션 하지만 사용할 다른 방법을 찾아야 할 F # 프로그램에서 같은 인터페이스 구현 다형성을 위해 설계할 때의 호환성 및 F #에서 여전히 존재 합니다.

### <a name="function-and-member-signatures"></a>함수 및 구성원 서명

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>적은 수의 여러 관련 없는 값을 반환 하는 경우 반환 값에 대 한 튜플을 사용 하 여

반환 형식에 튜플을 사용의 좋은 예는 다음과 같습니다.

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

에 대 한 여러 구성 요소를 포함 하는 형식을 반환 하거나 구성 요소 식별이 가능한 엔터티는 관련 된, 튜플을 대신 명명 된 형식을 사용 하 여 고려해 야 합니다.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>사용 하 여 `Async<T>` F # API 경계에서 비동기 프로그래밍에 대 한

라는 해당 동기 작업 인지 `Operation` 반환 하는 `T`, 비동기 작업 이름을 지정 해야 하는 다음 `AsyncOperation` 반환 하는 경우 `Async<T>` 또는 `OperationAsync` 반환 하는 경우 `Task<T>`합니다. 사용 하는 것이 좋습니다 Begin/End 메서드를 노출 하는 일반적으로 사용 되는.NET 형식에 대 한 `Async.FromBeginEnd` 확장 메서드는.NET Api에 F # 비동기 프로그래밍 모델을 제공 하려면 외관으로 씁니다.

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>예외

예외는.net; 예외 즉, 이러한 발생 하지 않습니다 자주 런타임 시. 그럴 경우 포함 된 정보 유용 합니다. 예외는 핵심.NET;의 최고 수준의 개념 응용 프로그램의 예외를 적절 한 다음 구성 요소 인터페이스의 디자인의 일환으로 쓰일 수 있으므로 it 합니다.

#### <a name="follow-the-net-guidelines-for-exceptions"></a>예외에 대 한.NET 지침에 따라

[.NET 라이브러리 디자인 지침](../../standard/design-guidelines/exceptions.md) 모든.NET 프로그래밍의 컨텍스트에서 예외 사용에 뛰어난 도움말을 제공 합니다. 이러한 지침 중 일부는 다음과 같습니다.

* 정상적인 제어 흐름에 대 한 예외를 사용 하지 마십시오. 이 기술은 OCaml 등의 언어에는 대개, 하지만 버그 발생 하기 쉽습니다 및.NET에서 비효율적일 수 있습니다. 대신, 반환 해 보십시오는 `None` 옵션에 공용 또는 예상 발생 한 실패를 나타내는 값입니다.

* 함수를 잘못 사용 하면 구성 요소에서 발생 한 예외를 문서화 합니다.

* 가능한 경우, 기존 예외는 시스템 네임 스페이스를 사용 합니다. 방지 <xref:System.ApplicationException>되지만, 합니다.

* throw 하지 않습니다 <xref:System.Exception> 는 사용자 코드로 이스케이프 되는 경우. 여기에 사용 하지 `failwith`, `failwithf`, 스크립트에서 사용 하기 위해 및 개발 중인 코드에 대 한 유용한 함수는 있지만 F # 라이브러리 코드를 더 구체적인 예외 형식 발생 하기 위해에서 제거 해야 합니다.

* 사용 하 여 `nullArg`, `invalidArg`, 및 `invalidOp` 시키려면 메커니즘으로 <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, 및 <xref:System.InvalidOperationException> 적절 합니다.

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a>실패 예외 시나리오는 아닌 경우 반환 형식에 대 한 옵션 값을 사용 하는 것이 좋습니다

"예외"; 수 있어야 하는 예외에 대 한.NET 접근이입니다. 즉, 비교적 자주 발생 해야 합니다. 그러나 일부 작업 (예: 테이블 검색)이 자주 실패할 수 있습니다. F # 옵션 값은 이러한 작업의 반환 형식을 나타낼 수 있는 좋은 방법입니다. 이러한 작업은 일반적으로 "try" 이름 접두사로 시작:

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a>확장 멤버

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>F #에서 F # 확장 멤버를 신중 하 게 적용-에-F # 구성 요소

일반적으로 대부분의 모드를 사용 하 여의 형식과 연관 내장 연산의 클로저에 있는 작업에 대해 F # 확장 멤버에만 사용 해야 합니다. 일반적으로 사용 F #에 다양 한.NET 형식의 관용구 더 있는 Api를 제공 하는 것:

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>공용 구조체 유형

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>구분 된 공용 구조체를 사용 하 여 트리 구조의 데이터에 대 한 클래스 계층 구조 대신

트리 형식 구조는 재귀적으로 정의 합니다. 이것은 상속을 잘못 된 구문이 구별 된 결합 된 세련 된입니다.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

또한 구별 된 공용 구조체를 사용 하 여 트리 형식 데이터를 나타내는 패턴 일치에서 exhaustiveness에서 이점을 얻을 수 있습니다.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>사용 하 여 `[<RequireQualifiedAccess>]` 사례 이름이 충분히 고유 하지 않습니다. 공용 구조체 형식에 대해

직접 있는 도메인 이름이 같은 구별 된 공용 구조체 케이스와 같은 다른 작업에 가장 적합 한 이름을 찾을 수 있습니다. 사용할 수 있습니다 `[<RequireQualifiedAccess>]` 혼동 인 한 오류 숨기기 종속의 순서를 트리거하지 않도록 하기 위해 case 이름을 명확 하 게 `open` 문

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>이진 호환 Api에 대 한 구별 된 공용 구조체의 표현의 숨기는 이러한 종류의 디자인은 변경 될 수 있으므로

F # 패턴 일치 forms 간결한 프로그래밍 모델에 대 한 공용 구조체 형식을 사용합니다. 앞에서 설명한 대로 이러한 형식의 디자인은 변경 될 수 있으므로 하는 경우 구체적인 데이터 표현을 노출 하지 마십시오.

예를 들어 구별된 된 공용 구조체의 표현을 숨길 수 있는 private 또는 internal 선언을 사용 하 여 또는 서명 파일을 사용 하 여 합니다.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

구별 된 공용 구조체를 무차별적으로 표시 하는 경우 알 수 있습니다이 버전으로 하드 라이브러리 사용자 코드를 중단시 키 지 않고도. 대신, 해당 형식의 값에 대 한 패턴 일치를 허용 하기 위해 하나 이상의 활성 패턴을 노출 하는 것이 좋습니다.

활성 패턴에는 F # 공용 구조체 형식에 직접 노출 방지 하는 동안 일치 하는 패턴으로 F # 소비자가 제공 하는 다른 방법을 제공 합니다.

### <a name="inline-functions-and-member-constraints"></a>인라인 함수와 멤버 제약 조건

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>인라인 함수를 사용 하 여 암시적된 멤버 제약 조건, 정적으로 확인 된 제네릭 형식이 일반 숫자 알고리즘을 정의 합니다.

산술 멤버 제약 조건 및 F # 비교 제약 F # 프로그래밍에 대 한 표준은입니다. 예를 들어, 다음 코드를 고려하세요.

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

이 함수는 다음과 같습니다.

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

이것이 수학 라이브러리의 공용 API에 대 한 적절 한 함수입니다.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>형식 클래스 및 덕 시뮬레이션 하기 멤버 제약 조건을 사용 하지 마십시오

"덕"를 시뮬레이션할 수는 F # 멤버 제약 조건을 사용 하 여 합니다. 그러나 멤버 하는 사용 하 여이 F #에 속하지 않은 일반을 사용 해야-에-F # 라이브러리 디자인 합니다. 사용자 코드 고정적인 하 고 하나의 특정 프레임 워크 패턴 제한은를 모르거나 비표준 암시적 제약 조건에 따라 라이브러리 디자인 있기 때문입니다.

또한 매우 긴 컴파일 시간 많이 이런이 방식으로 멤버 제약 조건 사용할 때 발생할 수 있는 가능성이 있습니다.

### <a name="operator-definitions"></a>연산자 정의

#### <a name="avoid-defining-custom-symbolic-operators"></a>기호화 된 사용자 지정 연산자를 정의 하지 마십시오.

사용자 지정 연산자는 상황에 따라 필수 이며 구현 코드의 큰 본문이 내에 매우 유용한 표기 장치입니다. 라이브러리의 새 사용자에 대 한 명명 된 함수는 보다 쉽게 사용할 수 있습니다. 또한 사용자 지정 기호 연산자는 문서를 하기 어려울 수 있습니다 및 사용자 들이 찾을 IDE 및 검색 엔진에서 기존 제한으로 인해 연산자에 대 한 도움말을 조회 하기가 더 어려워집니다.

결과적으로, 프로그램 및 기능을 명명 된 함수 멤버를 게시 하 고 또한 표기법 상의 이점을 설명서와 cognitive 비용 있는 것 보다 클 경우에이 기능에 대 한 연산자를 노출 하는 것이 좋습니다.

### <a name="units-of-measure"></a>측정 단위

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>신중 하 게 측정 단위를 사용 하 여 F # 코드에 추가 된 형식 안정성

측정 단위에 대 한 입력 추가 정보는 다른.NET 언어에서 볼 때 지워집니다. 주의.NET 구성 요소, 도구 및 리플렉션 단위 san은 형식 표시 됩니다. 예를 들어 C# 소비자가 표시 됩니다 `float` 대신 `float<kg>`합니다.

### <a name="type-abbreviations"></a>형식 약어

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>신중 하 게 형식 약어를 사용 하 여 F # 코드를 단순화 합니다.

.NET 구성 요소, 도구 및 리플렉션 형식에 대 한 약식된 이름이 표시 되지 않습니다. 형식 약어의 중요 한 사용량에 나타날 것 보다 복잡 한 실제로, 소비자가 혼동을 줄 수 있는 도메인을 축소할 수 있습니다.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>해당 멤버 및 속성 형식에서 사용할 수 있는 기본적으로 달라 야 하는 공용 형식에 대 한 형식 약어를 방지 합니다.

이 경우 형식에서 정의 하 고 실제 형식 표현에 대해 자세히 보여 줍니다. 대신, 클래스 유형 또는 단일 대/소문자 구별 된 공용 구조체에는 약어를 배치 하는 것이 좋습니다. 또는, 성능이 필수적인 경우는 약어를 래핑하는 구조체 형식을 사용 하십시오.

예를 들어 F # 맵의 특별 한 경우로 예를 들어 다중 지도 정의 하기 쉽습니다.

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

그러나이 형식에 대 한 논리 점 표기법 작업 지도 대 한 작업으로 동일 하지 않은-lookup 연산자 매핑할 수 있는지 합리적인 하는 예를 들어 합니다. [키] 반환이 예외를 발생 시키는 대신 사전에 키가 없는 경우에 빈 목록입니다.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>다른.NET 언어에서 사용 하기 위해 라이브러리에 대 한 지침

다른.NET 언어에서 사용 하기 위해 라이브러리를 디자인할 때이에 맞게 중요는 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)합니다. 이 문서에 이러한 라이브러리는 F # 달리 바닐라.NET 라이브러리로 표시 된-제한 없이 생성 F #을 사용 하는 라이브러리를 연결 합니다. F #의 사용을 최소화 하 여.NET Framework의 나머지 부분과 일치 친숙 하 고 관용구 Api를 제공 하 의미 바닐라.NET 라이브러리 디자인-공용 API에서 특정 구문입니다. 규칙은 다음 섹션에 설명 되어 있습니다.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Namespace 및 형식 디자인 (라이브러리에 대 한 다른.NET 언어에서 사용 하기 위해)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>구성 요소의 공용 API에.NET 명명 규칙을 적용

약식된 이름이 및.NET 대/소문자가 지침의 사용에 특별히 주의 해야 합니다.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>구성 요소에 대 한 기본 조직 구조도 네임 스페이스, 형식 및 멤버를 사용 하 여

공용 기능을 포함 하는 모든 파일으로 시작 해야는 `namespace` 선언 및 네임 스페이스에만 공용 엔터티 형식 이어야 합니다. F # 모듈을 사용 하지 마십시오.

구현 코드, 형식 유틸리티 및 유틸리티 함수를 보유 하 public이 아닌 모듈을 사용 합니다.

정적 형식은 해야 원하는 모듈을 통해 F # 모듈 내에서 사용할 수 없습니다..NET API 디자인 개념 하 고 다른 오버 로드를 사용 하는 API의 향후 발전을 허용 합니다.

예를 들어 다음 공용 API 대신:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

대신 고려 하십시오.

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>형식 디자인 하지 발전 하는 경우 F # 레코드 형식을 바닐라.NET Api에서 사용

F # 레코드 종류는 간단한.NET 클래스를 컴파일합니다. 이러한 작업은 몇 가지 단순 하 고 안정적인 형식 Api에 대 한 적합 합니다. 사용을 고려해 야는 `[<NoEquality>]` 및 `[<NoComparison>]` 특성을 인터페이스의 자동 생성을 표시 합니다. 또한 공용 필드 이러한 노출으로 바닐라.NET Api의에서 변경 가능한 레코드 필드를 사용 하지 마십시오. 항상 클래스 API의 미래 변화에 대 한 보다 유연한 옵션을 제공 하는지 여부를 고려 합니다.

예를 들어 다음 F # 코드는 C# 소비자에 게 공용 API를 노출합니다.

F #의 경우:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

C#: 

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>.NET Api 바닐라에서 F # 공용 구조체 형식의 표현을 숨기기

F # 공용 구조체 형식을 거의 사용 되지 않는 구성 요소 경계를 넘어에 F #-에-F # 코딩 합니다. 구성 요소 및 라이브러리에서 내부적으로 사용 될 때에 뛰어난 구현 장치 됩니다.

바닐라.NET API를 디자인할 때 공용 구조체 형식의 표현을 개인 선언 또는 서명 파일을 사용 하 여 숨기는 것이 좋습니다.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

또한 원하는 제공 하기 내부적으로 멤버와 함께 union 표현을 사용 하는 형식을 보강할 수 있습니다. NET 연결 API입니다.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>디자인 GUI 및 프레임 워크의 디자인 패턴을 사용 하 여 다른 구성 요소

WinForms, WPF 및 ASP.NET 같은.NET에서 사용할 수 있는 다양 한 프레임 워크 있습니다. 이러한 프레임 워크에서 사용 하기 위해 구성 요소를 디자인 하는 경우 각각에 대 한 이름 지정 및 디자인 규칙에 사용 해야 합니다. 예를 들어 WPF 프로그래밍에 대 한 디자인 하는 클래스에 대 한 WPF 디자인 패턴을 적용 합니다. 사용자 인터페이스 프로그래밍에서 모델에 대 한 이벤트와 같은 디자인 패턴을 사용 하 여 이며 같은 알림 기반 컬렉션에 <xref:System.Collections.ObjectModel>합니다.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>개체와 멤버 디자인 (라이브러리에 대 한 다른.NET 언어에서 사용 하기 위해)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>CLIEvent 특성을 사용 하 여.NET 이벤트를 노출 하려면

생성 한 `DelegateEvent` 대리자 개체를 사용 하는 형식의 특정.net 및 `EventArgs` (아닌 `Event`, 사용 하는 `FSharpHandler` 유형을 기본적으로) 하는 이벤트는 다른.NET 언어에 친숙 한 방식으로 게시 됩니다.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>.NET 작업을 반환 하는 메서드로 비동기 작업 노출

작업을 나타내는 활성 비동기 계산.NET에서 사용 됩니다. 작업은 일반적으로 F # 보다 덜 compositional `Async<T>` 개체의 경우 "이미 실행 중" 작업을 나타내는지과 병렬 컴퍼지션을 수행 하는 하거나 취소 신호 오류 코드 및 기타 전파를 숨기는 함께 구성 될 수 있으므로 컨텍스트 매개 변수입니다.

그러나, 그럼에도 불구 하 고 작업을 반환 하는 메서드는.NET에서 비동기 프로그래밍의 표준 표현입니다.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

자주 됩니다도 명시적 취소 토큰을 수락 하려면:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>F # 함수 형식 대신.NET 대리자 형식을 사용합니다

와 같은 "화살표" 형식 "F # 함수 형식"을 의미 하는 여기 `int -> int`합니다.

문장을 사용 하십시오.

```fsharp
member this.Transform(f:int->int) =
    ...
```

방법

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

F # 함수 형식으로 나타납니다 `class FSharpFunc<T,U>` 다른.NET 언어 이며 대리자 형식을 이해 하는 언어 기능 및 도구에 대 한 덜 적합 합니다. .NET Framework 3.5 이상을 대상으로 하는 상위 기 메서드를 작성할 때는 `System.Func` 및 `System.Action` 대리자는.NET 개발자가 원활한 방식으로 이러한 Api를 사용할 수 있도록 게시 하려면 오른쪽 Api입니다. (.NET Framework 2.0을 대상으로 지정 하는 경우 시스템에서 정의한 대리자 형식이 더 제한적 이며와 같은 미리 정의 된 대리자 유형을 사용 하 여 `System.Converter<T,U>` 하거나 특정 대리자 형식을 정의 합니다.)

긍 적 적인 측면에서.NET의 대리자는 F #에 대 한 자연-라이브러리 연결 (F #에 다음 섹션을 참조 하십시오.-연결 라이브러리)입니다. 더 높은 순서 메서드 바닐라.NET 라이브러리를 개발 하는 경우 일반적인 구현 전략을 처리할 수 있도록 모든 F # 함수 형식을 사용 하 여 구현 한 후 실제 F # 위에 씬 외관으로 대리자를 사용 하 여 공용 API를 만드는 결과적으로, 구현입니다.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>F # 옵션 값을 반환 하는 대신 TryGetValue 패턴을 사용 하 고 F # 옵션 값을 인수로 사용 하도록 메서드 오버 로드 하는 것이 좋습니다.

Api에서 F # 옵션 종류를 위한 일반적인 패턴은 더 나은 바닐라에서 구현 된 표준.NET을 사용 하 여.NET Api 디자인 기술을 합니다. F # 옵션 값을 반환 하는 대신 bool 반환 형식 및 "TryGetValue" 패턴에서와 같이 out 매개 변수를 사용 하는 것이 좋습니다. 및 F # 옵션 값을 매개 변수로 수행 하는 대신 메서드 오버 로드 또는 선택적 인수를 사용 하 여 것이 좋습니다.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>.NET 컬렉션 인터페이스를 사용 하 여 형식을 IEnumerable\<T\> 및 IDictionary\<키, 값\> 매개 변수 및 반환 값

.NET 배열과 같은 구체적 컬렉션 형식의 사용 하지 않도록 `T[]`, F # 형식 `list<T>`, `Map<Key,Value>` 및 `Set<T>`, 및와 같은.NET 구체적 컬렉션 형식은 `Dictionary<Key,Value>`합니다. .NET 라이브러리 디자인 지침이 같은 다양 한 컬렉션 형식을 사용 하는 경우에 관한 좋은 조언 `IEnumerable<T>`합니다. 일부 배열 사용 (`T[]`) 성능 부 지에 따라에서 허용 됩니다. 특히 `seq<T>` 은 방금 F #에 별칭이 `IEnumerable<T>`, 되어 있으므로 seq 종종 바닐라.NET API에 대 한 적절 한 형식입니다.

F #을 나열 합니다.

```fsharp
member this.PrintNames(names : string list) =
    ...
```

F # 시퀀스를 사용 합니다.

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>0 인수 메서드를 정의 메서드의 유일한 입력된 유형으로의 단위 유형을 사용 하거나 유일한으로 void를 반환 하는 메서드를 정의 하는 형식 반환

단위 형식의 다른 곳에 사용을 하지 마십시오. 다음은 좋은입니다.

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

다음은 잘못 되었습니다.

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>바닐라.NET API 경계에 null 값을 확인

F # 구현 코드를 변경할 수 없는 디자인 패턴 및 F # 형식에 대 한 null 리터럴의 사용에 대 한 제한으로 인해 더 적은 null 값이 있는 경향이 있습니다. 다른.NET 언어 종종 null 값 훨씬 더 자주 사용 합니다. 이 인해 바닐라.NET API를 공개 하는 F # 코드 API 경계에서 null에 대 한 매개 변수를 확인 하 고 F # 구현 코드를 더 깊은 흐름에서 이러한 값을 방지 해야 합니다. `isNull` 함수 또는에 패턴 일치는 `null` 패턴을 사용할 수 있습니다.

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>튜플 반환 값으로 사용 하지 마십시오.

대신, 데이터를 집계를 보유 하 고 있거나 out 매개 변수를 사용 하 여 여러 값을 반환 하는 명명 된 형식을 반환 하는 것이 좋습니다. 한 구조체.NET에 있어도 (튜플 구조체에 대 한 C# 언어 지원과 포함)은 가장 많이 제공 하지 않습니다 이상적인 및 예상 되는 API.NET 개발자를 위한.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>변환 매개 변수는 사용 하지

대신,.NET 호출 규칙을 사용 하 여 ``Method(arg1,arg2,…,argN)``합니다.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

팁: 모든.NET 언어에서 사용 하기 위해 라이브러리를 디자인 하는 경우 없기 맬웨어에 일부 실험적 C# 및 Visual Basic 프로그래밍 라이브러리 "느낌 오른쪽" 이러한 언어에서 충족 되도록 작업을 실제로 수행 합니다. 또한 Reflector.NET 및 Visual Studio 개체 브라우저와 같은 도구를 사용 하 여 라이브러리 및 해당 설명서 개발자에 게 예상 대로 표시 되는지 확인 합니다.

## <a name="appendix"></a>부록

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>다른.NET 언어에서 사용 하기 위해 F # 코드를 디자인할 때의 종단 간 예제

다음 클래스를 살펴보세요.

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

이 클래스의 유추 된 F # 형식은 다음과 같습니다.

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

F # 이와 다른.NET 언어를 사용 하 여 프로그래머에 표시 되는 방식을 살펴보겠습니다. 예를 들어 대략적인 C# "서명"은 다음과 같습니다.

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

F # 나타내는 방법 구문 여기에서 주의 해야 할 몇 가지 중요 한 사항이 있습니다. 예를 들어:

* 인수 이름 같은 메타 데이터를 유지 되었습니다.

* 두 개의 인수를 사용 하는 F # 메서드로는 두 개의 인수를 사용 하는 C# 메서드가 됩니다.

* 함수 및 목록에는 F # 라이브러리 시그니처에 있는 해당 형식에 대 한 참조 됩니다.

다음 코드에서는 이러한 것 들을 고려 하도록 하려면이 코드를 조정 하는 방법을 보여 줍니다.

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

코드의 유추 된 F # 형식은 다음과 같습니다.

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

C# 시그니처는 이제 다음과 같습니다.

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

바닐라.NET 라이브러리의 일부는 다음과 같이이 형식을 사용 하기 위해 준비 하는 수정 사항은 구성.

* 여러 개의 이름을 조정: `Point1`, `n`, `l`, 및 `f` 상태가 된 `RadialPoint`, `count`, `factor`, 및 `transform`각각.

* 반환 형식으로 사용 되는 `seq<RadialPoint>` 대신 `RadialPoint list` 변경 사용 하 여 목록을 생성 하 여 `[ ... ]` 를 사용 하 여 시퀀스 생성 `IEnumerable<RadialPoint>`합니다.

* .NET 대리자 형식을 사용 `System.Func` F # 함수 형식 대신 합니다.

따라서 C# 코드에서 사용할 테 훨씬 더 있습니다.
