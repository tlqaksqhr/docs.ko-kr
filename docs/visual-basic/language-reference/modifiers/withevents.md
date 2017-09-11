---
title: "WithEvents (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b956f8f0d6f0a2fd9f41c5df6d6c82b43fa09018
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="withevents-visual-basic"></a><span data-ttu-id="9189e-102">WithEvents(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9189e-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="9189e-103">선언 된 멤버 변수를 하나 이상의 이벤트를 발생 시킬 수 있는 클래스의 인스턴스를 참조 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9189e-104">주의</span><span class="sxs-lookup"><span data-stu-id="9189e-104">Remarks</span></span>  
 <span data-ttu-id="9189e-105">변수를 사용 하 여 정의 되 면 `WithEvents`, 메서드를 사용 하 여 변수의 이벤트를 처리 하는 선언적으로 지정할 수는 `Handles` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="9189e-106">사용할 수 있습니다 `WithEvents` 클래스 또는 모듈 수준에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="9189e-107">즉, 선언 컨텍스트는 `WithEvents` 변수는 클래스 또는 모듈 이어야 하며 소스 파일, 네임 스페이스, 구조체 또는 프로시저 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="9189e-108">사용할 수 없습니다 `WithEvents` 구조체 멤버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="9189e-109">개별 변수만 선언할 수 있습니다-배열은 하지-와 `WithEvents`합니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="9189e-110">규칙</span><span class="sxs-lookup"><span data-stu-id="9189e-110">Rules</span></span>  
  
-   <span data-ttu-id="9189e-111">**요소 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="9189e-111">**Element Types.**</span></span> <span data-ttu-id="9189e-112">선언 해야 `WithEvents` 클래스 인스턴스 변수를 받아들일 수 있도록 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="9189e-113">그러나 매개 변수를 선언할 수 없습니다 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="9189e-114">이벤트를 발생 시킬 수 있는 특정 클래스로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9189e-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="9189e-115">`WithEvents` 한정자는이 컨텍스트에서 사용할 수 있습니다: [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="9189e-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9189e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9189e-116">See Also</span></span>  
 <span data-ttu-id="9189e-117">[핸들](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="9189e-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="9189e-118"> [키워드](../../../visual-basic/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9189e-118"> [Keywords](../../../visual-basic/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="9189e-119"> [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="9189e-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
