---
title: 키워드 참조(F#)
description: '모든 F # 언어 키워드에 대 한 정보 링크를를 찾습니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 2cb2fbb3236fcfeebc801b467d657f031b8da55a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="keyword-reference"></a>키워드 참조

이 항목에서는 모든 F # 언어 키워드에 대 한 정보 링크를 제공 합니다.

## <a name="f-keyword-table"></a>F # 키워드 테이블

다음 표에서 간략 한 설명 및 자세한 정보가 포함 된 관련 항목에 대 한 링크와 함께 알파벳 순서로 모든 F # 키워드를 보여 줍니다.

|키워드|링크|설명|
|-------|----|-----------|
|`abstract`|[멤버](members/index.md)<br /><br />[추상 클래스](abstract-classes.md)|에는 선언 또는 가상 인지 하 고는 기본 구현을 글꼴로 구현이 없는 메서드를 나타냅니다.|
|`and`|[`let` 바인딩](functions/let-bindings.md)<br /><br />[멤버](members/index.md)<br /><br />[제약 조건](generics/constraints.md)|상호 재귀 바인딩, 속성 선언에서 및 제네릭 매개 변수에 대 한 여러 제약 조건에 사용 합니다.|
|`as`|[클래스](classes.md)<br /><br />[패턴 일치](Pattern-Matching.md)|현재 클래스 개체에는 개체 이름을 지정 하는 데 사용 합니다. 또한 일치 하는 패턴 내의 전체 패턴에 이름을 지정 하는 데 사용 합니다.|
|`assert`|[어설션](assertions.md)|디버깅 하는 동안 코드를 확인 하는 데 사용 합니다.|
|`base`|[클래스](classes.md)<br /><br />[상속](inheritance.md)|기본 클래스 개체의 이름으로 사용 합니다.|
|`begin`|[자세한 구문](verbose-syntax.md)|자세한 구문 코드 블록의 시작을 나타냅니다.|
|`class`|[클래스](classes.md)|자세한 구문 클래스 정의의 시작을 나타냅니다.|
|`default`|[멤버](members/index.md)|추상 메서드의 구현을 나타냅니다. 추상 메서드 선언 함께 사용 하는 가상 메서드를 만듭니다.|
|`delegate`|[대리자](delegates.md)|대리자를 선언 하는 데 사용 합니다.|
|`do`|[do 바인딩](functions/do-bindings.md)<br /><br />[루프: `for...to` 식](loops-for-to-expression.md)<br /><br />[루프: `for...in` 식](loops-for-in-expression.md)<br /><br />[루프: `while...do` 식](loops-while-do-expression.md)|루프 구문 또는 명령 코드를 실행 하는 데 사용 합니다.|
|`done`|[자세한 구문](verbose-syntax.md)|자세한 구문에서 반복 식에 코드 블록의 끝을 나타냅니다.|
|`downcast`|[캐스팅 및 변환](casting-and-conversions.md)|하위 상속 체인에 있는 형식으로 변환 하는 데 사용 합니다.|
|`downto`|[루프: `for...to` 식](loops-for-to-expression.md)|에 `for` 역순에서 수를 계산할 때 사용 되는 식입니다.|
|`elif`|[조건식: `if...then...else`](conditional-expressions-if-then-else.md)|조건부 분기에 사용 합니다. 약식 형태 `else if`합니다.|
|`else`|[조건식: `if...then...else`](conditional-expressions-if-then-else.md)|조건부 분기에 사용 합니다.|
|`end`|[구조체](structures.md)<br /><br />[구별된 공용 구조체](discriminated-unions.md)<br /><br />[레코드](records.md)<br /><br />[형식 확장명](type-extensions.md)<br /><br />[자세한 구문](verbose-syntax.md)|형식 정 및 형식 확장에서 멤버 정의 섹션의 끝을 나타냅니다.<br /><br />로 시작 하는 코드 블록의 끝을 지정 하는 데 사용 되는 자세한 구문에서는 `begin` 키워드입니다.|
|`exception`|[예외 처리](exception-handling/index.md)<br /><br />[예외 형식](exception-handling/exception-types.md)|예외 형식을 선언 하는 데 사용 합니다.|
|`extern`|[외부 함수](functions/external-functions.md)|선언 된 프로그램 요소를 다른 어셈블리 또는 이진 파일에 정의 되었는지 나타냅니다.|
|`false`|[기본 형식](primitive-types.md)|부울 리터럴은으로 사용 됩니다.|
|`finally`|[예외: `try...finally` 식](exception-handling/the-try-finally-expression.md)|와 함께 사용 `try` 예외 발생 여부에 관계 없이 실행 되는 코드 블록을 소개 합니다.|
|`fixed`|[고정](fixed.md)|포인터를 가비지 수집 되지 않도록 방지 하기 위해 스택의 "고정" 하는 데 사용 합니다.|
|`for`|[루프: `for...to` 식](loops-for-to-expression.md)<br /><br />[루프: for...in 식](loops-for-in-expression.md)|루프 구문에 사용 합니다.|
|`fun`|[람다 식:는 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md)|람다 식, 익명으로 알려진 함수에에서 사용 합니다.|
|`function`|[일치 식](match-expressions.md)<br /><br />[람다 식: fun 키워드](functions/lambda-expressions-the-fun-keyword.md)|대신 하는 약식 표현으로 사용는 `fun` 키워드와 `match` 가 단일 인수를 일치 시킬 패턴을 유지 하는 람다 식에는 식입니다.|
|`global`|[네임스페이스](namespaces.md)|최상위.NET 네임 스페이스를 참조 하는 데 사용 합니다.|
|`if`|[조건식: `if...then...else`](conditional-expressions-if-then-else.md)|조건부 분기 구문에 사용 합니다.|
|`in`|[루프: for...in 식](loops-for-in-expression.md)<br /><br />[자세한 구문](verbose-syntax.md)|한 사용 되는 시퀀스 식, 자세한 구문에서 식을 바인딩과 구분을 합니다.|
|`inherit`|[상속](inheritance.md)|기본 클래스 또는 기본 인터페이스를 지정 하는 데 사용 합니다.|
|`inline`|[함수](functions/index.md)<br /><br />[인라인 함수](functions/inline-functions.md)|호출자의 코드에 직접 통합 해야 하는 함수를 나타내는 데 사용 합니다.|
|`interface`|[인터페이스](interfaces.md)|선언 하 고 인터페이스를 구현 하는 데 사용 합니다.|
|`internal`|[Access Control](access-control.md)|멤버가 표시 되는지 지정 하는 데 외부가 아니라 어셈블리 내 합니다.|
|`lazy`|[지연 계산](lazy-computations.md)|계산 결과가 필요한 경우에 수행 하는 것을 지정 하는 데 사용 합니다.|
|`let`|[`let` 바인딩](functions/let-bindings.md)|연결 하거나 값 또는 함수 이름을 바인딩하려면 하는 데 사용 합니다.|
|`let!`|[비동기 워크플로](asynchronous-workflows.md)<br /><br />[계산 식](computation-expressions.md)|비동기 이름을 비동기 계산의 결과에 바인딩할 워크플로와 또는 결과 계산 하는 형식의 이름을 바인딩하는 데 사용 되는 다른 계산 식를 사용 합니다.|
|`match`|[일치 식](match-expressions.md)|패턴 값을 비교 하 여 분기 하는 데 사용 합니다.|
|`member`|[멤버](members/index.md)|속성이 나 메서드가 개체 형식에서 선언 하는 데 사용 합니다.|
|`module`|[모듈](modules.md)|관련된 형식, 값 및 기능을 논리적으로 분리 하 고 다른 코드의 그룹 이름을 연결 하는 데 사용 합니다.|
|`mutable`|[let 바인딩](functions/let-bindings.md)|변경할 수 있는 값 즉, 변수를 선언 하는 데 사용 합니다.|
|`namespace`|[네임스페이스](namespaces.md)|논리적으로 분리 하 고 다른 코드에서 관련된 형식 및 모듈의 그룹 이름을 연결 하는 데 사용 합니다.|
|`new`|[생성자](members/constructors.md)<br /><br />[제약 조건](generics/constraints.md)|선언, 정의 또는 만들어지는 또는 개체를 만들 수 있는 생성자를 호출 하는 데 사용 합니다.<br /><br />또한 제네릭 매개 변수 제약 조건에 나타내는 데는 형식이 특정 생성자를 포함 해야 합니다.|
|`not`|[기호 및 연산자 참조](symbol-and-operator-reference/index.md)<br /><br />[제약 조건](generics/constraints.md)|실제로 키워드입니다. 그러나 `not struct` 조합 하 여 제네릭 매개 변수 제약 조건으로 사용 됩니다.|
|`null`|[Null 값](values/null-values.md)<br /><br />[제약 조건](generics/constraints.md)|개체의 없음을 나타냅니다.<br /><br />제네릭 매개 변수 제약 조건에도 사용 합니다.|
|`of`|[구별된 공용 구조체](discriminated-unions.md)<br /><br />[대리자](delegates.md)<br /><br />[예외 형식](exception-handling/exception-types.md)|대리자 및 예외 선언 및 구분 된 공용 구조체의 값을 범주 유형을 나타내는 사용 합니다.|
|`open`|[가져오기 선언: `open` 키워드](import-declarations-the-open-keyword.md)|네임 스페이스 또는 모듈의 내용을 한정자 없이 사용할 수 있도록 하는 데 사용 합니다.|
|`or`|[기호 및 연산자 참조](symbol-and-operator-reference/index.md)<br /><br />[제약 조건](generics/constraints.md)|부울 조건으로 사용 하는 부울으로 `or` 연산자입니다. 에 해당 '||`.<br /><br />또한 멤버 제약 조건을 사용합니다.|
|`override`|[멤버](members/index.md)|추상 또는 가상 메서드는 기본 버전에서 다른 버전을 구현 하는 데 사용 합니다.|
|`private`|[Access Control](access-control.md)|코드에 동일한 형식이 나 모듈 멤버에 대 한 액세스를 제한합니다.|
|`public`|[Access Control](access-control.md)|형식 외부에서 멤버에 액세스할 수 있습니다.|
|`rec`|[함수](functions/index.md)|재귀 것을 나타내는 데 사용 합니다.|
|`return`|[비동기 워크플로](Asynchronous-Workflows.md)<br /><br />[계산 식](computation-expressions.md)|계산 식의 결과로 제공 하는 값을 나타내는 데 사용 합니다.|
|`return!`|[계산 식](computation-expressions.md)<br /><br />[비동기 워크플로](asynchronous-workflows.md)|계산 식을 나타내는 데는 평가 시 포함 하는 계산 식의 결과 제공 합니다.|
|`select`|[쿼리 식](query-expressions.md)|쿼리 식에는 필드 또는 추출 하는 열을 지정할 수 있습니다. Note 이것이 고 실제로 예약어 하지 않은 경우의 적절 한 컨텍스트 키워드 처럼만 작동 하는 상황별 키워드입니다.|
|`static`|[멤버](members/index.md)|메서드 또는 형식 인스턴스 없이 호출 될 수 있는 속성이 나 형식의 모든 인스턴스 간에 공유 되는 값 멤버를 나타내는 데 사용 합니다.|
|`struct`|[구조체](structures.md)<br /><br />[제약 조건](generics/constraints.md)|구조체 형식을 선언 하는 데 사용 합니다.<br /><br />제네릭 매개 변수 제약 조건에도 사용 합니다.<br /><br />모듈 정의에서 OCaml 호환성을 위해 사용 합니다.|
|`then`|[조건식: `if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[생성자](members/constructors.md)|조건식에 사용 합니다.<br /><br />또한 개체 생성 후 부작용을 수행 하는 데 사용 합니다.|
|`to`|[루프: `for...to` 식](loops-for-to-expression.md)|에 사용 된 `for` 루프 범위를 나타냅니다.|
|`true`|[기본 형식](primitive-types.md)|부울 리터럴은으로 사용 됩니다.|
|`try`|[예외: try...with 식](exception-handling/the-try-with-expression.md)<br /><br />[: 예외 마지막 식](exception-handling/the-try-finally-expression.md)|예외를 생성할 수 있는 코드 블록을 소개 하는 데 사용 합니다. 와 함께 사용 `with` 또는 `finally`합니다.|
|`type`|[F# 형식](fsharp-types.md)<br /><br />[클래스](classes.md)<br /><br />[레코드](records.md)<br /><br />[구조체](structures.md)<br /><br />[열거형](enumerations.md)<br /><br />[구별된 공용 구조체](discriminated-unions.md)<br /><br />[형식 약어](type-abbreviations.md)<br /><br />[측정 단위](units-of-measure.md)|클래스, 레코드, 구조체, 구분된 된 공용 구조체, 열거형 형식, 측정 단위를 선언 하거나 약어를 입력 하는 데 사용 합니다.|
|`upcast`|[캐스팅 및 변환](casting-and-conversions.md)|상위 상속 체인에 있는 형식으로 변환 하는 데 사용 합니다.|
|`use`|[리소스 관리: `use` 키워드](resource-management-the-use-keyword.md)|대신 `let` 필요로 하는 값에 대 한 `Dispose` 리소스를 호출 합니다.|
|`use!`|[계산 식](computation-expressions.md)<br /><br />[비동기 워크플로](asynchronous-workflows.md)|대신 `let!` 비동기 워크플로 및 기타 계산 해야 하는 값에 대 한 `Dispose` 리소스를 호출 합니다.|
|`val`|[명시적 필드: `val` 키워드](members/explicit-fields-the-val-keyword.md)<br /><br />[시그니처](signatures.md)<br /><br />[멤버](members/index.md)|제한 된 상황에서 멤버를 선언 하는 형식 또는 값을 나타내기 위해 서명에서 사용 합니다.|
|`void`|[기본 형식](primitive-types.md)|.NET 나타냅니다 `void` 유형입니다. 다른.NET 언어와 상호 작용할 때 사용 됩니다.|
|`when`|[제약 조건](generics/constraints.md)|부울 조건에 사용 됩니다 (*때 가드*) 패턴 일치 하 고 제네릭 형식 매개 변수에 대 한 제약 조건 절을 사용 하 여 합니다.|
|`while`|[루프: `while...do` 식](loops-while-do-expression.md)|루핑 구성을 소개합니다.|
|`with`|[일치 식](match-expressions.md)<br /><br />[개체 식](object-expressions.md)<br /><br />[레코드 식 복사 및 업데이트](copy-and-update-record-expressions.md)<br /><br />[형식 확장명](type-extensions.md)<br /><br />[예외: `try...with` 식](exception-handling/the-try-with-expression.md)|와 함께 사용 된 `match` 패턴 일치 식에에서는 키워드입니다. 또한 개체 식에 사용 되는 레코드 복사 식 되 고 멤버의 정의 소개 하 고 예외 처리기를 사용 하 여 확장을 입력 합니다.|
|`yield`|[시퀀스](sequences.md)|시퀀스 식에서 시퀀스에 대 한 값을 생성 하는 데 사용 합니다.|
|`yield!`|[계산 식](computation-expressions.md)<br /><br />[비동기 워크플로](asynchronous-workflows.md)|계산 식에서 포함 하는 계산 식에 대 한 결과 컬렉션에 지정한 계산 식의 결과 추가 하는 데 사용 합니다.|

다음과 같은 토큰 OCaml 언어의 키워드에에서 있기 때문에 F #에서 예약 되어 있습니다.

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

사용 하는 경우는 `--mlcompatibility` 컴파일러 옵션을 식별자로 위의 키워드를 사용할 수는 있습니다.

다음과 같은 토큰 F # 언어의 향후 확장에 대 한 키워드로 예약 되어 있습니다.

* `atomic`
* `break`
* `checked`
* `component`
* `const`
* `constraint`
* `constructor`
* `continue`
* `eager`
* `event`
* `external`
* `fixed`
* `functor`
* `include`
* `method`
* `mixin`
* `object`
* `parallel`
* `process`
* `protected`
* `pure`
* `sealed`
* `tailcall`
* `trait`
* `virtual`
* `volatile`

## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[기호 및 연산자 참조](symbol-and-operator-reference/index.md)

[컴파일러 옵션](compiler-options.md)
