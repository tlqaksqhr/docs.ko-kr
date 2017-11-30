---
title: "기본값 표(C# 참조)"
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034c1daf495c50e299fec4c5bf399652dad08ce
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2017
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="cc26a-102">기본값 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cc26a-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="cc26a-103">다음 표는 기본 생성자에서 반환한 값 형식의 기본값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc26a-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="cc26a-104">기본 생성자는 다음과 같이 `new` 연산자를 사용하여 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc26a-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="cc26a-105">위의 문은 다음에 오는 문과 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc26a-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="cc26a-106">C#에서는 초기화되지 않은 변수를 사용할 수 없음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="cc26a-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="cc26a-107">값 형식</span><span class="sxs-lookup"><span data-stu-id="cc26a-107">Value type</span></span>|<span data-ttu-id="cc26a-108">기본값</span><span class="sxs-lookup"><span data-stu-id="cc26a-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="cc26a-109">bool</span><span class="sxs-lookup"><span data-stu-id="cc26a-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="cc26a-110">byte</span><span class="sxs-lookup"><span data-stu-id="cc26a-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="cc26a-111">0</span><span class="sxs-lookup"><span data-stu-id="cc26a-111">0</span></span>|
|[<span data-ttu-id="cc26a-112">char</span><span class="sxs-lookup"><span data-stu-id="cc26a-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="cc26a-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="cc26a-113">'\0'</span></span>|
|[<span data-ttu-id="cc26a-114">decimal</span><span class="sxs-lookup"><span data-stu-id="cc26a-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="cc26a-115">M 0</span><span class="sxs-lookup"><span data-stu-id="cc26a-115">0M</span></span>|
|[<span data-ttu-id="cc26a-116">double</span><span class="sxs-lookup"><span data-stu-id="cc26a-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="cc26a-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="cc26a-117">0.0D</span></span>|
|[<span data-ttu-id="cc26a-118">enum</span><span class="sxs-lookup"><span data-stu-id="cc26a-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="cc26a-119">식 (E)0으로 생성한 값이며 여기서 E는 열거형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="cc26a-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="cc26a-120">float</span><span class="sxs-lookup"><span data-stu-id="cc26a-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="cc26a-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="cc26a-121">0.0F</span></span>|
|[<span data-ttu-id="cc26a-122">int</span><span class="sxs-lookup"><span data-stu-id="cc26a-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="cc26a-123">0</span><span class="sxs-lookup"><span data-stu-id="cc26a-123">0</span></span>|
|[<span data-ttu-id="cc26a-124">long</span><span class="sxs-lookup"><span data-stu-id="cc26a-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="cc26a-125">0L</span><span class="sxs-lookup"><span data-stu-id="cc26a-125">0L</span></span>|
|[<span data-ttu-id="cc26a-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="cc26a-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="cc26a-127">0</span><span class="sxs-lookup"><span data-stu-id="cc26a-127">0</span></span>|
|[<span data-ttu-id="cc26a-128">short</span><span class="sxs-lookup"><span data-stu-id="cc26a-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="cc26a-129">0</span><span class="sxs-lookup"><span data-stu-id="cc26a-129">0</span></span>|
|[<span data-ttu-id="cc26a-130">struct</span><span class="sxs-lookup"><span data-stu-id="cc26a-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="cc26a-131">모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cc26a-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="cc26a-132">uint</span><span class="sxs-lookup"><span data-stu-id="cc26a-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="cc26a-133">0</span><span class="sxs-lookup"><span data-stu-id="cc26a-133">0</span></span>|
|[<span data-ttu-id="cc26a-134">ulong</span><span class="sxs-lookup"><span data-stu-id="cc26a-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="cc26a-135">0</span><span class="sxs-lookup"><span data-stu-id="cc26a-135">0</span></span>|
|[<span data-ttu-id="cc26a-136">ushort</span><span class="sxs-lookup"><span data-stu-id="cc26a-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="cc26a-137">0</span><span class="sxs-lookup"><span data-stu-id="cc26a-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="cc26a-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc26a-138">See also</span></span>
 [<span data-ttu-id="cc26a-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="cc26a-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cc26a-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cc26a-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cc26a-141">값 형식 표</span><span class="sxs-lookup"><span data-stu-id="cc26a-141">Value Types Table</span></span>](../../../csharp/language-reference/keywords/value-types-table.md)  
 [<span data-ttu-id="cc26a-142">값 형식</span><span class="sxs-lookup"><span data-stu-id="cc26a-142">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="cc26a-143">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="cc26a-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="cc26a-144">형식 참조 테이블</span><span class="sxs-lookup"><span data-stu-id="cc26a-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
