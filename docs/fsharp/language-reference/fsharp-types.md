---
title: F# 형식
description: 'F # 및 F # 형식 어떻게 명명 및 설명 대 한 사용 되는 형식에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 42521ed75a76753af81d3bbb9693ec5af29536ad
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="f-types"></a>F# 형식

이 항목에서는 F # 및 F # 형식 어떻게 명명 및 설명 대 한 사용 되는 형식에 설명 합니다.


## <a name="summary-of-f-types"></a>F # 형식 요약
일부 형식은 간주 됩니다 *기본 형식*, 예: 부울 형식 `bool` 및 바이트 수와 문자에 대 한 형식을 포함 하는 다양 한 크기의 정수 계열 및 부동 소수점 형식입니다. 이러한 형식은에 설명 된 [기본 형식](primitive-types.md)합니다.

다른 언어에 내장 된 튜플, 목록, 배열, 시퀀스, 레코드, 포함 형식과 구별 된 공용 구조체입니다. 다른.NET 언어와 경험이 F # 학습 하는 경우 이러한 각 형식에 대 한 항목은 읽어야 합니다. 에 포함 된 이러한 형식에 대 한 자세한 정보에 대 한 링크는 [관련 항목](https://msdn.microsoft.com/library/#rel) 이 항목의 섹션입니다. 이러한 F #-특정 형식을 함수형 프로그래밍 언어에 공통적인 프로그래밍의 스타일을 지원 합니다. 이 형식의 대부분 연결한 F # 라이브러리에서 이러한 형식에서 일반적인 작업을 지 원하는 모듈입니다.

함수 형식의 매개 변수 형식에 대 한 정보를 포함 및 반환 형식입니다.

.NET Framework에는 개체 형식, 인터페이스 형식, 대리자 형식 및 다른 사용자의 원인입니다. 다른.NET 언어의 경우와 마찬가지로 사용자 고유의 개체 형식을 정의할 수 있습니다.

F # 코드에서 라는 별칭을 정의할 수는 또한 *형식 약어*, 하는 형식에 대 한 대체 이름입니다. 형식을 나중에 변경 될 수 있습니다 및 형식에 의존 하는 코드를 변경 하지 못하도록 할 때 형식 약어를 사용할 수 있습니다. 또는 코드를 읽고 이해 하기 쉽게 만들 수 있는 형식에 대 한 이름으로 형식 약어를 사용할 수 있습니다.

F # 함수형 프로그래밍을 염두에 두고 설계 되는 유용한 컬렉션 형식을 제공 합니다. 이러한 컬렉션 형식은 사용 코드 스타일의 기능적를 작성할 수 있습니다. 자세한 내용은 참조 [F # 컬렉션 형식](fsharp-collection-types.md)합니다.


## <a name="syntax-for-types"></a>형식에 대 한 구문
F # 코드에서는 형식 이름을 작성 해야 하는 경우가 많습니다. 모든 형식에 구문 형식 및 형식 주석을, 추상 메서드 선언, 대리자 선언, 서명 및 기타 구문에서 이러한 구문 형식을 사용 합니다. 인터프리터의 새 프로그램 구조를 선언 하면 때마다 해당 형식에 대 한 구문 및 구문의 이름을 출력 합니다. 이 구문은 기본 제공 식별자에 대 한 이러한 또는 사용자 정의 형식에 대 한 식별자로만 될 수 있습니다 `int` 또는 `string`만 더 복잡 한 형식에 대 한 구문은 더 복잡 한 합니다.

다음 표에서 F # 형식에 대 한 구문 측면을 보여 줍니다.



