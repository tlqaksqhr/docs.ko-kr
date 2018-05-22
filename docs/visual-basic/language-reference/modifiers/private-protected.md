---
title: 개인 보호 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="4642b-102">개인 보호 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4642b-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="4642b-103">`Private Protected` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="4642b-104">A `Private Protected` 멤버는 포함 하는 클래스에서 파생 된 형식에 따라서도 모든 멤버를 포함 하는 클래스에 액세스할 수 있는 경우에 포함 하는 어셈블리가에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span> 

<span data-ttu-id="4642b-105">지정할 수 있습니다 `Private Protected` ; 클래스의 멤버에 대해서만 적용할 수 없습니다 `Private Protected` 구조체의 멤버에 게 되므로 구조체를 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="4642b-106">`Private Protected` 액세스 한정자는 Visual Basic 15.5에서 이상에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="4642b-107">를 사용 하려면 Visual Basic 프로젝트 (\*.vbproj) 파일에 다음 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="4642b-108">Visual Basic 15.5 하기만 이상 시스템에 설치 되어, Visual Basic 컴파일러의 최신 버전에서 지 원하는 모든 언어 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="4642b-109">Visual Studio에서에 F1 도움말을 선택 하면 `private protected` 중 하나에 대 한 도움말을 제공 [개인](private.md) 또는 [보호](protected.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-109">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="4642b-110">IDE의 복합 단어 보다는 커서에서 단일 토큰을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-110">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="4642b-111">규칙</span><span class="sxs-lookup"><span data-stu-id="4642b-111">Rules</span></span>

- <span data-ttu-id="4642b-112">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="4642b-112">**Declaration Context.**</span></span> <span data-ttu-id="4642b-113">사용할 수 있습니다 `Private Protected` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-113">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="4642b-114">즉, 선언 컨텍스트는 `Protected` 요소는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-114">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="4642b-115">동작</span><span class="sxs-lookup"><span data-stu-id="4642b-115">Behavior</span></span>

- <span data-ttu-id="4642b-116">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="4642b-116">**Access Level.**</span></span> <span data-ttu-id="4642b-117">클래스의 모든 코드를 해당 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-117">All code in a class can access its elements.</span></span> <span data-ttu-id="4642b-118">모든 기본 클래스에서 파생 되 고 동일한 어셈블리에 포함 된 모든 클래스의 코드에 액세스할 수는 `Private Protected` 기본 클래스의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-118">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="4642b-119">그러나 기본 클래스에서 파생 되 고 다른 어셈블리에 포함 된 모든 클래스의 코드는 기본 클래스에 액세스할 수 없습니다 `Private Protected` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-119">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="4642b-120">**액세스 한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="4642b-120">**Access Modifiers.**</span></span> <span data-ttu-id="4642b-121">액세스 수준을 지정 하는 키워드 라고 *액세스 한정자*합니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-121">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="4642b-122">액세스 한정자는 비교를 참조 하십시오. [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-122">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>
  
 <span data-ttu-id="4642b-123">`Private Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4642b-123">The `Private Protected` modifier can be used in these contexts:</span></span>  
  
 <span data-ttu-id="4642b-124">[Class 문](../../../visual-basic/language-reference/statements/class-statement.md) 중첩된 클래스의</span><span class="sxs-lookup"><span data-stu-id="4642b-124">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>  
  
 [<span data-ttu-id="4642b-125">Const 문</span><span class="sxs-lookup"><span data-stu-id="4642b-125">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="4642b-126">Declare 문</span><span class="sxs-lookup"><span data-stu-id="4642b-126">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="4642b-127">[Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md) 클래스에서 중첩 대리자</span><span class="sxs-lookup"><span data-stu-id="4642b-127">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>  
  
 [<span data-ttu-id="4642b-128">Dim 문</span><span class="sxs-lookup"><span data-stu-id="4642b-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 <span data-ttu-id="4642b-129">[Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md) 는 eumeration의 클래스에서 중첩</span><span class="sxs-lookup"><span data-stu-id="4642b-129">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an eumeration nested in a class</span></span> 
  
 [<span data-ttu-id="4642b-130">Event 문</span><span class="sxs-lookup"><span data-stu-id="4642b-130">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="4642b-131">Function 문</span><span class="sxs-lookup"><span data-stu-id="4642b-131">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 <span data-ttu-id="4642b-132">[Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md) 클래스에서 중첩 된 인터페이스의</span><span class="sxs-lookup"><span data-stu-id="4642b-132">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span> 
  
 [<span data-ttu-id="4642b-133">Property 문</span><span class="sxs-lookup"><span data-stu-id="4642b-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 <span data-ttu-id="4642b-134">[문을 구조체](../../../visual-basic/language-reference/statements/structure-statement.md) 클래스에서 중첩 된 구조체</span><span class="sxs-lookup"><span data-stu-id="4642b-134">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span> 
  
 [<span data-ttu-id="4642b-135">Sub 문</span><span class="sxs-lookup"><span data-stu-id="4642b-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4642b-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4642b-136">See Also</span></span>

[<span data-ttu-id="4642b-137">공용</span><span class="sxs-lookup"><span data-stu-id="4642b-137">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="4642b-138">보호됨</span><span class="sxs-lookup"><span data-stu-id="4642b-138">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="4642b-139">[Friend](friend.md) </span><span class="sxs-lookup"><span data-stu-id="4642b-139">[Friend](friend.md) </span></span>  
[<span data-ttu-id="4642b-140">전용</span><span class="sxs-lookup"><span data-stu-id="4642b-140">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="4642b-141">[Protected Friend](./protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="4642b-141">[Protected Friend](./protected-friend.md) </span></span>  
[<span data-ttu-id="4642b-142">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="4642b-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="4642b-143">절차</span><span class="sxs-lookup"><span data-stu-id="4642b-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="4642b-144">구조체</span><span class="sxs-lookup"><span data-stu-id="4642b-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="4642b-145">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="4642b-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
