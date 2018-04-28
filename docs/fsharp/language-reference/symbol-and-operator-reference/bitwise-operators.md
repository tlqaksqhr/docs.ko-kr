---
title: 비트 연산자(F#)
description: 'F # 프로그래밍 언어에서 사용할 수 있는 비트 연산자에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4d5abff564a5d1dcbe52b99edf431ca10e442061
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="bitwise-operators"></a><span data-ttu-id="4939e-103">비트 연산자</span><span class="sxs-lookup"><span data-stu-id="4939e-103">Bitwise Operators</span></span>

<span data-ttu-id="4939e-104">이 항목에서는 F # 언어에서 사용할 수 있는 비트 연산자를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="4939e-105">비트 연산자 요약</span><span class="sxs-lookup"><span data-stu-id="4939e-105">Summary of Bitwise Operators</span></span>
<span data-ttu-id="4939e-106">다음 표에서 F # 언어에서 정수 계열 형식과 unboxed에 지원 되는 비트 연산자를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="4939e-107">연산자</span><span class="sxs-lookup"><span data-stu-id="4939e-107">Operator</span></span>|<span data-ttu-id="4939e-108">노트</span><span class="sxs-lookup"><span data-stu-id="4939e-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="4939e-109">비트 AND 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-109">Bitwise AND operator.</span></span> <span data-ttu-id="4939e-110">결과 비트의에서 경우에 두 소스 피연산자의 해당 비트는 1이 고 값 1을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="4939e-111">비트 OR 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-111">Bitwise OR operator.</span></span> <span data-ttu-id="4939e-112">결과 비트는 값 1 경우 원본에 해당 비트의 두 피연산자가 1입니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="4939e-113">비트 배타적 OR 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="4939e-114">결과의 비트 소스 피연산자의 비트 같지 않은 값이 있는 경우에 값 1을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="4939e-115">비트 부정 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-115">Bitwise negation operator.</span></span> <span data-ttu-id="4939e-116">단항 연산자 이므로 결과 생성 중인 소스 피연산자의 모든 0 비트는 1 비트 변환할 모든 1 비트를 0 비트로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="4939e-117">비트 왼쪽 시프트 연산자.</span><span class="sxs-lookup"><span data-stu-id="4939e-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="4939e-118">결과 비트를 첫 번째 피연산자는 두 번째 피연산자의 비트 수 만큼 왼쪽 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="4939e-119">가장 중요 한 위치에서 벗어나 이동한 비트 위치로 돌아가지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="4939e-120">가장 덜 중요 한 비트는 0으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="4939e-121">두 번째 인수 형식이 `int32`합니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="4939e-122">비트 오른쪽 시프트 연산자.</span><span class="sxs-lookup"><span data-stu-id="4939e-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="4939e-123">결과 두 번째 피연산자의 비트 수 만큼 오른쪽으로 이동 하는 비트를 첫 번째 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="4939e-124">가장 덜 중요 한 위치에서 벗어나 이동한 비트 위치 돌아가지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="4939e-125">부호 없는 형식에 대 한 최상위 비트는 0으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="4939e-126">부호 있는 형식에 대 한 최상위 비트는 1로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-126">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="4939e-127">두 번째 인수 형식이 `int32`합니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="4939e-128">비트 연산자와 함께 사용할 수는 다음과 같은: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, 및 `unativeint`합니다.</span><span class="sxs-lookup"><span data-stu-id="4939e-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4939e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4939e-129">See Also</span></span>
[<span data-ttu-id="4939e-130">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="4939e-130">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="4939e-131">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="4939e-131">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="4939e-132">부울 연산자</span><span class="sxs-lookup"><span data-stu-id="4939e-132">Boolean Operators</span></span>](boolean-operators.md)

