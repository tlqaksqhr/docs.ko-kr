---
title: Private(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a><span data-ttu-id="a6026-102">Private(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6026-102">Private (Visual Basic)</span></span>
<span data-ttu-id="a6026-103">하나 이상의 선언 된 프로그래밍 요소를에서 포함 된 모든 형식을 포함 하 여 해당 변수의 선언 컨텍스트 내 에서만 액세스할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6026-104">설명</span><span class="sxs-lookup"><span data-stu-id="a6026-104">Remarks</span></span>  
 <span data-ttu-id="a6026-105">프로그래밍 요소 소유권이 있는 기능 또는 기밀 데이터가 포함 된 경우에 일반적으로 최대한 엄격 하 게 액세스를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="a6026-106">모듈, 클래스 또는 구조체 정의에 액세스 하는 허용 하 여 최대 한계를 달성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="a6026-107">이러한 방식으로 요소에 대 한 액세스를 제한 하려면 사용 하 여 선언할 수 있습니다 `Private`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a6026-108">규칙</span><span class="sxs-lookup"><span data-stu-id="a6026-108">Rules</span></span>  
  
-   <span data-ttu-id="a6026-109">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="a6026-109">**Declaration Context.**</span></span> <span data-ttu-id="a6026-110">`Private`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-110">You can use `Private` only at module level.</span></span> <span data-ttu-id="a6026-111">즉, 선언 컨텍스트는 `Private` 요소 모듈, 클래스 또는 구조 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-111">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a6026-112">동작</span><span class="sxs-lookup"><span data-stu-id="a6026-112">Behavior</span></span>  
  
-   <span data-ttu-id="a6026-113">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="a6026-113">**Access Level.**</span></span> <span data-ttu-id="a6026-114">선언 컨텍스트 내에서 모든 코드가 액세스할 수 있는 해당 `Private` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-114">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="a6026-115">이 코드는 중첩 된 클래스 또는 열거형에 대입 식을 같은 포함 된 형식에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-115">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="a6026-116">선언 컨텍스트 외부에서 코드에 액세스할 수는 `Private` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-116">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="a6026-117">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="a6026-117">**Access Modifiers.**</span></span> <span data-ttu-id="a6026-118">액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-118">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="a6026-119">액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-119">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="a6026-120">`Private` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6026-120">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a6026-121">Class 문</span><span class="sxs-lookup"><span data-stu-id="a6026-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="a6026-122">Const 문</span><span class="sxs-lookup"><span data-stu-id="a6026-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="a6026-123">Declare 문</span><span class="sxs-lookup"><span data-stu-id="a6026-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="a6026-124">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="a6026-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="a6026-125">Dim 문</span><span class="sxs-lookup"><span data-stu-id="a6026-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="a6026-126">Enum 문</span><span class="sxs-lookup"><span data-stu-id="a6026-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="a6026-127">Event 문</span><span class="sxs-lookup"><span data-stu-id="a6026-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="a6026-128">Function 문</span><span class="sxs-lookup"><span data-stu-id="a6026-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a6026-129">Interface 문</span><span class="sxs-lookup"><span data-stu-id="a6026-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="a6026-130">Property 문</span><span class="sxs-lookup"><span data-stu-id="a6026-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a6026-131">Structure 문</span><span class="sxs-lookup"><span data-stu-id="a6026-131">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="a6026-132">Sub 문</span><span class="sxs-lookup"><span data-stu-id="a6026-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6026-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6026-133">See Also</span></span>  
 [<span data-ttu-id="a6026-134">공용</span><span class="sxs-lookup"><span data-stu-id="a6026-134">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="a6026-135">보호됨</span><span class="sxs-lookup"><span data-stu-id="a6026-135">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="a6026-136">Friend</span><span class="sxs-lookup"><span data-stu-id="a6026-136">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="a6026-137">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="a6026-137">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="a6026-138">절차</span><span class="sxs-lookup"><span data-stu-id="a6026-138">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="a6026-139">구조체</span><span class="sxs-lookup"><span data-stu-id="a6026-139">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="a6026-140">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="a6026-140">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
