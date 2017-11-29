---
title: "자세한 구문(F#)"
description: "F # 프로그래밍 언어에서 자세한 정보 및 간단한 구문 차이점에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0a6792b3-b312-4453-a025-21d9760eee5d
ms.openlocfilehash: 2cef359a879897825733a3186be97b38896f5953
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="verbose-syntax"></a><span data-ttu-id="f821f-104">자세한 구문</span><span class="sxs-lookup"><span data-stu-id="f821f-104">Verbose Syntax</span></span>

<span data-ttu-id="f821f-105">F # 언어의 많은 구문에 사용할 수 있는 두 가지 형태의 구문: *자세한 구문* 및 *간단한 구문을*합니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-105">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="f821f-106">자세한 구문 일반적으로 사용 되지는 했으나 들여쓰기에 크게 영향 하다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-106">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="f821f-107">와 같은 추가 키워드 보다는 간단한 구문은 짧은 들여쓰기를 사용 하 여 신호를 보내 시작과 끝의 구문, `begin`, `end`, `in`등입니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-107">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="f821f-108">기본 구문은 간단한 구문을입니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-108">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="f821f-109">이 항목에서는 간단한 구문을 사용 하지 않는 경우 F # 구문에 대 한 구문을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-109">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="f821f-110">자세한 구문 항상 사용 되므로 일부 구문에 대 한 자세한 구문을 여전히 사용할 수 간단한 구문을 사용 하는 경우에 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-110">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="f821f-111">사용 하 여 간단한 구문을 사용 하지 않도록 설정할 수는 `#light "off"` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-111">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="f821f-112">구문 표</span><span class="sxs-lookup"><span data-stu-id="f821f-112">Table of Constructs</span></span>
<span data-ttu-id="f821f-113">다음 표에서 상황에서 F # 언어 구문에 대 한 간단 하 고 자세한 구문을 보여 줍니다. 두 형식의 차이.</span><span class="sxs-lookup"><span data-stu-id="f821f-113">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="f821f-114">이 테이블에서 꺾쇠 괄호 (&lt;&gt;) 사용자가 제공한 구문 요소를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f821f-114">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="f821f-115">이러한 구문 내에서 사용 되는 구문에 대 한 자세한 내용을 보려면 각 언어 구문에 대 한 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f821f-115">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="f821f-116">언어 구문</span><span class="sxs-lookup"><span data-stu-id="f821f-116">Language construct</span></span></th>
<th><span data-ttu-id="f821f-117">간단한 구문</span><span class="sxs-lookup"><span data-stu-id="f821f-117">Lightweight syntax</span></span></th>
<th><span data-ttu-id="f821f-118">자세한 구문</span><span class="sxs-lookup"><span data-stu-id="f821f-118">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="f821f-119">복합 식</span><span class="sxs-lookup"><span data-stu-id="f821f-119">compound expressions</span></span>
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


<span data-ttu-id="f821f-120">중첩 된 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="f821f-120">nested `let` bindings</span></span>

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
<span data-ttu-id="f821f-121">코드 블록</span><span class="sxs-lookup"><span data-stu-id="f821f-121">code block</span></span>
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
<tr><td><span data-ttu-id="f821f-122">레코드</span><span class="sxs-lookup"><span data-stu-id="f821f-122">record</span></span>
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
<tr><td><span data-ttu-id="f821f-123">클래스</span><span class="sxs-lookup"><span data-stu-id="f821f-123">class</span></span>
</td><td><span data-ttu-id="f821f-124">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="f821f-124">
```
type <class-name>(<params>) = ... ```

</span></span></td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td><span data-ttu-id="f821f-125">구조체(structure)</span><span class="sxs-lookup"><span data-stu-id="f821f-125">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="f821f-126">구분된 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="f821f-126">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="f821f-127">interface(인터페이스)</span><span class="sxs-lookup"><span data-stu-id="f821f-127">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="f821f-128">개체 식</span><span class="sxs-lookup"><span data-stu-id="f821f-128">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="f821f-129">인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="f821f-129">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="f821f-130">형식 확장</span><span class="sxs-lookup"><span data-stu-id="f821f-130">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="f821f-131">name</span><span class="sxs-lookup"><span data-stu-id="f821f-131">module</span></span></td><td>

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



## <a name="see-also"></a><span data-ttu-id="f821f-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f821f-132">See Also</span></span>
[<span data-ttu-id="f821f-133">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="f821f-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="f821f-134">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="f821f-134">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="f821f-135">코드 서식 지정 지침</span><span class="sxs-lookup"><span data-stu-id="f821f-135">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
