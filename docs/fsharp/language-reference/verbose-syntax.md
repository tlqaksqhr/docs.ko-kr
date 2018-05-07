---
title: 자세한 구문(F#)
description: 'F # 프로그래밍 언어에서 자세한 정보 및 간단한 구문 차이점에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: b0bed66b4a76c5ab11e6c9e7aaf695f864e74ca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="verbose-syntax"></a>자세한 구문

F # 언어의 많은 구문에 사용할 수 있는 두 가지 형태의 구문: *자세한 구문* 및 *간단한 구문을*합니다. 자세한 구문 일반적으로 사용 되지는 했으나 들여쓰기에 크게 영향 하다는 이점이 있습니다. 와 같은 추가 키워드 보다는 간단한 구문은 짧은 들여쓰기를 사용 하 여 신호를 보내 시작과 끝의 구문, `begin`, `end`, `in`등입니다. 기본 구문은 간단한 구문을입니다. 이 항목에서는 간단한 구문을 사용 하지 않는 경우 F # 구문에 대 한 구문을 설명 합니다. 자세한 구문 항상 사용 되므로 일부 구문에 대 한 자세한 구문을 여전히 사용할 수 간단한 구문을 사용 하는 경우에 됩니다. 사용 하 여 간단한 구문을 사용 하지 않도록 설정할 수는 `#light "off"` 지시문입니다.


## <a name="table-of-constructs"></a>구문 표
다음 표에서 상황에서 F # 언어 구문에 대 한 간단 하 고 자세한 구문을 보여 줍니다. 두 형식의 차이. 이 테이블에서 꺾쇠 괄호 (&lt;&gt;) 사용자가 제공한 구문 요소를 묶습니다. 이러한 구문 내에서 사용 되는 구문에 대 한 자세한 내용을 보려면 각 언어 구문에 대 한 설명서를 참조 하십시오.



<table>
<tr>
<th>언어 구문</th>
<th>간단한 구문</th>
<th>자세한 구문</th>
</tr>
<tr>
<td>
복합 식
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


중첩 된 `let` 바인딩

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
코드 블록
</td><td>

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
begin
    <expression1>;
    <expression2>;
end
```
</td>
</tr>
<tr><td>
`for...do`
</td><td>

```
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td>레코드
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>클래스
</td><td>
```
type <class-name>(<params>) = ... ```

</td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td>구조체(structure)</td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>구분된 된 공용 구조체</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end    
```

</td>
</tr>
<tr><td>interface(인터페이스)</td><td>

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>개체 식</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td>인터페이스 구현</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>형식 확장</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>name</td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>



## <a name="see-also"></a>참고 항목
[F# 언어 참조](index.md)

[컴파일러 지시문](compiler-directives.md)

[코드 서식 지정 지침](code-formatting-guidelines.md)
