---
title: Friend(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 32f993e4b9bcd126ebb6d70310fc0781e8b137b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="friend-visual-basic"></a><span data-ttu-id="0af9f-102">Friend(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0af9f-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="0af9f-103">하나 이상의 선언 된 프로그래밍 요소를 해당 하는 어셈블리 내 에서만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0af9f-104">설명</span><span class="sxs-lookup"><span data-stu-id="0af9f-104">Remarks</span></span>  
 <span data-ttu-id="0af9f-105">대부분의 경우에서 클래스 및 구조체를 선언 하는 구성 요소에서 뿐만 아니라 전체 어셈블리에서 사용할 수 등의 요소를 프로그래밍 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="0af9f-106">그러나 있습니다 하지 하도록 할 수 (예를 들어 응용 프로그램이 경우 소유) 어셈블리 외부의 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="0af9f-107">이러한 방식으로 요소에 대 한 액세스를 제한 하려는 경우 사용 하 여 선언할 수 있습니다는 `Friend` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="0af9f-108">다른 클래스, 구조체 및 동일 하 게 컴파일된 모듈의 코드를 모든 어셈블리에 액세스할 수는 `Friend` 해당 어셈블리의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="0af9f-109">`Friend`액세스는 종종 응용 프로그램의 프로그래밍 요소에 대 한 기본 수준 및 `Friend` 는 기본 액세스 인터페이스, 모듈, 클래스 또는 구조체의 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="0af9f-110">사용할 수 있습니다 `Friend` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만.</span><span class="sxs-lookup"><span data-stu-id="0af9f-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="0af9f-111">따라서 선언 컨텍스트는 `Friend` 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 요소가 있어야 하며 프로시저 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  
  
 <span data-ttu-id="0af9f-112">사용할 수 있습니다는 `Friend` 와 함께에서 한정자는 [Protected](../../../visual-basic/language-reference/modifiers/protected.md) 같은 선언에는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-112">You can use the `Friend` modifier in conjunction with the [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modifier in the same declaration.</span></span> <span data-ttu-id="0af9f-113">한정자를이 함께 제공 둘 다 `Friend` 액세스 및 자체 클래스에서 및 파생된 클래스에서 동일한 어셈블리의 모든 위치에서 액세스할 수 있도록 선언된 된 요소에 대 한 액세스를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-113">This combination confers both `Friend` access and protected access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="0af9f-114">지정할 수 있습니다 `Protected Friend` 클래스의 멤버에 대해서만 합니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-114">You can specify `Protected Friend` only on members of classes.</span></span>  
  
 <span data-ttu-id="0af9f-115">에 대 한 비교 `Friend` 오류 코드 및 기타 참조, 액세스 한정자 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0af9f-116">Friend 어셈블리 모든 형식과로 표시 된 멤버에 액세스할 수 있는 다른 어셈블리 인지를 지정할 수 있습니다 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="0af9f-117">자세한 내용은 [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)(Friend 어셈블리)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0af9f-117">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0af9f-118">예제</span><span class="sxs-lookup"><span data-stu-id="0af9f-118">Example</span></span>  
 <span data-ttu-id="0af9f-119">다음 클래스에서 사용 하는 `Friend` 특정 멤버에 액세스 하는 어셈블리 내 다른 프로그래밍 요소를 허용 하는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="0af9f-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="0af9f-120">용도</span><span class="sxs-lookup"><span data-stu-id="0af9f-120">Usage</span></span>  
 <span data-ttu-id="0af9f-121">사용할 수는 `Friend` 다음 컨텍스트에서 한정자:</span><span class="sxs-lookup"><span data-stu-id="0af9f-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="0af9f-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="0af9f-123">Const 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="0af9f-124">Declare 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="0af9f-125">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="0af9f-126">Dim 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="0af9f-127">Enum 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="0af9f-128">Event 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="0af9f-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0af9f-130">Interface 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="0af9f-131">Module 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="0af9f-132">Property 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-132">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="0af9f-133">Structure 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-133">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="0af9f-134">Sub 문</span><span class="sxs-lookup"><span data-stu-id="0af9f-134">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0af9f-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0af9f-135">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="0af9f-136">공용</span><span class="sxs-lookup"><span data-stu-id="0af9f-136">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="0af9f-137">보호됨</span><span class="sxs-lookup"><span data-stu-id="0af9f-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="0af9f-138">전용</span><span class="sxs-lookup"><span data-stu-id="0af9f-138">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="0af9f-139">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="0af9f-139">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="0af9f-140">절차</span><span class="sxs-lookup"><span data-stu-id="0af9f-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="0af9f-141">구조체</span><span class="sxs-lookup"><span data-stu-id="0af9f-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="0af9f-142">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="0af9f-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
