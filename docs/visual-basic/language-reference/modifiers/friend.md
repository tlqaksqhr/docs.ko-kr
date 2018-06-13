---
title: Friend(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: d906fc8ada19f22059da44acbd76dd07dacd4801
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234591"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="428c1-102">Friend(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="428c1-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="428c1-103">하나 이상의 선언 된 프로그래밍 요소를 해당 하는 어셈블리 내 에서만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="428c1-104">설명</span><span class="sxs-lookup"><span data-stu-id="428c1-104">Remarks</span></span>  
 <span data-ttu-id="428c1-105">대부분의 경우에서 클래스 및 구조체를 선언 하는 구성 요소에서 뿐만 아니라 전체 어셈블리에서 사용할 수 등의 요소를 프로그래밍 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="428c1-106">그러나 있습니다 하지 하도록 할 수 (예를 들어 응용 프로그램이 경우 소유) 어셈블리 외부의 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="428c1-107">이러한 방식으로 요소에 대 한 액세스를 제한 하려는 경우 사용 하 여 선언할 수 있습니다는 `Friend` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="428c1-108">다른 클래스, 구조체 및 동일 하 게 컴파일된 모듈의 코드를 모든 어셈블리에 액세스할 수는 `Friend` 해당 어셈블리의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="428c1-109">`Friend` 액세스는 종종 응용 프로그램의 프로그래밍 요소에 대 한 기본 수준 및 `Friend` 는 기본 액세스 인터페이스, 모듈, 클래스 또는 구조체의 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="428c1-110">사용할 수 있습니다 `Friend` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만.</span><span class="sxs-lookup"><span data-stu-id="428c1-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="428c1-111">따라서 선언 컨텍스트는 `Friend` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 요소가 있어야 하며 프로시저 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="428c1-112">사용할 수도 있습니다는 [Protected Friend](protected-friend.md) 액세스 한정자를 클래스 멤버를 해당 클래스, 파생 된 클래스에서 및 클래스 정의 되어 있는 동일한 어셈블리 내에서 액세스할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="428c1-113">사용 하 게 동일한 어셈블리의 파생된 클래스에서 해당 클래스 내에서 멤버에 대 한 액세스를 제한 하는 [개인 보호](private-protected.md) 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="428c1-114">에 대 한 비교 `Friend` 오류 코드 및 기타 참조, 액세스 한정자 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="428c1-115">Friend 어셈블리 모든 형식과로 표시 된 멤버에 액세스할 수 있는 다른 어셈블리 인지를 지정할 수 있습니다 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="428c1-116">자세한 내용은 [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)(Friend 어셈블리)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="428c1-116">For more information, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="428c1-117">예제</span><span class="sxs-lookup"><span data-stu-id="428c1-117">Example</span></span>  
 <span data-ttu-id="428c1-118">다음 클래스에서 사용 하는 `Friend` 특정 멤버에 액세스 하는 어셈블리 내 다른 프로그래밍 요소를 허용 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="428c1-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="428c1-119">사용법</span><span class="sxs-lookup"><span data-stu-id="428c1-119">Usage</span></span>  
 <span data-ttu-id="428c1-120">사용할 수는 `Friend` 다음 컨텍스트에서 한정자:</span><span class="sxs-lookup"><span data-stu-id="428c1-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="428c1-121">Class 문</span><span class="sxs-lookup"><span data-stu-id="428c1-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="428c1-122">Const 문</span><span class="sxs-lookup"><span data-stu-id="428c1-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="428c1-123">Declare 문</span><span class="sxs-lookup"><span data-stu-id="428c1-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="428c1-124">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="428c1-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="428c1-125">Dim 문</span><span class="sxs-lookup"><span data-stu-id="428c1-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="428c1-126">Enum 문</span><span class="sxs-lookup"><span data-stu-id="428c1-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="428c1-127">Event 문</span><span class="sxs-lookup"><span data-stu-id="428c1-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="428c1-128">Function 문</span><span class="sxs-lookup"><span data-stu-id="428c1-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="428c1-129">Interface 문</span><span class="sxs-lookup"><span data-stu-id="428c1-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="428c1-130">Module 문</span><span class="sxs-lookup"><span data-stu-id="428c1-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="428c1-131">Property 문</span><span class="sxs-lookup"><span data-stu-id="428c1-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="428c1-132">Structure 문</span><span class="sxs-lookup"><span data-stu-id="428c1-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="428c1-133">Sub 문</span><span class="sxs-lookup"><span data-stu-id="428c1-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="428c1-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="428c1-134">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="428c1-135">공용</span><span class="sxs-lookup"><span data-stu-id="428c1-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="428c1-136">보호됨</span><span class="sxs-lookup"><span data-stu-id="428c1-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="428c1-137">전용</span><span class="sxs-lookup"><span data-stu-id="428c1-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 <span data-ttu-id="428c1-138">[보호 된 개인](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="428c1-138">[Private Protected](./private-protected.md) </span></span>  
 <span data-ttu-id="428c1-139">[Protected Friend](./protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="428c1-139">[Protected Friend](./protected-friend.md) </span></span>  
 [<span data-ttu-id="428c1-140">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="428c1-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="428c1-141">절차</span><span class="sxs-lookup"><span data-stu-id="428c1-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="428c1-142">구조체</span><span class="sxs-lookup"><span data-stu-id="428c1-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="428c1-143">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="428c1-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
