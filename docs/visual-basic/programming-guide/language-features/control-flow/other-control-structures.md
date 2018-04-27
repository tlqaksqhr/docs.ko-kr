---
title: 기타 제어 구조(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e1ea44cf2f0405dc55f8df60fb842691e50a9a0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="other-control-structures-visual-basic"></a><span data-ttu-id="4ac30-102">기타 제어 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ac30-102">Other Control Structures (Visual Basic)</span></span>
<span data-ttu-id="4ac30-103">Visual Basic 리소스를 삭제 하거나 개체 참조를 반복 해야 할 횟수를 줄일 제어 구조 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac30-103">Visual Basic provides control structures that help you dispose of a resource or reduce the number of times you have to repeat an object reference.</span></span>  
  
## <a name="usingend-using-construction"></a><span data-ttu-id="4ac30-104">사용 하 여... 생성을 사용 하는 끝</span><span class="sxs-lookup"><span data-stu-id="4ac30-104">Using...End Using Construction</span></span>  
 <span data-ttu-id="4ac30-105">`Using...End Using` 구문은 문 블록을 확인 하는 SQL 연결 같은 리소스의 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac30-105">The `Using...End Using` construction establishes a statement block within which you make use of a resource such as a SQL connection.</span></span> <span data-ttu-id="4ac30-106">사용 하 여 리소스를 선택적으로 가져올 수는 `Using` 문.</span><span class="sxs-lookup"><span data-stu-id="4ac30-106">You can optionally acquire the resource with the `Using` statement.</span></span> <span data-ttu-id="4ac30-107">종료 하면는 `Using` 블록, Visual Basic는 리소스의 사용 하기 위해 다른 코드에 사용할 수 있도록 자동으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac30-107">When you exit the `Using` block, Visual Basic automatically disposes of the resource so that it is available for other code to use.</span></span> <span data-ttu-id="4ac30-108">리소스는 로컬 이며 삭제할 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac30-108">The resource must be local and disposable.</span></span> <span data-ttu-id="4ac30-109">자세한 내용은 [using 문](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ac30-109">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="withend-with-construction"></a><span data-ttu-id="4ac30-110">사용... 생성과 함께 종료</span><span class="sxs-lookup"><span data-stu-id="4ac30-110">With...End With Construction</span></span>  
 <span data-ttu-id="4ac30-111">`With...End With` 생성 한 개체 참조를 한 번만 지정할 수 있습니다 다음 일련의 해당 멤버에 액세스 하는 문 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac30-111">The `With...End With` construction lets you specify an object reference once and then run a series of statements that access its members.</span></span> <span data-ttu-id="4ac30-112">이 코드를 단순화 하 고 Visual Basic 멤버에 액세스 하는 각 문에 대 한 참조를 다시 설정할 필요가 없기 때문에 성능이 향상 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac30-112">This can simplify your code and improve performance because Visual Basic does not have to re-establish the reference for each statement that accesses it.</span></span> <span data-ttu-id="4ac30-113">자세한 내용은 참조 [와... 문을 사용 하 여 종료](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4ac30-113">For more information, see [With...End With Statement](../../../../visual-basic/language-reference/statements/with-end-with-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac30-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ac30-114">See Also</span></span>  
 [<span data-ttu-id="4ac30-115">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="4ac30-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="4ac30-116">판단 구조</span><span class="sxs-lookup"><span data-stu-id="4ac30-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="4ac30-117">루프 구조</span><span class="sxs-lookup"><span data-stu-id="4ac30-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="4ac30-118">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="4ac30-118">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="4ac30-119">Using 문</span><span class="sxs-lookup"><span data-stu-id="4ac30-119">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)  
 [<span data-ttu-id="4ac30-120">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="4ac30-120">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
