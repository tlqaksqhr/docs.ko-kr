---
title: NotOverridable(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6fc5fb006b36cda1b6ad0e128604bc3bb427fd94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="f57db-102">NotOverridable(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f57db-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="f57db-103">파생된 클래스에서 속성 또는 프로시저를 재정의할 수 없음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f57db-104">설명</span><span class="sxs-lookup"><span data-stu-id="f57db-104">Remarks</span></span>  
 <span data-ttu-id="f57db-105">`NotOverridable` 파생된 클래스에서 재정의 되는 속성 또는 메서드를 방지 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="f57db-106">[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) 파생된 클래스에서 재정의 되도록 클래스에서 속성 또는 메서드를 허용 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="f57db-107">자세한 내용은 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f57db-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="f57db-108">경우는 `Overridable` 또는 `NotOverridable` 한정자를 지정 하지 않으면, 기본 설정 속성 또는 메서드의 기본 클래스 속성 또는 메서드의 재정의 하는 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="f57db-109">속성 또는 메서드는 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable`, 그렇지 않으면는 `NotOverridable`합니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="f57db-110">재정의할 수 없는 요소 라고도 *봉인* 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="f57db-111">속성 또는 프로시저 선언문에서만 `NotOverridable`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="f57db-112">지정할 수 있습니다 `NotOverridable` 속성이 나 다른 속성 또는 프로시저와 함께만에서 즉, 재정의 하는 프로시저에 대해서만 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="f57db-113">결합 된 한정자</span><span class="sxs-lookup"><span data-stu-id="f57db-113">Combined Modifiers</span></span>  
 <span data-ttu-id="f57db-114">지정할 수 없으며 `Overridable` 또는 `NotOverridable` 에 대 한 한 `Private` 메서드.</span><span class="sxs-lookup"><span data-stu-id="f57db-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="f57db-115">지정할 수 없습니다 `NotOverridable` 와 함께 `MustOverride`, `Overridable`, 또는 `Shared` 같은 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f57db-116">용도</span><span class="sxs-lookup"><span data-stu-id="f57db-116">Usage</span></span>  
 <span data-ttu-id="f57db-117">`NotOverridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f57db-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f57db-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="f57db-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="f57db-119">Property 문</span><span class="sxs-lookup"><span data-stu-id="f57db-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="f57db-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="f57db-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f57db-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f57db-121">See Also</span></span>  
 [<span data-ttu-id="f57db-122">한정자</span><span class="sxs-lookup"><span data-stu-id="f57db-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="f57db-123">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="f57db-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="f57db-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f57db-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="f57db-125">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="f57db-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="f57db-126">재정의</span><span class="sxs-lookup"><span data-stu-id="f57db-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="f57db-127">키워드</span><span class="sxs-lookup"><span data-stu-id="f57db-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="f57db-128">Visual Basic의 숨김 기능</span><span class="sxs-lookup"><span data-stu-id="f57db-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
