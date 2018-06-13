---
title: 기본 형식(F#)
description: 'F # 언어에 사용 되는 기본 기본 형식을 검색 합니다.'
ms.date: 05/16/2016
ms.openlocfilehash: efe419e5ebf2e49be9433bbd3025ff290d648296
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564471"
---
# <a name="primitive-types"></a><span data-ttu-id="c4ce4-103">기본 형식</span><span class="sxs-lookup"><span data-stu-id="c4ce4-103">Primitive Types</span></span>

<span data-ttu-id="c4ce4-104">이 항목에서는 F # 언어에 사용 되는 기본 기본 형식을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-104">This topic lists the fundamental primitive types that are used in the F# language.</span></span> <span data-ttu-id="c4ce4-105">또한 각 유형의 해당 .NET 형식과 최소 및 최대값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-105">It also provides the corresponding .NET types and the minimum and maximum values for each type.</span></span>

## <a name="summary-of-primitive-types"></a><span data-ttu-id="c4ce4-106">기본 형식 요약</span><span class="sxs-lookup"><span data-stu-id="c4ce4-106">Summary of Primitive Types</span></span>
<span data-ttu-id="c4ce4-107">다음 표에서 기본 F # 형식의 속성이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-107">The following table summarizes the properties of the primitive F# types.</span></span>

|<span data-ttu-id="c4ce4-108">형식</span><span class="sxs-lookup"><span data-stu-id="c4ce4-108">Type</span></span>|<span data-ttu-id="c4ce4-109">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="c4ce4-109">.NET type</span></span>|<span data-ttu-id="c4ce4-110">설명</span><span class="sxs-lookup"><span data-stu-id="c4ce4-110">Description</span></span>|
|----|---------|-----------|
|`bool`|`System.Boolean`|<span data-ttu-id="c4ce4-111">가능한 값은 `true`와 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-111">Possible values are `true` and `false`.</span></span>|
|`byte`|`System.Byte`|<span data-ttu-id="c4ce4-112">0에서 255 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-112">Values from 0 to 255.</span></span>|
|`sbyte`|`System.SByte`|<span data-ttu-id="c4ce4-113">-128에서 127 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-113">Values from -128 to 127.</span></span>|
|`int16`|`System.Int16`|<span data-ttu-id="c4ce4-114">-32768에서 32767 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-114">Values from -32768 to 32767.</span></span>|
|`uint16`|`System.UInt16`|<span data-ttu-id="c4ce4-115">0에서 65535 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-115">Values from 0 to 65535.</span></span>|
|`int`|`System.Int32`|<span data-ttu-id="c4ce4-116">-2147483648에서 2147483647 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|`System.UInt32`|<span data-ttu-id="c4ce4-117">0에서 4,294,967,295 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-117">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|`System.Int64`|<span data-ttu-id="c4ce4-118">-9223372036854775808에서 9223372036854775807 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|`System.UInt64`|<span data-ttu-id="c4ce4-119">0에서 18446744073709551615 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|`System.IntPtr`|<span data-ttu-id="c4ce4-120">부호 있는 정수로 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-120">A native pointer as a signed integer.</span></span>|
|`unativeint`|`System.UIntPtr`|<span data-ttu-id="c4ce4-121">부호 없는 정수는 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-121">A native pointer as an unsigned integer.</span></span>|
|`char`|`System.Char`|<span data-ttu-id="c4ce4-122">유니코드 문자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-122">Unicode character values.</span></span>|
|`string`|`System.String`|<span data-ttu-id="c4ce4-123">유니코드 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-123">Unicode text.</span></span>|
|`decimal`|`System.Decimal`|<span data-ttu-id="c4ce4-124">부동 소수점 적어도 28 개의 유효 자릿수를 가진 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-124">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="c4ce4-125">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c4ce4-125">not applicable</span></span>|<span data-ttu-id="c4ce4-126">실제 값이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-126">Indicates the absence of an actual value.</span></span> <span data-ttu-id="c4ce4-127">형식에는 하나의 정식 값 `()`합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-127">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="c4ce4-128">단위 값 `()`, 여기서는 값이 필요 하지만 실제 값이 없거나 의미 자리 표시자로 흔히 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-128">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|`System.Void`|<span data-ttu-id="c4ce4-129">없는 형식 또는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-129">Indicates no type or value.</span></span>|
|`float32, single`|`System.Single`|<span data-ttu-id="c4ce4-130">32 비트 부동 소수점 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-130">A 32-bit floating point type.</span></span>|
|`float, double`|`System.Double`|<span data-ttu-id="c4ce4-131">64 비트 부동 소수점 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-131">A 64-bit floating point type.</span></span>|

>[!NOTE]
<span data-ttu-id="c4ce4-132">64 비트 정수 형식에 대 한 너무 큰 정수를 계산 하는 데 사용 하 여 수행할 수 있습니다는 [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-132">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="c4ce4-133">`bigint` 기본 형식; 간주 되지 않습니다. 에 대 한 약어 `System.Numerics.BigInteger`합니다.</span><span class="sxs-lookup"><span data-stu-id="c4ce4-133">`bigint` is not considered a primitive type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4ce4-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4ce4-134">See Also</span></span>
[<span data-ttu-id="c4ce4-135">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c4ce4-135">F# Language Reference</span></span>](index.md)
