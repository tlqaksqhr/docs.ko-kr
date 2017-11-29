---
title: Public(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6cd70adf6ec31c56f39d0443d320dd1b00b00d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="public-visual-basic"></a><span data-ttu-id="49a2e-102">Public(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49a2e-102">Public (Visual Basic)</span></span>
<span data-ttu-id="49a2e-103">선언 된 프로그래밍 요소를 하나 이상의 액세스 제한이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49a2e-104">설명</span><span class="sxs-lookup"><span data-stu-id="49a2e-104">Remarks</span></span>  
 <span data-ttu-id="49a2e-105">구성 요소 또는 클래스 라이브러리와 같은 구성 요소 집합을 게시 하는 경우 일반적으로 프로그래밍 요소 어셈블리와 상호 작용 하는 모든 코드에서 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="49a2e-106">없이 요소에 대해 무제한 액세스를 하려면 사용 하 여 선언할 수 있습니다 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="49a2e-107">공용 액세스는 일반 프로그래밍 요소에 대 한 경우이에 대 한 액세스를 제한할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="49a2e-108">인터페이스, 모듈, 클래스 또는 구조체 내에 선언 된 액세스 수준 요소에는 기본적으로 `Public` 따로 선언 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="49a2e-109">규칙</span><span class="sxs-lookup"><span data-stu-id="49a2e-109">Rules</span></span>  
  
-   <span data-ttu-id="49a2e-110">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="49a2e-110">**Declaration Context.**</span></span> <span data-ttu-id="49a2e-111">사용할 수 있습니다 `Public` 모듈, 인터페이스 또는 네임 스페이스 수준 에서만.</span><span class="sxs-lookup"><span data-stu-id="49a2e-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="49a2e-112">즉, 선언 컨텍스트는 `Public` 요소 소스 파일, 네임 스페이스, 인터페이스, 모듈, 클래스 또는 구조체 이어야 하며 프로시저일 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="49a2e-113">동작</span><span class="sxs-lookup"><span data-stu-id="49a2e-113">Behavior</span></span>  
  
-   <span data-ttu-id="49a2e-114">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="49a2e-114">**Access Level.**</span></span> <span data-ttu-id="49a2e-115">모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드가 액세스할 수 있는 해당 `Public` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="49a2e-116">**기본 액세스 합니다.**</span><span class="sxs-lookup"><span data-stu-id="49a2e-116">**Default Access.**</span></span> <span data-ttu-id="49a2e-117">공용 액세스를 프로시저 기본값 내의 지역 변수는에 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="49a2e-118">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="49a2e-118">**Access Modifiers.**</span></span> <span data-ttu-id="49a2e-119">액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="49a2e-120">액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="49a2e-121">`Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="49a2e-122">Class 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="49a2e-123">Const 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="49a2e-124">Declare 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="49a2e-125">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="49a2e-126">Dim 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="49a2e-127">Enum 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="49a2e-128">Event 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="49a2e-129">Function 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="49a2e-130">Interface 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="49a2e-131">Module 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="49a2e-132">Operator 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="49a2e-133">Property 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="49a2e-134">Structure 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="49a2e-135">Sub 문</span><span class="sxs-lookup"><span data-stu-id="49a2e-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="49a2e-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49a2e-136">See Also</span></span>  
 [<span data-ttu-id="49a2e-137">보호됨</span><span class="sxs-lookup"><span data-stu-id="49a2e-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="49a2e-138">Friend</span><span class="sxs-lookup"><span data-stu-id="49a2e-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="49a2e-139">전용</span><span class="sxs-lookup"><span data-stu-id="49a2e-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="49a2e-140">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="49a2e-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="49a2e-141">절차</span><span class="sxs-lookup"><span data-stu-id="49a2e-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="49a2e-142">구조체</span><span class="sxs-lookup"><span data-stu-id="49a2e-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="49a2e-143">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="49a2e-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
