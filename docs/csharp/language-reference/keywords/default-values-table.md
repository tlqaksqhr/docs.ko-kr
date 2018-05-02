---
title: 기본값 표(C# 참조)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
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
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="ce1e3-102">기본값 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ce1e3-102">Default values table (C# Reference)</span></span>

<span data-ttu-id="ce1e3-103">다음 표는 기본 생성자에서 반환한 값 형식의 기본값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce1e3-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="ce1e3-104">기본 생성자는 다음과 같이 `new` 연산자를 사용하여 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce1e3-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="ce1e3-105">위의 문은 다음에 오는 문과 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce1e3-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="ce1e3-106">C#에서는 초기화되지 않은 변수를 사용할 수 없음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ce1e3-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="ce1e3-107">값 형식</span><span class="sxs-lookup"><span data-stu-id="ce1e3-107">Value type</span></span>|<span data-ttu-id="ce1e3-108">기본값</span><span class="sxs-lookup"><span data-stu-id="ce1e3-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="ce1e3-109">bool</span><span class="sxs-lookup"><span data-stu-id="ce1e3-109">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="ce1e3-110">byte</span><span class="sxs-lookup"><span data-stu-id="ce1e3-110">byte</span></span>](byte.md)|<span data-ttu-id="ce1e3-111">0</span><span class="sxs-lookup"><span data-stu-id="ce1e3-111">0</span></span>|
|[<span data-ttu-id="ce1e3-112">char</span><span class="sxs-lookup"><span data-stu-id="ce1e3-112">char</span></span>](char.md)|<span data-ttu-id="ce1e3-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="ce1e3-113">'\0'</span></span>|
|[<span data-ttu-id="ce1e3-114">decimal</span><span class="sxs-lookup"><span data-stu-id="ce1e3-114">decimal</span></span>](decimal.md)|<span data-ttu-id="ce1e3-115">0M</span><span class="sxs-lookup"><span data-stu-id="ce1e3-115">0M</span></span>|
|[<span data-ttu-id="ce1e3-116">double</span><span class="sxs-lookup"><span data-stu-id="ce1e3-116">double</span></span>](double.md)|<span data-ttu-id="ce1e3-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="ce1e3-117">0.0D</span></span>|
|[<span data-ttu-id="ce1e3-118">enum</span><span class="sxs-lookup"><span data-stu-id="ce1e3-118">enum</span></span>](enum.md)|<span data-ttu-id="ce1e3-119">식 (E)0으로 생성한 값이며 여기서 E는 열거형 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ce1e3-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="ce1e3-120">float</span><span class="sxs-lookup"><span data-stu-id="ce1e3-120">float</span></span>](float.md)|<span data-ttu-id="ce1e3-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="ce1e3-121">0.0F</span></span>|
|[<span data-ttu-id="ce1e3-122">int</span><span class="sxs-lookup"><span data-stu-id="ce1e3-122">int</span></span>](int.md)|<span data-ttu-id="ce1e3-123">0</span><span class="sxs-lookup"><span data-stu-id="ce1e3-123">0</span></span>|
|[<span data-ttu-id="ce1e3-124">long</span><span class="sxs-lookup"><span data-stu-id="ce1e3-124">long</span></span>](long.md)|<span data-ttu-id="ce1e3-125">0L</span><span class="sxs-lookup"><span data-stu-id="ce1e3-125">0L</span></span>|
|[<span data-ttu-id="ce1e3-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="ce1e3-126">sbyte</span></span>](sbyte.md)|<span data-ttu-id="ce1e3-127">0</span><span class="sxs-lookup"><span data-stu-id="ce1e3-127">0</span></span>|
|[<span data-ttu-id="ce1e3-128">short</span><span class="sxs-lookup"><span data-stu-id="ce1e3-128">short</span></span>](short.md)|<span data-ttu-id="ce1e3-129">0</span><span class="sxs-lookup"><span data-stu-id="ce1e3-129">0</span></span>|
|[<span data-ttu-id="ce1e3-130">struct</span><span class="sxs-lookup"><span data-stu-id="ce1e3-130">struct</span></span>](struct.md)|<span data-ttu-id="ce1e3-131">모든 값 형식 필드를 기본값으로 설정하고 모든 참조 형식 필드를 `null`로 설정하여 생성한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ce1e3-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="ce1e3-132">uint</span><span class="sxs-lookup"><span data-stu-id="ce1e3-132">uint</span></span>](uint.md)|<span data-ttu-id="ce1e3-133">0</span><span class="sxs-lookup"><span data-stu-id="ce1e3-133">0</span></span>|
|[<span data-ttu-id="ce1e3-134">ulong</span><span class="sxs-lookup"><span data-stu-id="ce1e3-134">ulong</span></span>](ulong.md)|<span data-ttu-id="ce1e3-135">0</span><span class="sxs-lookup"><span data-stu-id="ce1e3-135">0</span></span>|
|[<span data-ttu-id="ce1e3-136">ushort</span><span class="sxs-lookup"><span data-stu-id="ce1e3-136">ushort</span></span>](ushort.md)|<span data-ttu-id="ce1e3-137">0</span><span class="sxs-lookup"><span data-stu-id="ce1e3-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="ce1e3-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce1e3-138">See also</span></span>
 [<span data-ttu-id="ce1e3-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ce1e3-139">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="ce1e3-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ce1e3-140">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="ce1e3-141">값 형식 표</span><span class="sxs-lookup"><span data-stu-id="ce1e3-141">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="ce1e3-142">값 형식</span><span class="sxs-lookup"><span data-stu-id="ce1e3-142">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="ce1e3-143">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="ce1e3-143">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="ce1e3-144">형식 참조 테이블</span><span class="sxs-lookup"><span data-stu-id="ce1e3-144">Reference Tables for Types</span></span>](reference-tables-for-types.md)
