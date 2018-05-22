---
title: C# 7.2의 새로운 기능
description: C# 7.2의 새로운 기능에 대한 개요입니다.
ms.date: 08/16/2017
ms.openlocfilehash: b813bf5b38ef17986b21e928c9c86e583174c7d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-72"></a><span data-ttu-id="da21d-103">C# 7.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="da21d-103">What's new in C# 7.2</span></span>

<span data-ttu-id="da21d-104">C# 7.2는 다양한 유용한 기능을 추가하는 또 하나의 지점 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-104">C# 7.2 is another point release that adds a number of useful features.</span></span>
<span data-ttu-id="da21d-105">이 릴리스의 한 테마는 불필요한 복사 또는 할당 없이 값 유형을 사용하여 보다 효율적으로 작동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-105">One theme for this release is working more efficiently with value types by avoiding unnecessary copies or allocations.</span></span> 

<span data-ttu-id="da21d-106">나머지 기능은 작지만 멋진 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-106">The remaining features are small, nice-to-have features.</span></span>

<span data-ttu-id="da21d-107">C# 7.2는 [언어 버전 선택](csharp-7-1.md#language-version-selection) 구성 요소를 사용하여 컴파일러 언어 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-107">C# 7.2 uses the [language version selection](csharp-7-1.md#language-version-selection) configuration element to select the compiler language version.</span></span>

<span data-ttu-id="da21d-108">이 릴리스의 새로운 언어 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-108">The new language features in this release are:</span></span>

* [<span data-ttu-id="da21d-109">값 형식과 참조 의미 체계</span><span class="sxs-lookup"><span data-stu-id="da21d-109">Reference semantics with value types</span></span>](#reference-semantics-with-value-types)
  - <span data-ttu-id="da21d-110">참조 의미 체계를 사용하는 값 유형으로 작동할 수 있는 구문 개선의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-110">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>
* [<span data-ttu-id="da21d-111">뒤에 오지 않는 명명된 인수</span><span class="sxs-lookup"><span data-stu-id="da21d-111">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="da21d-112">명명된 인수 뒤에는 위치 인수가 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-112">Named arguments can be followed by positional arguments.</span></span>
* [<span data-ttu-id="da21d-113">숫자 리터럴의 선행 밑줄</span><span class="sxs-lookup"><span data-stu-id="da21d-113">Leading underscores in numeric literals</span></span>](#leading-underscores-in-numeric-literals)
  - <span data-ttu-id="da21d-114">숫자 리터럴은 이제 인쇄된 숫자 앞에 선행 밑줄이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-114">Numeric literals can now have leading underscores before any printed digits.</span></span>
* [<span data-ttu-id="da21d-115">`private protected` 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="da21d-115">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="da21d-116">`private protected` 액세스 한정자는 동일한 어셈블리의 파생된 클래스에 대해 액세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-116">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>

## <a name="reference-semantics-with-value-types"></a><span data-ttu-id="da21d-117">값 형식과 참조 의미 체계</span><span class="sxs-lookup"><span data-stu-id="da21d-117">Reference semantics with value types</span></span>

<span data-ttu-id="da21d-118">7.2에 도입된 언어 기능을 사용하면 참조 의미 체계를 사용하면서 값 형식을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-118">Language features introduced in 7.2 let you work with value types while using reference semantics.</span></span> <span data-ttu-id="da21d-119">참조 유형 사용과 관련된 메모리를 할당하지 않으면서 값 형식 복사를 최소화하여 성능을 향상시키도록 설계되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-119">They are designed to increase performance by minimizing copying value types without incurring the memory allocations associated with using reference types.</span></span> <span data-ttu-id="da21d-120">포함된 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-120">The features include:</span></span>

 - <span data-ttu-id="da21d-121">매개 변수의 `in` 한정자는 인수가 참조에 의해 전달되지만 호출된 메서드에 의해 수정되지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-121">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span>
 - <span data-ttu-id="da21d-122">메서드의 `ref readonly` 한정자는 메서드가 참조별 값을 반환하지만 해당 개체에 대한 쓰기를 허용하지 않음을 나타내기 위해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-122">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span>
 - <span data-ttu-id="da21d-123">`readonly struct` 선언은 구조체가 변경 가능하지 않으며 `in` 매개 변수로서 멤버 메서드로 전달되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-123">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span>
 - <span data-ttu-id="da21d-124">`ref struct` 선언은 구조체 유형이 관리되는 메모리에 직접 액세스하고 항상 스택에 할당되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-124">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span>

<span data-ttu-id="da21d-125">[참조 의미 체계와 함께 값 형식 사용](../reference-semantics-with-value-types.md)에서 모든 변경 사항에 대해 자세히 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-125">You can read more about all these changes in [Using value types with reference semantics](../reference-semantics-with-value-types.md).</span></span>

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="da21d-126">뒤에 오지 않는 명명된 인수</span><span class="sxs-lookup"><span data-stu-id="da21d-126">Non-trailing named arguments</span></span>

<span data-ttu-id="da21d-127">명명된 인수가 올바른 위치에 있을 때 메서드 호출은 이제 위치 인수보다 앞에 있는 명명된 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-127">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="da21d-128">자세한 내용은 [명명된 인수 및 선택적 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da21d-128">For more information see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="leading-underscores-in-numeric-literals"></a><span data-ttu-id="da21d-129">숫자 리터럴의 선행 밑줄</span><span class="sxs-lookup"><span data-stu-id="da21d-129">Leading underscores in numeric literals</span></span>

<span data-ttu-id="da21d-130">C# 7.0에서는 자릿수 구분 기호에 대한 지원을 구현해도 `_`이 리터럴 값의 첫 번째 문자가 되는 것을 허용하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-130">The implementation of support for digit separators in C# 7.0 didn't allow the `_` to be the first character of the literal value.</span></span> <span data-ttu-id="da21d-131">16진수 및 이진 숫자 리터럴은 이제 `_`로 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-131">Hex and binary numeric literals may now begin with an `_`.</span></span> 

<span data-ttu-id="da21d-132">예:</span><span class="sxs-lookup"><span data-stu-id="da21d-132">For example:</span></span>

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a><span data-ttu-id="da21d-133">_private protected_ 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="da21d-133">_private protected_ access modifier</span></span>

<span data-ttu-id="da21d-134">마지막으로, 새로운 복합 액세스 한정자인 `private protected`는 동일한 어셈블리에 선언된 클래스 또는 파생 클래스를 포함하여 멤버에 액세스할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-134">Finally, a new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="da21d-135">`protected internal`은 동일한 어셈블리에 있는 파생 클래스나 클래스에 의한 액세스를 허용하지만 `private protected`는 동일한 어셈블리에서 선언된 파생 유형에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="da21d-135">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="da21d-136">자세한 내용은 언어 참조의 [액세스 한정자](../language-reference/keywords/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da21d-136">For more information see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>
