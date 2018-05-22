---
title: Private(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 40b64b8d2b6306d458b7a9cc657c5b7dc4270eb2
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="private-visual-basic"></a><span data-ttu-id="77567-102">Private(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77567-102">Private (Visual Basic)</span></span>
<span data-ttu-id="77567-103">하나 이상의 선언 된 프로그래밍 요소를에서 포함 된 모든 형식을 포함 하 여 해당 변수의 선언 컨텍스트 내 에서만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77567-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77567-104">설명</span><span class="sxs-lookup"><span data-stu-id="77567-104">Remarks</span></span>  
 <span data-ttu-id="77567-105">프로그래밍 요소 소유권이 있는 기능 또는 기밀 데이터가 포함 된 경우에 일반적으로 최대한 엄격 하 게 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="77567-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="77567-106">모듈, 클래스 또는 구조체 정의에 액세스 하는 허용 하 여 최대 한계를 달성 합니다.</span><span class="sxs-lookup"><span data-stu-id="77567-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="77567-107">이러한 방식으로 요소에 대 한 액세스를 제한 하려면 사용 하 여 선언할 수 있습니다 `Private`합니다.</span><span class="sxs-lookup"><span data-stu-id="77567-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="77567-108">사용할 수도 있습니다는 [개인 보호](private-protected.md) 액세스 한정자는 멤버를 포함 하는 어셈블리가에 있는 파생 된 클래스 및 해당 클래스 내에서 액세스할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77567-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="77567-109">규칙</span><span class="sxs-lookup"><span data-stu-id="77567-109">Rules</span></span>  

-   <span data-ttu-id="77567-110">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="77567-110">**Declaration Context.**</span></span> <span data-ttu-id="77567-111">`Private`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77567-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="77567-112">즉, 선언 컨텍스트는 `Private` 요소 모듈, 클래스 또는 구조 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77567-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="77567-113">동작</span><span class="sxs-lookup"><span data-stu-id="77567-113">Behavior</span></span>  
  
-   <span data-ttu-id="77567-114">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="77567-114">**Access Level.**</span></span> <span data-ttu-id="77567-115">선언 컨텍스트 내에서 모든 코드가 액세스할 수 있는 해당 `Private` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77567-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="77567-116">이 코드는 중첩 된 클래스 또는 열거형에 대입 식을 같은 포함 된 형식에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77567-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="77567-117">선언 컨텍스트 외부에서 코드에 액세스할 수는 `Private` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77567-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="77567-118">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="77567-118">**Access Modifiers.**</span></span> <span data-ttu-id="77567-119">액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="77567-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="77567-120">액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="77567-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="77567-121">`Private` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77567-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="77567-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="77567-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="77567-123">Const 문</span><span class="sxs-lookup"><span data-stu-id="77567-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="77567-124">Declare 문</span><span class="sxs-lookup"><span data-stu-id="77567-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="77567-125">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="77567-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="77567-126">Dim 문</span><span class="sxs-lookup"><span data-stu-id="77567-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="77567-127">Enum 문</span><span class="sxs-lookup"><span data-stu-id="77567-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="77567-128">Event 문</span><span class="sxs-lookup"><span data-stu-id="77567-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="77567-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="77567-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="77567-130">Interface 문</span><span class="sxs-lookup"><span data-stu-id="77567-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="77567-131">Property 문</span><span class="sxs-lookup"><span data-stu-id="77567-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="77567-132">Structure 문</span><span class="sxs-lookup"><span data-stu-id="77567-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="77567-133">Sub 문</span><span class="sxs-lookup"><span data-stu-id="77567-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="77567-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77567-134">See Also</span></span>  
 [<span data-ttu-id="77567-135">공용</span><span class="sxs-lookup"><span data-stu-id="77567-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="77567-136">보호됨</span><span class="sxs-lookup"><span data-stu-id="77567-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="77567-137">Friend</span><span class="sxs-lookup"><span data-stu-id="77567-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 <span data-ttu-id="77567-138">[보호 된 개인](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="77567-138">[Private Protected](./private-protected.md) </span></span>  
 <span data-ttu-id="77567-139">[Protected Friend](./protected-friend.md)[액세스 수준을 Visual basic    ](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="77567-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>  
 [<span data-ttu-id="77567-140">절차</span><span class="sxs-lookup"><span data-stu-id="77567-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="77567-141">구조체</span><span class="sxs-lookup"><span data-stu-id="77567-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="77567-142">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="77567-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
