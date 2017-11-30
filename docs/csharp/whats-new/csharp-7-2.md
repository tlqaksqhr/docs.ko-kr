---
title: "C# 7.2의 새로운 기능"
description: "C# 7.2에 대 한 새로운 기능의 개요입니다."
keywords: "C# 언어 디자인, 7.2, Visual Studio 2017 년"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="58dc9-104">C# 7.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="58dc9-104">What's new in C# 7.2</span></span>

<span data-ttu-id="58dc9-105">C# 7.2는 다양 한 유용한 기능을 추가 하는 다른 지점 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-105">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="58dc9-106">이 릴리스에 대 한 하나의 테마는 불필요 한 복사본 또는 할당을 방지 하 여 값 형식으로 보다 효율적으로 작업은 합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-106">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="58dc9-107">나머지 기능은 작은, 순위가 멋진 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-107">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="58dc9-108">사용 하 여 C# 7.2는 [언어 버전 선택](csharp-7-1.md#language-version-selection) 컴파일러 언어 버전을 선택 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-108">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="58dc9-109">이 릴리스의 새 언어 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-109">The new language features in this release are:</span></span>

* [<span data-ttu-id="58dc9-110">값 형식과 참조 의미 체계가</span><span class="sxs-lookup"><span data-stu-id="58dc9-110">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="58dc9-111">값 형식 참조 의미 체계가 사용 하 여 작업에 사용할 수 있는 구문 기능 향상의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-111">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="58dc9-112">비 후행 명명 된 인수</span><span class="sxs-lookup"><span data-stu-id="58dc9-112">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="58dc9-113">명명 된 인수를 위치 인수 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-113">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="58dc9-114">숫자 리터럴에서 선행 밑줄이</span><span class="sxs-lookup"><span data-stu-id="58dc9-114">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="58dc9-115">숫자 리터럴을 수 있는 인쇄 숫자 하기 전에 선행 밑줄이 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-115">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="58dc9-116">`private protected`액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="58dc9-116">`private protected` access modifier</span></span>](#private-protected)
  - <span data-ttu-id="58dc9-117">`private protected` 액세스 한정자를 사용 하면 동일한 어셈블리의 파생된 클래스에 대 한 액세스.</span><span class="sxs-lookup"><span data-stu-id="58dc9-117">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="58dc9-118">값 형식과 참조 의미 체계가</span><span class="sxs-lookup"><span data-stu-id="58dc9-118">Reference semantics with value types</span></span>

<span data-ttu-id="58dc9-119">7.2에 도입 된 언어 기능에는 참조 의미 체계가 사용 하는 동안 값 형식과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-119">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="58dc9-120">복사 값 형식은 참조 형식 사용과 관련 된 메모리 할당을 발생 시 키 지 않고 최소화 하 여 성능을 향상 시키기 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-120">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="58dc9-121">기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-121">The features include:</span></span>

 - <span data-ttu-id="58dc9-122">`in` 매개 변수를 인수로 참조로 전달 있지만 호출된 된 메서드에 의해 수정 되지 않음을 지정 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-122">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="58dc9-123">`ref readonly` 한정자 메서드가 반환 되 면 메서드는 참조로 값을 반환한 있지만 해당 개체에 대 한 쓰기를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-123">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="58dc9-124">`readonly struct` 구조체는 변경할 수 있으며 변수로 전달 해야 나타내기 위해 선언 된 `in` 매개 변수는 멤버 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-124">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="58dc9-125">`ref struct` 선언이 표시 되는 구조체 형식의 관리 되는 메모리에 직접 액세스 항상 스택 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-125">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="58dc9-126">이러한 모든 요소에 대 한 자세한 정보를 변경 읽을 수 [값 형식을 사용 하 여 참조 의미론을 통해](../reference-semantics-with-value-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-126">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="58dc9-127">비 후행 명명 된 인수</span><span class="sxs-lookup"><span data-stu-id="58dc9-127">Non-trailing named arguments</span></span>

<span data-ttu-id="58dc9-128">이제 메서드 호출 명명 된 인수는 올바른 위치에 배치 하는 경우 위치 인수 앞에 있는 명명 된 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-128">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="58dc9-129">자세한 내용은 참조 [명명 된 인수와 선택적 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-129">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="58dc9-130">숫자 리터럴에서 선행 밑줄이</span><span class="sxs-lookup"><span data-stu-id="58dc9-130">Leading underscores in numeric literals</span></span>

<span data-ttu-id="58dc9-131">자릿수 구분 기호에 C# 7.0에 대 한 지원 구현을 허용 하지 않습니다는 `_` 리터럴 값의 첫 번째 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-131">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="58dc9-132">16 진수 및 숫자 리터럴을 이진 수로 시작 이제는 `_`합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-132">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="58dc9-133">예:</span><span class="sxs-lookup"><span data-stu-id="58dc9-133">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

<span data-ttu-id="58dc9-134">새 복합 액세스 한정자를 마지막으로,: `private protected` 같은 어셈블리에 선언 된 파생된 클래스에서 구성원을 액세스할 수 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="58dc9-135">반면 `protected internal` 동일한 어셈블리에 있는 클래스 또는 파생된 클래스에서 액세스할 수 있도록 `private protected` 동일한 어셈블리에 선언 된 파생된 형식에 대 한 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="58dc9-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="58dc9-136">자세한 내용은 참조 [액세스 한정자](../language-reference/keywords/access-modifiers.md) 언어 참조에서.</span><span class="sxs-lookup"><span data-stu-id="58dc9-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
