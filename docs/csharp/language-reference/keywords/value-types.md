---
title: "값 형식(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 281b811f2a8a1f2c364405b563f9f103899b492c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-c-reference"></a><span data-ttu-id="b0763-102">값 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b0763-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="b0763-103">값 형식은 다음 두 가지 기본 범주로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="b0763-104">구조체</span><span class="sxs-lookup"><span data-stu-id="b0763-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="b0763-105">열거형</span><span class="sxs-lookup"><span data-stu-id="b0763-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="b0763-106">구조체는 다음 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="b0763-107">숫자 형식</span><span class="sxs-lookup"><span data-stu-id="b0763-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="b0763-108">정수 형식</span><span class="sxs-lookup"><span data-stu-id="b0763-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="b0763-109">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="b0763-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
    -   [<span data-ttu-id="b0763-110">decimal</span><span class="sxs-lookup"><span data-stu-id="b0763-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)  
  
-   [<span data-ttu-id="b0763-111">bool</span><span class="sxs-lookup"><span data-stu-id="b0763-111">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="b0763-112">사용자 정의 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-112">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="b0763-113">값 형식의 주요 기능</span><span class="sxs-lookup"><span data-stu-id="b0763-113">Main Features of Value Types</span></span>  
 <span data-ttu-id="b0763-114">값 형식을 기반으로 하는 변수에는 직접 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-114">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="b0763-115">값 형식 변수를 다른 값 형식 변수에 할당하면 포함된 값이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-115">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="b0763-116">이는 개체 자체가 아니라 참조를 개체에 복사하는 참조 형식 변수의 할당과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-116">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="b0763-117">모든 값 형식은 <xref:System.ValueType?displayProperty=nameWithType>에서 암시적으로 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-117">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="b0763-118">참조 형식과 달리 값 형식에서는 새 형식을 파생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-118">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="b0763-119">그러나 참조 형식과 마찬가지로 구조체가 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-119">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="b0763-120">참조 형식과 달리 값 형식에는 `null` 값을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-120">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="b0763-121">그러나 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md) 기능은 `null`에 값 형식 할당을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-121">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="b0763-122">각 값 형식에는 해당 형식의 기본값을 초기화하는 암시적 기본 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-122">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="b0763-123">값 형식의 기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0763-123">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="b0763-124">단순 형식의 주요 기능</span><span class="sxs-lookup"><span data-stu-id="b0763-124">Main Features of Simple Types</span></span>  
 <span data-ttu-id="b0763-125">C# 언어의 필수 형식인 모든 단순 형식은 .NET Framework 시스템 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-125">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="b0763-126">예를 들어 [int](../../../csharp/language-reference/keywords/int.md)는 <xref:System.Int32?displayProperty=nameWithType>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-126">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b0763-127">별칭의 전체 목록은 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0763-127">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="b0763-128">해당 피연산자가 모두 단순 형식 상수인 상수 식은 컴파일 시간에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-128">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="b0763-129">리터럴을 사용하여 단순 형식을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-129">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="b0763-130">예를 들어 ‘A’는 `char` 형식의 리터럴이고, 2001은 `int` 형식의 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-130">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="b0763-131">값 형식 초기화</span><span class="sxs-lookup"><span data-stu-id="b0763-131">Initializing Value Types</span></span>  
 <span data-ttu-id="b0763-132">C#의 지역 변수는 사용하기 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-132">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="b0763-133">예를 들어 다음 예제와 같이 초기화하지 않고 지역 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-133">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```  
int myInt;  
```  
  
 <span data-ttu-id="b0763-134">초기화하기 전에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-134">You cannot use it before you initialize it.</span></span> <span data-ttu-id="b0763-135">다음 문을 사용하여 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-135">You can initialize it using the following statement:</span></span>  
  
```  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="b0763-136">이 문은 다음 문과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-136">This statement is equivalent to the following statement:</span></span>  
  
```  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="b0763-137">물론, 다음 예제와 같이 선언과 초기화를 동일한 문에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-137">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```  
int myInt = new int();  
```  
  
 <span data-ttu-id="b0763-138">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="b0763-138">–or–</span></span>  
  
```  
int myInt = 0;  
```  
  
 <span data-ttu-id="b0763-139">[new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하면 특정 형식의 기본 생성자가 호출되고 변수에 기본값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-139">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="b0763-140">앞의 예제에서는 기본 생성자가 `0` 값을 `myInt`에 할당했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-140">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="b0763-141">기본 생성자를 호출하여 할당된 값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0763-141">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="b0763-142">사용자 정의 형식의 경우 [new](../../../csharp/language-reference/keywords/new.md)를 사용하여 기본 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-142">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="b0763-143">예를 들어 다음 문은 `Point` 구조체의 기본 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-143">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="b0763-144">이 호출 후에는 구조체가 한정적으로 할당된 것으로 간주됩니다. 즉, 모든 멤버가 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0763-144">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="b0763-145">새 연산자에 대한 자세한 내용은 [new](../../../csharp/language-reference/keywords/new.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0763-145">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="b0763-146">숫자 형식의 출력에 서식을 지정하는 방법에 대한 자세한 내용은 [숫자 결과 형식 지정 표](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0763-146">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0763-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0763-147">See Also</span></span>  
 [<span data-ttu-id="b0763-148">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b0763-148">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b0763-149">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b0763-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0763-150">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="b0763-150">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="b0763-151">유형</span><span class="sxs-lookup"><span data-stu-id="b0763-151">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="b0763-152">형식 참조 테이블</span><span class="sxs-lookup"><span data-stu-id="b0763-152">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [<span data-ttu-id="b0763-153">참조 형식</span><span class="sxs-lookup"><span data-stu-id="b0763-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
