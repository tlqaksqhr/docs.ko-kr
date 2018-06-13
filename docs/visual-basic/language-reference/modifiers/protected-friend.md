---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306548"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="56d3a-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56d3a-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="56d3a-103">`Protected Friend` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="56d3a-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="56d3a-104">항목 둘 다 제공 [Friend](friend.md) 액세스 및 [Protected](protected.md) 자체 클래스에서 및 파생된 클래스에서 동일한 어셈블리의 모든 위치에서 액세스할 수 있도록 선언된 된 요소에 대 한 액세스.</span><span class="sxs-lookup"><span data-stu-id="56d3a-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="56d3a-105">지정할 수 있습니다 `Protected Friend` ; 클래스의 멤버에 대해서만 적용할 수 없습니다 `Protected Friend` 구조체의 멤버에 게 되므로 구조체를 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56d3a-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="56d3a-106">Visual Studio에서에 F1 도움말을 선택 하면 `protected friend` 중 하나에 대 한 도움말을 제공 [보호](protected.md) 또는 [friend](friend.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="56d3a-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="56d3a-107">IDE의 복합 단어 보다는 커서에서 단일 토큰을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="56d3a-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="56d3a-108">규칙</span><span class="sxs-lookup"><span data-stu-id="56d3a-108">Rules</span></span>

- <span data-ttu-id="56d3a-109">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="56d3a-109">**Declaration Context.**</span></span> <span data-ttu-id="56d3a-110">사용할 수 있습니다 `Protected Friend` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="56d3a-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="56d3a-111">즉, 선언 컨텍스트는 `Protected` 요소는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56d3a-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 


## <a name="see-also"></a><span data-ttu-id="56d3a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56d3a-112">See Also</span></span>

[<span data-ttu-id="56d3a-113">공용</span><span class="sxs-lookup"><span data-stu-id="56d3a-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="56d3a-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="56d3a-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="56d3a-115">[Friend](friend.md) </span><span class="sxs-lookup"><span data-stu-id="56d3a-115">[Friend](friend.md) </span></span>  
[<span data-ttu-id="56d3a-116">전용</span><span class="sxs-lookup"><span data-stu-id="56d3a-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="56d3a-117">[보호 된 개인](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="56d3a-117">[Private Protected](./private-protected.md) </span></span>  
[<span data-ttu-id="56d3a-118">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="56d3a-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="56d3a-119">절차</span><span class="sxs-lookup"><span data-stu-id="56d3a-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="56d3a-120">구조체</span><span class="sxs-lookup"><span data-stu-id="56d3a-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="56d3a-121">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="56d3a-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