|형식|형식 구문|예제|
|----|-----------|--------|
|기본 형식|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|집계 유형 (클래스, 구조체, 공용 구조체, 레코드, 열거형, 및 등)|*type-name*|`System.DateTime`<br /><br />`Color`|
|형식 약어|*형식 약어 이름*|`bigint`|
|정규화 된 형식|*namespaces.type 이름*<br /><br />또는<br /><br />*modules.type 이름*<br /><br />또는<br /><br />*namespaces.modules.type 이름*|`System.IO.StreamWriter`|
|array|*형식 이름*또는<br /><br />*형식 이름* 배열|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|2 차원 배열|*형식 이름*[,]|`int[,]`<br /><br />`float[,]`|
|3 차원 배열|*형식 이름*[,]|`float[,,]`|
|tuple|*형식 name1* &#42; *형식 name2* ...|예를 들어 `(1,'b',3)` 형식이 `int * char * int`|
|제네릭 형식(generic type)|*형식 매개 변수* *제네릭 형식 이름*<br /><br />또는<br /><br />*제네릭 형식 이름을*&lt;*형식 매개 변수 목록*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|생성 된 형식 (제공 되는 특정 형식 인수가 있는 제네릭 형식)|*형식 인수* *제네릭 형식 이름*<br /><br />또는<br /><br />*제네릭 형식 이름을*&lt;*유형 인수 목록*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|단일 매개 변수가 있는 함수 형식|*매개 변수-type1*  - &gt; *반환 형식*|사용 하는 함수는 `int` 반환는 `string` 형식이 `int -> string`|
|여러 매개 변수가 있는 함수 형식|*매개 변수-type1*  - &gt; *매개 변수 type2*  - &gt; ...-&gt; *반환 형식*|사용 하는 함수는 `int` 및 `float` 반환는 `string` 형식이 `int -> float -> string`|
|매개 변수로 고차 함수|(*함수 형식*)|`List.map` 형식이 `('a -> 'b) -> 'a list -> 'b list`|
|대리자(delegate)|위임 *함수 형식*|`delegate of unit -> int`|
|유연한 형식|#*형식 이름*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>관련 항목


|항목|설명|
|-----|-----------|
|[기본 형식](primitive-types.md)|정수 계열 형식, 부울 형식 및 문자 형식 같은 기본 제공 단순 형식을 설명합니다.|
|[단위 형식](unit-type.md)|설명의 `unit` 형식, 값이 한 하 여 () 표시 되는 형식;에 해당 `void` C# 및 `Nothing` Visual Basic의 합니다.|
|[튜플](tuples.md)|튜플 형식을 쌍, 삼중 쌍, 상관 등에에서 그룹화 된 모든 형식의 연결 된 값으로 구성 된 형식에 설명 합니다.|
|[옵션](options.md)|값 중 하나 이거나 비워 둘 수 있는 형식 옵션 종류를 설명 합니다.|
|[목록](lists.md)|목록을 정렬 되 고 변경할 수 없는 일련의 요소는 설명 동일한 형식의 모든 합니다.|
|[배열](arrays.md)|인접 한 메모리 블록을 차지 하는 고정된 크기는 동일한 형식의 변경 가능한 요소를 정렬 된 배열에 설명 합니다.|
|[시퀀스](sequences.md)|논리 일련의 값을 나타내는 시퀀스 유형을 설명합니다 개별 값이 필요한 경우에 계산 됩니다.|
|[레코드](records.md)|명명 된 값의 작은 집계 레코드 종류를 설명합니다.|
|[구별된 공용 구조체](discriminated-unions.md)|구별 된 공용 구조체 형식의 값을 가진 가능한 형식 집합 중 하나를 사용할 수는 형식에 설명 합니다.|
|[함수](functions/index.md)|함수 값에 설명 합니다.|
|[클래스](classes.md)|.NET 참조 형식에 해당 하는 개체 형식을 클래스 형식에 설명 합니다. 클래스 형식 멤버, 속성, 구현 된 인터페이스 및 기본 형식을 포함할 수 있습니다.|
|[구조체](structures.md)|설명의 `struct` 유형,.NET 값 형식에 해당 하는 개체 유형입니다. `struct` 형식은 일반적으로 데이터의 작은 집계를 나타냅니다.|
|[인터페이스](interfaces.md)|인터페이스 종류는 특정 기능을 제공 하지만 데이터가 포함 되지 않은 멤버의 집합을 나타내는 형식에 설명 합니다. 인터페이스 형식은 유용 하 게 되려면 개체 유형별로 구현 되어야 합니다.|
|[대리자](delegates.md)|함수 개체를 나타내는 대리자 형식을 설명 합니다.|
|[열거형](enumerations.md)|명명 된 값의 집합에 속하는 값을 해당 하는 열거형 형식에 설명 합니다.|
|[특성](attributes.md)|다른 형식에 대 한 메타 데이터를 지정 하는 데 사용 되는 특성을 설명 합니다.|
|[예외 형식](exception-handling/exception-types.md)|오류 정보를 지정 하는 예외를 설명 합니다.|
