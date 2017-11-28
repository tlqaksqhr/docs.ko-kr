---
title: "열거형(F#)"
description: "F # 열거형 리터럴 대신 코드를 더 읽기 쉽고 쉽게 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9272bf5a-9a9f-4314-9e34-a3248e5244f5
ms.openlocfilehash: de0273900b707c99e6fb1bcc84e5c2b9ef2bc725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="enumerations"></a><span data-ttu-id="bd84c-104">열거형</span><span class="sxs-lookup"><span data-stu-id="bd84c-104">Enumerations</span></span>

<span data-ttu-id="bd84c-105">*열거형*라고도 *열거형*, 레이블 값의 하위 집합에 할당 되는 위치는 정수 계열 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-105">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="bd84c-106">코드를 더 읽기 쉽고 유지 가능하도록 만들기 위해 리터럴 대신 이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-106">You can use them in place of literals to make code more readable and maintainable.</span></span>


## <a name="syntax"></a><span data-ttu-id="bd84c-107">구문</span><span class="sxs-lookup"><span data-stu-id="bd84c-107">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="bd84c-108">설명</span><span class="sxs-lookup"><span data-stu-id="bd84c-108">Remarks</span></span>
<span data-ttu-id="bd84c-109">열거형은 매우 간단한 값을 가진 구별된 된 공용 구조체 유사 제외 하 고 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-109">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="bd84c-110">값은 일반적으로 0 또는 1부터 시작 하는 정수 또는 비트 위치를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-110">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="bd84c-111">열거형 비트 위치를 나타내는 하려는 경우 또한을 사용 해야는 [플래그](xref:System.FlagsAttribute) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-111">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="bd84c-112">열거형의 내부 형식은 사용 되는 리터럴을에서 결정, 예를 들어 있습니다 사용할 수 있도록 리터럴 접미사가 있는 같은 `1u`, `2u`, 등의 부호 없는 정수에 대 한 (`uint32`) 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-112">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="bd84c-113">명명된 된 값을 참조할 때 사용 해야 열거형 형식 자체의 이름 한정자로 즉, `enum-name.value1`뿐 아니라, `value1`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-113">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="bd84c-114">이 동작은 구별 된 공용 구조체의에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-114">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="bd84c-115">열거형이 항상 있기 때문입니다는 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-115">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="bd84c-116">다음 코드에서는 선언 및 열거형의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-116">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="bd84c-117">다음 코드에 나와 있는 것 처럼 적절 한 연산자를 사용 하 여 기본 형식에 열거형 변환할 쉽게.</span><span class="sxs-lookup"><span data-stu-id="bd84c-117">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="bd84c-118">열거 형식은 다음 기본 유형 중 하나일 수 있습니다: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, 및 `char`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-118">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="bd84c-119">열거형 형식에서 상속 된 형식으로.NET Framework에서 표현 됩니다 `System.Enum`를 차례로에서 상속 됨 `System.ValueType`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-119">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="bd84c-120">따라서 스택 또는 인라인으로 포함 하는 개체에 있는 값 형식 및 기본 형식의 모든 값이 열거형의 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-120">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="bd84c-121">이 기능은 중요 열거형에 패턴 일치, 값이 될 때 명명 되지 않은 값을 catch 하는 패턴을 제공 해야 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-121">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="bd84c-122">`enum` F # 라이브러리의 함수가 데 사용할 수는 미리 정의 된 다른 값도 하는 열거형 값을 생성할 명명 된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-122">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="bd84c-123">사용 된 `enum` 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-123">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="bd84c-124">기본 `enum` 함수는 형식 `int32`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-124">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="bd84c-125">따라서 다른 기본 형식을 포함 하는 열거형 형식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-125">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="bd84c-126">대신, 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd84c-126">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]
    
## <a name="see-also"></a><span data-ttu-id="bd84c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd84c-127">See Also</span></span>
[<span data-ttu-id="bd84c-128">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="bd84c-128">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="bd84c-129">캐스팅 및 변환</span><span class="sxs-lookup"><span data-stu-id="bd84c-129">Casting and Conversions</span></span>](casting-and-conversions.md)
