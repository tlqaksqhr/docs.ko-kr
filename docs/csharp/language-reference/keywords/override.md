---
title: override(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 8f692dfdf8bd34ddb62623d86ec3dadd2b8dead3
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199266"
---
# <a name="override-c-reference"></a><span data-ttu-id="6f440-102">override(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6f440-102">override (C# Reference)</span></span>
<span data-ttu-id="6f440-103">`override` 한정자는 상속된 메서드, 속성, 인덱서 또는 이벤트의 추상 또는 가상 구현을 확장하거나 수정하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f440-104">예</span><span class="sxs-lookup"><span data-stu-id="6f440-104">Example</span></span>  
 <span data-ttu-id="6f440-105">이 예제에서 `Square` 클래스는 `Area`가 추상 `ShapesClass`에서 상속되기 때문에 `Area`의 재정의된 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]  
  
 <span data-ttu-id="6f440-106">`override` 메서드는 기본 클래스에서 상속된 멤버의 새 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="6f440-107">`override` 선언에서 재정의된 메서드를 재정의된 기본 메서드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="6f440-108">재정의된 기본 메서드에는 `override` 메서드와 동일한 시그니처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="6f440-109">상속에 대한 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f440-109">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="6f440-110">비가상 또는 정적 메서드는 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="6f440-111">재정의된 기본 메서드는 `virtual`, `abstract` 또는 `override`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="6f440-112">`override` 선언에서는 `virtual` 메서드의 액세스 가능성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="6f440-113">`override` 메서드 및 `virtual` 메서드 둘 다에 동일한 [액세스 수준 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-113">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="6f440-114">`new`, `static` 또는 `virtual` 한정자를 사용하여 `override` 메서드를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="6f440-115">재정의 속성 선언은 상속된 속성과 동일한 액세스 한정자, 형식 및 이름을 지정해야 하고, 재정의된 속성은 `virtual`, `abstract` 또는 `override`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="6f440-116">`override` 키워드 사용 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f440-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f440-117">예</span><span class="sxs-lookup"><span data-stu-id="6f440-117">Example</span></span>  
 <span data-ttu-id="6f440-118">이 예제에서는 `Employee`라는 기본 클래스와 `SalesEmployee`라는 파생 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="6f440-119">`SalesEmployee` 클래스에는 추가 속성 `salesbonus`가 포함되어 있고, 이를 고려하기 위해 `CalculatePay` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6f440-119">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6f440-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6f440-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f440-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f440-121">See Also</span></span>  
 [<span data-ttu-id="6f440-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="6f440-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6f440-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6f440-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6f440-124">상속</span><span class="sxs-lookup"><span data-stu-id="6f440-124">Inheritance</span></span>](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [<span data-ttu-id="6f440-125">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="6f440-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6f440-126">한정자</span><span class="sxs-lookup"><span data-stu-id="6f440-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="6f440-127">abstract</span><span class="sxs-lookup"><span data-stu-id="6f440-127">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="6f440-128">virtual</span><span class="sxs-lookup"><span data-stu-id="6f440-128">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="6f440-129">new</span><span class="sxs-lookup"><span data-stu-id="6f440-129">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
 [<span data-ttu-id="6f440-130">다형성</span><span class="sxs-lookup"><span data-stu-id="6f440-130">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)
