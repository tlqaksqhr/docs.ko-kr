---
title: MustInherit(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 5d622c1cff77a45c8de7772af7efbb73586f4400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602842"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="1227e-102">MustInherit(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1227e-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="1227e-103">클래스를 기본 클래스로 사용할 수 있는지와에서 직접 개체를 만들 수 없음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1227e-104">설명</span><span class="sxs-lookup"><span data-stu-id="1227e-104">Remarks</span></span>  
 <span data-ttu-id="1227e-105">용도 *기본 클래스* (라고도 *추상 클래스*)에서 파생 된 모든 클래스에 공통적인 기능을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="1227e-106">파생된 클래스는 공통 요소를 재정의 하지 않아도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="1227e-107">경우에 따라이 일반적인 기능은 사용할 수 있는 개체를 만들 수 있을 만큼 완벽 하 고 각 파생된 클래스 누락 된 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="1227e-108">이 경우 개체를 만들 파생된 클래스 에서만에서 사용 하는 코드를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="1227e-109">사용 하면 `MustInherit` 이 값을 적용 하기 위해 기본 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="1227e-110">또 다른 용도 `MustInherit` 클래스는 관련된 클래스 집합에 변수를 제한 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="1227e-111">기본 클래스를 정의 하 고 이러한 모든 관련된 클래스에서 파생 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="1227e-112">기본 클래스는 모든 파생된 클래스에 공통 된 기능을 제공 하지 않아도 되지만 변수에 값을 할당에 대 한 필터 역할도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="1227e-113">기본 클래스로 변수를 선언 하는 사용 하는 코드를 하는 경우 Visual Basic를 사용 하면 파생된 클래스 중 하나에서 해당 변수는 개체에만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="1227e-114">여러.NET Framework 정의 `MustInherit` 클래스, 그중에서 <xref:System.Array>, <xref:System.Enum>, 및 <xref:System.ValueType>합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="1227e-115"><xref:System.ValueType> 변수를 제한 하는 기본 클래스의 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="1227e-116">모든 값 형식에서 파생 <xref:System.ValueType>합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="1227e-117">변수를 선언 하는 경우 <xref:System.ValueType>, 값 형식에만 변수에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1227e-118">규칙</span><span class="sxs-lookup"><span data-stu-id="1227e-118">Rules</span></span>  
  
-   <span data-ttu-id="1227e-119">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="1227e-119">**Declaration Context.**</span></span> <span data-ttu-id="1227e-120">사용할 수 있습니다 `MustInherit` 에서만 `Class` 문.</span><span class="sxs-lookup"><span data-stu-id="1227e-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
-   <span data-ttu-id="1227e-121">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="1227e-121">**Combined Modifiers.**</span></span> <span data-ttu-id="1227e-122">지정할 수 없으며 `MustInherit` 와 함께 `NotInheritable` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1227e-123">예제</span><span class="sxs-lookup"><span data-stu-id="1227e-123">Example</span></span>  
 <span data-ttu-id="1227e-124">다음 예제에는 강제 상속 및 강제 재정의 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="1227e-125">기본 클래스 `shape` 변수를 정의 `acrossLine`합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="1227e-126">클래스 `circle` 및 `square` 에서 파생 `shape`합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="1227e-127">정의 상속 `acrossLine`, 함수를 정의 해야 하지만 `area` 계산 셰이프의 각 종류에 대 한 다르기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 <span data-ttu-id="1227e-128">선언할 수 `shape1` 및 `shape2` 형식이 되도록 `shape`합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="1227e-129">그러나 개체를 만들 수 없습니다 `shape` 함수 기능이 없기 때문에 `area` 이며로 표시 되어 `MustInherit`합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="1227e-130">로 선언 되기 때문에 `shape`, 변수 `shape1` 및 `shape2` 파생된 클래스에서 개체에 제한 되어 `circle` 및 `square`합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="1227e-131">Visual Basic 없도록 이러한 변수를 다른 개체를 할당할 수는 높은 수준의 형식 안전성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="1227e-132">사용법</span><span class="sxs-lookup"><span data-stu-id="1227e-132">Usage</span></span>  
 <span data-ttu-id="1227e-133">`MustInherit` 한정자는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1227e-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="1227e-134">Class 문</span><span class="sxs-lookup"><span data-stu-id="1227e-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1227e-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1227e-135">See Also</span></span>  
 [<span data-ttu-id="1227e-136">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="1227e-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="1227e-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="1227e-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [<span data-ttu-id="1227e-138">키워드</span><span class="sxs-lookup"><span data-stu-id="1227e-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="1227e-139">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="1227e-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
