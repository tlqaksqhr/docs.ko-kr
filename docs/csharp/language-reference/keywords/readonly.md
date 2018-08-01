---
title: readonly 키워드(C# 참조)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 96607f1dd7f019169446e29a08496fb54e1ed493
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961185"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="4adce-102">readonly(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4adce-102">readonly (C# Reference)</span></span>

<span data-ttu-id="4adce-103">`readonly` 키워드는 세 가지 컨텍스트에서 사용할 수 있는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="4adce-104">[필드 선언](#readonly-field-example)에서 필드에 대한 할당을 나타내는 `readonly`는 선언의 일부로 또는 동일한 클래스의 생성자에서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span>
- <span data-ttu-id="4adce-105">[`readonly struct` 정의](#readonly-struct-example)에서 `readonly`는 `struct`가 불변임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-105">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="4adce-106">[`ref readonly` 메서드 반환](#ref-readonly-return-example)에서 `readonly` 한정자는 해당 메서드가 참조를 반환하고 해당 참조에 쓰기를 허용하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-106">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="4adce-107">마지막 두 컨텍스트가 C# 7.2에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-107">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="4adce-108">읽기 전용 필드 예제</span><span class="sxs-lookup"><span data-stu-id="4adce-108">Readonly field example</span></span>  

<span data-ttu-id="4adce-109">이 예제에서는 클래스 생성자에서 값이 할당되지만, `year` 필드의 값을 `ChangeYear` 메서드에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-109">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]  
  
<span data-ttu-id="4adce-110">다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-110">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
- <span data-ttu-id="4adce-111">변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-111">When the variable is initialized in the declaration, for example:</span></span>  

```csharp
public readonly int y = 5;  
```

- <span data-ttu-id="4adce-112">인스턴스 필드 선언을 포함하는 클래스의 인스턴스 생성자.</span><span class="sxs-lookup"><span data-stu-id="4adce-112">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="4adce-113">정적 필드 선언을 포함하는 클래스의 정적 생성자.</span><span class="sxs-lookup"><span data-stu-id="4adce-113">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="4adce-114">이러한 생성자 컨텍스트는 또한 `readonly` 필드를 [out](out-parameter-modifier.md) 또는 [ref](ref.md) 매개 변수로 전달하는 것이 유효한 유일한 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-114">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4adce-115">`readonly` 키워드와 [const](const.md) 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-115">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="4adce-116">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-116">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="4adce-117">`readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-117">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="4adce-118">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-118">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="4adce-119">또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-119">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]  
  
<span data-ttu-id="4adce-120">위 예제에서 다음 예제와 같은 명령문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="4adce-120">In the preceding example, if you use a statement like the following example:</span></span>  
  
`p2.y = 66;        // Error`  
  
<span data-ttu-id="4adce-121">컴파일러 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-121">you will get the compiler error message:</span></span>  
  
`The left-hand side of an assignment must be an l-value`  
  
<span data-ttu-id="4adce-122">상수에 값을 할당하려고 할 때 표시되는 것과 같은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-122">which is the same error you get when you attempt to assign a value to a constant.</span></span>  

## <a name="readonly-struct-example"></a><span data-ttu-id="4adce-123">읽기 전용 구조체 예제</span><span class="sxs-lookup"><span data-stu-id="4adce-123">Readonly struct example</span></span>

<span data-ttu-id="4adce-124">`struct` 정의의 `readonly` 한정자는 구조체가 **불변**임을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-124">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="4adce-125">다음 예제와 같이 `struct`의 모든 인스턴스 필드를 `readonly`로 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-125">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]  

<span data-ttu-id="4adce-126">앞의 예제는 [읽기 전용 자동 속성](../../properties.md#read-only)을 사용하여 저장소를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-126">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="4adce-127">이는 컴파일러가 해당 속성의 `readonly` 백킹 필드를 만들도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-127">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="4adce-128">`readonly` 필드를 직접 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-128">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="4adce-129">`readonly`로 표시되지 않은 필드를 추가하면 컴파일러 오류 `CS8340`: "읽기 전용 구조체의 인스턴스 필드는 읽기 전용이어야 합니다."가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-129">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="4adce-130">참조 읽기 전용 반환 예</span><span class="sxs-lookup"><span data-stu-id="4adce-130">Ref readonly return example</span></span>

<span data-ttu-id="4adce-131">`ref return`의 `readonly` 한정자는 반환된 참조를 수정할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-131">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="4adce-132">다음 예제는 원점에 대한 참조를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-132">The following example returns a reference to the origin.</span></span> <span data-ttu-id="4adce-133">호출자가 원본을 수정할 수 없음을 나타내기 위해 `readonly` 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-133">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]  
<span data-ttu-id="4adce-134">반환된 유형은 `readonly struct`일 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-134">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="4adce-135">`ref`에 의해 반환될 수 있는 모든 유형은 `ref readonly`에 의해 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4adce-135">Any type that can be returned by `ref` can be returned by `ref readonly`</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4adce-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4adce-136">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4adce-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4adce-137">See Also</span></span>  
[<span data-ttu-id="4adce-138">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4adce-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="4adce-139">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4adce-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="4adce-140">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="4adce-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="4adce-141">한정자</span><span class="sxs-lookup"><span data-stu-id="4adce-141">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
[<span data-ttu-id="4adce-142">const</span><span class="sxs-lookup"><span data-stu-id="4adce-142">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
[<span data-ttu-id="4adce-143">필드</span><span class="sxs-lookup"><span data-stu-id="4adce-143">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
