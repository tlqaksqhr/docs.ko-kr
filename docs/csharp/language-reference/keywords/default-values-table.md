---
title: 기본값 표(C# 참조)
description: 기본 생성자에서 반환한 값 형식의 기본값에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218792"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="e81c5-103">기본값 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e81c5-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="e81c5-104">다음 표는 기본 생성자에서 반환한 값 형식의 기본값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e81c5-104">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="e81c5-105">기본 생성자는 다음과 같이 `new` 연산자를 사용하여 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e81c5-105">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="e81c5-106">위의 문은 다음에 오는 문과 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e81c5-106">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="e81c5-107">C#에서는 초기화되지 않은 변수를 사용할 수 없음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="e81c5-107">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="e81c5-108">값 형식</span><span class="sxs-lookup"><span data-stu-id="e81c5-108">Value type</span></span>|<span data-ttu-id="e81c5-109">기본값</span><span class="sxs-lookup"><span data-stu-id="e81c5-109">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="e81c5-110">bool</span><span class="sxs-lookup"><span data-stu-id="e81c5-110">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="e81c5-111">byte</span><span class="sxs-lookup"><span data-stu-id="e81c5-111">byte</span></span>](byte.md)|<span data-ttu-id="e81c5-112">0</span><span class="sxs-lookup"><span data-stu-id="e81c5-112">0</span></span>|
|[<span data-ttu-id="e81c5-113">char</span><span class="sxs-lookup"><span data-stu-id="e81c5-113">char</span></span>](char.md)|<span data-ttu-id="e81c5-114">'\0'</span><span class="sxs-lookup"><span data-stu-id="e81c5-114">'\0'</span></span>|
|[<span data-ttu-id="e81c5-115">decimal</span><span class="sxs-lookup"><span data-stu-id="e81c5-115">decimal</span></span>](decimal.md)|<span data-ttu-id="e81c5-116">0M</span><span class="sxs-lookup"><span data-stu-id="e81c5-116">0M</span></span>|
|[<span data-ttu-id="e81c5-117">double</span><span class="sxs-lookup"><span data-stu-id="e81c5-117">double</span></span>](double.md)|<span data-ttu-id="e81c5-118">0.0D</span><span class="sxs-lookup"><span data-stu-id="e81c5-118">0.0D</span></span>|
|[<span data-ttu-id="e81c5-119">enum</span><span class="sxs-lookup"><span data-stu-id="e81c5-119">enum</span></span>](enum.md)|<span data-ttu-id="e81c5-120">식 (E)0으로 생성한 값이며 여기서 E는 열거형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e81c5-120">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="e81c5-121">float</span><span class="sxs-lookup"><span data-stu-id="e81c5-121">float</span></span>](float.md)|<span data-ttu-id="e81c5-122">0.0F</span><span class="sxs-lookup"><span data-stu-id="e81c5-122">0.0F</span></span>|
|[<span data-ttu-id="e81c5-123">int</span><span class="sxs-lookup"><span data-stu-id="e81c5-123">int</span></span>](int.md)|<span data-ttu-id="e81c5-124">0</span><span class="sxs-lookup"><span data-stu-id="e81c5-124">0</span></span>|
|[<span data-ttu-id="e81c5-125">long</span><span class="sxs-lookup"><span data-stu-id="e81c5-125">long</span></span>](long.md)|<span data-ttu-id="e81c5-126">0L</span><span class="sxs-lookup"><span data-stu-id="e81c5-126">0L</span></span>|
|[<span data-ttu-id="e81c5-127">sbyte</span><span class="sxs-lookup"><span data-stu-id="e81c5-127">sbyte</span></span>](sbyte.md)|<span data-ttu-id="e81c5-128">0</span><span class="sxs-lookup"><span data-stu-id="e81c5-128">0</span></span>|
|[<span data-ttu-id="e81c5-129">short</span><span class="sxs-lookup"><span data-stu-id="e81c5-129">short</span></span>](short.md)|<span data-ttu-id="e81c5-130">0</span><span class="sxs-lookup"><span data-stu-id="e81c5-130">0</span></span>|
|[<span data-ttu-id="e81c5-131">struct</span><span class="sxs-lookup"><span data-stu-id="e81c5-131">struct</span></span>](struct.md)|<span data-ttu-id="e81c5-132">모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e81c5-132">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="e81c5-133">uint</span><span class="sxs-lookup"><span data-stu-id="e81c5-133">uint</span></span>](uint.md)|<span data-ttu-id="e81c5-134">0</span><span class="sxs-lookup"><span data-stu-id="e81c5-134">0</span></span>|
|[<span data-ttu-id="e81c5-135">ulong</span><span class="sxs-lookup"><span data-stu-id="e81c5-135">ulong</span></span>](ulong.md)|<span data-ttu-id="e81c5-136">0</span><span class="sxs-lookup"><span data-stu-id="e81c5-136">0</span></span>|
|[<span data-ttu-id="e81c5-137">ushort</span><span class="sxs-lookup"><span data-stu-id="e81c5-137">ushort</span></span>](ushort.md)|<span data-ttu-id="e81c5-138">0</span><span class="sxs-lookup"><span data-stu-id="e81c5-138">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="e81c5-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e81c5-139">See also</span></span>
 [<span data-ttu-id="e81c5-140">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e81c5-140">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="e81c5-141">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e81c5-141">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="e81c5-142">값 형식 표</span><span class="sxs-lookup"><span data-stu-id="e81c5-142">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="e81c5-143">값 형식</span><span class="sxs-lookup"><span data-stu-id="e81c5-143">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="e81c5-144">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="e81c5-144">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="e81c5-145">형식 참조 테이블</span><span class="sxs-lookup"><span data-stu-id="e81c5-145">Reference Tables for Types</span></span>](reference-tables-for-types.md)
