---
title: "in(제네릭 한정자)(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- contravariance, in keyword [C#]
- in keyword [C#]
ms.assetid: 3a778c36-8aed-4ebe-aa8b-39f4057215b1
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 84773fca826b5a25679f1385a11c51b590ea20f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="in-generic-modifier-c-reference"></a><span data-ttu-id="5b05a-102">in(제네릭 한정자)(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5b05a-102">in (Generic Modifier) (C# Reference)</span></span>
<span data-ttu-id="5b05a-103">제네릭 형식 매개 변수에서 `in` 키워드는 형식 매개 변수를 반공변(contravariant)으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-103">For generic type parameters, the `in` keyword specifies that the type parameter is contravariant.</span></span> <span data-ttu-id="5b05a-104">제네릭 인터페이스 및 대리자에서 `in` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-104">You can use the `in` keyword in generic interfaces and delegates.</span></span>  
  
 <span data-ttu-id="5b05a-105">반공변성(Contravariance)을 통해 제네릭 매개 변수에 지정된 것보다 적은 파생 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-105">Contravariance enables you to use a less derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="5b05a-106">따라서 variant 인터페이스를 구현하는 클래스의 암시적 변환과 대리자 형식의 암시적 변환이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span> <span data-ttu-id="5b05a-107">제네릭 형식 매개 변수의 공변성(Covariance) 및 반공변성(Contravariance)은 참조 형식에 대해 지원되고 값 형식에 대해서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-107">Covariance and contravariance in generic type parameters are supported for reference types, but they are not supported for value types.</span></span>  
  
 <span data-ttu-id="5b05a-108">메서드 인수의 형식으로만 사용되고 메서드 반환 형식으로 사용되지 않는 경우 형식을 제네릭 인터페이스 또는 대리자에서 반공변(contravariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-108">A type can be declared contravariant in a generic interface or delegate if it is used only as a type of method arguments and not used as a method return type.</span></span> <span data-ttu-id="5b05a-109">`Ref` 및 `out` 매개 변수는 variant일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-109">`Ref` and `out` parameters cannot be variant.</span></span>  
  
 <span data-ttu-id="5b05a-110">반공변(contravariant) 형식 매개 변수가 있는 인터페이스는 해당 메서드가 인터페이스 형식 매개 변수에 지정된 형식보다 덜 파생된 형식의 인수를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-110">An interface that has a contravariant type parameter allows its methods to accept arguments of less derived types than those specified by the interface type parameter.</span></span> <span data-ttu-id="5b05a-111">예를 들어 .NET Framework 4의 <xref:System.Collections.Generic.IComparer%601> 인터페이스에서 T 형식은 반공변(contravariant)이므로 `Employee`가 `Person`을 상속하는 경우 특수 변환 메서드를 사용하지 않고 `IComparer(Of Person)` 형식의 개체를 `IComparer(Of Employee)` 형식의 개체에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-111">For example, because in .NET Framework 4, in the <xref:System.Collections.Generic.IComparer%601> interface, type T is contravariant, you can assign an object of the `IComparer(Of Person)` type to an object of the `IComparer(Of Employee)` type without using any special conversion methods if `Employee` inherits `Person`.</span></span>  
  
 <span data-ttu-id="5b05a-112">반공변(contravariant) 대리자에 동일한 형식의 다른 대리자를 할당할 수 있지만 덜 파생된 제네릭 형식 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-112">A contravariant delegate can be assigned another delegate of the same type, but with a less derived generic type parameter.</span></span>  
  
 <span data-ttu-id="5b05a-113">자세한 내용은 [공변성(Covariance) 및 반공변성(Contravariance)](../../programming-guide/concepts/covariance-contravariance/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b05a-113">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b05a-114">예제</span><span class="sxs-lookup"><span data-stu-id="5b05a-114">Example</span></span>  
 <span data-ttu-id="5b05a-115">다음 예제에서는 반공변(contravariant) 제네릭 인터페이스를 선언, 확장 및 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-115">The following example shows how to declare, extend, and implement a contravariant generic interface.</span></span> <span data-ttu-id="5b05a-116">또한 이 인터페이스를 구현하는 클래스에 대해 암시적 변환을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-116">It also shows how you can use implicit conversion for classes that implement this interface.</span></span>  
  
 [!code-csharp[csVarianceKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="5b05a-117">예제</span><span class="sxs-lookup"><span data-stu-id="5b05a-117">Example</span></span>  
 <span data-ttu-id="5b05a-118">다음 예제에서는 반공변(contravariant) 제네릭 대리자를 선언, 인스턴스화 및 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-118">The following example shows how to declare, instantiate, and invoke a contravariant generic delegate.</span></span> <span data-ttu-id="5b05a-119">또한 대리자 형식을 암시적으로 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b05a-119">It also shows how you can implicitly convert a delegate type.</span></span>  
  
 [!code-csharp[csVarianceKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/in-generic-modifier_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5b05a-120">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5b05a-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b05a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b05a-121">See Also</span></span>  
 [<span data-ttu-id="5b05a-122">out</span><span class="sxs-lookup"><span data-stu-id="5b05a-122">out</span></span>](../../../csharp/language-reference/keywords/out-generic-modifier.md)  
 [<span data-ttu-id="5b05a-123">공 분산 및 반공 분산</span><span class="sxs-lookup"><span data-stu-id="5b05a-123">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="5b05a-124">한정자</span><span class="sxs-lookup"><span data-stu-id="5b05a-124">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
