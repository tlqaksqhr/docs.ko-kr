---
title: 제약 조건(F#)
description: '제네릭 형식 또는 함수 형식 인수에 대 한 요구 사항을 지정 하려면 제네릭 형식 매개 변수에 적용 되는 F # 제약 조건에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 7af064159d2722256f0db8286a99fc02435a99cd
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936867"
---
# <a name="constraints"></a>제약 조건

제네릭에 적용할 수 있는 제약 조건을 설명 하는이 항목에서는 제네릭 형식 또는 함수 형식 인수에 대 한 요구 사항을 지정 하는 매개 변수를 입력 합니다.


## <a name="syntax"></a>구문

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>설명
제네릭 형식에 사용할 수 있는 형식을 제한 하는 데 적용할 수 있습니다 하는 여러 다른 제약 조건이 있습니다. 다음 표에서 나열 하 고 이러한 제약 조건을 설명 합니다.

|제약 조건|구문|설명|
|----------|------|-----------|
|형식 제약 조건|*형식 매개 변수* :&gt; *형식*|제공된 된 형식 같거나 파생, 지정 된 형식에서 이거나, 형식이 인터페이스 이면 제공 된 형식이 인터페이스를 구현 해야 합니다.|
|Null 제약 조건|*형식 매개 변수* : null|제공된 된 형식에는 null 리터럴을 지원 해야 합니다. 모든.NET 개체 형식 이지만 하지 F # 목록, 튜플, 함수, 클래스, 레코드 또는 공용 구조체 형식을 포함 됩니다.|
|명시적 멤버 제약 조건|[()]*형식 매개 변수* [또는... 또는 *형식 매개 변수*)]: (*멤버 시그니처에*)|하나 이상의 제공 된 형식 인수를 지정 된 서명을; 멤버가 있어야 합니다. 일반적인 용도로 적합 하지 합니다. 멤버가 하거나 명시적으로 정의 되어야 형식 또는 암시적 형식 확장의 일부를 명시적 멤버 제약 조건에 대 한 유효한 대상이 되도록 합니다.|
|생성자 제약 조건|*형식 매개 변수* : (새: unit-&gt; '는)|제공된 된 형식 기본 생성자가 있어야 합니다.|
|값 형식 제약 조건|: 구조체|제공된 된 형식에는.NET 값 형식 이어야 합니다.|
|참조 형식 제약 조건|: 하지 구조체|제공된 된 형식에는.NET 참조 형식 이어야 합니다.|
|열거형 형식 제약 조건|: 열거형&lt;*기본 형식*&gt;|제공된 된 형식에 지정된 된 기본 형식을 하는 열거 형식 이어야 합니다. 일반적인 용도로 적합 하지 합니다.|
|대리자 제약 조건|: 위임&lt;*튜플 매개 변수 형식*, *반환 형식*&gt;|제공된 된 형식 인수가 지정 하는 대리자 형식 이어야 하며 값을 반환 합니다. 일반적인 용도로 적합 하지 합니다.|
|비교 제약 조건|: 비교|제공된 된 형식 비교를 지원 해야 합니다.|
|동등 제약 조건|: 같음|제공된 된 형식 동등을 지원 해야 합니다.|
|관리 되지 않는 제약 조건|: 관리 되지 않는|제공된 된 형식에는 관리 되지 않는 형식 이어야 합니다. 관리 되지 않는 형식은 특정 기본 형식 (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`를 `float32`, `float`를 `int16`, `uint16`, `int32`를 `uint32`, `int64`, `uint64`, 또는 `decimal`), 열거형 형식 `nativeptr&lt;_&gt;`, 또는 해당 필드는 모두 관리 되지 않는 형식 제네릭이 아닌 구조체입니다.|
코드에 일반적 제약 조건 형식이 있지만 아닌 형식에서 사용할 수 있는 기능을 사용 하는 경우 제약 조건을 추가 해야 합니다. 예를 들어, 형식 제약 조건을 사용 하 여 클래스 형식을 지정 하는 경우에 제네릭 함수 또는 형식에 해당 클래스의 메서드 중 하나를 사용할 수 있습니다.

제약 조건을 지정 하는 경우에 필요 형식 매개 변수를 명시적으로 작성, 제약 조건 없이 컴파일러는 기능을 사용 하는 형식에 대해 런타임 시 제공 될 수도 있습니다는 모든 형식에 사용할 수 있도록 확인할 방법이 없어 때문에 매개 변수입니다.

F # 코드에서 사용할 가장 일반적인 제약 조건은 기본 클래스 또는 인터페이스를 지정 하는 형식 제약 조건이 있습니다. 다른 제약 조건과 산술 연산자의 오버 로드 된 연산자를 구현 하는 데 사용 됩니다 또는 F # 지원 전체 기능이 있기 때문에 제공 되는 명시적 구성원 제약 조건 등의 특정 기능을 구현 하기 F # 라이브러리에서 사용 하거나는 공용 언어 런타임에서 지원 되는 제약 조건의 집합입니다.

형식 유추 과정에서 몇 가지 제약 조건이 컴파일러에서 자동으로 유추 됩니다. 예를 들어, 사용 하는 경우는 `+` 함수에 연산자를 컴파일러는 명시적 구성원 제약 조건 식에 사용 되는 변수 형식에서 유추 합니다.

다음 코드에서는 몇 가지 제약 조건을 선언 합니다.

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a>참고 항목
[제네릭](index.md)

[제약 조건](constraints.md)
