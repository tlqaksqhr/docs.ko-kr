---
title: Protected(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a><span data-ttu-id="dd99d-102">Protected(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd99d-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="dd99d-103">하나 이상의 선언 된 프로그래밍 요소는 자체 클래스 내부나 파생 클래스에서 에서만 액세스할 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-103">Specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd99d-104">설명</span><span class="sxs-lookup"><span data-stu-id="dd99d-104">Remarks</span></span>  
 <span data-ttu-id="dd99d-105">클래스에서 선언 된 프로그래밍 요소 중요 한 데이터 나 제한 된 코드를 포함 하는 경우에 따라 및 요소에 대 한 액세스를 제한 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="dd99d-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="dd99d-106">그러나 클래스는 상속 될 수 없습니다 파생된 클래스의 계층 구조를 예상 하는 경우 데이터 나 코드에 액세스 하려면 해당 파생된 클래스에 대 한 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="dd99d-107">이 경우 요소는 기본 클래스에서 및 모든 파생된 클래스에서 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="dd99d-108">이런이 방식으로 요소에 대 한 액세스를 제한 하려면 사용 하 여 선언할 수 있습니다 `Protected`합니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="dd99d-109">규칙</span><span class="sxs-lookup"><span data-stu-id="dd99d-109">Rules</span></span>  
  
-   <span data-ttu-id="dd99d-110">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="dd99d-110">**Declaration Context.**</span></span> <span data-ttu-id="dd99d-111">사용할 수 있습니다 `Protected` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-111">You can use `Protected` only at class level.</span></span> <span data-ttu-id="dd99d-112">즉, 선언 컨텍스트는 `Protected` 요소는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-112">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
-   <span data-ttu-id="dd99d-113">**결합 된 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="dd99d-113">**Combined Modifiers.**</span></span> <span data-ttu-id="dd99d-114">사용할 수 있습니다는 `Protected` 와 함께 한정자는 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 같은 선언에는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-114">You can use the `Protected` modifier together with the [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modifier in the same declaration.</span></span> <span data-ttu-id="dd99d-115">이렇게 하면 선언 된 요소 자체 클래스에서 및 파생된 클래스에서 동일한 어셈블리의 모든 위치에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-115">This combination makes the declared elements accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="dd99d-116">지정할 수 있습니다 `Protected Friend` 클래스의 멤버에 대해서만 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-116">You can specify `Protected Friend` only on members of classes.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="dd99d-117">동작</span><span class="sxs-lookup"><span data-stu-id="dd99d-117">Behavior</span></span>  
  
-   <span data-ttu-id="dd99d-118">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="dd99d-118">**Access Level.**</span></span> <span data-ttu-id="dd99d-119">클래스의 모든 코드를 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-119">All code in a class can access its elements.</span></span> <span data-ttu-id="dd99d-120">모든 기본 클래스에서 파생 된 모든 클래스의 코드에 액세스할 수는 `Protected` 기본 클래스의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="dd99d-121">이 파생의 모든 세대에 대해 true입니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="dd99d-122">즉, 클래스에 액세스할 수 있도록 `Protected` 기본 클래스 및 등의 기본 클래스의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="dd99d-123">보호 된 액세스는 상위 또는 하위 집합의 friend 액세스 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-123">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="dd99d-124">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="dd99d-124">**Access Modifiers.**</span></span> <span data-ttu-id="dd99d-125">액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="dd99d-126">액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="dd99d-127">`Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd99d-127">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="dd99d-128">Class 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="dd99d-129">Const 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="dd99d-130">Declare 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="dd99d-131">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="dd99d-132">Dim 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="dd99d-133">Enum 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="dd99d-134">Event 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="dd99d-135">Function 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="dd99d-136">Interface 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="dd99d-137">Property 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="dd99d-138">Structure 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="dd99d-139">Sub 문</span><span class="sxs-lookup"><span data-stu-id="dd99d-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd99d-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd99d-140">See Also</span></span>  
 [<span data-ttu-id="dd99d-141">공용</span><span class="sxs-lookup"><span data-stu-id="dd99d-141">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="dd99d-142">Friend</span><span class="sxs-lookup"><span data-stu-id="dd99d-142">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="dd99d-143">전용</span><span class="sxs-lookup"><span data-stu-id="dd99d-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="dd99d-144">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="dd99d-144">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="dd99d-145">절차</span><span class="sxs-lookup"><span data-stu-id="dd99d-145">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="dd99d-146">구조체</span><span class="sxs-lookup"><span data-stu-id="dd99d-146">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="dd99d-147">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="dd99d-147">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
