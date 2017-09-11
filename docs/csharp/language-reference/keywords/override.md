---
title: "override(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- override
- override_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
caps.latest.revision: 26
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0f5a87eaa5894b61187c379c92ad785336aa79b2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="override-c-reference"></a><span data-ttu-id="0f253-102">override(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0f253-102">override (C# Reference)</span></span>
<span data-ttu-id="0f253-103">`override` 한정자는 상속된 메서드, 속성, 인덱서 또는 이벤트의 추상 또는 가상 구현을 확장하거나 수정하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f253-104">예제</span><span class="sxs-lookup"><span data-stu-id="0f253-104">Example</span></span>  
 <span data-ttu-id="0f253-105">이 예제에서 `Square` 클래스는 `Area`가 추상 `ShapesClass`에서 상속되기 때문에 `Area`의 재정의된 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>  
  
 <span data-ttu-id="0f253-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0f253-106">[!code-cs[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_1.cs)]</span></span>  
  
 <span data-ttu-id="0f253-107">`override` 메서드는 기본 클래스에서 상속된 멤버의 새 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-107">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="0f253-108">`override` 선언에서 재정의된 메서드를 재정의된 기본 메서드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-108">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="0f253-109">재정의된 기본 메서드에는 `override` 메서드와 동일한 시그니처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-109">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="0f253-110">상속에 대한 자세한 내용은 [상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f253-110">For information about inheritance, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="0f253-111">비가상 또는 정적 메서드는 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-111">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="0f253-112">재정의된 기본 메서드는 `virtual`, `abstract` 또는 `override`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-112">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="0f253-113">`override` 선언에서는 `virtual` 메서드의 액세스 가능성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-113">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="0f253-114">`override` 메서드 및 `virtual` 메서드 둘 다에 동일한 [액세스 수준 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-114">Both the `override` method and the `virtual` method must have the same [access level modifier](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="0f253-115">`new`, `static` 또는 `virtual` 한정자를 사용하여 `override` 메서드를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-115">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>  
  
 <span data-ttu-id="0f253-116">재정의 속성 선언은 상속된 속성과 동일한 액세스 한정자, 형식 및 이름을 지정해야 하고, 재정의된 속성은 `virtual`, `abstract` 또는 `override`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-116">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>  
  
 <span data-ttu-id="0f253-117">`override` 키워드 사용 방법에 대한 자세한 내용은 [Override 및 New 키워드를 사용하여 버전 관리](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) 및 [Override 및 New 키워드를 사용해야 하는 경우](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f253-117">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f253-118">예제</span><span class="sxs-lookup"><span data-stu-id="0f253-118">Example</span></span>  
 <span data-ttu-id="0f253-119">이 예제에서는 `Employee`라는 기본 클래스와 `SalesEmployee`라는 파생 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-119">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="0f253-120">`SalesEmployee` 클래스에는 추가 속성 `salesbonus`가 포함되어 있고, 이를 고려하기 위해 `CalculatePay` 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0f253-120">The `SalesEmployee` class includes an extra property, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>  
  
 <span data-ttu-id="0f253-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0f253-121">[!code-cs[csrefKeywordsModifiers#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/override_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0f253-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="0f253-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0f253-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f253-123">See Also</span></span>  
 <span data-ttu-id="0f253-124">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0f253-125">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0f253-126">[상속](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-126">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="0f253-127">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="0f253-128">[한정자](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-128">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="0f253-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-129">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span></span>  
 <span data-ttu-id="0f253-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-130">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 <span data-ttu-id="0f253-131">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="0f253-131">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 [<span data-ttu-id="0f253-132">다형성</span><span class="sxs-lookup"><span data-stu-id="0f253-132">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)

