---
title: WithEvents(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 240058a534456ae20c9c129a068bae575ac45eda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596010"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="af232-102">WithEvents(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af232-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="af232-103">하나 이상의 선언 된 멤버 변수가 이벤트를 발생 시킬 수 있는 클래스의 인스턴스 참조 하는지 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af232-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af232-104">설명</span><span class="sxs-lookup"><span data-stu-id="af232-104">Remarks</span></span>  
 <span data-ttu-id="af232-105">변수를 사용 하 여 정의 되 면 `WithEvents`, 메서드를 사용 하 여 변수의 이벤트를 처리 하는 선언적으로 지정할 수 있습니다는 `Handles` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="af232-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="af232-106">사용할 수 있습니다 `WithEvents` 클래스 또는 모듈 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="af232-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="af232-107">즉, 선언 컨텍스트는 `WithEvents` 변수는 클래스 또는 모듈 이어야 하며 원본 파일, 네임 스페이스, 구조, 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af232-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="af232-108">사용할 수 없습니다 `WithEvents` 구조체 멤버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af232-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="af232-109">만 개별 변수를 선언할 수-하지 배열은-와 `WithEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="af232-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="af232-110">규칙</span><span class="sxs-lookup"><span data-stu-id="af232-110">Rules</span></span>  
  
-   <span data-ttu-id="af232-111">**요소 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="af232-111">**Element Types.**</span></span> <span data-ttu-id="af232-112">선언 해야 `WithEvents` 변수를 수락할 수 있도록 개체 변수 클래스 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="af232-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="af232-113">그러나로 선언할 수 없습니다 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="af232-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="af232-114">이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af232-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="af232-115">`WithEvents` 한정자는이 컨텍스트에서 사용할 수 있습니다: [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="af232-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af232-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af232-116">See Also</span></span>  
 [<span data-ttu-id="af232-117">Handles</span><span class="sxs-lookup"><span data-stu-id="af232-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="af232-118">키워드</span><span class="sxs-lookup"><span data-stu-id="af232-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="af232-119">이벤트</span><span class="sxs-lookup"><span data-stu-id="af232-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
