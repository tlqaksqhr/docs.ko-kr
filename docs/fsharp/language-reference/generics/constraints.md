---
title: 제약 조건(F#)
description: '제네릭 형식 또는 함수에서 형식 인수에 대 한 요구 사항을 지정 하려면 제네릭 형식 매개 변수에 적용 되는 F # 제약 조건에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: f0722cafe27a4e2c38dfbf091973edb136cf5228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="constraints"></a>제약 조건

제네릭에 적용할 수 있는 제약 조건을 설명 하는이 항목 형식 매개 변수는 제네릭 형식 또는 함수에서 형식 인수에 대 한 요구 사항을 지정 합니다.


## <a name="syntax"></a>구문

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>설명
제네릭 형식에 사용할 수 있는 형식을 제한 적용할 수 있는 여러 다른 제약 조건이 있습니다. 다음 표에서 나열 하 고 이러한 제약 조건을 설명 합니다.

|제약 조건|구문|설명|
|----------|------|-----------|
|형식 제약 조건|*형식 매개 변수* :&gt; *유형*|제공 된 형식 또는 그 파생, 지정 된 형식에서 이거나, 형식이 인터페이스 이면 제공 된 형식이 인터페이스를 구현 해야 합니다.|
|Null 제약 조건|*형식 매개 변수* : null|제공 된 형식에는 null 리터럴을 지원 해야 합니다. 여기에 모든.NET 개체 유형 하지만 하지 F # 목록, 튜플, 함수, 클래스, 레코드 또는 공용 구조체 형식이 포함 됩니다.|
|명시적 멤버 제약 조건|[()]*형식 매개 변수* [또는... 또는 *형식 매개 변수*)]: (* 멤버 시그너처 *)|지정한 서명을 가진 멤버를 제공 된 형식 인수 중 하나 이상 있어야 일반적인 용도 대 한 없습니다. 멤버 정의 되어야 합니다 하거나 명시적으로 명시적 멤버 제약 조건을 대 한 유효한 대상이 될 형식이 나 암시적 형식 확장의 일부가에.|
|생성자 제약 조건|*형식 매개 변수* : (new: 장치-&gt; '는)|제공 된 형식이 기본 생성자를 있어야 합니다.|
|값 형식 제약 조건|: 구조체|제공 된 형식에는.NET 값 형식 이어야 합니다.|
|참조 형식 제약 조건|: 하지 구조체|제공 된 형식에는.NET 참조 형식 이어야 합니다.|
|열거형 형식 제약 조건|: 열거형&lt;*기본 형식*&gt;|제공 된 형식이 지정 된 기본 형식이; 지정 된 열거 형식 이어야 합니다. 일반적인 용도 대 한 없습니다.|
|대리자 제약 조건|: 위임&lt;*튜플 매개 변수 형식*, *반환 형식*&gt;|제공 된 형식이 지정 된 인수를 포함 하는 대리자 형식 이어야 하며 반환 값입니다. 일반적인 용도 대 한 없습니다.|
|제약 조건 비교|: 비교|제공 된 형식 비교를 지원 해야 합니다.|
|동등 제약 조건|: 같음|제공 된 형식 일치를 지원 해야 합니다.|
|관리 되지 않는 제약 조건|: 관리 되지 않는|제공 된 형식에는 관리 되지 않는 형식 이어야 합니다. 관리 되지 않는 유형은 특정 기본 형식 (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, 또는 `decimal`), 열거형 형식 `nativeptr&lt;_&gt;`, 또는 제네릭이 아닌 구조 해당 필드는 모두 관리 되지 않는 형식입니다.|
코드에서 일반적 형식 제외 제약 조건 형식 에서만 사용할 수 있는 기능을 사용 하 여 때 제약 조건을 추가 해야 합니다. 예를 들어 형식 제약 조건을 사용 하 여 클래스 유형을 지정 하는 제네릭 함수 또는 형식에 해당 클래스의 메서드 중 하나를 사용할 수 있습니다.

제약 조건을 지정 하는 경우에 필요 형식 매개 변수를 명시적으로 작성 한 제약 조건 없이 컴파일러에는 기능을 사용 하는 형식에 대해 런타임 시 제공 될 수도 있습니다는 모든 형식에 사용할 수 있는지 확인할 방법이 없어 있기 때문에 매개 변수입니다.

F # 코드에서 사용 하는 가장 일반적인 제약 조건에는 기본 클래스 또는 인터페이스를 지정 하는 형식 제약 조건입니다. 다른 제약 조건과 산술 연산자에 대 한 오버 로드 된 연산자를 구현 하는 데 사용 하거나 F #에서는 전체 기능이 있기 때문에 제공 되는 명시적 멤버 제약 조건 등의 특정 기능을 구현할 위해 F # 라이브러리에서 사용 하거나 공용 언어 런타임에서 지원 되는 제약 조건의 집합.

형식 유추 과정에서 몇 가지 제약 조건이 컴파일러에 의해 자동으로 유추 됩니다. 예를 들어, 사용 하는 경우는 `+` 함수에 연산자를 컴파일러가 식에 사용 되는 변수 유형에 대 한 명시적 멤버 제약 조건을 유추 합니다.

다음 코드에서는 몇 가지 제약 조건 선언을 보여 줍니다.

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
