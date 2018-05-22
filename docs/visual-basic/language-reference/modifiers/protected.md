---
title: Protected(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 5f279ed0a33840bb1f2321c17a1ffba412837c07
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="protected-visual-basic"></a><span data-ttu-id="e1be0-102">Protected(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1be0-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="e1be0-103">하나 이상의 선언 된 프로그래밍 요소를 지정 하는 멤버 액세스 한정자는 자체 클래스 내부나 파생 클래스에서 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1be0-104">설명</span><span class="sxs-lookup"><span data-stu-id="e1be0-104">Remarks</span></span>  
 <span data-ttu-id="e1be0-105">클래스에서 선언 된 프로그래밍 요소 중요 한 데이터 나 제한 된 코드를 포함 하는 경우에 따라 및 요소에 대 한 액세스를 제한 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="e1be0-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="e1be0-106">그러나 클래스는 상속 될 수 없습니다 파생된 클래스의 계층 구조를 예상 하는 경우 데이터 나 코드에 액세스 하려면 해당 파생된 클래스에 대 한 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="e1be0-107">이 경우 요소는 기본 클래스에서 및 모든 파생된 클래스에서 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="e1be0-108">이런이 방식으로 요소에 대 한 액세스를 제한 하려면 사용 하 여 선언할 수 있습니다 `Protected`합니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  

> [!NOTE]
> <span data-ttu-id="e1be0-109">`Protected` 액세스 한정자는 다른 두 한정자와 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
> - <span data-ttu-id="e1be0-110">[Protected Friend](protected-friend.md) 한정자를 사용 하면 클래스 멤버는 해당 클래스, 파생 된 클래스에서 및 클래스 정의 되어 있는 동일한 어셈블리 내에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> 
> - <span data-ttu-id="e1be0-111">[개인 보호](private-protected.md) 한정자는 클래스 멤버에 액세스할 수 있게 포함 하는 어셈블리가 내의 파생 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>
  
## <a name="rules"></a><span data-ttu-id="e1be0-112">규칙</span><span class="sxs-lookup"><span data-stu-id="e1be0-112">Rules</span></span>  
  
-   <span data-ttu-id="e1be0-113">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="e1be0-113">**Declaration Context.**</span></span> <span data-ttu-id="e1be0-114">사용할 수 있습니다 `Protected` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="e1be0-115">즉, 선언 컨텍스트는 `Protected` 요소는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  

## <a name="behavior"></a><span data-ttu-id="e1be0-116">동작</span><span class="sxs-lookup"><span data-stu-id="e1be0-116">Behavior</span></span>  
  
-   <span data-ttu-id="e1be0-117">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="e1be0-117">**Access Level.**</span></span> <span data-ttu-id="e1be0-118">클래스의 모든 코드를 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-118">All code in a class can access its elements.</span></span> <span data-ttu-id="e1be0-119">모든 기본 클래스에서 파생 된 모든 클래스의 코드에 액세스할 수는 `Protected` 기본 클래스의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="e1be0-120">이 파생의 모든 세대에 대해 true입니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="e1be0-121">즉, 클래스에 액세스할 수 있도록 `Protected` 기본 클래스 및 등의 기본 클래스의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="e1be0-122">보호 된 액세스는 상위 또는 하위 집합의 friend 액세스 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-122">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="e1be0-123">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="e1be0-123">**Access Modifiers.**</span></span> <span data-ttu-id="e1be0-124">액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="e1be0-125">액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="e1be0-126">`Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1be0-126">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e1be0-127">Class 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="e1be0-128">Const 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="e1be0-129">Declare 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="e1be0-130">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="e1be0-131">Dim 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="e1be0-132">Enum 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="e1be0-133">Event 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="e1be0-134">Function 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e1be0-135">Interface 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="e1be0-136">Property 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e1be0-137">Structure 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="e1be0-138">Sub 문</span><span class="sxs-lookup"><span data-stu-id="e1be0-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e1be0-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1be0-139">See Also</span></span>  
 [<span data-ttu-id="e1be0-140">공용</span><span class="sxs-lookup"><span data-stu-id="e1be0-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="e1be0-141">Friend</span><span class="sxs-lookup"><span data-stu-id="e1be0-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="e1be0-142">전용</span><span class="sxs-lookup"><span data-stu-id="e1be0-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 <span data-ttu-id="e1be0-143">[보호 된 개인](private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="e1be0-143">[Private Protected](private-protected.md) </span></span>  
 <span data-ttu-id="e1be0-144">[Protected Friend](protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="e1be0-144">[Protected Friend](protected-friend.md) </span></span>  
 [<span data-ttu-id="e1be0-145">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="e1be0-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="e1be0-146">절차</span><span class="sxs-lookup"><span data-stu-id="e1be0-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="e1be0-147">구조체</span><span class="sxs-lookup"><span data-stu-id="e1be0-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="e1be0-148">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="e1be0-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
